## Quick start

*(Note: The commands below use the [GitHub CLI (`gh`)](https://cli.github.com/). If you don't have it installed, you can [follow the installation instructions](https://cli.github.com/) or create the repository manually on GitHub).*

```sh
gh repo create my-slides --template robinlovelace/reproducible-project-template
cd my-slides
# Enable Pages: Settings → Pages → Source: GitHub Actions
# Edit slides.qmd, then push
git push
```

Your slides are live in ~30 seconds.

## Features

| Feature | Description |
|---------|-------------|
| **clean-revealjs theme** | Bundled in `_extensions/`, zero install needed |
| **Auto-deploy** | `actions/deploy-pages@v4` on every push to main |
| **Auto-detect** | Uses `quarto inspect` to detect R/Python needs; only installs what's required |
| **PR previews** | Deploy preview versions for review before merging |
| **Quarto freeze** | Cache computation results locally; CI only re-renders markdown |
| **Self-contained HTML** | Offline-capable HTML with all images, CSS, and JS embedded |
| **PDF export** | Auto-generated via DeckTape on every release |
| **Date-based releases** | Automatic versioned releases on every push |
| **Citation support** | `references.bib` ready for bibliographies |

## Workflows

| Workflow | Trigger | What it does |
|----------|---------|--------------|
| `publish.yml` | Push to main | Render site → deploy to GitHub Pages |
| `release-standalone.yml` | Push to main | Build self-contained HTML + PDF → create dated release |
| `pr-preview.yml` | PR to main | Build preview → deploy to temporary URL |

## Structure

```
├── slides.qmd                  # Main slide deck
├── index.qmd                   # Landing page
├── _quarto.yml                 # Project config (output-dir, freeze, navbar)
├── references.bib              # Bibliography
├── _extensions/clean/          # clean-revealjs theme (bundled)
└── .github/workflows/
    ├── publish.yml             # Render + deploy to Pages
    ├── release-standalone.yml  # Self-contained HTML + PDF release
    └── pr-preview.yml          # PR preview deployments
```

## Built with this template

- [AUM 2026 slides](https://robinlovelace.net/aum26/) — Modelling multi-model traffic, casualties and risk
- [ITF Workshop slides](https://robinlovelace.net/itfworkshop/) — Building communities of transport practitioners