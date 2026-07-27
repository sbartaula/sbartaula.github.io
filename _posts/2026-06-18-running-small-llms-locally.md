---
layout: post
title: "Running Small LLMs Locally on Limited Hardware"
date: 2026-06-18
tags: [LLMs, Linux, Local AI, AI Engineering]
excerpt: "What local model experiments taught me about speed, memory, and practical constraints."
---

I run small LLMs locally because it exposes the engineering truth quickly: every performance claim is bounded by hardware.

On constrained Ubuntu machines, the objective is not to run the largest model possible. The objective is to identify practical operating zones for real workflows.

## Evaluation frame

I use the same dimensions in each run so results are comparable over time:

* inference throughput
* memory footprint (RAM/VRAM)
* response quality under constrained context windows
* system responsiveness while the model is active
* setup and operational complexity

## Benchmark matrix

| Dimension | Why it matters | Current public status |
|---|---|---|
| Tokens per second | Determines usability for interactive workflows | Measurement in progress |
| Peak memory usage | Hard cap for local hardware viability | Measurement in progress |
| Prompt/context sensitivity | Impacts output stability and quality | Evaluation in progress |
| Quantization tradeoff | Controls speed-quality-memory balance | Comparison in progress |
| Runtime overhead | Affects repeatable developer workflows | Evaluation in progress |

## Observed constraints that matter most

These constraints repeatedly dominate outcomes:

* **Memory headroom:** low spare memory collapses usability before model quality becomes relevant
* **Context inflation:** larger prompts can quietly degrade latency and user experience
* **Quantization choice:** speed gains may come with quality loss that is task-dependent
* **Driver/runtime setup:** small environment mismatches can invalidate otherwise good configs

## Failure modes

Common failure patterns during local runs:

* throughput looks acceptable in short tests but degrades in extended sessions
* response quality drops under longer context chains
* machine becomes operationally unpleasant even when inference technically succeeds

Mitigation direction:

* standardize run profiles by task class
* treat local workloads as budgeted systems (latency and memory budgets first)
* separate demo configs from sustained-workflow configs

## Practical takeaway

Local-first experimentation is valuable because it forces architecture discipline.
It becomes clear which model/runtime choices can survive repeated use, not just one successful notebook demo.

## Next milestone

The next update will include comparative benchmark snapshots across selected model sizes and quantization profiles, using one reproducible prompt and hardware baseline.
