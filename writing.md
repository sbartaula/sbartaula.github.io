---
layout: default
title: Writing
permalink: /writing/
---

<section class="page-header">
  <h1>Writing</h1>
  <p>Engineering notes, experiments, and technical essays from the workbench.</p>
</section>

<section class="panel writing-callout">
  <h2>Subscribe</h2>
  <p>
    The site has a working RSS feed at <a href="{{ '/feed.xml' | relative_url }}">/feed.xml</a>.
    That is the cleanest way to follow new notes for now. If I add email updates later, I’ll link them here.
  </p>
  <p>
    To write a new post, add a Markdown file to <code>_posts</code> using the date-title format and include the front matter shown in the README.
  </p>
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
