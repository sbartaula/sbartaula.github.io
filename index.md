---
layout: default
title: Home
---

<section class="hero">
  <div class="hero-grid">
    <div>
      <p class="eyebrow">Applied AI · Backend Systems · Product Engineering</p>
      <h1>I build AI-enabled products from ambiguous idea to working system.</h1>
      <p class="lede">
        I am Saroj, an engineer based in Spain working across applied AI, backend systems, and product development.
        I build with Python, FastAPI/Django, LLM and agent workflows, ML integrations, real-time applications,
        and modern web/mobile stacks.
      </p>
      <p class="lede">
        My focus is simple: turn emerging AI capability into useful products that real users can run,
        evaluate, and trust.
      </p>

      <div class="quick-links" aria-label="Primary links">
        <a class="button" href="{{ '/projects/' | relative_url }}">View selected work</a>
        <a href="{{ '/resume/' | relative_url }}">Resume</a>
        <a href="{{ '/writing/' | relative_url }}">Writing</a>
        <a href="{{ site.social.github }}">GitHub</a>
        <a href="{{ site.social.linkedin }}">LinkedIn</a>
      </div>
    </div>

    <aside class="hero-note panel" aria-label="Current focus">
      <p class="meta">Current focus</p>
      <h2>AI applications that ship fast and hold quality.</h2>
      <p>
        Current build themes include LLM workflow automation, backend reliability patterns,
        and applied computer vision where model output must drive product decisions.
      </p>
      <div class="signal-chips" aria-label="System signal priorities">
        <span>Execution speed</span>
        <span>Reliability</span>
        <span>Product utility</span>
      </div>
      <ul class="clean-list compact-list">
        <li>AI agent workflows with operational guardrails</li>
        <li>API and backend systems for model-enabled products</li>
        <li>Real-time CV pipelines under practical device constraints</li>
      </ul>
    </aside>
  </div>
</section>

<section class="panel" id="work">
  <div class="section-heading">
    <p class="eyebrow">Work</p>
    <h2>Selected work</h2>
  </div>
  <div class="project-grid home-project-grid">
    <article class="mini-card">
      <p class="meta">AI Agent Chat</p>
      <p>Slack-first engineering assistant for PR intake, CI monitoring, merge gating, and GPT-4o powered check summaries.</p>
      <a class="text-link" href="{{ '/projects/#ai-agent-chat' | relative_url }}">See project</a>
    </article>
    <article class="mini-card">
      <p class="meta">Flowtrack</p>
      <p>Local-first productivity tracker with AI-powered dashboard behavior and no cloud account dependency.</p>
      <a class="text-link" href="{{ '/projects/#flowtrack' | relative_url }}">See project</a>
    </article>
    <article class="mini-card">
      <p class="meta">Tenslam Gym</p>
      <p>Android-based AI trainer with pose estimation, posture feedback, and rep counting for everyday workouts.</p>
      <a class="text-link" href="{{ '/projects/#tenslam-gym' | relative_url }}">See project</a>
    </article>
  </div>
</section>

<section class="panel" id="experience">
  <div class="section-heading">
    <p class="eyebrow">Experience</p>
    <h2>Career timeline</h2>
  </div>
  <div class="split-columns">
    <div>
      <p><strong>2026-Present · Tenslam Vision</strong><br>Founder and Applied AI Engineer</p>
      <p><strong>2022-2024 · Tenslam</strong><br>ML Engineer</p>
      <p><strong>2022-2023 · TheHeCapp</strong><br>AI Engineer</p>
    </div>
    <div>
      <p><strong>2022 · Greentech Barcelona</strong><br>Data Science and Web Development</p>
      <p><strong>2018-2020 · Eventti</strong><br>Junior Backend Developer</p>
      <p class="meta">See full role detail and tools in the resume page.</p>
    </div>
  </div>
</section>

<section class="panel">
  <div class="section-heading">
    <p class="eyebrow">Recognition</p>
    <h2>Selected external validation</h2>
  </div>
  <p><strong>March 2026 · Humans in the Loop ALIA Challenge</strong></p>
  <p>3rd place in the ALIA challenge, focused on model optimization, iterative refinement, and human-in-the-loop safe AI workflow design.</p>
</section>

<section class="panel">
  <div class="section-heading">
    <p class="eyebrow">Writing</p>
    <h2>Recent writing</h2>
  </div>
  <div class="post-list">
    {% for post in site.posts limit:3 %}
      <article class="post-item">
        <p class="meta">{{ post.date | date: "%B %d, %Y" }} · {{ post.tags | join: ", " }}</p>
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <p>{{ post.excerpt | strip_html }}</p>
      </article>
    {% endfor %}
  </div>
  <p class="section-link"><a href="{{ '/writing/' | relative_url }}">Browse all writing</a></p>
</section>
