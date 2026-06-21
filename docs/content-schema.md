# Post Frontmatter Schema (Quick Reference)

Use this as a compact checklist when adding or editing posts.

## Required fields

```yaml
layout: post
title: "Post title"
date: 2024-01-01 00:00:00 +00:00
image: /images/example.png
categories: research
```

## Common optional fields

```yaml
author: "Sihan Shao"
authors: "Author A, Author B"
venue: "Conference or Journal"
course: "Course or project label"
paper: /pdfs/example.pdf
slides: /pdfs/slides.pdf
poster: /pdfs/poster.pdf
code: https://github.com/user/repo
video: https://...
video2: https://...
website: https://...
patent: https://...
patent2: https://...
patent3: https://...
subtitle: "Optional subtitle"
```

## Category behavior in current homepage

- `research`: shown in the **Research** section.
- Any category other than `research` and `Intel`: shown in **Projects**.
- `Intel`: currently hidden because the Intel section in `_layouts/default.html` is commented out.

## Image convention

If `image` is `/images/foo.png`, the card thumbnail is expected at `/tn/images/foo.png`.
Generate missing thumbnails with:

```bash
bash _make_thumbnails.sh
```
