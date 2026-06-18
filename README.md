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
---
```

## Deploy with GitHub Pages

1. Create a GitHub repository named `sbartaula.github.io`.
2. Push this project to the repository.
3. In the repository settings, open Pages.
4. Set the source to the `main` branch and the root folder.
5. Wait for the build to finish, then open `https://sbartaula.github.io`.

If the repository is named something else, GitHub Pages publishes it at a project URL like `https://sbartaula.github.io/<repo>/`. To use the root URL `https://sbartaula.github.io/`, the repository itself must be `sbartaula.github.io`.

## Edit the CV

The CV page lives in `cv.md`. Update the summary, skills, experience, education, and links there directly.

## Edit projects

The project portfolio lives in `projects.md`. Each project is a simple HTML section, so you can add, remove, or reorder projects without touching any other part of the site.

## Site structure

- `_config.yml` site settings
- `_layouts/` page templates
- `_includes/` shared header and footer
- `_posts/` blog posts
- `assets/css/style.css` main stylesheet
