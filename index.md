---
layout: default
title: Home
---

<section class="hero">
  <div class="hero-grid">
    <div>
      <p class="eyebrow">Engineering notebook · AI systems · motion intelligence</p>
      <h1>Hi, I’m Saroj Bartaula. I build AI products that work outside the demo.</h1>
      <p class="lede">
        I’m an AI/ML engineer and product builder based in Spain, working across computer vision,
        backend systems, and real-time AI. I care about useful software, clean execution, and
        turning rough ideas into something people can actually use.
      </p>
      <p class="lede">
        Right now I’m building Tenslam Vision: motion intelligence that turns video into structured
        human movement data for fitness, sports, and future physical AI systems.
      </p>

      <div class="quick-links" aria-label="Primary links">
        <a class="button" href="{{ '/projects/' | relative_url }}">View projects</a>
        <a href="{{ '/writing/' | relative_url }}">Writing</a>
        <a href="{{ '/cv/' | relative_url }}">CV</a>
        <a href="{{ site.social.github }}">GitHub</a>
        <a href="{{ site.social.linkedin }}">LinkedIn</a>
        <a href="{{ site.social.email }}">Email</a>
      </div>
    </div>

    <aside class="hero-note panel" aria-label="Current focus">
      <p class="meta">Current focus</p>
      <h2>Building motion intelligence from real video.</h2>
      <p>
        The thread behind most of my work is simple: take messy physical-world signals and turn
        them into reliable software behavior.
      </p>
      <ul class="clean-list compact-list">
        <li>Pose pipelines and movement analysis</li>
        <li>Real-time systems with practical feedback loops</li>
        <li>Fast prototypes that can survive contact with users</li>
      </ul>
    </aside>
  </div>
</section>

<section class="panel intro-grid">
  <div>
    <h2>What this site is for</h2>
    <p>
      This site has three jobs: show what I can build, document how I think, and publish technical writing around AI,
      engineering, and the edge where software meets the physical world.
    </p>
  </div>
  <div>
    <h2>What visitors should find here</h2>
    <ul class="clean-list">
      <li>Projects with clear technical decisions and real use cases</li>
      <li>Writing about AI systems, computer vision, tooling, and science-adjacent ideas</li>
      <li>A public record of experiments, prototypes, and product thinking</li>
      <li>A fast way to see whether my work fits your team or collaboration</li>
    </ul>
  </div>
</section>

<section class="panel proof-panel">
  <div class="section-heading">
    <p class="eyebrow">For Hiring</p>
    <h2>If you are evaluating me for a technical role</h2>
  </div>
  <div class="split-columns">
    <div>
      <p class="supporting-copy">
        The strongest signal on this site is not a tagline. It is the combination of shipped prototypes,
        technical writing, and a visible pattern of building across AI, backend systems, and product execution.
      </p>
    </div>
    <div>
      <ul class="clean-list compact-list">
        <li>Start with Projects if you want to see applied work</li>
        <li>Read Writing if you want to understand how I reason</li>
        <li>Open the CV if you want the compressed version</li>
      </ul>
    </div>
  </div>
</section>

<section class="panel stack-panel">
  <div class="section-heading">
    <p class="eyebrow">Now</p>
    <h2>What I am spending time on</h2>
  </div>
  <div class="split-columns">
    <div>
      <ul class="clean-list compact-list">
        <li>Building Tenslam Vision and related motion-analysis tooling</li>
        <li>Exploring computer vision, digital twins, robotics simulation, local LLMs, and AI agents</li>
        <li>Writing technical notes directly from experiments instead of polished hindsight</li>
      </ul>
    </div>
    <div>
      <p class="supporting-copy">
        I am most interested in the layer between models and products: the infrastructure, the
        iteration loops, and the design choices that make an AI system genuinely useful.
      </p>
    </div>
  </div>
</section>

<section class="panel">
  <div class="section-heading">
    <p class="eyebrow">Work</p>
    <h2>Selected work</h2>
  </div>
  <div class="project-grid home-project-grid">
    <article class="mini-card">
      <p class="meta">Tenslam Gym</p>
      <p>Android-based AI trainer with pose estimation, posture feedback, and rep counting for everyday workouts.</p>
      <a class="text-link" href="{{ '/projects/' | relative_url }}">See project</a>
    </article>
    <article class="mini-card">
      <p class="meta">Tenslam Vision Motion Engine</p>
      <p>Video-to-skeleton pipeline for fitness, sports, digital twins, and future physical AI systems.</p>
      <a class="text-link" href="{{ '/projects/' | relative_url }}">See project</a>
    </article>
    <article class="mini-card">
      <p class="meta">Local LLM Learning Lab</p>
      <p>Experiments running small models on Ubuntu, learning what is practical on limited hardware.</p>
      <a class="text-link" href="{{ '/projects/' | relative_url }}">See project</a>
    </article>
  </div>
</section>

<section class="panel">
  <div class="section-heading">
    <p class="eyebrow">Favorites</p>
    <h2>Things I keep coming back to</h2>
  </div>
  <div class="favorites-grid">
    <article class="favorite-card">
      <p class="meta">Podcasts and channels</p>
      <ul class="clean-list compact-list">
        <li>All-In Podcast for product, markets, and operator energy</li>
        <li>Dwarkesh for long-form conversations with technical depth</li>
        <li>Founders for company-building stories and obsession</li>
        <li>Lex Fridman when I want patient, wide-ranging interviews</li>
        <li>Aperture for thoughtful visual essays and internet culture</li>
        <li>Joe Rogan occasionally, mostly when the guest is unusually strong</li>
      </ul>
    </article>
    <article class="favorite-card">
      <p class="meta">Books I liked</p>
      <ul class="clean-list compact-list">
        <li>The Almanack of Naval Ravikant</li>
        <li>Zero to One</li>
        <li>Shoe Dog</li>
        <li>Atomic Habits</li>
        <li>The Hard Thing About Hard Things</li>
        <li>Deep Work</li>
      </ul>
      <p class="favorite-note">This list is intentionally lightweight for now and easy to swap out later.</p>
    </article>
  </div>
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
