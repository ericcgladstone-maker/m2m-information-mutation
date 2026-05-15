# Handoff Note — M2M Information Mutation
**For:** Next Claude Code session
**Date written:** 2026-05-07 (Session 23 update)
**Status:** V15 is the canonical DOCX (table-rendering backport applied to the unchanged V14 content). Social Networks submission package fully staged at `submission/social_networks/`. Awaiting Eric's placeholder fills (corresponding email/phone, repository/DOI, cover-letter date, optional acknowledgements) and then submission.

---

## What You Need to Know

This is a simulation study of information mutation in machine-to-machine (LLM) networks. Six topologies, seven seeds, 420 chains, 5,880 transmission events. Machine coders only — **no human coders in this study** (the Brashears & Gladstone 2016 work used human coders; this one does not).

The authority framing is decomposed into four constructs that must be kept separate: **capability placement** (single structurally consequential node), **capability asymmetry** (parallel input chains feeding a synthesis node), **capability disclosure** (source-labeling), and **authority-like adoption** (the empirical incorporation outcome). "Machine authority" is an umbrella term only — never used as a demonstrated phenomenon.

---

## Current State

**Canonical manuscript:** `manuscript/M2M Information Mutation.md` (always edit this; rebuild DOCX from it).
**Current canonical DOCX:** `manuscript/M2M Information Mutation V15.docx` (~253 KB, built 2026-05-07 via `dev/build_docx_mac.py`; 4 docx tables + embedded Figure 1; identical statistical content to V14).
**Prior DOCX:** V14 retained as `M2M Information Mutation V14.docx` and as the explicit `M2M Information Mutation V14 (legacy table render).docx` backup. V8–V13 also preserved.
**Reproducibility script for Appendix A:** `dev/mixed_effects_robustness.py` (runs in ~30 seconds; six models).
**Figure:** `manuscript/figure_1_topology_error_profile.png` — per-topology error profile (drift, divergence, fabrication). Also staged at `submission/social_networks/figures/Figure_1.png`.
**Primary dataset:** `data/m2m_mutation_1775269632888.csv` — 5,880 rows, 420 chains, 12 conditions, 7 seeds, 5 lineages, hops 1–11.
**Verification script:** `dev/final_audit.py` — run from `/tmp` (working dir has spaces; script uses relative paths). PASSes with 0 discrepancies. Not re-run in Session 23 because the MD didn't change.

**Build wrappers (persistent in `dev/`):**
- `dev/build_docx_mac.py` — canonical builder (e.g. `python3 dev/build_docx_mac.py --out V<n>`).
- `dev/build_blinded_docx.py` — blinded builder for the *Social Networks* package (handles the no-author-block sentinel logic and clears DOCX core properties).
- `dev/build_aux_docx.py` — renders the auxiliary submission `.md` files into matching `.docx` files.

All three wrappers fix two latent rendering bugs in `archive/build_docx.py` that silently degraded every DOCX from V8 through V14: duplicate Tables 1/2 (Python-built + raw markdown) and leaked Tables 3/A.1 (raw markdown only).

---

## Social Networks submission package (Session 23)

Located at `submission/social_networks/`. See `submission/social_networks/README.md` for the file inventory, placeholder list, and pre-submission checklist.

Eight deliverables, each in `.md` (editable source) and `.docx` (Elsevier-portal upload):
1. Title Page
2. Blinded Manuscript (DOCX has 4 real tables + embedded Figure 1 + cleared core properties)
3. Highlights (5 bullets, all ≤85 chars)
4. Declaration of Competing Interests (none)
5. CRediT Author Statement
6. Declaration of Generative AI use (broader version: research + writing)
7. Data Availability Statement (deposit-at-publication)
8. Cover Letter

Plus `figures/Figure_1.png` for separate upload.

**Open placeholders Eric must fill:**
- Corresponding author email + phone (Title Page; email also referenced in Cover Letter)
- Cover letter date
- Repository name + DOI/URL for the data deposit (in DAS standalone AND inside the blinded manuscript)
- Acknowledgements section (or delete if none)

**Anonymization done in Session 23:** abstract replaced (≤100 words), keywords reduced to 6, sampling/representation/generalizability paragraph added at the top of Limitations, "Gladstone's (2016) dissertation" softened. All B&G self-citations remain in third-person form per Elsevier's double-blind guidance.

---

## Session 22 (2026-05-06): V14 Final Verification

User requested comprehensive verification of replicability, transparency, accuracy, and absence of hallucinations/fabrications before settling on V14. All four domains confirmed clean. Detail in Session 22 dev log entry; summary:

- **Data replicability:** raw CSV present (5,880 rows); simulation HTML regenerates end-to-end given API key; sibling pilot CSVs retained.
- **Accessibility / transparency:** canonical MD, two analysis scripts, full methods/prompts/limitations disclosure.
- **Analytical accuracy:** `final_audit.py` 11th pass = 0 discrepancies; all 19 Appendix A statistics verified against `mixed_effects_robustness.py` output.
- **Hallucinations / fabrications:** none detected. Every number traces to data via one of the two scripts; every methods claim about the simulation prompt traces to `simulations/m2m_v2.html` line 922; illustrative examples trace to specific CSV rows; no manufactured citations.

**Honest disclosures already in the manuscript** (these are accurate transparency, not deficiencies): H1 partially supported; H5 single-stimulus exploratory; LLM-coder within-instrument inference; capability effects don't survive chain-level terminal collapse; mediator for capability placement is inferred not directly tested.

V14 verified submission-ready.

## What Changed in Session 21 (2026-05-06): V14

User reviewed V13, confirmed all four tables clean, but flagged one Table A1 cell (Terminal hallucination row) where the V11-vintage interpretive language remained. Softened to: "Capability effects are not retained in the single terminal-observation model; topology remains robust." The fuller interpretive sentence stays in the substantive-read paragraph below the table, where framing-as-interpretation is appropriate.

Statistical content unchanged. final_audit.py = 0 discrepancies (tenth clean pass). V14 DOCX built.

## What Changed in Session 20 (2026-05-06): V13

User's V12 review described V12 as "submission-close" and flagged three small final-polish items. Implemented all three; one verification item confirmed (Table 2 already correct).

- **Abstract: "type of error" → "type of mutation"** — taxonomy discipline consistency.
- **Keywords: "machine authority" → "capability configuration"** — umbrella keyword now matches the manuscript's actual organizing construct.
- **Machine Authority section softened:** "In a directed hierarchy, capability typically descends with position" → "In a *capability-ordered* directed hierarchy—the manipulated condition tested here—capability descends with position by design... hierarchies are not inherently capability-ordered." Closes a residual implication that the topology entails capability stratification.
- **Table 2 verification:** confirmed already in V12 capability-configuration vocabulary; no change needed.
- **LLM coding limitation:** user said "this is enough for this version"; no action. Future work direction noted.

Statistical content unchanged. final_audit.py re-run = 0 discrepancies (ninth clean pass).

## What Changed in Session 19 (2026-05-06): V12

User reviewed V11 and proposed five targeted refinements to the mixed-effects appendix and surrounding language. Implemented four; the fifth (Table 2 H3/H4 harmonization) was already complete in V11 and confirmed.

- **Seed-as-fixed-effect note added** to Appendix A Specification paragraph, explicitly framing it as a design choice rather than an omission.
- **"under any specification we tried" → "under the robustness specifications reported here"** — removes the informal/exploratory connotation.
- **Softened the chain-level capability null explanation** to "This suggests that capability placement is more visible in node-level trajectories than in single terminal summaries" — keeps the mechanism without overexplaining.
- **Updated appendix substantive read** to "capability-configuration effects on hallucination severity survive at the node level, driven primarily by placement rather than disclosure" — consistent with V11's four-construct framework.
- **Downstream Limitations sentence harmonized** to use the same capability-configuration / placement-vs-disclosure phrasing.
- **Table 2 verification:** user thought H3/H4 still had legacy authority labels but they were already harmonized in V11; no change needed.

Statistical content unchanged. final_audit.py re-run = 0 discrepancies (eighth clean pass).

## What Changed in Session 18 (2026-05-06): V11

User reviewed V10 and proposed (a) four small terminology fixes and (b) a mixed-effects robustness appendix. Implemented all of them.

- **Terminology fixes:** contribution sentence now says "capability-configuration effects"; Synthesis-Structures network-selection prose now says "capability asymmetry" (not placement); the hub passage now reads "one of the capability-configuration constructs we develop below" (fixing both count and category). "Authority-like adoption" is reserved for theoretical-construct contexts; "higher-capability content incorporation rate" is the empirical/results term.
- **Appendix A — Mixed-Effects Robustness Analyses.** Six models. Random-intercept-only specifications; random slopes attempted but unstable, dropped per fallback guidance. Models: (1) evol_fidelity LMM, (2) completeness LMM, (3a) any-hallucination GEE logistic, (3b) positive hallucination severity LMM (log1p), (4) chain-level terminal models (n=420), (5) cell-level XL-SD OLS (n=196). Table A1 summarizes outcomes × topology effect retained × capability effect retained × notes.
- **Substantive read of the appendix:** All nine omnibus topology tests highly significant. Capability placement effects on hallucination severity survive at node level (H3 confirmed). Capability disclosure null survives (H4 confirmed). XL-SD architectural-not-capability survives (H7 confirmed). One honest finding to disclose: capability effects do not survive collapse to chain-level terminal outcomes (n=420 only). The manuscript explicitly notes this and explains it as compounding within-chain effects that get averaged out at the terminal-only summary.
- **Manuscript additions:** new paragraph in Analytic Strategy cross-referencing Appendix A; updated Limitations sentence about node-level inference now points to the appendix and confirms the substantive pattern is unchanged.

Statistical content unchanged. `final_audit.py` still reports 0 discrepancies — seventh clean audit pass.

See Session 18 entry in `M2M Information Mutation — Dev Log.md` for the full record.

## What Changed in Session 17 (2026-05-06): V10

User reviewed V9 and shared a focused punch list — five status-material refinements plus four findings-side tightenings. We implemented all of them.

- **Abstract:** "capability configuration" replaces "capability-linked authority-like mechanisms" in the first mention. Cleaner.
- **Hierarchy:** distinguished *structurally* tiered (always present) from *capability-ordered* (only in the manipulated high-capability condition).
- **Capability placement vs capability asymmetry:** capability *placement* is now reserved for hub/hierarchy (single structurally consequential node); capability *asymmetry* is the term for lattice/bilattice (asymmetry across parallel input chains). H3 renamed "Capability Placement and Asymmetry, and Fabrication" with explicit prediction that placement effects exceed asymmetry effects. The framework now lists four constructs: placement, asymmetry, disclosure, authority-like adoption.
- **DV renamed:** "Authority-like adoption rate" → "Higher-capability content incorporation rate." More measurement-faithful; "authority-like adoption" retained only as the theoretical mechanism construct.
- **Mediator hedge:** Discussion's "reduces fabrication because outputs are better" softened to "consistent with the interpretation that upgraded nodes generate more stable downstream inputs." Mediator was inferred, not directly tested — now flagged.
- **Definitions:** crisp one-liners for drift, divergence, fabrication added at start of Hypotheses; used consistently throughout.
- **Mutation vs error:** "mutation types" / "failure modes" used for the taxonomic claim; "error" reserved for impairment-bearing claims. Drift in particular can include benign paraphrase, so it doesn't always behave as error.
- **Hub bottleneck-tradeoff paragraph:** new paragraph in Discussion frames hub's near-zero divergence and concentrated bias as a single mechanism — bottleneck reduces variance at the cost of concentrating whatever the hub carries. Lower variance ≠ lower error; it's *systematic* rather than *idiosyncratic* mutation.
- **Table 3:** per-topology mapping of architecture → dominant mutation risk → mechanism → audit remedy. Six rows. Closing note about fact-retention audits being insufficient.

Statistical content unchanged. `final_audit.py` still reports 0 discrepancies — sixth clean audit pass.

See Session 17 entry in `M2M Information Mutation — Dev Log.md` for the full record.

## What Changed in Session 16 (2026-05-06): V9

User shared a 26-point critique of V8. Constraints: no human coders, no new computational experiments. We executed 17 ordered passes over the canonical MD. Highlights:

- **Authority decomposed.** Replaced broad "machine authority" framing with capability placement / capability disclosure / authority-like adoption. SCT reframed as bounded analogy. H3 renamed "Capability Placement and Fabrication" and reinterpreted as a placement effect (not a demonstration of status-like deference). H4 renamed "Capability Disclosure" and reinterpreted as a null *disclosure* effect (not a confirmation of authority). H7 reframed as "architectural property, not local capability."
- **Two-mechanism fabrication.** Added subsection distinguishing synthesis fabrication (multi-input reconciliation) from sequential reconstruction fabrication (cumulative single-input drift). H1 revised to predict both mechanisms; H1 results revised to "partially supported" — omnibus topology effect confirmed, original ordering claim qualified.
- **Factual retention elevated.** Moved from a footnote-style note in Hypotheses to a dedicated Results subsection. Defined epistemic-status fabrication as a subtype of hallucination.
- **Bartlett bounded.** Single-stimulus caveat added in both Results and Discussion. Schema analogy made explicit ("we use schema analogically rather than literally").
- **Audit Implications.** Replaced Design Implications with conditional audit principles per topology.
- **Mutation ≠ task success paragraph added** clarifying normative stance.
- **Abstract rewritten** with two-mechanism finding, capability placement framing, softened firstness/establishment claims.
- **Hallucination scoring detail.** Added a full DV section grounded in the actual Sonnet 4.6 prompt (sourced from `simulations/m2m_v2.html`, line 922). Specifies comparison-to-seed (not predecessor/chain history), paraphrase exclusion, causal/temporal addition inclusion, no-examples-in-prompt.
- **Independent-units clarification.** Made explicit that the 5,880 figure is descriptive node-level n; the inferential unit is the chain (n=420), with XL-SD analyzed at the cell level.
- **New Figure 1.** Per-topology error profile across drift, divergence, and fabrication, generated from existing data and embedded in Results after Table 1.
- **Limitations rewritten.** Model-family dependence, narrowed authority operationalization, within-instrument-coding caveat, single-Bartlett caveat, statistical-inference-at-node-level caveat. Future Work paragraph added on stronger SCT-style designs.
- **Polish.** Topology labels tightened ("ring with shortcuts" not just "ring"); architectural bundle language added in Design; intro overclaims softened; "first" claims narrowed with "to our knowledge" + explicit caveat; hybrid taxonomy compressed; examples relabeled "Measurement Examples."

Statistical content unchanged. `final_audit.py` still reports 0 discrepancies.

See Session 16 entry in `M2M Information Mutation — Dev Log.md` for the full record.

---

## Immediate Next Steps (likely)

1. **Eric fills the open placeholders** (corresponding email/phone, repository/DOI, cover-letter date, optional acknowledgements) and submits to *Social Networks*. See `submission/social_networks/README.md` for the full list and pre-submission checklist.
2. **Co-author (Brashears) review of CRediT split** before submission.
3. **Editorial Manager upload.** Each file maps to a specific item type — see the README inventory table.
4. **After acceptance / before publication: deposit data + scripts** (CSV, simulation HTML, audit script, robustness script) at the chosen repository and update DAS placeholders.

---

## Replicability Posture

If a reviewer or co-author asks whether every number in the manuscript traces to raw data:

- **Yes.** `final_audit.py` covers every reported statistic. Eleven clean audit passes through V14; V15 has identical content (MD untouched in Session 23).
- **Sentence-level provenance:** every transmission event is one row in the CSV with `sentence`, `topology`, `authority`, `seed_idx`, `lineage`, `chain_id`, `hop`, and all DVs.
- **Simulation reproducibility:** `simulations/m2m_v2.html` regenerates data end-to-end from an Anthropic API key.
- **Mixed-effects robustness:** `dev/mixed_effects_robustness.py` reproduces all 19 statistics in Table A.1.
- **B&G 2016 baseline data:** `archive/original_data_clean.csv` (4,089 human-rated pairs) is the theoretical anchor only, not a validation target for this study.

---

## Important Cautions

- **Do NOT reintroduce the 300-pair human-coder validation framing.** Removed in V8, still removed through V15. Within-instrument framing is the operative defense; absolute fidelity claims are explicitly limited.
- **Do NOT treat capability disclosure as equivalent to status signaling demonstrated.** The H4 null is evidence *against* status-like deference under the tested conditions, not confirmation of authority.
- **`archive/build_docx.py` is Windows-pathed AND has two latent rendering bugs** (duplicate Tables 1/2; leaked Tables 3/A.1 as raw markdown). Do NOT call it directly on Mac. Always use `dev/build_docx_mac.py` (canonical), `dev/build_blinded_docx.py` (blinded), or `dev/build_aux_docx.py` (auxiliaries).
- **Figure 1 embedding requires post-processing.** The build wrappers detect `![Figure 1...](path)` markdown, replace with a sentinel, build the doc, then locate the sentinel paragraph and insert the PNG via python-docx.
- **Blinded MDs need a sentinel author block.** When the author block is removed, the archive builder's `i <= 5` branch misclassifies the abstract body as centered author info. `dev/build_blinded_docx.py` already handles this (inserts five sentinel paragraphs after the title and removes them post-build).
- **Canonical file rule:** always edit `manuscript/M2M Information Mutation.md`, then rebuild the DOCX. Never edit the DOCX directly. For the *Social Networks* submission, edit `.md` files in `submission/social_networks/` and rebuild via the dev/ wrappers.

---

## Key Files

| File | Purpose |
|---|---|
| `manuscript/M2M Information Mutation.md` | Canonical manuscript — sole source of truth |
| `manuscript/M2M Information Mutation V15.docx` | Current canonical DOCX (~253 KB; 4 docx tables + embedded Figure 1; built 2026-05-07 via `dev/build_docx_mac.py`) |
| `manuscript/M2M Information Mutation V14.docx` and earlier | Prior DOCX history (V8–V14) — note these have the table-rendering defect (duplicate Tables 1/2 + leaked Tables 3/A.1) that V15 fixes |
| `manuscript/M2M Information Mutation V14 (legacy table render).docx` | Snapshot of V14 made before discovering the rendering issue |
| `manuscript/figure_1_topology_error_profile.png` | Per-topology error profile (300 dpi PNG) |
| `submission/social_networks/` | Social Networks submission package (8 files in MD + DOCX, plus figures/ and a README) |
| `dev/build_docx_mac.py` | Mac wrapper for canonical DOCX builds (use this, not archive/build_docx.py directly) |
| `dev/build_blinded_docx.py` | Mac wrapper for blinded submission DOCX (sentinel author-block + cleared core properties) |
| `dev/build_aux_docx.py` | Renders auxiliary submission `.md` files into matching `.docx` |
| `dev/mixed_effects_robustness.py` | Reproducibility script for Appendix A — six robustness models |
| `dev/final_audit.py` | Full verification script (0 discrepancies through V14; V15 content unchanged) |
| `dev/M2M Information Mutation — Dev Log.md` | Complete session history |
| `data/m2m_mutation_1775269632888.csv` | Primary 5,880-row dataset |
| `archive/build_docx.py` | Underlying DOCX builder — Windows-pathed and has two latent rendering bugs; do NOT call directly on Mac |
| `archive/original_data_clean.csv` | B&G 2016 human-rated pairs — reference, not validation target |
| `simulations/m2m_v2.html` | Simulation tool used for final run; source of the canonical hallucination prompt |
| `references/Gladstone & Brashears — Error Correction Mechanisms M2M.pdf` | The 2016 paper |

---

*Full history in `M2M Information Mutation — Dev Log.md`. Ask Eric if anything is unclear.*
