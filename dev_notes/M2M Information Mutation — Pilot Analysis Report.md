# M2M Information Mutation Pilot — Comprehensive Statistical Analysis Report

**Generated:** 2026-04-02  
**Data file:** `m2m_mutation_1775269632888.csv`  
**Analysis scope:** Full pilot dataset, all 12 conditions, 7 seeds, active mediation, English only

---

## Dataset Overview

| Attribute | Value |
|---|---|
| Total observations | 5,880 |
| Topologies | 6 (bilattice, hierarchy, hub, lattice, linear, ring) |
| Conditions (topology × authority) | 12 |
| Seeds | 7 (seed_idx 1–6 = organizational; seed_idx 7 = Bartlett / War of the Ghosts) |
| Lineages (reps per condition × seed) | 5 |
| Hops per chain | 1–11 (max 11 per design) |

**Condition cell sizes:** Hub and hierarchy have 385 observations each (standard + high × 35 runs × 11 hops); lattice has 560 per authority level (16 nodes per run × 35 runs); bilattice has 630 per level (18 nodes/run); linear and ring have 385 each (single authority).

**Structural note on topologies:**
- **Linear / Ring / Hub / Hierarchy:** 11 nodes per run (hub branches across 11 spoke-chains per run)
- **Lattice:** 16 nodes per run (2 parallel chains A/B of 5 hops each → merge into main chain hops 6–11)
- **Bilattice:** 18 nodes per run (2 parallel chains A/B of 5.5 hops each → merge into main chain hops 6–11)
- **Hierarchy:** 11 nodes per run spread across 3 tiers (upper1-3: hops 1-3, mid1-5: hops 4-8, lower1-3: hops 9-11)

**XL-SD note:** Hierarchy is excluded from main-chain XL-SD because it has no `chain_id = 'main'`; hierarchy XL-SD is reported separately using the deepest terminal chain (lower3, hop 11).

---

## Statistical Approach Notes

**Why Kruskal-Wallis instead of ANOVA:** All four DVs fail the Shapiro-Wilk normality test severely (W range 0.39–0.82, all p < 10⁻²²). Hallucination is particularly pathological: zero-inflated (27% zeros), right-skewed (mean 10.2, SD 24.8, max 100). ANOVA's normality assumption is not satisfied; Kruskal-Wallis is the appropriate non-parametric analog for independent groups.

**Why not beta regression for hallucination here:** Beta regression requires strictly (0,1) values; hallucination scores are integer 0–100 with mass at both endpoints. Zero-inflated models (hurdle or two-part) would be the formal solution for a confirmatory analysis, but are not run here as the pilot goal is directional characterization rather than precise parameter estimation.

**Effect sizes reported:**
- Kruskal-Wallis: eta-squared (η² = (H − k + 1) / (N − k)), interpretive benchmarks: small ≈ .01, medium ≈ .06, large ≈ .14
- Pairwise Mann-Whitney: rank-biserial correlation r (equivalent to |r| ≈ .1 small, .3 medium, .5 large)

**Multiple comparisons:** Bonferroni correction applied to post-hoc topology pairwise comparisons (15 pairs, α = .0033). Authority comparisons within topology use Bonferroni for three-level conditions (3 pairs, α = .0167).

**Note on clustering:** Observations within the same run/lineage are not independent (each hop depends on the prior node's output). The analyses below treat nodes as the unit of analysis, which inflates degrees of freedom. Effects that survive should be treated as directional; confirmatory analyses should use run- or lineage-level aggregates as the unit, or mixed models with random effects for run.

---

## 1. Hallucination Distribution Analysis

Hallucination is zero-inflated and heavily right-skewed. Overall: M = 10.2, Mdn = 3.0, SD = 24.8, IQR = 5.0; 27.0% of nodes score exactly 0, 66.2% score 1–50, and 6.8% score >50.

**Table 1. Hallucination Distribution by Condition**

| Topology | Authority | n | Mean | Median | SD | % Zero | % >0 | % >50 |
|---|---|---|---|---|---|---|---|---|
| bilattice | declared | 630 | 11.7 | 3.0 | 26.2 | 23.0% | 77.0% | 7.8% |
| bilattice | implicit | 630 | 12.5 | 3.0 | 26.6 | 22.5% | 77.5% | 8.1% |
| bilattice | standard | 630 | 15.7 | 3.0 | 30.8 | 14.4% | 85.6% | 11.4% |
| hierarchy | high | 385 | 2.6 | 0.0 | 10.3 | 51.4% | 48.6% | 1.0% |
| hierarchy | standard | 385 | 5.2 | 2.0 | 17.2 | 36.4% | 63.6% | 3.1% |
| hub | high | 385 | 6.2 | 3.0 | 15.0 | 19.0% | 81.0% | 2.1% |
| hub | standard | 385 | 10.3 | 2.0 | 26.7 | 32.7% | 67.3% | 8.1% |
| lattice | declared | 560 | 8.3 | 3.0 | 21.2 | 31.6% | 68.4% | 4.6% |
| lattice | implicit | 560 | 7.2 | 3.0 | 19.9 | 30.4% | 69.6% | 4.1% |
| lattice | standard | 560 | 11.7 | 3.0 | 26.8 | 24.5% | 75.5% | 8.0% |
| linear | standard | 385 | 15.1 | 3.0 | 30.9 | 24.4% | 75.6% | 11.4% |
| ring | standard | 385 | 12.1 | 3.0 | 27.8 | 25.2% | 74.8% | 8.8% |

**Interpretation:** Hierarchy shows the most favorable hallucination profile — over half of all nodes score exactly zero under high authority, and the mean is 2.6. Linear and bilattice standard show the worst profiles (means ~15–16, ~11–14% of nodes scoring >50). The zero-inflation rate varies meaningfully across conditions (14–51%), suggesting the distribution shape itself is condition-sensitive. Standard deviations are uniformly large (10–31), consistent with a mixture distribution where most nodes produce low hallucination but a minority produce extreme values.

---

## 2. Descriptive Statistics by Condition

**Table 2a. Evolutionary Fidelity (evol_fidelity): node output vs. original seed**

| Topology | Authority | n | Mean | SD | Median |
|---|---|---|---|---|---|
| bilattice | declared | 630 | 94.93 | 4.94 | 97.0 |
| bilattice | implicit | 630 | 95.25 | 3.83 | 97.0 |
| bilattice | standard | 630 | 94.89 | 4.65 | 97.0 |
| hierarchy | high | 385 | 96.98 | 1.49 | 97.0 |
| hierarchy | standard | 385 | 96.86 | 0.76 | 97.0 |
| hub | high | 385 | 96.23 | 2.20 | 97.0 |
| hub | standard | 385 | 96.64 | 1.11 | 97.0 |
| lattice | declared | 560 | 95.98 | 3.24 | 97.0 |
| lattice | implicit | 560 | 96.26 | 2.74 | 97.0 |
| lattice | standard | 560 | 96.01 | 2.91 | 97.0 |
| linear | standard | 385 | 95.61 | 2.80 | 97.0 |
| ring | standard | 385 | 96.33 | 2.10 | 97.0 |

**Table 2b. Hallucination (see Table 1 for full distribution; mean/SD/median reproduced here)**

| Topology | Authority | n | Mean | SD | Median |
|---|---|---|---|---|---|
| bilattice | declared | 630 | 11.73 | 26.21 | 3.0 |
| bilattice | implicit | 630 | 12.52 | 26.59 | 3.0 |
| bilattice | standard | 630 | 15.72 | 30.83 | 3.0 |
| hierarchy | high | 385 | 2.59 | 10.32 | 0.0 |
| hierarchy | standard | 385 | 5.16 | 17.21 | 2.0 |
| hub | high | 385 | 6.21 | 14.99 | 3.0 |
| hub | standard | 385 | 10.33 | 26.73 | 2.0 |
| lattice | declared | 560 | 8.26 | 21.16 | 3.0 |
| lattice | implicit | 560 | 7.20 | 19.87 | 3.0 |
| lattice | standard | 560 | 11.66 | 26.75 | 3.0 |
| linear | standard | 385 | 15.09 | 30.90 | 3.0 |
| ring | standard | 385 | 12.08 | 27.78 | 3.0 |

**Table 2c. Factual Retention**

| Topology | Authority | n | Mean | SD | Median |
|---|---|---|---|---|---|
| bilattice | declared | 630 | 95.05 | 5.56 | 97.0 |
| bilattice | implicit | 630 | 96.04 | 4.23 | 97.0 |
| bilattice | standard | 630 | 95.43 | 3.83 | 95.0 |
| hierarchy | high | 385 | 97.22 | 2.74 | 97.0 |
| hierarchy | standard | 385 | 96.12 | 3.16 | 97.0 |
| hub | high | 385 | 96.79 | 3.70 | 97.0 |
| hub | standard | 385 | 95.83 | 3.31 | 95.0 |
| lattice | declared | 560 | 96.42 | 4.07 | 97.0 |
| lattice | implicit | 560 | 96.19 | 3.98 | 97.0 |
| lattice | standard | 560 | 95.84 | 3.56 | 97.0 |
| linear | standard | 385 | 95.57 | 4.36 | 97.0 |
| ring | standard | 385 | 95.80 | 3.66 | 97.0 |

**Table 2d. Completeness**

| Topology | Authority | n | Mean | SD | Median |
|---|---|---|---|---|---|
| bilattice | declared | 630 | 96.70 | 4.13 | 97.0 |
| bilattice | implicit | 630 | 97.13 | 3.39 | 98.0 |
| bilattice | standard | 630 | 96.44 | 4.49 | 97.0 |
| hierarchy | high | 385 | 98.57 | 1.18 | 99.0 |
| hierarchy | standard | 385 | 98.29 | 0.89 | 99.0 |
| hub | high | 385 | 97.82 | 1.94 | 99.0 |
| hub | standard | 385 | 97.97 | 0.97 | 98.0 |
| lattice | declared | 560 | 97.69 | 2.48 | 99.0 |
| lattice | implicit | 560 | 97.82 | 2.23 | 99.0 |
| lattice | standard | 560 | 97.33 | 2.81 | 97.5 |
| linear | standard | 385 | 97.61 | 1.74 | 98.0 |
| ring | standard | 385 | 97.64 | 1.48 | 97.0 |

**Overall pattern:** The median for evol_fidelity is 97 across nearly all conditions — this is a floor-effect concern. Most variation is driven by a minority of nodes that show meaningful degradation. Completeness and factual_retention show similar ceiling clustering. Hallucination shows genuine condition-level variation (means range 2.6–15.7). Hierarchy is consistently the best-performing topology on all DVs; bilattice standard is consistently the worst.

---

## 3. Topology Main Effect (Kruskal-Wallis)

**Table 3. Topology Main Effects (collapsed across authority, Kruskal-Wallis)**

| DV | H(5) | p | η² | Interpretation |
|---|---|---|---|---|
| evol_fidelity | 254.09 | < .001 | .042 | Small-medium effect |
| hallucination | 285.14 | < .001 | .048 | Small-medium effect |
| factual_retention | 35.70 | < .001 | .005 | Very small effect |
| completeness | 316.62 | < .001 | .053 | Small-medium effect |

All topology main effects are statistically significant. Effect sizes for evol_fidelity, hallucination, and completeness are in the small-medium range (η² = .04–.05). Factual retention shows only a trivial effect (η² = .005), suggesting this measure is less sensitive to topology variation in this pilot.

**Condition means by topology (collapsed across authority):**

| Topology | evol_fidelity M | hallucination M | factual_ret M | completeness M |
|---|---|---|---|---|
| bilattice | 95.02 | 13.32 | 95.51 | 96.76 |
| hierarchy | 96.92 | 3.88 | 96.67 | 98.43 |
| hub | 96.44 | 8.27 | 96.31 | 97.90 |
| lattice | 96.08 | 9.04 | 96.15 | 97.61 |
| linear | 95.61 | 15.09 | 95.57 | 97.61 |
| ring | 96.33 | 12.08 | 95.80 | 97.64 |

**Rank order (best to worst on hallucination):** hierarchy < hub < lattice < ring < bilattice < linear  
**Rank order (best to worst on completeness):** hierarchy > hub > lattice ≈ linear ≈ ring > bilattice

### Post-Hoc Pairwise Comparisons (Bonferroni-corrected, α = .0033)

**evol_fidelity — significant pairs (11/15):**

| Comparison | r_rb | p_bonf | Direction |
|---|---|---|---|
| bilattice vs. hierarchy | 0.28 | < .001 | hierarchy higher |
| bilattice vs. hub | 0.14 | < .001 | hub higher |
| bilattice vs. lattice | 0.12 | < .001 | lattice higher |
| bilattice vs. ring | 0.11 | .001 | ring higher |
| hierarchy vs. hub | −0.16 | < .001 | hierarchy higher |
| hierarchy vs. lattice | −0.17 | < .001 | hierarchy higher |
| hierarchy vs. linear | −0.32 | < .001 | hierarchy higher |
| hierarchy vs. ring | −0.19 | < .001 | hierarchy higher |
| hub vs. linear | −0.17 | < .001 | hub higher |
| lattice vs. linear | −0.15 | < .001 | lattice higher |
| linear vs. ring | 0.14 | .001 | ring higher |

**hallucination — significant pairs (10/15):**

| Comparison | r_rb | p_bonf | Direction |
|---|---|---|---|
| bilattice vs. hierarchy | −0.39 | < .001 | hierarchy lower hallucination |
| bilattice vs. hub | −0.17 | < .001 | hub lower |
| bilattice vs. lattice | −0.16 | < .001 | lattice lower |
| bilattice vs. ring | −0.11 | .013 | ring lower (marginal after correction) |
| hierarchy vs. hub | 0.24 | < .001 | hierarchy lower |
| hierarchy vs. lattice | 0.24 | < .001 | hierarchy lower |
| hierarchy vs. linear | 0.32 | < .001 | hierarchy lower |
| hierarchy vs. ring | 0.29 | < .001 | hierarchy lower |
| hub vs. linear | 0.11 | .037 | marginal, not significant after correction |
| lattice vs. linear | 0.10 | .037 | marginal, not significant after correction |

**completeness — significant pairs (10/15):** hierarchy is highest (all comparisons with other topologies significant at p_bonf < .001); bilattice is lowest (all comparisons significant). The hierarchy vs. ring comparison shows the largest effect size (r = −.38).

**factual_retention — significant pairs (4/15):** Only bilattice vs. hierarchy, bilattice vs. hub, bilattice vs. lattice, and hierarchy vs. ring reach corrected significance — confirming this DV is not well-differentiated by topology.

---

## 4. Authority Effects Within Topology

### 4a. Hub: Standard vs. High Authority

**Table 4a. Hub Authority Comparison (Mann-Whitney)**

| DV | M (std) | M (high) | U | p | r_rb | Direction |
|---|---|---|---|---|---|---|
| evol_fidelity | 96.64 | 96.23 | 80,168 | .008 | −0.082 | standard slightly higher |
| hallucination | 10.33 | 6.21 | 63,437 | < .001 | 0.144 | high authority lower |
| factual_retention | 95.83 | 96.79 | 57,396 | < .001 | 0.226 | high authority higher |
| completeness | 97.97 | 97.82 | 67,788 | .025 | 0.085 | trivial |

**Interpretation:** High authority in hub significantly reduces hallucination (39.9% mean reduction, r = .14) and improves factual retention (r = .23). The evol_fidelity effect, while significant, runs counter to expectation (standard slightly higher) and is trivially small (r = .08). Completeness is not meaningfully affected. This pattern suggests hub high authority has a targeted effect on fabrication suppression rather than general fidelity improvement.

### 4b. Hierarchy: Standard vs. High Authority

**Table 4b. Hierarchy Authority Comparison (Mann-Whitney)**

| DV | M (std) | M (high) | U | p | r_rb | Direction |
|---|---|---|---|---|---|---|
| evol_fidelity | 96.86 | 96.98 | 68,670 | .008 | 0.073 | negligible |
| hallucination | 5.16 | 2.59 | 88,076 | < .001 | −0.188 | high authority lower |
| factual_retention | 96.12 | 97.22 | 59,192 | < .001 | 0.201 | high authority higher |
| completeness | 98.29 | 98.57 | 57,728 | < .001 | 0.221 | high authority higher |

**Interpretation:** Hierarchy high authority shows the clearest authority benefit: 49.7% mean reduction in hallucination (r = .19), improved factual retention (r = .20), and improved completeness (r = .22). Effects are small-medium but consistent across three DVs. This is the most internally coherent authority effect in the dataset.

### 4c. Lattice: Standard vs. Implicit vs. Declared (Kruskal-Wallis + pairwise)

**Table 4c. Lattice Authority Comparison**

| DV | H(2) | p | η² | Significant pairs (Bonferroni, α = .017) |
|---|---|---|---|---|
| evol_fidelity | 2.23 | .328 | .0001 | None |
| hallucination | 5.04 | .080 | .0018 | None (marginal: std > both authority types) |
| factual_retention | 19.94 | < .001 | .011 | std < implicit (r=.10), std < declared (r=.15) |
| completeness | 39.61 | < .001 | .022 | std < implicit (r=.18), std < declared (r=.17) |

Pairwise detail for significant DVs (Bonferroni α = .017):
- factual_retention: std (M=95.84) < implicit (M=96.19, p=.008, r=.10); std < declared (M=96.42, p<.001, r=.15)
- completeness: std (M=97.33) < implicit (M=97.82, p<.001, r=.18); std < declared (M=97.69, p<.001, r=.17)
- Implicit and declared do not differ from each other on any DV

**Interpretation:** For lattice, authority condition (both implicit and declared) improves factual retention and completeness modestly (r ≈ .10–.18) but does not significantly suppress hallucination. The distinction between implicit vs. declared authority shows no effect — both types are equally effective (or equally ineffective). This may reflect that in a lattice topology, authority labeling influences content completeness but not fabrication.

### 4d. Bilattice: Standard vs. Implicit vs. Declared (Kruskal-Wallis + pairwise)

**Table 4d. Bilattice Authority Comparison**

| DV | H(2) | p | η² | Significant pairs (Bonferroni, α = .017) |
|---|---|---|---|---|
| evol_fidelity | 1.23 | .541 | −.0004 | None |
| hallucination | 10.66 | .005 | .0046 | std vs. declared only (p=.003, r=.11) |
| factual_retention | 19.88 | < .001 | .010 | std < implicit (r=.14); implicit > declared (r=.09) |
| completeness | 19.36 | < .001 | .009 | std < implicit (r=.13); std < declared (r=.09) |

Specific pairwise details:
- hallucination: std (M=15.72) > declared (M=11.73, p_bonf=.003, r=.11); std vs. implicit p_bonf=.36 (ns); implicit vs. declared ns
- factual_retention: std (M=95.43) < implicit (M=96.04, p<.001, r=.14); implicit > declared (M=95.05, p_bonf=.019, r=.09); std vs. declared ns
- completeness: std (M=96.44) < implicit (M=97.13, p<.001, r=.13); std < declared (M=96.70, p_bonf=.011, r=.09); implicit vs. declared ns

**Interpretation:** In bilattice, only declared authority significantly suppresses hallucination (25.4% mean reduction; implicit shows a 20% reduction that does not reach corrected significance). Implicit authority improves factual retention and completeness; declared authority improves completeness. The bilattice authority pattern is noisier than hub/hierarchy — effects are present but smaller (r ≈ .09–.14) and inconsistent across authority types and DVs.

---

## 5. Cross-Lineage Standard Deviation (XL-SD) Analysis

XL-SD measures divergence: how much do different lineage replications of the same condition converge on the same final output? Low XL-SD = high convergence (reproducibility); high XL-SD = divergent outputs across lineages.

**Computation:** For each (topology × authority × seed_idx) cell, SD of evol_fidelity across the 5 lineage replications at the final hop of the main transmission chain (hop 11 for all topologies with a main chain). Hierarchy is excluded from main-chain XL-SD (no main chain) and reported separately.

**Table 5a. XL-SD Summary by Condition (main chain, averaged across 7 seeds)**

| Topology | Authority | Mean XL-SD | SD of XL-SD | Min | Max | n seeds |
|---|---|---|---|---|---|---|
| bilattice | declared | 4.93 | 3.03 | 0.89 | 10.02 | 7 |
| bilattice | implicit | 3.38 | 2.43 | 0.00 | 6.26 | 7 |
| bilattice | standard | 3.36 | 2.85 | 0.00 | 6.27 | 7 |
| hub | high | 0.21 | 0.37 | 0.00 | 0.89 | 7 |
| hub | standard | 0.00 | 0.00 | 0.00 | 0.00 | 7 |
| lattice | declared | 1.24 | 1.98 | 0.00 | 4.24 | 7 |
| lattice | implicit | 1.48 | 2.15 | 0.00 | 6.02 | 7 |
| lattice | standard | 1.43 | 2.44 | 0.00 | 6.54 | 7 |
| linear | standard | 1.63 | 2.11 | 0.00 | 6.02 | 7 |
| ring | standard | 1.43 | 2.01 | 0.00 | 5.52 | 7 |

**Table 5b. Hierarchy XL-SD (lower3 terminal chain, hop 11)**

| Authority | Mean XL-SD | SD | Median |
|---|---|---|---|
| high | 0.73 | 1.71 | 0.00 |
| standard | 0.47 | 1.02 | 0.00 |

### Kruskal-Wallis on XL-SD by Topology

H(4) = 25.67, p < .001, η² = .333 (large effect at the condition level)

Pairwise medians:
- bilattice: Mdn = 4.03, M = 3.89 — substantially higher than all others
- hub: Mdn = 0.00, M = 0.10 — near-perfect convergence
- lattice: Mdn = 0.45, M = 1.39
- linear: Mdn = 0.84, M = 1.63
- ring: Mdn = 0.45, M = 1.43

### OLS Regression: XL-SD ~ Topology + Authority

R² = .329, F(7, 62) = 4.35, p < .001

| Predictor | Coefficient | SE | t | p |
|---|---|---|---|---|
| Intercept (bilattice, declared) | 4.34 | 0.66 | 6.55 | < .001 |
| hub | −3.65 | 1.05 | −3.48 | .001 |
| lattice | −2.50 | 0.66 | −3.78 | < .001 |
| linear | −2.01 | 1.05 | −1.92 | .059 |
| ring | −2.22 | 1.05 | −2.12 | .038 |
| authority: high | −0.49 | 1.40 | −0.35 | .731 |
| authority: implicit | −0.66 | 0.81 | −0.81 | .418 |
| authority: standard | −0.69 | 0.81 | −0.85 | .397 |

**Interpretation:** Topology is the dominant predictor of cross-lineage divergence (η² = .333 at the condition level — a large effect). Bilattice produces dramatically more divergent outputs across lineage replications; hub standard produces essentially zero divergence (all 5 lineages arrive at identical final-hop scores across all 7 seeds). Authority condition does not significantly predict XL-SD once topology is controlled — divergence is a function of network architecture, not authority labeling.

**Key finding:** The bilattice declared condition shows the highest XL-SD (M = 4.93), which is counterintuitive if one expects authority to suppress divergence. This may reflect a floor effect in convergence: bilattice produces more variability regardless of authority type, with declared showing slightly more divergence than standard or implicit (though the within-bilattice authority difference is not significant, KW H(2) = 1.93, p = .38, η² = −.004).

---

## 6. Seed Type Moderation

### 6a. Bartlett vs. Organizational Seeds — Overall

| Seed Type | n | Hallucination M | Mdn | SD |
|---|---|---|---|---|
| Organizational (seeds 1–6) | 5,040 | 4.60 | 3.0 | 13.20 |
| Bartlett / War of Ghosts (seed 7) | 840 | 44.06 | 20.0 | 43.74 |

Mann-Whitney: U = 580,906, p < .001, r_rb = 0.726 — a very large effect. The Bartlett stimulus generates 9.6× more hallucination on average than organizational seeds.

**Kruskal-Wallis across all 7 seeds:** H(6) = 1,773.25, p < .001, η² = .301 (large effect). Seed identity explains 30% of variance in hallucination rank order.

**Table 6a. Hallucination by Seed Index**

| Seed | Label | M | Mdn | SD |
|---|---|---|---|---|
| 1 | Organizational | 4.73 | 2.0 | 16.13 |
| 2 | Organizational | 2.86 | 2.0 | 2.44 |
| 3 | Organizational | 7.00 | 3.0 | 18.13 |
| 4 | Organizational | 3.62 | 0.0 | 15.15 |
| 5 | Organizational | 4.45 | 3.0 | 9.08 |
| 6 | Organizational | 4.91 | 3.0 | 11.38 |
| 7 | **Bartlett** | **44.06** | **20.0** | **43.74** |

Seed 2 is the most stable organizational seed (SD = 2.44, all hops clustered near median). Seeds 3 and 1 show more within-seed variability — these may be worth examining for content characteristics in the confirmatory design.

### 6b. Topology × Seed Type Interaction on Hallucination

**Table 6b. Hallucination by Topology and Seed Type**

| Topology | Org M | Bartlett M | Ratio | r_rb | p |
|---|---|---|---|---|---|
| bilattice | 7.78 | 46.61 | 6.0× | 0.668 | < .001 |
| hierarchy | 1.60 | 17.54 | 11.0× | 0.610 | < .001 |
| hub | 2.27 | 44.27 | 19.5× | 0.863 | < .001 |
| lattice | 3.13 | 44.52 | 14.2× | 0.770 | < .001 |
| linear | 6.91 | 64.15 | 9.3× | 0.874 | < .001 |
| ring | 3.74 | 62.13 | 16.6× | 0.892 | < .001 |

**Kruskal-Wallis: topology effect on hallucination within seed type:**
- Organizational seeds: H(5) = 281.93, p < .001, η² = .055
- Bartlett seed: H(5) = 106.25, p < .001, η² = .121

The topology effect on hallucination is **larger for the Bartlett stimulus** (η² = .12) than for organizational content (η² = .06). This suggests topology moderates how well the network handles narratively complex / culturally-distorted content more than it moderates routine organizational message transmission.

**Notable:** Hub and ring show the highest Bartlett hallucination (M ≈ 44–62). Hierarchy shows the lowest (17.5), consistent with its general advantage. Linear shows the worst absolute Bartlett hallucination (M = 64.2, Mdn = 100) — meaning the modal output of a linear chain for the War of the Ghosts seed is maximum hallucination. This is a striking finding.

---

## 7. Final-Hop Analysis

Final-hop analysis uses only the node at the maximum hop overall per run (hop 11 for all topologies — the deepest terminal node in the network). This is the output a real-world decision-maker would receive. n = 35 per condition (5 lineages × 7 seeds).

**Table 7a. Final-Hop Descriptives**

| Topology | Authority | n | evol_fid M | hall M | fact_ret M | completeness M |
|---|---|---|---|---|---|---|
| bilattice | declared | 35 | 91.91 | 28.29 | 92.06 | 94.40 |
| bilattice | implicit | 35 | 92.97 | 24.40 | 95.66 | 95.43 |
| bilattice | standard | 35 | 91.49 | 23.00 | 94.89 | 93.80 |
| hierarchy | high | 35 | 96.20 | 6.00 | 96.71 | 97.63 |
| hierarchy | standard | 35 | 96.51 | 11.91 | 96.03 | 97.97 |
| hub | high | 35 | 95.97 | 10.60 | 96.71 | 97.74 |
| hub | standard | 35 | 96.51 | 13.54 | 95.11 | 97.80 |
| lattice | declared | 35 | 94.86 | 16.49 | 95.86 | 96.51 |
| lattice | implicit | 35 | 94.40 | 11.80 | 96.06 | 96.80 |
| lattice | standard | 35 | 95.26 | 16.00 | 96.14 | 96.40 |
| linear | standard | 35 | 94.83 | 18.26 | 95.29 | 96.91 |
| ring | standard | 35 | 95.86 | 12.60 | 95.23 | 97.40 |

**Kruskal-Wallis on final-hop nodes by topology:**

| DV | H(5) | p | η² |
|---|---|---|---|
| evol_fidelity | 40.23 | < .001 | .085 |
| hallucination | 47.38 | < .001 | .102 |
| factual_retention | 7.27 | .201 | .006 |
| completeness | 44.29 | < .001 | .095 |

**Interpretation:** At the final hop, topology effects are larger than in the full-dataset analysis (η² = .085–.102 vs. .042–.053 all-hops). This is the more practically relevant analysis: the message a decision-maker receives at the end of the chain shows meaningfully different quality depending on network topology. Effect sizes are now approaching medium (η² ≈ .10). Hierarchy and hub produce the best final outputs; bilattice standard and linear produce the worst. Factual retention remains non-significant at the final hop — it is not well-differentiated by topology even at the terminal node.

**Comparison of all-hops vs. final-hop η²:**

| DV | All hops η² | Final-hop η² | Change |
|---|---|---|---|
| evol_fidelity | .042 | .085 | +0.043 |
| hallucination | .048 | .102 | +0.054 |
| completeness | .053 | .095 | +0.042 |
| factual_retention | .005 | .006 | +0.001 |

The doubling of effect sizes from all-hops to final-hop confirms that topology differences compound across hops — early differences are small but cumulative effects are substantially larger by hop 11.

---

## 8. DV Correlation Matrix

**Table 8. Spearman Correlation Matrix (n = 5,880)**

| | evol_fidelity | hallucination | factual_retention | completeness | consec_fidelity |
|---|---|---|---|---|---|
| evol_fidelity | 1.000 | −0.595*** | 0.137*** | 0.628*** | 0.204*** |
| hallucination | −0.595*** | 1.000 | −0.058*** | −0.568*** | −0.163*** |
| factual_retention | 0.137*** | −0.058*** | 1.000 | 0.282*** | 0.007 |
| completeness | 0.628*** | −0.568*** | 0.282*** | 1.000 | 0.166*** |
| consec_fidelity | 0.204*** | −0.163*** | 0.007 | 0.166*** | 1.000 |

***: p < .001

**Pearson correlations (for reference):**

| | evol_fidelity | hallucination | factual_retention | completeness |
|---|---|---|---|---|
| evol_fidelity | 1.000 | −0.544 | 0.093 | 0.830 |
| hallucination | −0.544 | 1.000 | −0.051 | −0.481 |
| factual_retention | 0.093 | −0.051 | 1.000 | 0.119 |
| completeness | 0.830 | −0.481 | 0.119 | 1.000 |

**Interpretation:**

1. **hallucination vs. evol_fidelity** (r_s = −.595): The expected strong negative correlation is confirmed. Nodes that hallucinate more have substantially lower evolutionary fidelity. This validates the construct convergence of these two measures.

2. **evol_fidelity vs. completeness** (r_s = .628, Pearson r = .830): These two DVs are highly correlated — more so than any other pair. This raises a multicollinearity concern: in any regression including both, they will be partially redundant. In a confirmatory analysis, consider using one as the primary DV or computing a composite.

3. **hallucination vs. completeness** (r_s = −.568): Hallucination and completeness are strongly negatively correlated — hallucinating nodes tend to omit rather than add. This is consistent with a substitution mechanism: hallucinated content displaces accurate content rather than supplementing it.

4. **factual_retention** is weakly correlated with everything (max |r| = .28 with completeness). It behaves as a relatively independent dimension. This may reflect that retaining specific named facts (the operational definition of factual_retention) is a different cognitive/computational process than maintaining overall semantic fidelity. **The weak correlation with hallucination (r = −.058) is notable:** a node can hallucinate while retaining most factual anchors, or vice versa.

5. **consec_fidelity** (node-to-node sequential fidelity) correlates weakly with all long-range fidelity measures. This is consistent with error accumulation: high consec_fidelity locally does not guarantee high evol_fidelity globally. r_s = .007 with factual_retention (p = .574, ns) suggests sequential fidelity is essentially unrelated to whether specific facts survive.

---

## 9. Evol_Fidelity Trajectory by Hop (selected topologies)

**Linear chain (clean degradation baseline):**

| Hop | M | SD |
|---|---|---|
| 1 | 96.97 | 0.45 |
| 3 | 96.20 | 2.01 |
| 5 | 95.54 | 2.55 |
| 8 | 94.71 | 3.49 |
| 11 | 94.83 | 4.06 |

Linear shows monotonic degradation with increasing variance — the expected telephone game pattern.

**Hierarchy (by position in hierarchy):**

| Hop | Tier | M | SD |
|---|---|---|---|
| 1–3 | Upper | 97.14 avg | 0.62 avg |
| 4–8 | Mid | 97.10 avg | 0.62 avg |
| 9–11 | Lower | 96.33 avg | 1.91 avg |

Remarkably flat across the upper and mid tiers, with meaningful degradation only at the lower tier. Hierarchy's architecture appears to buffer against early degradation.

**Bilattice main chain (entering at hop 6 after parallel branches merge):**

| Hop | M | SD |
|---|---|---|
| 6 | 93.71 | 5.16 |
| 8 | 93.16 | 5.63 |
| 11 | 92.12 | 6.70 |

Bilattice enters the main chain already at ~93.7 — substantially below baseline. The merge point (A + B branches → main) does not recover fidelity lost in the parallel branches.

---

## Summary: Effect Robustness Assessment

### Robust findings (pursue in confirmatory sweep)

| Finding | Evidence | Priority |
|---|---|---|
| **Topology main effect on hallucination** | H(5) = 285, η² = .048 all-hops; η² = .102 final-hop; large Bartlett moderation | HIGH |
| **Hierarchy best topology for hallucination suppression** | Consistently lowest hallucination, highest completeness across all analyses; holds for both org and Bartlett seeds | HIGH |
| **Bilattice worst topology for XL-SD / divergence** | Mean XL-SD 3.9–4.9 vs. 0–1.6 for all other topologies; OLS effect significant | HIGH |
| **Hub standard XL-SD = 0 (perfect convergence)** | All 35 lineage reps produce identical final-hop evol_fidelity; no variation whatsoever | HIGH |
| **Bartlett seed drives massive hallucination (r = .73 vs. org)** | 10× elevation; topology effect on hallucination is larger for Bartlett (η² = .12 vs. .06) | HIGH |
| **High authority reduces hallucination in hub (40%) and hierarchy (50%)** | Hub: r = .14, p < .001; Hierarchy: r = .19, p < .001; consistent effect direction | HIGH |
| **Final-hop effects double all-hop effects** | η² roughly doubles from all-hops to final-hop for all significant DVs | HIGH |
| **Hallucination and completeness are strongly inversely correlated (r = −.57)** | Consistent with substitution mechanism | MEDIUM |

### Tentative findings (worth exploring, not confirmatory-ready)

| Finding | Concern |
|---|---|
| **Lattice/bilattice authority effects on completeness and factual_retention** | Small effect sizes (r ≈ .09–.18); implicit vs. declared indistinguishable | MEDIUM |
| **Bilattice declared authority highest XL-SD** | Counterintuitive; may be n-driven; within-bilattice authority KW not significant | LOW |
| **Linear worst topology for Bartlett hallucination** (Mdn = 100) | Based on 55 observations; needs replication | MEDIUM |
| **Seed 2 vs. Seed 3 differences within org seeds** | Seed explains variance (η² = .30 overall) but individual seed differences are content-driven, not manipulated | LOW |
| **Hub high authority slightly worse evol_fidelity than hub standard** | Effect small (r = .08), direction unexpected; may reflect mean reversion or authority-induced style shift | LOW |

### Null findings (do not pursue)

| Finding | Evidence |
|---|---|
| **Factual retention not differentiated by topology** | η² = .005–.006 all-hops and final-hop; only bilattice vs. others survive correction | — |
| **Authority does not predict XL-SD** | OLS coefficients all p > .39 after controlling topology | — |
| **Lattice authority does not affect hallucination** | H(2) = 5.04, p = .080, η² = .002 — trend but not significant | — |
| **Implicit vs. declared authority: no significant difference anywhere** | All pairwise comparisons ns across all DVs and topologies | — |

---

## Recommendations for Confirmatory Sweep

1. **Primary DVs:** Use hallucination and completeness as the focal DVs. They show the strongest condition sensitivity, correlate as expected (r = −.57), and show the largest final-hop effect sizes. Evol_fidelity is redundant with completeness (Pearson r = .83). Factual retention is insensitive to topology manipulation and should be secondary.

2. **Analysis unit:** Aggregate to run level for the main analysis (mean DV score per run = 1 data point per lineage). This resolves the non-independence problem. With 5 lineages × 7 seeds × 35 runs-per-condition, you have 35 observations per condition — sufficient for mixed-effects models.

3. **Pre-register the final-hop analysis as primary.** The effect sizes are twice as large as the all-hops analysis. The final output is also what matters substantively. All-hops analysis should be secondary or exploratory.

4. **Topology contrast coding:** Rather than omnibus KW, pre-register specific contrasts: (a) hierarchy vs. all others, (b) bilattice vs. all others, (c) linear vs. ring (both sequential, test for loop benefit). Hub is unique enough structurally to treat as its own reference.

5. **Bartlett seed as a moderator:** Include seed_type (Bartlett vs. org) as a planned moderator. The topology × seed_type interaction on hallucination (η² shift from .06 to .12) should be explicitly tested. Consider whether the confirmatory design should have a dedicated Bartlett condition or use Bartlett as a stress test.

6. **Authority manipulation:** Focus confirmatory power on hub and hierarchy high vs. standard. Effects are robust (r ≈ .14–.22) and consistent. The lattice/bilattice implicit/declared manipulation shows at best small, inconsistent effects — either drop it from the confirmatory design or reduce the cell count.

7. **XL-SD as a secondary DV:** Report XL-SD as a condition-level secondary outcome. Hub standard's zero-divergence finding is striking and replicable by definition (all seeds showed zero variance). Bilattice's high divergence warrants a separate analysis examining whether the A/B merge point amplifies or introduces variance.

8. **Sample size note:** Pilot cell sizes (35 runs per condition) are likely adequate for the large effects (topology main effect η² ≈ .05–.10) but may be underpowered for small authority effects (r ≈ .08–.14). For the confirmatory sweep, consider power analysis targeting r = .15 minimum detectable effect.

9. **Hierarchical modeling:** The data structure (nodes nested in chains nested in runs) calls for mixed-effects models in the confirmatory phase. Suggested structure: `hallucination ~ topology * authority + (1 | run) + (1 | seed_idx)`, with run and seed as random effects to account for repeated sampling.

---

## Statistical Addendum: Distribution Details

**Normality violations (Shapiro-Wilk, n = 500 sample):**
- evol_fidelity: W = 0.416, p < .001 (severe left skew / ceiling)
- hallucination: W = 0.388, p < .001 (zero inflation + right skew)
- factual_retention: W = 0.819, p < .001 (ceiling concentration)
- completeness: W = 0.474, p < .001 (ceiling concentration)

None of the DVs are even approximately normal. Parametric tests (ANOVA, t-test) should not be used without transformation. Non-parametric tests (Kruskal-Wallis, Mann-Whitney) or appropriate GLMs (beta regression for 0-100 bounded DVs; zero-inflated negative binomial or hurdle model for hallucination) are appropriate for the confirmatory phase.

**Note on hallucination modeling:** For the confirmatory analysis, a two-part (hurdle) model for hallucination is recommended: (1) logistic regression predicting P(hallucination > 0), and (2) a positive-only model (e.g., log-normal or gamma) predicting the level of hallucination given that it occurs. This cleanly separates "does this node hallucinate at all?" from "how much does it hallucinate when it does?" — two potentially distinct mechanisms.

---

*End of report. All statistics computed from raw CSV; no values approximated or summarized. Python libraries: pandas, numpy, scipy, statsmodels.*
