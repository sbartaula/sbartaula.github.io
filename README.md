# Saroj Bartaula — Engineering Lab

This repository is a minimal Jekyll site for my engineering identity on GitHub Pages.

It is meant for:

- technical writing
- project portfolio pages
- a short online CV
- engineering notes in Markdown

The site is intentionally simple: Jekyll, Markdown, HTML, CSS, and GitHub Pages compatibility.

## Run locally

Install dependencies and start the local Jekyll server:

```bash
bundle install
bundle exec jekyll serve
```

Then open the local URL that Jekyll prints in the terminal, usually `http://127.0.0.1:4000`.

## Add a new blog post

Create a new Markdown file inside `_posts` using this format:

```text
YYYY-MM-DD-title.md
```

Example front matter:

```yaml
---
layout: post
title: "My Blog Title"
date: 2026-06-18
tags: [AI, Computer Vision]
excerpt: "Short summary here."
hero_image: /assets/images/my-post-image.jpg
hero_image_alt: "Short alt text"
hero_image_caption: "Optional caption."
---
```

You can also use normal Markdown images inside posts:

```md
![Alt text](/assets/images/example.jpg)
```

Put images in `assets/images/` so they stay easy to organize later.

## Deploy with GitHub Pages

1. Create a GitHub repository named `sbartaula.github.io`.
2. Push this project to the repository.
3. In the repository settings, open Pages.
4. Set the source to the `main` branch and the root folder.
5. Wait for the build to finish, then open `https://sbartaula.github.io`.

To use the root URL `https://sbartaula.github.io/`, the repository itself must be renamed to `sbartaula.github.io`. After that rename, GitHub Pages will publish it like a user site at the root.

## Edit the CV

The CV page lives in `cv.md`. Update the summary, skills, experience, education, and links there directly.

## Edit projects

The project portfolio lives in `projects.md`. Each project is a simple HTML section, so you can add, remove, or reorder projects without touching any other part of the site.

## RSS and subscriptions

The site already publishes an RSS feed at `/feed.xml`. That is the simplest subscription option and works well for readers who want a low-friction way to follow new posts.

If you want email subscriptions later, a common next step is to add a service like Buttondown, Mailchimp, or ConvertKit, then link it from the writing page and footer.

## Site structure

- `_config.yml` site settings
- `_layouts/` page templates
- `_includes/` shared header and footer
- `_posts/` blog posts
- `assets/css/style.css` main stylesheet
