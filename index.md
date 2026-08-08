---
layout: default
title: Home
description: "Saroj builds applied AI products, reliable backend systems, LLM workflows, and real-time computer vision applications."
---

<section class="hero">
  <div class="hero-grid">
    <div>
      <p class="eyebrow">Applied AI · Backend Systems · Product Engineering</p>
      <h1>I build AI-enabled products from ambiguous idea to working system.</h1>
      <p class="lede">
        I’m Saroj, an engineer based in Spain working across applied AI, backend systems, and product development.
        I build with Python, FastAPI/Django, LLM and agent workflows, ML integrations, and modern web/mobile technologies.
      </p>
      <p class="lede">
        My focus is simple: turn new technical capability into products people can actually use, evaluate, and trust.
      </p>

      <nav class="quick-links" aria-label="Primary links">
        <a class="button" href="{{ '/projects/' | relative_url }}">View selected work</a>
        <a href="{{ site.social.email }}">Start a conversation</a>
        <a href="{{ '/resume/' | relative_url }}">Resume</a>
        <a href="{{ site.social.github }}" rel="me">GitHub</a>
      </nav>
    </div>

    <aside class="hero-note panel" aria-label="Current focus">
      <p class="meta">Current focus</p>
      <h2>AI applications that ship fast and hold quality.</h2>
      <p>
        Current build themes include LLM workflow automation, backend reliability patterns,
        and applied computer vision where model output must drive product decisions.
      </p>
      <ul class="signal-chips" aria-label="System signal priorities">
        <li>Execution speed</li>
        <li>Reliability</li>
        <li>Product utility</li>
      </ul>
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
      <p class="meta">Flagship AI workflow</p>
      <h3>AI Agent Chat</h3>
      <p>Slack-first engineering assistant for PR intake, CI monitoring, merge gating, and GPT-4o powered check summaries.</p>
      <a class="text-link" href="{{ '/projects/#ai-agent-chat' | relative_url }}">See project and architecture</a>
    </article>
    <article class="mini-card">
      <p class="meta">Local-first product</p>
      <h3>Flowtrack</h3>
      <p>Local-first productivity tracker with AI-powered dashboard behavior and no cloud account dependency.</p>
      <a class="text-link" href="{{ '/projects/#flowtrack' | relative_url }}">See project</a>
    </article>
    <article class="mini-card">
      <p class="meta">Real-time computer vision</p>
      <h3>Tenslam Gym</h3>
      <p>Android-based AI trainer with pose estimation, posture feedback, and rep counting for everyday workouts.</p>
      <a class="text-link" href="{{ '/projects/#tenslam-gym' | relative_url }}">See project</a>
    </article>
    <article class="mini-card">
      <p class="meta">Motion intelligence</p>
      <h3>Motion Intelligence Experiments</h3>
      <p>Ongoing work on converting video into structured human-movement information for products and systems.</p>
      <a class="text-link" href="{{ '/projects/#tenslam-vision-motion-engine' | relative_url }}">See project</a>
    </article>
  </div>
</section>

<section class="panel">
  <div class="section-heading">
    <p class="eyebrow">Archive</p>
    <h2>Ask my archive</h2>
  </div>
  <p>Ask about my writing, public projects, or background. Answers are generated from information published on this site and may be incomplete. Sources and dates are shown where available.</p>
</section>

<section class="panel" id="experience">
  <div class="section-heading">
    <p class="eyebrow">Experience</p>
    <h2>Career timeline</h2>
  </div>
  <div class="split-columns">
    <div>
      <p><strong>2025–Present · Tenslam Vision</strong><br>Founder & Applied AI / Product Engineer</p>
      <p><strong>2023–2025 · Tenslam</strong><br>Co-Founder & ML / Product Developer</p>
      <p><strong>2022–2023 · Box99 / TheHeCapp</strong><br>AI / Product Contributor</p>
      <p><strong>2022 · Demium</strong><br>Entrepreneur in Residence</p>
    </div>
    <div>
      <p><strong>2020–2022 · Independent Web & Data Projects</strong><br>Self-employed / Independent · Spain</p>
      <p><strong>2018–2020 · Eventti.net</strong><br>Backend Development Contributor</p>
      <p><strong>2013–2016 · Sky Infosys</strong><br>Computer Technician</p>
      <p class="meta">See the full role detail and tools on the resume page.</p>
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
        <p class="meta"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time> · {{ post.tags | join: ", " }}</p>
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <p>{{ post.excerpt | strip_html }}</p>
      </article>
    {% endfor %}
  </div>
  <p class="section-link"><a href="{{ '/writing/' | relative_url }}">Browse all writing</a></p>
</section>
