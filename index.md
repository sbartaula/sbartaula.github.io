---
layout: default
title: Home
---

<section class="hero">
  <p class="eyebrow">Engineering notebook</p>
  <h1>Hi, I’m Saroj Bartaula.</h1>
  <p class="lede">
    I’m an AI/ML engineer and product builder based in Spain. I build computer vision, backend,
    and real-time AI systems with a focus on useful, shippable prototypes.
  </p>
  <p class="lede">
    Currently building Tenslam Vision — motion intelligence that turns video into structured human movement data
    for fitness, sports, and digital twins.
  </p>

  <div class="quick-links" aria-label="Primary links">
    <a href="{{ '/writing/' | relative_url }}">Writing</a>
    <a href="{{ '/projects/' | relative_url }}">Projects</a>
    <a href="{{ '/cv/' | relative_url }}">CV</a>
    <a href="{{ site.social.github }}">GitHub</a>
    <a href="{{ site.social.linkedin }}">LinkedIn</a>
    <a href="{{ site.social.email }}">Email</a>
  </div>
</section>

<section class="panel intro-grid">
  <div>
    <h2>What this site is for</h2>
    <p>
      A place to document engineering work, show live experiments, and keep a public trail of technical notes.
      I use this site for writing, portfolio proof, and lightweight updates on what I am building now.
    </p>
  </div>
  <div>
    <h2>Focus areas</h2>
    <ul class="clean-list">
      <li>Computer vision and motion intelligence</li>
      <li>Backend systems and APIs</li>
      <li>Real-time AI and local models</li>
      <li>Product prototyping and technical writing</li>
    </ul>
  </div>
</section>

<section class="panel">
  <h2>Currently</h2>
  <ul class="clean-list">
    <li>Building Tenslam Vision</li>
    <li>Exploring computer vision, digital twins, robotics simulation, local LLMs, and AI agents</li>
    <li>Writing technical notes from real projects and experiments</li>
  </ul>
</section>

<section class="panel">
  <h2>Selected work</h2>
  <div class="project-grid home-project-grid">
    <article class="mini-card">
      <p class="meta">Tenslam Gym</p>
      <p>Android-based AI trainer with pose estimation, posture feedback, and rep counting.</p>
      <a class="text-link" href="{{ '/projects/' | relative_url }}">See project</a>
    </article>
    <article class="mini-card">
      <p class="meta">Tenslam Vision Motion Engine</p>
      <p>Video-to-skeleton pipeline for fitness, sports, digital twins, and physical AI.</p>
      <a class="text-link" href="{{ '/projects/' | relative_url }}">See project</a>
    </article>
    <article class="mini-card">
      <p class="meta">Local LLM Learning Lab</p>
      <p>Experiments running small models on Ubuntu with limited hardware.</p>
      <a class="text-link" href="{{ '/projects/' | relative_url }}">See project</a>
    </article>
  </div>
</section>

<section class="panel">
  <h2>Recent writing</h2>
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
