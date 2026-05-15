# M2M Information Mutation Simulation
**Version:** V1  
**File:** `m2m_v1.html`  
**Paper:** Gladstone & Brashears (manuscript) — *Machine-to-Machine Information Mutation*

---

## Overview

A browser-based simulation of information mutation across machine-to-machine (M2M) networks. Messages pass through LLM nodes arranged in six network topologies. At each node, messages are either faithfully relayed (passive) or actively paraphrased (active mediation). The simulation scores fidelity, factual retention, completeness, drift, and hallucination at each hop using a separate coder model.

Designed to replicate and extend Brashears & Gladstone (2016), testing whether LLM transmission networks produce structural parallels to human serial reproduction.

---

## Requirements

- Modern browser (Chrome recommended)
- Anthropic API key (`sk-ant-...`)
- Internet connection (calls Anthropic API directly from browser)

---

## Setup

1. Open `m2m_v1.html` in a browser
2. Enter your Anthropic API key in the **API key** field (left panel)
3. Configure models, conditions, and seeds
4. Run a single trial or a full sweep

No installation, build step, or server required.

---

## Models

| Role | Default | Purpose |
|------|---------|---------|
| Baseline (transmission) | Claude Haiku 4.5 | All standard-authority nodes |
| High-authority | Claude Sonnet 4.6 | High-authority nodes (hub, hierarchy upper tier, Chain A in lattice/bilattice) |
| Coder | Claude Sonnet 4.6 | Scores fidelity and all DVs; runs separately from transmission |

Models are configurable via dropdowns in the Setup panel.

---

## Network Topologies

All topologies are equalized to **11 total nodes**.

| Topology | Structure | Authority |
|----------|-----------|-----------|
| **Linear chain** | 11 sequential nodes | None (no authority manipulation) |
| **Hub-and-spoke** | Hub → 10 parallel spokes | Positional: hub model is standard or high-capability |
| **Lattice** | 2 parallel chains of 5 → synthesis → 5 output nodes | Competitive: standard / implicit / declared |
| **Bidirectional lattice** | Same as lattice + back-communication rounds before synthesis | Competitive: standard / implicit / declared |
| **Directed hierarchy** | 3 upper → 5 mid (synthesis) → 3 lower | Positional: upper-tier model is standard or high-capability |
| **Ring with shortcuts** | 3 ring segments with shortcut bypasses converging at 3 junction nodes | None |

---

## Machine Authority Conditions

Authority is manipulated differently by topology class.

### Class I — Sequential structures (hub-and-spoke)
| Condition | Model at hub |
|-----------|-------------|
| `standard` | Baseline (Haiku) |
| `high` | High-authority (Sonnet) |

### Class II — Synthesis structures (lattice, bilattice)
| Condition | Chain A model | Chain B model | Signal to synthesis node? |
|-----------|--------------|--------------|--------------------------|
| `standard` | Baseline | Baseline | No |
| `implicit` | High-authority | Baseline | No |
| `declared` | High-authority | Baseline | Yes — "Note: Version A was processed by a higher-capability system." |

**Implicit** tests whether quality-based deference emerges without provenance metadata (ecologically valid for real M2M systems where text arrives without source labels).  
**Declared** tests whether an explicit capability signal amplifies deference beyond quality alone.  
The synthesis node always uses the baseline model in both conditions — only the inputs differ.

### Class III — Hierarchical structures (directed hierarchy)
| Condition | Upper-tier model |
|-----------|-----------------|
| `standard` | Baseline (Haiku) |
| `high` | High-authority (Sonnet) |

### Ring with shortcuts
No authority manipulation. Included as a structural control for path-length heterogeneity without formal authority gradient.

---

## Node Types

| Type | Behavior | Temperature |
|------|----------|-------------|
| **Passive relay** | Reproduce message as accurately as possible | 0.0 |
| **Active mediation** | Read and rewrite to capture meaning | Configurable (default 0.7) |

---

## Message Formats

| Format | Description |
|--------|-------------|
| **English** | Standard written English (low entropy) |
| **Text pidgin** | Abbreviations, numbers for words, omit vowels (high entropy) |

---

## Dependent Variables

Scored by a separate coder model (Sonnet) using LLM-as-judge prompts. All scores 0–100.

| DV | Description |
|----|-------------|
| **Consecutive fidelity** | Semantic similarity of each node's output to its direct input |
| **Evolutionary fidelity** | Semantic similarity of each node's output to the original seed |
| **Factual retention** | Proportion of specific factual details (numbers, dates, thresholds) preserved from seed |
| **Information completeness** | Proportion of semantic content from seed preserved in transmission |
| **Register drift** | Shift toward more formal (100) or informal (0) register relative to seed; 50 = no change |
| **Specificity drift** | Shift toward more specific (100) or more general (0) relative to seed; 50 = no change |
| **Hallucination** | Degree to which transmission contains claims absent from the original seed |

### Seed 7 only (War of the Ghosts — Bartlett bridge)
| DV | Description |
|----|-------------|
| **Leveling** | Shortening / omission of detail relative to original |
| **Assimilation** | Replacement of anomalous elements with schema-consistent content |
| **Sharpening** | Imposition of causal/temporal coherence not present in original |
| **Word count** | Computed directly |

---

## Seed Sentences

Seven seeds, each targeting a different organizational content category:

| # | Category | Key features |
|---|----------|-------------|
| 1 | Supply chain audit | Numerical specificity, thresholds, cost estimates |
| 2 | Ethics review | Normative/regulatory language, procedural requirements |
| 3 | Research incident | Narrative structure, temporal sequence, causal ambiguity |
| 4 | Procedural protocol | Sequential steps, conditional logic, compliance framing |
| 5 | Epidemiological report | Statistical data, causal inference, institutional attribution |
| 6 | AI governance policy | Abstract policy language, justification-heavy framing |
| 7 | War of the Ghosts | Bartlett (1932) folk tale — exploratory Bartlett bridge |

Seeds 1–6 are the primary study corpus. Seed 7 is analyzed separately as an exploratory extension.

Load all seven via **Load defaults** in the Sweep panel.

---

## Running the Simulation

### Single trial
1. Select **Setup** tab (left panel)
2. Configure topology, node type, format, and authority
3. Enter or edit the seed sentence
4. Click **▶ Run**
5. Results display in the **Chain view** panel with per-hop scores

### Sweep
1. Select **Sweep** tab (left panel)
2. Check desired topologies, node types, formats, and authority conditions
3. Set replications per cell (default: 10, per Brashears & Gladstone 2016)
4. Load seed sentences
5. Click **▶ Run sweep**
6. Progress and condition-level summaries display in **Sweep results**
7. Export full data via **⬇ CSV**

**Stop** halts the sweep after the current chain completes. Partial data remains exportable.

---

## CSV Output

One row per node per chain. Key columns:

| Column | Description |
|--------|-------------|
| `run_id` | Unique run identifier |
| `seed` | Seed sentence text |
| `topology` | Topology name |
| `node_type` | `passive` or `active` |
| `format` | `english` or `pidgin` |
| `authority` | `standard`, `high`, `implicit`, or `declared` |
| `hop` | Node position in chain (0 = seed) |
| `node_label` | Human-readable node name |
| `chain_id` | Sub-chain identifier (e.g., `A`, `B`, `main`, `spoke3`) |
| `is_authority` | Whether this node used the high-authority model |
| `sentence` | Text output at this node |
| `consec_fidelity` | Consecutive fidelity score |
| `evol_fidelity` | Evolutionary fidelity score |
| `factual_retention` | Factual retention score |
| `completeness` | Information completeness score |
| `register` | Register drift score |
| `specificity` | Specificity drift score |
| `hallucination` | Hallucination score |
| `leveling` | (Seed 7 only) Leveling score |
| `assimilation` | (Seed 7 only) Assimilation score |
| `sharpening` | (Seed 7 only) Sharpening score |
| `word_count` | (Seed 7 only) Word count of transmission |

---

## API and Rate Limiting

- Calls go directly from the browser to `api.anthropic.com`
- Exponential backoff on overload (HTTP 529): configurable base delay (default 8s), multiplied by attempt number
- Failed calls (overload retries) are not counted in the API call counter

---

## Design Summary (per manuscript)

| Class | Topologies | Factors | Conditions/seed |
|-------|-----------|---------|----------------|
| Class I | Linear chain, Hub-and-spoke | Topology × node type × format (+hub authority) | 8 base + 4 hub authority = 12 hub-and-spoke |
| Class II | Lattice, Bidirectional lattice | Topology × node type × authority | 12 |
| Class III | Directed hierarchy, Ring w/ shortcuts | Topology × node type (+hierarchy authority) | 10 |

10 replications per cell per seed sentence.

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| V1 | 2026-03 | Initial build: six topologies, seven seeds, eight DVs |
| V1 (updated) | 2026-04-02 | Split `high` authority into `implicit` / `declared` for Class II (lattice, bilattice); updated sweep condition builder to route topologies to correct authority sets |

---

*For paper context, theoretical framing, and hypothesis details, see `M2M Information Mutation.md`.*
