---
layout: post
title: "Running Small LLMs Locally on Limited Hardware"
date: 2026-06-18
tags: [LLMs, Linux, Local AI, AI Engineering]
excerpt: "What local model experiments taught me about speed, memory, and practical constraints."
---

I like running small language models locally because it forces you to confront the real engineering constraints.

When a model runs on your own machine, every choice becomes visible. RAM matters. GPU memory matters. Quantization matters. Prompt length matters. Even the operating system and driver setup can change whether the experiment feels smooth or frustrating.

On Ubuntu with limited hardware, the goal was not to chase the biggest model. The goal was to understand what is practical. I wanted to learn how inference behaves, how much memory different setups consume, and how far I could push local execution before the machine stopped being pleasant to use.

I found that small open-source models are useful for learning because they make the tradeoffs obvious. You can compare latency, context size, quality, and resource use without losing sight of the fact that the machine is finite. That kind of constraint is healthy for engineering.

The experiments also helped me understand the difference between demo-friendly AI and deployable AI. A model that looks impressive in a notebook may be awkward in a real workflow if it is too slow, too large, or too expensive to run repeatedly.

This is one reason I keep building local-first prototypes. They teach me how models behave in the real world, and they sharpen my intuition for what should be optimized in production.
