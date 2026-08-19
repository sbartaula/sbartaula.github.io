---
layout: default
title: Work
permalink: /projects/
description: "Selected LLM, computer vision, backend, and product engineering work with direct links to public products and source code."
---

<section class="page-header" id="projects-top">
  <h1>Work</h1>
  <p>Selected applied AI and product-engineering work, led by projects that can be opened, tested, or inspected.</p>
</section>

<section class="panel work-intro">
  <p class="eyebrow">A note on evidence</p>
  <h2>Public work first. Private work labeled.</h2>
  <p>
    Live products and source code are linked directly. For private systems, I show the problem,
    implemented controls, and a sanitized architecture without presenting internal claims as independent proof.
  </p>
</section>

<nav class="panel project-index" aria-label="Jump to a project">
  <h2>Featured projects</h2>
  <ol>
    <li><a href="#personal-blog-ai-assistant">SaroAI — Site-Grounded Blog Assistant</a></li>
    <li><a href="#flowtrack">Flowtrack</a></li>
    <li><a href="#tenslam-gym">Tenslam Gym</a></li>
    <li><a href="#tenslam-vision-motion-engine">Tenslam Vision Motion Engine</a></li>
    <li><a href="#ai-agent-chat">AI Agent Chat</a></li>
  </ol>
  <a class="text-link" href="#engineering-explorations">Additional engineering explorations</a>
</nav>

<section class="project-grid" aria-label="Featured project case studies">
  <article class="panel project-card project-card-featured" id="personal-blog-ai-assistant">
    <div class="project-card-header">
      <div>
        <p class="meta">Featured personal project · Live</p>
        <h2>SaroAI — Site-Grounded Blog Assistant</h2>
      </div>
      <a class="button button-compact" href="{{ site.projects.blog_assistant }}">Try SaroAI</a>
    </div>
    <p class="project-lede">
      An LLM-powered Q&amp;A layer for my personal blog that lets visitors ask across published articles and receive concise, context-grounded answers.
    </p>

    <h3>Problem</h3>
    <p>A growing archive is difficult to explore one post at a time, especially when a visitor arrives with a specific question rather than a title or keyword.</p>

    <h3>What I built</h3>
    <p>
      I implemented a site-grounded AI chat experience on sarojbartaula.com that answers questions across my published archive and background.
      It turns a static reading experience into an interactive way to discover relevant ideas and source context.
    </p>

    <h3>Product decisions</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Grounded the experience in my public writing and background instead of presenting it as a general-purpose chatbot</li>
      <li>Used conversational questions to reduce the effort of searching across an archive</li>
      <li>Deployed the feature on the live personal site so reviewers can evaluate the product experience directly</li>
    </ul>

    <h3>What this shows</h3>
    <p>Hands-on LLM product integration, conversational interface design, and the ability to add a useful AI layer to an existing web product.</p>

    <h3>Technical scope</h3>
    <p>RAG, LLM integration, content retrieval and grounding, conversational UI, web product engineering</p>

    <div class="project-proof">
      <span>Public artifact</span>
      <a href="{{ site.projects.blog_assistant }}">sarojbartaula.com</a>
    </div>
    <p class="project-nav"><a href="#projects-top">Back to top</a></p>
  </article>

  <article class="panel project-card" id="flowtrack">
    <div class="project-card-header">
      <div>
        <p class="meta">Open source · Active build</p>
        <h2>Flowtrack</h2>
      </div>
      <a class="button button-compact" href="{{ site.projects.flowtrack }}">View source on GitHub</a>
    </div>
    <p class="project-lede">A local-first activity tracker with a browser dashboard and AI-assisted analysis, designed around user control rather than mandatory cloud accounts.</p>

    <h3>Problem</h3>
    <p>Many productivity tools require users to send detailed activity data to a hosted service, even when a local workflow would be faster and more private.</p>

    <h3>What I built</h3>
    <ul class="clean-list compact-list signal-list">
      <li>A background tracker for active windows, timestamps, context switches, and optional screenshots</li>
      <li>A localhost browser dashboard for live logs, screenshot review, storage controls, AI analysis, and chat</li>
      <li>Support for local Ollama models plus opt-in hosted providers and explicit backup workflows</li>
    </ul>

    <h3>Key engineering decisions</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Binds the dashboard to <code>127.0.0.1</code> so it is not exposed to the network by default</li>
      <li>Keeps activity data on the user's machine unless the user explicitly invokes an external provider or backup</li>
      <li>Applies screenshot retention and storage limits so passive capture does not grow without control</li>
    </ul>

    <h3>What this shows</h3>
    <p>End-to-end product delivery across background services, local data handling, AI integrations, and a usable browser interface.</p>

    <h3>Tech stack</h3>
    <p>Python, browser dashboard, JSONL, systemd, local and hosted LLM integrations</p>

    <div class="project-proof">
      <span>Source code</span>
      <a href="{{ site.projects.flowtrack }}">github.com/sbartaula/Flowtrack</a>
    </div>
    <p class="project-nav"><a href="#projects-top">Back to top</a></p>
  </article>

  <article class="panel project-card" id="tenslam-gym">
    <div class="project-card-header">
      <div>
        <p class="meta">Live on Android · Actively developed</p>
        <h2>Tenslam Gym</h2>
      </div>
      <a class="button button-compact" href="{{ site.projects.tenslam_gym }}">Visit live product</a>
    </div>
    <p class="project-lede">An Android AI trainer that uses real-time pose analysis for rep tracking and movement feedback during gym and home workouts.</p>

    <h3>Role and ownership</h3>
    <p>I own the computer-vision logic, app behavior, product loop, and ongoing technical iteration.</p>

    <h3>Problem</h3>
    <p>Most fitness apps record what a user did after a session but cannot respond to movement quality while the user is training.</p>

    <h3>What I built</h3>
    <p>An Android product that detects body pose in real time, follows exercise state, counts repetitions, and delivers feedback within the workout flow.</p>

    <h3>Engineering constraints</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Maintaining stable feedback when joints are occluded or the camera angle changes</li>
      <li>Separating valid repetitions from noisy or incomplete pose transitions</li>
      <li>Keeping the camera-to-feedback loop useful under mobile-device constraints</li>
    </ul>

    <h3>Tech stack</h3>
    <p>Android, Kotlin/Java, MediaPipe, Firebase, computer vision, pose estimation</p>

    <p><strong>Current product signal:</strong> 20+ users and 5,000+ exercise reps processed (internal product telemetry).</p>

    <div class="project-proof">
      <span>Public product</span>
      <a href="{{ site.projects.tenslam_gym }}">tenslam.com</a>
    </div>
    <p class="project-nav"><a href="#projects-top">Back to top</a></p>
  </article>

  <article class="panel project-card" id="tenslam-vision-motion-engine">
    <div class="project-card-header">
      <div>
        <p class="meta">Public product site · Engine in active development</p>
        <h2>Tenslam Vision Motion Engine</h2>
      </div>
      <a class="button button-compact" href="{{ site.projects.tenslam_vision }}">Visit Tenslam Vision</a>
    </div>
    <p class="project-lede">A video-to-skeleton motion-intelligence pipeline for turning human movement into structured information for sports, fitness, and physical-AI workflows.</p>

    <h3>Problem</h3>
    <p>Raw video is rich in visual information but difficult for downstream products to query, compare, and use as structured motion data.</p>

    <h3>What I built</h3>
    <p>A pipeline that extracts human movement signals from video and transforms them into structured skeletal and motion features.</p>

    <h3>Engineering focus</h3>
    <ul class="clean-list compact-list signal-list">
      <li>Improving landmark stability under camera, lighting, and movement variation</li>
      <li>Normalizing motion representations so repeated clips can be compared consistently</li>
      <li>Designing outputs that can support analytics, feedback products, and later physical-AI use cases</li>
    </ul>

    <h3>Tech stack</h3>
    <p>Python, OpenCV, pose estimation, skeletal representations, motion analysis</p>

    <div class="project-proof">
      <span>Public product site</span>
      <a href="{{ site.projects.tenslam_vision }}">tenslamvision.com</a>
    </div>
    <p class="project-nav"><a href="#projects-top">Back to top</a></p>
  </article>

  <article class="panel project-card" id="ai-agent-chat">
    <div class="project-card-header">
      <div>
        <p class="meta">Private deployment · Sanitized architecture available</p>
        <h2>AI Agent Chat</h2>
      </div>
      <a class="button button-secondary button-compact" href="{{ '/assets/img/ai-agent-workflow.svg' | relative_url }}">Open architecture</a>
    </div>
    <p class="project-lede">A Slack-first engineering assistant for task intake, GitHub pull-request workflows, CI monitoring, failure summaries, and guarded automation.</p>

    <h3>Role and ownership</h3>
    <p>I owned the architecture and implementation end to end, from API design and workflow orchestration to deployment and security hardening.</p>

    <h3>What I built</h3>
    <p>A Slack assistant that captures ideas and tasks, opens GitHub draft pull requests, monitors CI, gates merges behind passing checks, summarizes failures with an LLM, and supports freeform conversations.</p>

    <figure class="project-figure" id="ai-agent-architecture">
      <a class="project-diagram-link" href="{{ '/assets/img/ai-agent-workflow.svg' | relative_url }}" aria-label="Open the AI Agent Chat architecture diagram at full size">
        <picture>
          <source media="(max-width: 720px)" srcset="{{ '/assets/img/ai-agent-workflow-mobile.svg' | relative_url }}" width="720" height="1120">
          <img src="{{ '/assets/img/ai-agent-workflow.svg' | relative_url }}" width="1200" height="720" loading="lazy" decoding="async" alt="Architecture flow from Slack through webhook verification, deduplication, routing, guarded execution, GitHub, and LLM summaries">
        </picture>
      </a>
      <figcaption>Sanitized system architecture. Deterministic controls surround the model call; private deployment details are omitted.</figcaption>
    </figure>

    <h3>Security and reliability controls</h3>
    <ul class="clean-list compact-list signal-list">
      <li>HMAC-SHA256 verification on Slack and GitHub webhook endpoints</li>
      <li>Timestamp validation and event deduplication to limit replay and retry behavior</li>
      <li>Separate deterministic command routing from freeform LLM conversations</li>
      <li>Staged execution modes and per-task spend limits for controlled automation</li>
    </ul>

    <h3>Tech stack</h3>
    <p>Python 3.12, FastAPI, SQLite, GitHub REST API, Slack APIs, OpenRouter, GPT-4o, Render</p>

    <div class="project-proof project-proof-private">
      <span>Evidence boundary</span>
      <p>The deployment is private. The sanitized architecture is the public artifact; a deeper implementation walkthrough is available during an interview.</p>
    </div>
    <p class="project-nav"><a href="#projects-top">Back to top</a></p>
  </article>
</section>

<section class="panel explorations" id="engineering-explorations" aria-labelledby="explorations-title">
  <div class="section-heading">
    <p class="eyebrow">Additional work</p>
    <h2 id="explorations-title">Engineering explorations</h2>
    <p>Smaller experiments that show technical range without presenting them as finished public products.</p>
  </div>

  <div class="exploration-grid">
    <article id="model-training-and-adaptation">
      <h3>Model Training &amp; Adaptation</h3>
      <p>Built and trained a 423K-parameter TinyGPT from scratch on custom text for 3,000 CPU steps, covering tokenization, context windows, Transformer blocks, training, evaluation, and generation. Also tested Hugging Face Qwen and PEFT/LoRA adaptation workflows.</p>
      <p class="meta">Python · PyTorch · Hugging Face · PEFT/LoRA · Qwen · Linux</p>
      <a class="text-link" href="{{ '/writing/running-small-llms-locally/' | relative_url }}">Read the field notes</a>
    </article>

    <article id="django-nextjs-product-systems">
      <h3>Django + Next.js Product Systems</h3>
      <p>Full-stack prototypes spanning REST APIs, authentication, dashboards, frontend integration, and MVP deployment.</p>
      <p class="meta">Python · Django REST Framework · Next.js · React · PostgreSQL</p>
    </article>

    <article id="ai-research-platform-experiments">
      <h3>AI Research Platform Experiments</h3>
      <p>Workflow-orchestration experiments centered on retries, structured logging, observability, token control, and predictable failure handling.</p>
      <p class="meta">Python · FastAPI · workflow graphs · logging · APIs</p>
    </article>
  </div>

  <p class="project-nav"><a href="#projects-top">Back to top</a></p>
</section>
