# Social Networks submission package

> **Historical.** These are the materials for an earlier submission of a prior version of this study to *Social Networks*. The affiliations and title reflect that submission. The current version is *Information mutation across implemented AI-agent communication architectures*, revise and resubmit at *Scientific Reports*.

**Manuscript:** "The Modern Telephone: Information Mutation in Machine-to-Machine Communication Networks"
**Authors:** Eric Gladstone (U. Kentucky) & Matthew E. Brashears (U. South Carolina)
**Target journal:** *Social Networks* (Elsevier; double-anonymized review)
**Built:** 2026-05-07 from canonical `manuscript/M2M Information Mutation.md`

## File inventory

| # | File | What it is | Submit as |
|---|------|------------|-----------|
| 01 | `01_Title_Page.md` / `.docx` | Title page (author identifying info, corresponding-author block, funding, competing-interests, CRediT) | Title Page |
| 02 | `02_Blinded_Manuscript.md` / `.docx` | Anonymized manuscript with ≤100-word abstract, 6 keywords, embedded Figure 1, Tables 1–3 + Table A.1, Data Availability + Generative AI declaration appended | Manuscript (blinded) |
| 03 | `03_Highlights.md` / `.docx` | 5 highlights, each ≤85 chars | Highlights |
| 04 | `04_Declaration_of_Competing_Interests.md` / `.docx` | None declared | Declaration of Interest |
| 05 | `05_CRediT_Author_Statement.md` / `.docx` | CRediT split (Gladstone primary; Brashears conceptualization / methodology / supervision / writing) | CRediT |
| 06 | `06_Declaration_of_Generative_AI.md` / `.docx` | Broader version: AI used for both research design and manuscript prep | Generative AI Declaration |
| 07 | `07_Data_Availability_Statement.md` / `.docx` | Deposit-at-publication version | Data Statement |
| 08 | `08_Cover_Letter.md` / `.docx` | Cover letter to Editors | Cover Letter |
|    | `figures/Figure_1.png` | Per-topology error profile (300 dpi) | Figure (separate upload) |

The DOCX versions are byte-for-byte regenerable from the matching `.md` source by running `python3 dev/build_aux_docx.py` (auxiliaries) or `python3 dev/build_blinded_docx.py` (the blinded manuscript). Edit the `.md` and rebuild rather than editing the `.docx` directly.

## Placeholders to fill before submission

These remain unresolved in the package and need Eric's input:

- [ ] **Corresponding author email** — `01_Title_Page.md` line containing `[INSERT CORRESPONDING EMAIL]`; same placeholder in `08_Cover_Letter.md`.
- [ ] **Corresponding author phone** — `01_Title_Page.md` line containing `[INSERT PHONE OR OMIT]`. If you don't want to provide one, delete the line.
- [ ] **Acknowledgements** — `01_Title_Page.md`. If none, delete the entire `## Acknowledgements` section.
- [ ] **Cover letter date** — `08_Cover_Letter.md` line `[Date]`.
- [ ] **Data deposit repository + DOI/URL** — appears twice: `07_Data_Availability_Statement.md` and inside the blinded manuscript (`02_Blinded_Manuscript.md`, in the Data Availability Statement section before References). Both need `[REPOSITORY]` and `[DOI OR URL]` filled. If the deposit isn't set up yet, the alternative phrasing is "available from the corresponding author upon reasonable request and will be deposited in a public repository prior to publication."

After editing any `.md`, re-run the matching builder to regenerate the DOCX:

```
python3 dev/build_blinded_docx.py        # rebuilds 02_Blinded_Manuscript.docx
python3 dev/build_aux_docx.py            # rebuilds all auxiliaries
```

## Pre-submission checklist

- [ ] Open every DOCX and visually inspect: tables render as actual tables, Figure 1 is embedded, no raw markdown pipes, no leftover `[INSERT ...]` placeholders.
- [ ] Confirm `02_Blinded_Manuscript.docx` has no author-identifying content. The DOCX core properties were cleared on build; re-check after any rebuild.
- [ ] Save copies of the DOCX files locally before uploading (Elsevier's portal sometimes asks for re-upload during revision).
- [ ] In Elsevier Editorial Manager, upload each file under the matching item type (column 4 of the inventory table above).
- [ ] Confirm CRediT split with Brashears before submission; you accepted the draft as-is, but a co-author check is standard practice.

## Anonymization summary (already applied)

The blinded manuscript has been scrubbed of:

- Author block (names + affiliations)
- Corresponding-author footer
- Acknowledgements
- The one possessive self-citation ("Gladstone's (2016) dissertation" → "the dissertation work of Gladstone (2016)")
- DOCX core properties (author / title / subject / keywords / comments / category)

Brashears & Gladstone (2016) and Gladstone (2016) citations remain in third-person form per Elsevier's double-blind guidance ("references may remain in the blinded manuscript, including self-citations"). The Cornell University reference in the dissertation entry stays for the same reason.

## Source-of-truth pointers

- Canonical manuscript content: `manuscript/M2M Information Mutation.md`
- Canonical DOCX (with author info): `manuscript/M2M Information Mutation V15.docx`
- Build wrappers: `dev/build_docx_mac.py` (canonical), `dev/build_blinded_docx.py` (blinded), `dev/build_aux_docx.py` (auxiliaries)
- Audit script: `dev/final_audit.py` (run from `/tmp`; 0 discrepancies)
- Mixed-effects robustness: `dev/mixed_effects_robustness.py` (Appendix A)
