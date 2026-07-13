---
layout: default
title: Projects
permalink: /projects/
---

<section class="page-header">
  <h1>Projects</h1>
  <p>A selection of systems, prototypes, and experiments across AI, computer vision, and product engineering.</p>
</section>

<section class="panel writing-callout">
  <h2>How to read this page</h2>
  <p>
    I prefer projects that sit between research and product: technically serious enough to be interesting,
    but concrete enough to be useful. The most important thing here is not the polish level of each prototype;
    it is the pattern of what I choose to build and how I turn ideas into working systems.
  </p>
  <p>
    If you are hiring, look for three things here: whether I can turn ambiguous ideas into systems,
    whether I can work across the stack when needed, and whether I choose technical problems that matter.
  </p>
</section>

<section class="project-grid">
  <article class="panel project-card">
    <h2>Tenslam Gym</h2>
    <p class="meta">Status: Live / prototype / actively developed</p>
    <p>Real-time AI personal trainer Android app using pose estimation, posture correction, rep counting, Firebase, and computer vision.</p>
    <h3>Problem</h3>
    <p>Most fitness apps record activity, but do not help users understand movement quality while they are training.</p>
    <h3>What I built</h3>
    <p>An Android prototype that detects pose in real time, tracks reps, and gives feedback on posture and movement execution.</p>
    <h3>What this shows</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Applied computer vision in a user-facing product</li>
      <li>Real-time feedback loops under mobile constraints</li>
      <li>Bridging model output to useful product behavior</li>
    </ul>
    <h3>Tech stack</h3>
    <p>Android, Kotlin/Java, MediaPipe, Firebase, Computer Vision, Pose Estimation</p>
    <h3>Links</h3>
    <p>Demo, source, and case study links can live here as they are finalized.</p>
  </article>

  <article class="panel project-card">
    <h2>Tenslam Vision Motion Engine</h2>
    <p class="meta">Status: In development</p>
    <p>A video-to-skeleton motion intelligence system for fitness, sports, digital twins, and physical AI.</p>
    <h3>Problem</h3>
    <p>Raw video is easy to store but hard to use in downstream systems that need structured motion data.</p>
    <h3>What I built</h3>
    <p>A pipeline that extracts human movement signals from video and turns them into structured motion features.</p>
    <h3>What this shows</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Designing structure from noisy real-world video input</li>
      <li>Thinking beyond demos toward reusable motion infrastructure</li>
      <li>Connecting vision pipelines to downstream product use cases</li>
    </ul>
    <h3>Tech stack</h3>
    <p>Python, Computer Vision, Pose Estimation, OpenCV, AI, Digital Twins</p>
    <h3>Links</h3>
    <p>Architecture notes, demos, and implementation breakdowns can live here.</p>
  </article>

  <article class="panel project-card">
    <h2>Local LLM Learning Lab</h2>
    <p class="meta">Status: Learning / experiments</p>
    <p>Experiments running and fine-tuning small open-source language models locally on Ubuntu with limited hardware.</p>
    <h3>Problem</h3>
    <p>I wanted to understand the practical limits of local inference and how model size, quantization, and memory constraints affect real usage.</p>
    <h3>What I built</h3>
    <p>Small-scale local inference and fine-tuning experiments on consumer hardware.</p>
    <h3>What this shows</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Curiosity grounded in hardware and system constraints</li>
      <li>Hands-on understanding of quantization, memory, and inference tradeoffs</li>
      <li>Practical evaluation instead of abstract model hype</li>
    </ul>
    <h3>Tech stack</h3>
    <p>Python, PyTorch, Hugging Face Transformers, Linux, LoRA, Qwen</p>
    <h3>Links</h3>
    <p>Experiment notes, notebooks, and learnings can live here.</p>
  </article>

  <article class="panel project-card">
    <h2>Django + Next.js Product Systems</h2>
    <p class="meta">Status: Multiple prototypes</p>
    <p>Full-stack product experiments with REST APIs, authentication, dashboards, wallets, and MVP deployment.</p>
    <h3>Problem</h3>
    <p>Many ideas need a fast path from backend logic to a usable product surface.</p>
    <h3>What I built</h3>
    <p>Product prototypes that combine Django APIs with a modern frontend and deployable infrastructure.</p>
    <h3>What this shows</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Ability to move from backend logic to usable product surfaces</li>
      <li>End-to-end ownership across APIs, frontend, and deployment</li>
      <li>Bias toward shipping MVPs instead of isolated code exercises</li>
    </ul>
    <h3>Tech stack</h3>
    <p>Python, Django REST Framework, Next.js, React, PostgreSQL, Firebase, Koyeb, Vercel</p>
    <h3>Links</h3>
    <p>Prototype notes and selected demos can live here.</p>
  </article>

  <article class="panel project-card">
    <h2>AI Research Platform Experiments</h2>
    <p class="meta">Status: Research / product engineering experiments</p>
    <p>Experiments around AI agent workflows, observability, token control, structured logging, API governance, retries, and reliability.</p>
    <h3>Problem</h3>
    <p>AI systems need more than prompts; they need predictable, observable, and debuggable orchestration.</p>
    <h3>What I built</h3>
    <p>Workflow experiments focused on failure handling, telemetry, and operational clarity.</p>
    <h3>What this shows</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Systems thinking around reliability, observability, and control</li>
      <li>Interest in the engineering layer around AI, not just model calls</li>
      <li>Comfort working on product-facing infrastructure problems</li>
    </ul>
    <h3>Tech stack</h3>
    <p>Python, FastAPI, LangGraph-style workflows, logging, APIs, dashboards</p>
    <h3>Links</h3>
    <p>Architecture, observability, and workflow notes can live here.</p>
  </article>
</section>
