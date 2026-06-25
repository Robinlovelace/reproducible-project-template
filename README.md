# Quarto revealjs slides template

A template for reproducible slides with Quarto, GitHub Actions, and GitHub Pages.

**Live demo:** https://robinlovelace.github.io/reproducible-project-template/slides.html

## Quick start

```sh
gh repo create my-slides --template robinlovelace/reproducible-project-template
cd my-slides
# Edit slides.qmd, then push
git push
```

Then enable Pages: **Settings → Pages → Source: GitHub Actions**.

## What's included

- **clean-revealjs theme** — bundled in `_extensions/`, no install needed
- **GitHub Actions** — renders and deploys on every push (deploy-pages@v4)
- **Self-contained HTML** — automatic release workflow for offline sharing
- **Citation support** — `references.bib` ready for bibliographies

## Built with this template

- [AUM 2026 slides](https://robinlovelace.net/aum26/) — Modelling multi-model traffic, casualties and risk
- [ITF Workshop slides](https://robinlovelace.net/itfworkshop/) — Building communities of transport practitioners

## Structure

```
├── slides.qmd              # Main slide deck
├── index.qmd               # Landing page
├── _quarto.yml             # Project config
├── references.bib          # Bibliography
├── _extensions/clean/      # clean-revealjs theme
└── .github/workflows/
    ├── publish.yml          # Render + deploy to Pages
    └── release-standalone.yml  # Build self-contained HTML
```