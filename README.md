# Communication Theory Primer (Jekyll + GitHub Pages)

This repository is configured as a Jekyll website designed for non-technical audiences who want to understand communication theory and apply it to contemporary problems, including AI-mediated communication.

## Site structure

- `index.md` — Home page / project introduction.
- `pages/transmission-view.md` — Transmission model and its limits.
- `pages/meaning-and-culture.md` — Semiotics and meaning-making.
- `pages/interpretation-and-power.md` — Encoding/decoding and power.
- `pages/interpretation-and-intention.md` — Eco + intentio algorithmi lens.
- `pages/what-to-do.md` — Practical guidance page.
- `pages/how-this-site-was-built.md` — Build/process transparency page.
- `_layouts/default.html` — Shared accessible page layout and navigation.
- `assets/css/style.css` — Main styling with editable CSS variables.
- `assets/images/` — Image folder for your content assets.
- `.github/workflows/jekyll-build.yml` — GitHub Actions workflow that builds on push to `main`.

## Local development

1. Install Ruby and Bundler if needed.
2. Install dependencies:
   ```bash
   bundle install
   ```
3. Start a local server:
   ```bash
   bundle exec jekyll serve
   ```
4. Open the local URL shown in the terminal (usually `http://127.0.0.1:4000/comm-primer/`).

## Writing and updating content

### 1) Edit page content

Each page is a Markdown file with front matter at the top:

```yaml
---
layout: default
title: Page Title
permalink: /pages/example.html
---
```

Keep the front matter block in place. Replace the boilerplate body text under it with your final writing.

### 2) Add new pages (optional)

1. Create a new Markdown file in `/pages`.
2. Add front matter with `layout`, `title`, and `permalink`.
3. Add a navigation link in `/_layouts/default.html`.

### 3) Add images

1. Put image files in `/assets/images/`.
2. Reference them in Markdown using a path like:
   ```md
   ![Alt text]({{ '/assets/images/example.jpg' | relative_url }})
   ```
3. Always write descriptive alt text for accessibility.

## Accessibility checklist for your content

When writing final content, keep these practices:

- Use headings in logical order (`##`, then `###`, etc.).
- Give every image meaningful alt text.
- Keep link text descriptive (avoid "click here").
- Use short paragraphs and bullet lists for readability.

## Basic style customization

Edit the CSS variables in `assets/css/style.css` under `:root`:

- `--bg-color`
- `--surface-color`
- `--text-color`
- `--heading-color`
- `--accent-color`
- `--accent-strong`
- `--border-color`
- `--focus-color`
- `--muted-color`

You can adjust these values to tune branding while preserving the existing layout and accessibility defaults.

## GitHub Pages build automation

The workflow at `.github/workflows/jekyll-build.yml` builds the Jekyll site on every push to `main`.

Repository-aware values are already set in `_config.yml`:

- `url: https://abbyfriedman1.github.io`
- `baseurl: /comm-primer`
- `repository: abbyfriedman1/comm-primer`

If the repository name changes, update `baseurl` and `repository`.
