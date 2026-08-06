---
layout: default
title: Writing
permalink: /writing/
description: "Technical writing on applied AI, LLM systems, computer vision, backend reliability, local models, and product engineering."
---

<section class="page-header">
  <h1>Writing</h1>
  <p>Engineering notes, technical essays, and working ideas across AI, software, and science.</p>
</section>

<section class="panel writing-callout">
  <h2>What I write about</h2>
  <p>
    This section is for applied technical writing, not content for content's sake. Expect notes on computer vision,
    local models, backend systems, AI tooling, product lessons, and occasional science-heavy curiosity.
  </p>
  <p>
    If you want to follow new posts, the site has an RSS feed at <a href="{{ '/feed.xml' | relative_url }}">/feed.xml</a>.
  </p>
</section>

<section class="panel">
  <div class="post-list">
    {% for post in site.posts %}
      <article class="post-item">
        <p class="meta"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time> · {{ post.tags | join: ", " }}</p>
        <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
        <p>{{ post.excerpt | strip_html }}</p>
      </article>
    {% endfor %}
  </div>
</section>
