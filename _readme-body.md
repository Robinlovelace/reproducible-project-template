## Quick start

*(Note: The commands below use the [GitHub CLI (`gh`)](https://cli.github.com/). If you don't have it installed, you can [follow the installation instructions](https://cli.github.com/) or create the repository manually on GitHub).*

```sh
gh repo create my-slides --template robinlovelace/reproducible-project-template
cd my-slides
# Enable Pages: Settings → Pages → Source: Deploy from a branch → Branch: gh-pages, / (root)
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
| **Word version** | `paper.qmd` builds a `.docx` for co-authors to edit with tracked changes |

## Workflows

| Workflow | Trigger | What it does |
|----------|---------|--------------|
| `publish.yml` | Push to main | Render site → deploy to GitHub Pages |
| `release-standalone.yml` | Push to main | Build self-contained HTML + PDF → create dated release |
| `pr-preview.yml` | PR to main | Build preview → deploy to temporary URL |

## Structure

```
├── slides.qmd                  # Main slide deck
├── paper.qmd                   # Paper, built as .docx
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

## Word version for co-authors

`paper.qmd` builds a Word document (`docs/paper.docx`), rendered to the site as an "Other Formats" download. Citations from `references.bib` are rendered as text, for example [@peng2011].

To turn it off, delete the `docx: default` line in the `format:` block of `paper.qmd`. To add a docx to another page, copy the same `format:` block into that page.

Editing with tracked changes:

1. Download the docx from the site, or from the `docx` artifact of the latest Publish run.
2. Co-authors turn on Review, Track Changes in Word and edit as normal.
3. The author opens the `.qmd` next to the returned docx and copies each accepted change back by hand. Convert the file to Markdown to see changes quickly with `pandoc --track-changes=all -t markdown paper.docx`.
4. Commit the `.qmd`. The next build replaces the docx.

The docx is a snapshot. Edits made in Word are not read back automatically, so always edit the `.qmd` as the source of truth.

