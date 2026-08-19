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
        I’m Saroj Bartaula, an engineer based in Spain working across applied AI, backend systems, and product development.
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

  <article class="featured-project" aria-labelledby="blog-assistant-title">
    <div>
      <p class="meta">Featured personal project · Live</p>
      <h3 id="blog-assistant-title">SaroAI — Site-Grounded Blog Assistant</h3>
      <p>
        I turned my personal blog into an interactive archive with an LLM-powered Q&amp;A experience.
        Visitors can ask across published articles and receive concise, context-grounded answers instead of searching post by post.
      </p>
      <ul class="signal-chips" aria-label="Project capabilities">
        <li>LLM integration</li>
        <li>Conversational UI</li>
        <li>Live product</li>
      </ul>
    </div>
    <div class="project-actions">
      <a class="button" href="{{ site.projects.blog_assistant }}">Try SaroAI</a>
      <a class="text-link" href="{{ '/projects/#personal-blog-ai-assistant' | relative_url }}">Read the project overview</a>
    </div>
  </article>

  <div class="project-grid home-project-grid">
    <article class="mini-card">
      <p class="meta">AI workflow engineering</p>
      <h3>AI Agent Chat</h3>
      <p>Slack-first engineering assistant for PR intake, CI monitoring, merge gating, and GPT-4o powered check summaries.</p>
      <a class="text-link" href="{{ '/projects/#ai-agent-chat' | relative_url }}">See project and architecture</a>
    </article>
    <article class="mini-card">
      <p class="meta">Local-first product</p>
      <h3>Flowtrack</h3>
      <p>Open-source activity tracker with a browser dashboard, AI analysis/chat, and local data ownership by default.</p>
      <div class="project-links">
        <a class="text-link" href="{{ '/projects/#flowtrack' | relative_url }}">See project</a>
        <a class="text-link" href="{{ site.projects.flowtrack }}">View source</a>
      </div>
    </article>
    <article class="mini-card">
      <p class="meta">Real-time computer vision</p>
      <h3>Tenslam Gym</h3>
      <p>Android AI trainer with real-time pose feedback, used by 20+ users with 5,000+ exercise reps processed.</p>
      <div class="project-links">
        <a class="text-link" href="{{ '/projects/#tenslam-gym' | relative_url }}">See project</a>
        <a class="text-link" href="{{ site.projects.tenslam_gym }}">Visit live product</a>
      </div>
    </article>
    <article class="mini-card">
      <p class="meta">Motion intelligence</p>
      <h3>Tenslam Vision Motion Engine</h3>
      <p>Ongoing work on converting video into structured human-movement information for products and systems.</p>
      <div class="project-links">
        <a class="text-link" href="{{ '/projects/#tenslam-vision-motion-engine' | relative_url }}">See project</a>
        <a class="text-link" href="{{ site.projects.tenslam_vision }}">Visit Tenslam Vision</a>
      </div>
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
      <p><strong>Sep 2025–Present · Tenslam Vision</strong><br>Founder & Applied AI / Product Engineer</p>
      <p><strong>Jun 2023–Mar 2025 · TenSlam</strong><br>Co-Founder & ML / Product Developer</p>
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
  <p><strong>March 2026 · <a href="{{ site.recognition.alia_2026 }}">Humans in the Loop ALIA Challenge</a></strong></p>
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
