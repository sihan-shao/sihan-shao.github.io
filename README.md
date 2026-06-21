# Sihan Shao — Personal Website

This repository contains the source for my personal website, built on a fork of [Jekyll Now](https://github.com/barryclark/jekyll-now) and adapted from [Jon Barron's website](https://jonbarron.info/).

Please feel free to reuse the template structure, but respect copyright for content in `images/`, `pdfs/`, and posts.

## Repository structure

- `_layouts/`: page templates.
- `_posts/`: current posts shown on the website.
- `_old_posts/`: migrated legacy posts kept for reference.
- `images/`: full-size images.
- `tn/images/`: generated thumbnails used in index cards.
- `pdfs/`: papers, slides, CV, and related documents.

## Local workflow

### 1) Generate missing thumbnails

```bash
bash _make_thumbnails.sh
```

### 2) Build and serve with Jekyll

If you have a standard Jekyll setup:

```bash
bundle exec jekyll serve
```

Then open `http://127.0.0.1:4000`.

## Content notes

- The homepage currently renders **two visible sections**: `Research` and `Projects`.
- The old `Intel` section remains in `_layouts/default.html` but is intentionally commented out.
- Posts use frontmatter fields such as `title`, `date`, `image`, `categories`, and optional links (`paper`, `code`, `slides`, etc.).

See `docs/content-schema.md` for a compact frontmatter guide.

## Known constraints

- `permalink: /` is intentionally used. This avoids generating separate post pages for this site style, but can create repeated sitemap entries for `index.html`.
- Some legacy posts contain extra frontmatter metadata that is no longer used by current templates.
- Thumbnail references assume the same relative path under `tn/` as the source image path under `images/`.
