# Auricular Research Atlas

Krishna Koka · Computational evaluation and cartilage matching for auricular frameworks.

- **[Surgeon-facing interactive review](https://kkoka1116.github.io/auricular-research-atlas/surgeon/)** — an explainer prepared for surgical discussion, with component models, study comparisons, forming animations, literature and questions for review.
- **[Complete public atlas](https://kkoka1116.github.io/auricular-research-atlas/)** — the eleven development milestones and detailed methods notes.

This is the public website edition. It contains project-authored findings and appropriately attributed ear-derived geometry. Native CCSeg cartilage anatomy, CT previews, scan-coordinate placements and supplied course-handbook images are withheld. The separate full research repository remains private.

The work is exploratory. No complete four-component allocation or clinical validation has been established. The animations and mechanical estimates are conditional on the stated assumptions; they are not validated operative plans.

## Hosting and updates

GitHub Pages serves `docs/` from `main`. No build step is required; `.nojekyll` preserves the static files. Relative links support the project URL. Push updated site files to `main` to publish an update.

For a local preview, run `python3 -m http.server 8780 --directory docs` and open http://127.0.0.1:8780/.

The website requires HTTP serving and a current browser with WebGL and gzip decompression support. No account or external research software is needed to read it.

## Attribution and checks

See [third-party notices](docs/THIRD_PARTY_NOTICES.md), [publication scope](docs/public-edition-verification.json), [asset verification](docs/website-verification.json), and [surgeon-brief verification](docs/surgeon/verification.json).

Ear-derived geometry is adapted from Díez-Montiel and colleagues’ [2024 supplementary models](https://zenodo.org/records/10958624) under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). Attribution and modification notices are retained. Other assets retain their respective terms; this repository does not grant a blanket license to third-party material.
