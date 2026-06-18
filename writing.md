---
layout: default
title: Writing
permalink: /writing/
---

<section class="page-header">
  <h1>Writing</h1>
  <p>Engineering notes, experiments, and technical essays from the workbench.</p>
</section>

<section class="panel">
  <div class="post-list">
    {% for post in site.posts %}
      <article class="post-item">
        <p class="meta">{{ post.date | date: "%B %d, %Y" }} · {{ post.tags | join: ", " }}</p>
        <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
        <p>{{ post.excerpt | strip_html }}</p>
        <a class="text-link" href="{{ post.url | relative_url }}">Read more</a>
      </article>
    {% endfor %}
  </div>
</section>
