---
layout: default
title: Home
---

<section class="hero">
  <p class="eyebrow">Engineering notebook</p>
  <h1>Hi, I’m Saroj Bartaula.</h1>
  <p class="lede">
    I’m an AI/ML engineer and product builder from Nepal, based in Spain. I build computer vision, backend,
    and real-time AI systems.
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

<section class="panel">
  <h2>Currently</h2>
  <ul class="clean-list">
    <li>Building Tenslam Vision</li>
    <li>Exploring computer vision, digital twins, robotics simulation, local LLMs, and AI agents</li>
    <li>Writing technical notes from real projects and experiments</li>
  </ul>
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
</section>
