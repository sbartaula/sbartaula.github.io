---
layout: default
title: Resume
permalink: /resume/
description: "Saroj Bartaula's resume: applied AI, Python backend systems, LLM and agent applications, model training, and computer vision."
body_class: resume-page
---

<section class="page-header">
  <h1>Resume</h1>
  <p>A concise, application-ready record of my experience, skills, and selected work.</p>
</section>

<article class="panel resume-document" aria-labelledby="resume-name">
  <header class="resume-header">
    <p class="eyebrow resume-kicker">Applied AI · Backend Systems · Product Engineering</p>
    <h2 id="resume-name">Saroj Bartaula</h2>
    <p class="resume-title">Applied AI and Product Engineer</p>

    <address class="resume-contact" aria-label="Contact details">
      <span>Spain</span>
      <a href="{{ site.social.email }}">sarojbartaula152@gmail.com</a>
      <a href="{{ site.social.website }}">sarojbartaula.com</a>
      <a href="{{ site.social.github }}">github.com/sbartaula</a>
      <a href="{{ site.social.linkedin }}">linkedin.com/in/man-on-mission</a>
    </address>

    <p class="resume-summary">
      Applied AI and product engineer who turns ambiguous requirements into working software. Strong in Python backend
      systems, LLM and agent applications, model training and adaptation, API integrations, and applied computer vision—from
      architecture and experimentation through deployment, reliability, and iteration.
    </p>

    <div class="resume-actions">
      <a class="button" href="{{ '/assets/Saroj-Bartaula-Resume.pdf' | relative_url }}" download>Download PDF</a>
      <button class="button button-secondary print-button" type="button" onclick="window.print()">Print a fresh copy</button>
      <span class="meta">One-page A4 · formatted for recruiter review and ATS parsing.</span>
    </div>
  </header>

  <section class="resume-section" aria-labelledby="skills-heading">
    <h3 id="skills-heading">Technical Skills</h3>
    <div class="resume-skill-grid">
      <p><strong>AI and models:</strong> LLM applications, agents, RAG, tool calling, model training, dataset preparation, tokenization, Hugging Face, PEFT/LoRA, evaluation, guardrails</p>
      <p><strong>Backend:</strong> Python, FastAPI, Django/DRF, REST APIs, Pydantic, PostgreSQL, webhooks, authentication, third-party integrations</p>
      <p><strong>ML and delivery:</strong> PyTorch, TensorFlow, OpenCV, MediaPipe, pose estimation, Docker, Linux, GitHub Actions, CI/CD, Firebase, React/Next.js, Android</p>
    </div>
  </section>

  <section class="resume-section" aria-labelledby="experience-heading">
    <h3 id="experience-heading">Professional Experience</h3>

    <article class="resume-entry">
      <header class="resume-entry-heading">
        <div>
          <h4>Founder & Applied AI / Product Engineer</h4>
          <p class="resume-organization"><a href="{{ site.projects.tenslam_vision }}">Tenslam Vision</a></p>
        </div>
        <p class="resume-period">Sep 2025–Present · Spain</p>
      </header>
      <ul class="clean-list">
        <li>Shipped <a href="{{ site.projects.tenslam_gym }}">Tenslam Gym</a> for Android, combining real-time pose estimation, movement logic, and user-facing feedback; used by 20+ users with 5,000+ exercise reps processed.</li>
        <li>Build and test motion-intelligence workflows, AI/backend infrastructure, and product experiments, owning architecture, deployment, and iteration under latency, privacy, and reliability constraints.</li>
      </ul>
    </article>

    <article class="resume-entry">
      <header class="resume-entry-heading">
        <div>
          <h4>Co-Founder & ML / Product Developer</h4>
          <p class="resume-organization">TenSlam</p>
        </div>
        <p class="resume-period">Jun 2023–Mar 2025 · Spain</p>
      </header>
      <ul class="clean-list">
        <li>Built tennis-focused video-analysis prototypes with Python, OpenCV, object-detection tools, and Django REST APIs for movement tracking and technical feedback.</li>
        <li>Ran product experiments and customer discovery around making video analysis useful to players and coaches without specialist hardware.</li>
      </ul>
    </article>

    <p class="resume-earlier"><strong>Earlier experience:</strong> AI / Product—Box99 / TheHeCapp (2022–2023); Entrepreneur in Residence—Demium (2022); independent web/data work (2020–2022); backend development—Eventti (2018–2020).</p>
  </section>

  <section class="resume-section" aria-labelledby="projects-heading">
    <h3 id="projects-heading">Selected AI Engineering Work</h3>
    <div class="resume-project-list">
      <article class="resume-project">
        <h4>AI Agent Chat</h4>
        <p>Built a FastAPI system integrating Slack, GitHub, and LLMs for PR intake, CI monitoring, merge gating, and failure summaries, with webhook verification, replay protection, deduplication, and spend caps.</p>
      </article>
      <article class="resume-project">
        <h4><a href="{{ site.projects.blog_assistant }}">SaroAI — Site-Grounded Blog Assistant</a></h4>
        <p>Implemented an AI Q&amp;A experience over my published archive so readers can ask across articles and receive concise, context-grounded answers.</p>
      </article>
      <article class="resume-project">
        <h4>Model Training &amp; Adaptation</h4>
        <p>Built and trained a 423K-parameter TinyGPT from scratch on custom text for 3,000 CPU steps; also tested Hugging Face Qwen and PEFT/LoRA adaptation workflows.</p>
      </article>
      <article class="resume-project">
        <h4><a href="{{ site.projects.flowtrack }}">Flowtrack</a></h4>
        <p>Built an open-source, local-first activity tracker with a browser dashboard and AI analysis/chat; data stays on the machine by default.</p>
      </article>
    </div>
  </section>

  <div class="resume-bottom-grid">
    <section class="resume-section" aria-labelledby="recognition-heading">
      <h3 id="recognition-heading">Recognition</h3>
      <p><strong>3rd Place</strong> · <a href="{{ site.recognition.alia_2026 }}">Humans in the Loop ALIA Challenge</a> · March 2026</p>
    </section>

    <section class="resume-section" aria-labelledby="education-heading">
      <h3 id="education-heading">Education</h3>
      <ul class="clean-list">
        <li><strong>Computer Science</strong> — STC Higher Education, Malta · Partial completion (2016; no degree awarded)</li>
      </ul>
    </section>

    <section class="resume-section" aria-labelledby="languages-heading">
      <h3 id="languages-heading">Languages</h3>
      <p>English (fluent) · Spanish (conversational) · Nepali (native)</p>
    </section>
  </div>
</article>
