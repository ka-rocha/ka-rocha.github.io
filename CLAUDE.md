# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Kyle Rocha's personal academic website, built on the [al-folio](https://github.com/alshedivat/al-folio) Jekyll theme and deployed to `ka-rocha.github.io` via GitHub Pages. Pushing to `main` triggers automatic deployment (takes ~4 min via GitHub Actions).

## Running locally

```bash
bundle install          # first time only
bundle exec jekyll serve
# → http://localhost:4000
```

Or with Docker (no Ruby setup needed):
```bash
docker compose pull && docker compose up
# → http://localhost:8080
```

Build static output (no server):
```bash
bundle exec jekyll build   # output goes to _site/
```

## Content architecture

All site content lives in a handful of directories; everything else is theme infrastructure:

| Path | Controls |
|---|---|
| `_pages/about.md` | Homepage — bio, subtitle, profile card |
| `_pages/*.md` | All other pages (CV, projects, publications, etc.) |
| `_bibliography/papers.bib` | Publications — Jekyll Scholar auto-renders these |
| `_data/cv.yml` | CV fallback data (used if `assets/json/resume.json` is absent or empty) |
| `assets/json/resume.json` | Primary CV data (JSON Resume standard); takes precedence over `_data/cv.yml` |
| `_news/` | News items shown on the homepage |
| `_projects/` | Project cards shown on `/projects/` |
| `_posts/` | Blog posts |
| `_data/repositories.yml` | GitHub repos/users shown on `/repositories/` |
| `assets/img/` | Images (profile photo, project thumbnails, etc.) |
| `assets/pdf/` | PDFs linked from publications |

## Key config

`_config.yml` is the single source of truth for:
- Personal info: `first_name`, `last_name`, `email`, social handles
- Scholar config: `scholar.last_name` / `scholar.first_name` — update these from "Einstein" to "Rocha" so publications sort correctly
- Feature flags: `enable_darkmode`, `enable_math`, `selected_papers`, etc.
- `inspirehep_id`, `scholar_userid` — already set; drives publication badges

## Publications

Edit `_bibliography/papers.bib`. Extra per-entry fields supported: `pdf`, `arxiv`, `code`, `poster`, `slides`, `abstract`, `selected={true}` (surfaces on homepage), `preview` (thumbnail image path).

## Theme customization

- Colors: `_sass/_themes.scss` → `--global-theme-color`
- Available color variables: `_sass/_variables.scss`
- Layout tweaks: `_layouts/` (Liquid templates) and `_includes/` (partials)
