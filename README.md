# Notebooks for a neuro-AI course

Supporting Colab notebooks and figure-generation code for a neuro-AI course.  
Notebooks are standalone, and also generate figures used in companion Google Slides decks (the decks themselves do not live in this repo).

## What's in this repo
- `notebooks/` — Instructor notebooks intended to run in Colab
  - `notebooks/ch01/`, `notebooks/ch02/`, ...
- `utils/` — Shared helper code (e.g., seeding, plotting defaults, figure export helpers)
- `manifests/` — Tables of contents and links (chapters → notebooks → slide decks), plus pointers to shared Drive folders
- `scripts/` — Small utilities (e.g., regenerate figures for a chapter, sync outputs to Drive)
- 'figures/' — Local build output (ignored by git). Canonical figures are stored in a shared Google Drive folder (see manifests/figures.yml).

## Slides (external)
- Slides are authored and edited in Google Slides (Drive).
- Canonical slide deck links live in `manifests/course_toc.yml` (or an equivalent index file).
- Optional: exported snapshots (PDF/PPTX) can be stored under `slides_exports/` for release tagging, but the editable source remains in Drive.

## Notebooks and Colab

- Notebooks are intended to run in Google Colab (GPU used in some chapters).
- Canonical Colab links live in `manifests/course_toc.yml`.

## Figures

**Goal:** figures are reproducible and updateable without manual slide-by-slide replacement.

Conventions:
- Figures are addressed by a *relative path* (a “figure key”) that is used both locally and in Slides.
- Naming convention: `ch{chapter}/fig_{chapter}_{section}_{number}_{shortname}.png`  
  Example: `ch03/fig_03_02_01_gradient_flow.png`
- Notebooks should set seeds so regenerated figures are pixel-stable.
- Figures are generated locally under `figures/` (ignored by git) and written/synced to the shared Google Drive folder defined in `manifests/figures.yml`.

### Slide figure refresh workflow (recommended)

- Any figure that should be auto-refreshable in Slides must have **Alt Text → Description** set to:
  - `FIG:<relative_path>`
  - Example: `FIG:ch03/fig_03_02_01_gradient_flow.png`
- The `<relative_path>` is relative to the shared Drive figures folder defined in `manifests/figures.yml`.
- Use the Slides menu item `Course Tools → Refresh tagged figures` to update all tagged figures in-place.
  - (The Apps Script is stored inside each Slides deck.)

## Third-party materials

If you add third-party images/figures, include attribution inline (on-slide or in the adjacent notebook cell) and respect the original licence.

## Licensing

- **Code** is licensed under the **MIT License** (see `LICENSE`).
- **Notebook prose and original figures** are licensed under **CC BY 4.0** (see `LICENSE-CONTENT`).
- **Third-party materials** retain their own licences (see attributions inline).
