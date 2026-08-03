---
layout: default
title: Work
permalink: /projects/
---

<section class="page-header" id="projects-top">
  <h1>Work</h1>
  <p>Selected applied AI, backend, and product-engineering work with implementation detail and decision context.</p>
</section>

<section class="panel writing-callout">
  <h2>How to read this work</h2>
  <p>
    Each project is structured around problem, role, architecture decisions, and outcome signal.
    The goal is to make engineering judgment and execution style easy to evaluate.
  </p>
</section>

<section class="panel">
  <h2>Jump to project</h2>
  <ul class="clean-list compact-list">
    <li><a href="#ai-agent-chat">AI Agent Chat - Slack-First Engineering Assistant</a></li>
    <li><a href="#flowtrack">Flowtrack - Local-First AI Productivity</a></li>
    <li><a href="#tenslam-gym">Tenslam Gym</a></li>
    <li><a href="#tenslam-vision-motion-engine">Tenslam Vision Motion Engine</a></li>
    <li><a href="#local-llm-learning-lab">Local LLM Learning Lab</a></li>
    <li><a href="#django-nextjs-product-systems">Django + Next.js Product Systems</a></li>
    <li><a href="#ai-research-platform-experiments">AI Research Platform Experiments</a></li>
  </ul>
</section>

<section class="project-grid">
  <article class="panel project-card" id="ai-agent-chat">
    <h2>AI Agent Chat - Slack-First Engineering Assistant</h2>
    <p class="meta">Status: Deployed in private production environment</p>
    <p>Designed and built a production-grade AI workflow assistant to streamline engineering operations inside Slack.</p>
    <h3>Role and ownership</h3>
    <p>Owned architecture and implementation end-to-end, from API design and workflow orchestration to deployment and security hardening.</p>
    <h3>Timeline</h3>
    <p>Built from scratch and promoted through staged execution modes from intake-only behavior to active workflow automation.</p>
    <h3>Problem</h3>
    <p>Engineering teams often split context across chat, pull requests, CI logs, and ad hoc notes, which slows execution and creates visibility gaps.</p>
    <h3>What I built</h3>
    <p>A Slack-first assistant that captures ideas and tasks, opens GitHub draft PRs from Slack messages, monitors CI status, gates merges behind passing checks, summarizes failed checks with AI, and supports freeform GPT-4o conversations.</p>
    <h3>Security design</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Verified all Slack and GitHub webhook endpoints with HMAC-SHA256 signatures</li>
      <li>Blocked replay attacks with a strict 5-minute timestamp validation window</li>
      <li>Disabled API documentation routes in production deployments</li>
      <li>Applied prompt-injection hardening so user input cannot override system instructions</li>
      <li>Enforced per-task LLM spend caps to prevent runaway cost events</li>
    </ul>
    <h3>Key engineering decisions</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Event deduplication cache prevents duplicate responses from Slack retry behavior</li>
      <li>Two-layer routing separates deterministic command workflows from freeform LLM chat</li>
      <li>Execution-worker budget guardrail halts runs before exceeding cost thresholds</li>
      <li>Execution modes (intake_only, simulate, apply) support safe progression from observer to active editor</li>
    </ul>
    <h3>What this shows</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Production-minded AI workflow engineering with strong operational controls</li>
      <li>Ability to integrate LLMs into deterministic software systems without losing reliability</li>
      <li>Applied security and cost governance in real deployment conditions</li>
    </ul>
    <h3>Tech stack</h3>
    <p>Python 3.12, FastAPI, SQLite, GitHub REST API, Slack Events API, Slack Slash Commands, Slack Interactions API, OpenRouter (GPT-4o), Render</p>
    <h3>Public evidence</h3>
    <p>Production deployment is private, but architecture and implementation write-up can be shared in interview or portfolio walkthrough format.</p>
    <p class="project-nav"><a href="#projects-top">Back to top</a></p>
  </article>

  <article class="panel project-card" id="flowtrack">
    <h2>Flowtrack - Local-First AI Productivity</h2>
    <p class="meta">Status: Active build</p>
    <p>Built a local-first productivity tracker that uses AI-assisted dashboard behavior without requiring cloud account dependency.</p>
    <h3>Role and ownership</h3>
    <p>Owned product and engineering delivery across backend logic, AI integration points, and user workflow design.</p>
    <h3>Problem</h3>
    <p>Most productivity tools depend on cloud-heavy workflows even when users only need fast local control and privacy-first behavior.</p>
    <h3>What I built</h3>
    <p>A local-first tracker with AI-assisted dashboard interactions designed for low-friction daily use.</p>
    <h3>What this shows</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Product engineering beyond a single AI niche</li>
      <li>Ability to design around privacy and practical user constraints</li>
      <li>Execution from idea to usable product workflow</li>
    </ul>
    <h3>Tech stack</h3>
    <p>Python, local storage patterns, AI integration workflows, product UI iteration</p>
    <p class="project-nav"><a href="#projects-top">Back to top</a></p>
  </article>

  <article class="panel project-card" id="tenslam-gym">
    <h2>Tenslam Gym</h2>
    <p class="meta">Status: Live / prototype / actively developed</p>
    <p>Real-time AI personal trainer Android app using pose estimation, posture correction, rep counting, Firebase, and computer vision.</p>
    <h3>Role and ownership</h3>
    <p>End-to-end ownership across CV logic, app behavior, and product loop.</p>
    <h3>Timeline</h3>
    <p>Active build phase, iterating through production-minded prototypes.</p>
    <h3>Problem</h3>
    <p>Most fitness apps record activity, but do not help users understand movement quality while they are training.</p>
    <h3>What I built</h3>
    <p>An Android prototype that detects pose in real time, tracks reps, and gives feedback on posture and movement execution.</p>
    <h3>Current evidence</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Latency envelope for on-device feedback loop</li>
      <li>Rep-count reliability on selected movement classes</li>
      <li>Failure conditions: occlusion, camera angle, and tempo changes</li>
    </ul>
    <h3>What this shows</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Applied computer vision in a user-facing product</li>
      <li>Real-time feedback loops under mobile constraints</li>
      <li>Bridging model output to useful product behavior</li>
    </ul>
    <h3>Tech stack</h3>
    <p>Android, Kotlin/Java, MediaPipe, Firebase, Computer Vision, Pose Estimation</p>
    <h3>Public evidence</h3>
    <p>Demo walkthrough and architecture brief available on request during private iteration.</p>
    <p class="project-nav"><a href="#projects-top">Back to top</a></p>
  </article>

  <article class="panel project-card" id="tenslam-vision-motion-engine">
    <h2>Tenslam Vision Motion Engine</h2>
    <p class="meta">Status: In development</p>
    <p>A video-to-skeleton motion intelligence system for fitness, sports, digital twins, and physical AI.</p>
    <h3>Role and ownership</h3>
    <p>Owned architecture and implementation across data representation and pipeline behavior.</p>
    <h3>Timeline</h3>
    <p>Core pipeline phase with ongoing representation and quality improvements.</p>
    <h3>Problem</h3>
    <p>Raw video is easy to store but hard to use in downstream systems that need structured motion data.</p>
    <h3>What I built</h3>
    <p>A pipeline that extracts human movement signals from video and turns them into structured motion features.</p>
    <h3>Current evidence</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Landmark stability under camera and lighting variation</li>
      <li>Feature extraction consistency across repeated clips</li>
      <li>Downstream usability for analytics and feedback products</li>
    </ul>
    <h3>What this shows</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Designing structure from noisy real-world video input</li>
      <li>Thinking beyond demos toward reusable motion infrastructure</li>
      <li>Connecting vision pipelines to downstream product use cases</li>
    </ul>
    <h3>Tech stack</h3>
    <p>Python, Computer Vision, Pose Estimation, OpenCV, AI, Digital Twins</p>
    <h3>Current signal</h3>
    <p>Pipeline and representation quality are under active validation for wider release.</p>
    <p class="project-nav"><a href="#projects-top">Back to top</a></p>
  </article>

  <article class="panel project-card" id="local-llm-learning-lab">
    <h2>Local LLM Learning Lab</h2>
    <p class="meta">Status: Learning / experiments</p>
    <p>Experiments running and fine-tuning small open-source language models locally on Ubuntu with limited hardware.</p>
    <h3>Role and ownership</h3>
    <p>Independently designed and executed local inference experiments under constrained hardware.</p>
    <h3>Timeline</h3>
    <p>Ongoing applied research cycle focused on practical deployment tradeoffs.</p>
    <h3>Problem</h3>
    <p>I wanted to understand the practical limits of local inference and how model size, quantization, and memory constraints affect real usage.</p>
    <h3>What I built</h3>
    <p>Small-scale local inference and fine-tuning experiments on consumer hardware.</p>
    <h3>Current evidence</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Tokens-per-second across selected model sizes and quantization levels</li>
      <li>Memory and VRAM usage by configuration</li>
      <li>Usability thresholds for local-first product workflows</li>
    </ul>
    <h3>What this shows</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Curiosity grounded in hardware and system constraints</li>
      <li>Hands-on understanding of quantization, memory, and inference tradeoffs</li>
      <li>Practical evaluation instead of abstract model hype</li>
    </ul>
    <h3>Tech stack</h3>
    <p>Python, PyTorch, Hugging Face Transformers, Linux, LoRA, Qwen</p>
    <h3>Current signal</h3>
    <p>Selected notes are published in Writing while benchmark summaries are still in progress.</p>
    <p class="project-nav"><a href="#projects-top">Back to top</a></p>
  </article>

  <article class="panel project-card" id="django-nextjs-product-systems">
    <h2>Django + Next.js Product Systems</h2>
    <p class="meta">Status: Multiple prototypes</p>
    <p>Full-stack product experiments with REST APIs, authentication, dashboards, wallets, and MVP deployment.</p>
    <h3>Role and ownership</h3>
    <p>Owned backend API design, frontend integration, deployment path, and delivery scope.</p>
    <h3>Timeline</h3>
    <p>Multiple build cycles across different product hypotheses.</p>
    <h3>Problem</h3>
    <p>Many ideas need a fast path from backend logic to a usable product surface.</p>
    <h3>What I built</h3>
    <p>Product prototypes that combine Django APIs with a modern frontend and deployable infrastructure.</p>
    <h3>Current evidence</h3>
    <ul class="clean-list compact-list signal-list">
      <li>MVP delivery time from idea to deployable build</li>
      <li>API surface and reliability checks used during iteration</li>
      <li>Feature-to-feedback loop speed in prototype cycles</li>
    </ul>
    <h3>What this shows</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Ability to move from backend logic to usable product surfaces</li>
      <li>End-to-end ownership across APIs, frontend, and deployment</li>
      <li>Bias toward shipping MVPs instead of isolated code exercises</li>
    </ul>
    <h3>Tech stack</h3>
    <p>Python, Django REST Framework, Next.js, React, PostgreSQL, Firebase, Koyeb, Vercel</p>
    <h3>Current signal</h3>
    <p>Selected implementation breakdowns are available and being consolidated into cleaner public case studies.</p>
    <p class="project-nav"><a href="#projects-top">Back to top</a></p>
  </article>

  <article class="panel project-card" id="ai-research-platform-experiments">
    <h2>AI Research Platform Experiments</h2>
    <p class="meta">Status: Research / product engineering experiments</p>
    <p>Experiments around AI agent workflows, observability, token control, structured logging, API governance, retries, and reliability.</p>
    <h3>Role and ownership</h3>
    <p>Designed and implemented workflow orchestration experiments with reliability as a first-class goal.</p>
    <h3>Timeline</h3>
    <p>Iterative platform experimentation aligned to practical AI product operations.</p>
    <h3>Problem</h3>
    <p>AI systems need more than prompts; they need predictable, observable, and debuggable orchestration.</p>
    <h3>What I built</h3>
    <p>Workflow experiments focused on failure handling, telemetry, and operational clarity.</p>
    <h3>Current evidence</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Failure-mode taxonomy and retry behavior under common error classes</li>
      <li>Tracing and logging coverage for debugging and incident review</li>
      <li>Token and cost control patterns for repeatable operations</li>
    </ul>
    <h3>What this shows</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Systems thinking around reliability, observability, and control</li>
      <li>Interest in the engineering layer around AI, not just model calls</li>
      <li>Comfort working on product-facing infrastructure problems</li>
    </ul>
    <h3>Tech stack</h3>
    <p>Python, FastAPI, LangGraph-style workflows, logging, APIs, dashboards</p>
    <h3>Current signal</h3>
    <p>Internal reliability notes and architecture patterns are being condensed for public release.</p>
    <p class="project-nav"><a href="#projects-top">Back to top</a></p>
  </article>
</section>
