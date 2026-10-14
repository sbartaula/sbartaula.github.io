---
layout: post
title: "Building Tenslam MiniLM: 29.9M to 60.1M Parameters, 791M Tokens, and an Evaluation Bug"
date: 2026-10-14
tags: [LLMs, PyTorch, Model Training, AI Engineering]
excerpt: "An engineering write-up on training two decoder-only Transformers, recovering an inference export, and fixing misleading validation."
hero_image: /assets/img/late-night-language-model-lab.png
hero_image_alt: "A laptop showing language-model training charts in a late-night development workspace"
og_image: /assets/img/late-night-language-model-lab.png
og_image_alt: "A laptop showing language-model training charts in a late-night development workspace"
og_image_type: image/png
og_image_width: 1672
og_image_height: 941
---

I wanted a language-model project small enough that I could understand the entire path from raw text to generated tokens, but serious enough to encounter the problems that show up in real training systems.

That became Tenslam MiniLM: a custom PyTorch decoder-only Transformer implementation with byte-level BPE tokenization, data preparation, training, checkpointing, evaluation, and CPU inference.

I trained two models, both from randomly initialized weights. The first used TinyStories as a constrained learning problem. The second used a broader six-source corpus. Neither is an instruction-tuned chatbot, and I don't present either as a competitive general-purpose model.

The implementation is available at [github.com/sbartaula/Minillm-pretrain](https://github.com/sbartaula/Minillm-pretrain). The source code is MIT-licensed; the Stage 2 weights are not publicly distributed while the mixed-data redistribution terms are being reviewed.

## The runs at a glance

| | Stage 1 | Stage 2 |
|---|---:|---:|
| Parameters | 29,893,120 | 60,060,800 |
| Transformer blocks | 8 | 10 |
| Model width | 512 | 640 |
| Attention heads | 8 | 10 |
| Feed-forward width | 1,408 | 1,728 |
| Vocabulary | 8,192 | 16,384 |
| Context length | 512 tokens | 512 tokens |
| Training tokens processed | 100,007,936 | 791,412,736 |
| GPU for the actual run | RTX PRO 6000 Blackwell MIG 1g.24gb | NVIDIA L4 |
| Training duration | 1,004 seconds | 19,801 seconds |
| End condition | Completed configured steps | Reached 5.5-hour cap |

Stage 1 produced readable, simple story completions. Stage 2 learned broader text patterns but still had repetition and factual errors. The second run's export was recovered and successfully used for CPU generation.

## 1. Model architecture: modern components, intentionally small

Both versions are pre-norm, decoder-only Transformers with causal self-attention, RMSNorm, RoPE, SwiGLU, and tied input/output embeddings. These are established architectural components, not new inventions in this project.

I chose them partly because I wanted to understand the implementation instead of treating the model as an opaque library call. The network runs inside a conventional next-token prediction loop:

```text
text
  → byte-level BPE IDs
  → token embeddings
  → repeated [RMSNorm → causal attention → residual;
              RMSNorm → SwiGLU MLP → residual]
  → final normalization
  → vocabulary logits
  → cross-entropy / next-token sampling
```

The input and output embeddings share a weight matrix. That matters at this scale: an 8,192-token vocabulary at width 512 already uses about 4.19 million embedding parameters. A 50,000-token vocabulary would take roughly 25.6 million entries in the same matrix, leaving little capacity in a 30M-parameter budget for the rest of the network. Stage 2 doubled the vocabulary to handle a more varied corpus, with the corresponding embedding cost.

Both models use a 512-token context. It was a deliberate compute constraint, not an attempt to build a long-context model.

## 2. The data pipeline was a larger project than I expected

Stage 1 used TinyStories. Stage 2 mixed educational web text, encyclopedia text, literature, synthetic educational material, and simple stories.

The Stage 2 preparation produced:

| Source | Prepared training tokens | Share |
|---|---:|---:|
| TinyStories | 121,332,737 | 12.8% |
| FineWeb-Edu | 378,572,806 | 40.0% |
| Wikipedia | 159,699,679 | 16.9% |
| Gutenberg | 170,840,785 | 18.1% |
| Cosmopedia Stanford | 81,039,477 | 8.6% |
| Cosmopedia OpenStax | 34,601,828 | 3.7% |
| Total | 946,087,312 | 100% |

The prepared validation stream contained an additional 5,747,658 tokens across the six sources.

The actual pipeline did more than concatenate downloaded text. It pinned dataset revisions; separated training and validation at the parent-document level; filtered invalid content; performed exact and near-deduplication; removed train/validation overlaps; and trained the tokenizer only from training text. The preparation manifest records counts, revisions and hashes so the input can be audited.

The tokenized documents were separated by EOS tokens and written as a flat `uint16` token stream. Training uses memory-mapped arrays and sampled windows of 513 IDs: 512 inputs and their next-token targets. Attention isn't masked across document boundaries in this packed-stream design, which is a simplification worth documenting.

One subtlety: windows are sampled with replacement. 791M tokens processed is not proof that 791M distinct corpus tokens were seen. It is a count of training targets processed.

Data preparation itself took about 57 minutes on the production RunPod machine. Earlier attempts had run into slow laptop streaming, incomplete browser uploads, and overlapping jobs after repeated command submissions. The final workflow used a locked driver script with resume behavior and packaged artifacts with checksums.

The boring parts were not actually boring. They determined whether the training run was repeatable.

## 3. Training setup and what the hardware actually delivered

The effective batch size in both stages was:

```text
micro-batch 32 × gradient accumulation 4 × sequence 512
= 65,536 training tokens per optimizer step
```

The trainer uses AdamW, weight decay, warmup followed by cosine learning-rate decay, gradient clipping, BF16 autocast on supported hardware, NaN/Inf guards, metrics logging, and atomic checkpoints. Stage 2 used a peak learning rate of `6e-4`, a minimum of `6e-5`, and 500 warmup steps.

Stage 1 completed 1,526 optimizer steps on a Blackwell MIG slice, processing 100,007,936 tokens in about 16.7 minutes of training. Its typical reported throughput was around 102k tokens/s.

The larger production run used an NVIDIA L4. It processed 12,076 steps, or 791,412,736 tokens, in approximately 5.5 hours, typically around 40.7k tokens/s. The logged peak CUDA allocation was about 10.27 GiB.

Before that run, I had benchmarked a different GPU, the Blackwell MIG slice, at several micro-batch sizes. Those numbers did not predict the L4's actual throughput. That is an important operational lesson: a benchmark is tied to hardware, batch shape, precision, and the surrounding execution path.

The Stage 2 target was about 1B processed tokens, which translated to 15,259 planned steps. The run also had a 5.5-hour safety cap. The cap won: training ended cleanly at 12,076 / 15,259 steps, then exported and packaged the model. It did not crash, and it did not finish the full token target.

## 4. Evaluation: a plausible metric that measured the wrong slice

Stage 1's TinyStories evaluation was straightforward. Over the selected validation subset, loss fell from approximately 9.08 at initialization to 1.6312 after 1,526 steps, with reported perplexity 5.11. Generated examples became short, readable stories. That supports the narrow claim that the model learned the TinyStories distribution.

Stage 2 exposed a much more interesting mistake.

The training log contained an attractive aggregate validation value around 1.567 loss / 4.79 perplexity. But the source-specific snapshots near step 12,000 looked like this:

| Validation source | Partial loss |
|---|---:|
| TinyStories | 1.6000 |
| FineWeb-Edu | 3.3959 |
| Wikipedia | 3.1045 |
| Gutenberg | 3.3116 |
| Cosmopedia Stanford | 2.5654 |
| Cosmopedia OpenStax | 2.6276 |

Why was the aggregate number so much lower than most of the sources?

The original evaluator consumed the first 50 batches of a concatenated validation stream:

```text
50 × 32 × 512 = 819,200 validation targets
```

TinyStories happened to be first and contained 1,009,411 prepared validation tokens. So the entire aggregate evaluation window was drawn from TinyStories. The number was valid for that partial slice, but not for the full six-source mixture.

This is exactly the kind of bug that survives if you only look for decreasing loss. The model trains, the evaluator returns finite numbers, and the dashboard looks good. Nothing crashes. The label is simply misleading.

I corrected the evaluator for future runs: evaluate each source separately and compute a combined value weighted by the validation-token counts. A regression test now checks the aggregation. The historical archive was not rewritten.

I also cannot retroactively claim a full-mix score for that run. The original validation token bins were not included in the recovered archive. A weighted calculation from the partial per-source samples gives an estimate of roughly 2.92 loss (perplexity ~18.5), but that is not a measured full-validation result and shouldn't be reported as one.

The last scheduled validation was at step 12,000. The exported weights were from step 12,076, so even the partial metric isn't an exact evaluation of the final export.

The lesson here is not “always trust lower perplexity.” It is first verify what your evaluation is sampling.

## 5. Testing the exported model on CPU

I recovered the Stage 2 inference bundle and ran a small fixed set of greedy and sampled prompts locally. The base model can produce locally coherent story prose. With a prompt about a girl finding a map, its greedy continuation produced a recognizable short narrative.

On factual prompts, it was far less reliable. A continuation about Einstein invented a publication detail; other examples repeated phrases or wandered off topic. Those are important observations, not outputs to hide.

This is a base autoregressive model. It was trained for next-token prediction, without supervised instruction tuning, preference optimization, or a chat template. Testing it as if it were ChatGPT would conflate different capabilities.

I keep the repeatable local evaluation outputs separate from the public repository. The repository includes the evaluation script, not a curated set of cherry-picked model responses.

## 6. Artifact recovery: inference export vs. training checkpoint

The pipeline produced a compressed results archive of 223,452,784 bytes (~223.45 MB decimal or ~213.10 MiB binary). I downloaded it and its SHA-256 checksum file, verified integrity, and extracted the export:

```text
export/
├── model.safetensors
├── config.json
├── tokenizer.json
└── export_info.json
```

The export loads with Tenslam's custom PyTorch model implementation. It is not a standard Hugging Face `AutoModelForCausalLM` layout.

There was also a roughly 703 MB `last.pt` on the pod, containing the richer training state: model, optimizer, schedule and RNG data needed for exact continuation. I failed to download that checkpoint before terminating RunPod. The exported weights survived, but an exact resume from step 12,076 is no longer available from the local artifacts.

It is technically possible to initialize a fresh optimizer from inference weights and continue training, but that would not reproduce the original optimizer trajectory. I decided not to spend more GPU time simply to chase the nominal step count before evaluating the model I already had.

The current model weights are private. The public GitHub code is MIT-licensed, but the training corpus has several different provenance and redistribution considerations; a public model-weight license needs separate review.

## 7. What I would change on the next run

A few changes are clear from this experiment:

1. Benchmark on the production GPU. A good tokens/s estimate from another card is not a budget.
2. Make validation source-aware from day one. Test the evaluation sampling logic with deliberately uneven source sizes.
3. Back up the resumable checkpoint before termination. An inference export solves a different problem.
4. Treat preprocessing as first-class engineering. Record data hashes, revisions, sample counts and overlap checks.
5. Budget for the whole lifecycle. Data preparation, training, evaluation, upload/download and recovery all take time.
6. Evaluate with text, not just metrics. A finite loss is necessary, but generation exposes repetition and factual mistakes immediately.

The source repository's latest local full test run reported 92 passed, 1 skipped after the evaluation changes.

## What this project demonstrates and what it doesn't

It demonstrates an end-to-end small-model training system: architecture implementation, byte-level BPE, reproducible data preparation, GPU training, checkpoints, local export and inference, and post-run failure analysis.

It does not demonstrate a generally capable chatbot, a completed one-billion-token run, state-of-the-art language-model quality, or a validated six-source perplexity of 4.79.

For me, the best result is that the entire system is now concrete. I can inspect the model code, point to every part of the training loop, identify why an evaluation number was wrong, and distinguish a usable model export from a resumable checkpoint.

The next useful step is to explore post-training on a separately licensed, already pretrained base model, with a clear baseline and held-out evaluation. For this project, making the machinery understandable was the goal.

Code and documentation: [Tenslam MiniLM on GitHub](https://github.com/sbartaula/Minillm-pretrain) · [Hugging Face project card (documentation only; no weights)](https://huggingface.co/saroj479/tenslam-minilm-60m)
