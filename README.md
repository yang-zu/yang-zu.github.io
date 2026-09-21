# yang-zu.github.io

Personal academic website for **Yang Zu** (Associate Professor of Economics, University of Macau),
built with [Quarto](https://quarto.org) and deployed to GitHub Pages.

Live site: <https://yang-zu.github.io>

## Structure

```
_quarto.yml          # site config (theme, navbar, URL)
index.qmd            # home / about page
publications.qmd     # publications listing page
publications/        # one .qmd per paper (title, links, BibTeX)
teaching.qmd
styles.css
cv.pdf               # CV (replace to update)
profile.jpg          # headshot (replace the placeholder)
.github/workflows/publish.yml   # renders + deploys on every push to main
```

## How it deploys

Every push to `main` triggers the GitHub Action, which runs `quarto render` and
publishes `_site/` to GitHub Pages. Nothing needs to be built or committed by hand;
`_site/` and `.quarto/` are gitignored.

**One-time setup:** in the repo, go to **Settings → Pages → Build and deployment →
Source = "GitHub Actions"**.

## Add or edit a publication

Copy an existing file in `publications/`, e.g.:

```yaml
---
title: "Paper title"
description: "Authors (Year). *Journal* vol, pages."
date: 2026-01-01        # controls sort order (newest first)
categories: [Bubble testing, forthcoming]   # become filter tags
---
```

Add a `## Links` section (journal DOI, working paper, code) and a `## BibTeX`
block. Save and push — it appears on `/publications` automatically.

## Edit locally (optional)

Install Quarto (<https://quarto.org/docs/get-started/>), then:

```
quarto preview     # live-reloading local preview
quarto render      # build _site/
```

## Common tweaks

- **Theme:** change `theme:` in `_quarto.yml` (`cosmo`, `litera`, `flatly`, `journal`, `zephyr`).
- **Photo:** replace `profile.jpg` with a headshot (~400×500 px).
- **CV:** replace `cv.pdf`.
