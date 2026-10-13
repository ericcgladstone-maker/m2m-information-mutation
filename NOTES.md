# github/ — Export folder

Copied materials prepared for GitHub upload. **Not the canonical source.**

## What this is

A staging area for a clean GitHub presentation of the M2M Information Mutation simulation work. Files here are copies. Originals remain in the parent project folder.

## Refresh model

- Treat this folder as **derived**. Do not edit files here as the primary copy.
- When the parent project changes, refresh by re-copying from the canonical source, not by editing the export in place.
- Future re-exports may overwrite anything added directly here.
- A future CoMSES deposit may pull from the same staging.

## What was copied

- `README.md` — top-level overview.
- `simulations/` — interactive HTML simulations (`m2m_v1.html`, `m2m_v2.html`, `m2m_pilot.html`).
- `data/` — results CSVs (single-condition and multi-condition runs).
- `figures/figure_1_topology_error_profile.png` — final figure asset.
- `references/Gladstone & Brashears — Error Correction Mechanisms M2M.pdf` — companion paper PDF.
- `dev_notes/` — Markdown dev notes (`M2M Information Mutation — Dev Log.md`, `M2M Information Mutation — Handoff Note.md`, `M2M Information Mutation — Pilot Analysis Report.md`).
- `submission_materials/social_networks/` — Markdown source for the earlier *Social Networks* submission bundle, retained as history (the current version is revise and resubmit at *Scientific Reports*) (title page, blinded manuscript, highlights, declarations, cover letter, data availability statement, figures).

## What was deliberately excluded

- `archive/` (~13 MB) — old Stata `.do`/`.dta` files, an early Java-era reference PDF, an `original_data_clean.csv`, the V5 simulation HTML, AI/Claude logs (`.docx`). Historical only.
- `manuscript/` — all manuscript versions (`.docx`). Manuscript text does not belong in the code-and-data repo.
- `dev/*.py` and `dev/M2M … Claude Log.docx` — build scripts for the Word/PDF artifacts and AI session logs; not useful to outside readers.
- `submission/social_networks/*.docx` — the rendered Word artifacts; the Markdown source is preserved.
- `_claude_memory.md` — private session notes.

## Uncertain inclusion decisions

- **`references/Gladstone & Brashears — Error Correction Mechanisms M2M.pdf`** — companion paper. Confirm preprint-redistribution rights before public upload. If unsure, remove and replace with a citation in the README.
- **`submission_materials/`** — includes submission prose (cover letter, blinded manuscript). Decide whether to keep these in the public repo (some authors keep the blinded manuscript for transparency; others reserve it for the journal).
- **`data/m2m_mutation_177*.csv`** — bulk results from earlier runs. Are these still the canonical results, or do `m2m_single_20260402_*.csv` supersede them? Confirm before final upload.

## Outstanding items before upload

- Add a `LICENSE` (MIT or CC-BY-4.0).
- Add a `CITATION.cff` once authorship/citation form is finalized.
- Add a `requirements.txt` / environment file if a Python analysis path will be advertised (currently no Python pipeline is included — only HTML simulations and result CSVs).
- Verify the companion-paper PDF may be redistributed.
