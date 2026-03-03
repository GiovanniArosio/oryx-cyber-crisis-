# Technical Complexity Index (TCI) — Methodology

## Overview

The Technical Complexity Index (TCI) is the thesis's original methodological contribution. It operationalises the concept of "technical complexity" as a quantifiable, composite variable that can be systematically applied to any cyber attack mapped onto the MITRE ATT&CK framework.

The purpose of the TCI is to enable correlation between the technical dimension of a cyber crisis and its communication dynamics — bridging the gap between cybersecurity analysis and crisis communication theory.

---

## The Formula
TCI = (T × 0.25) + (A × 0.20) + (Z × 0.20) + (M × 0.15) + (S × 0.10) + (D × 0.10)

Where:

- **T** = Technique breadth (number of unique ATT&CK techniques used, normalised)
- **A** = Tactic coverage (number of ATT&CK tactics involved out of 14, normalised)
- **Z** = Zero-day exploitation (binary: 0 or 1, scaled to 0–10)
- **M** = Custom malware (binary: custom tooling = 1, commodity malware = 0, scaled to 0–10)
- **S** = Stealth level (based on the proportion of Defense Evasion techniques relative to total techniques, normalised 0–10)
- **D** = Attribution difficulty (qualitative assessment: Confirmed = 2, Probable = 4, Suspected = 7, Unknown = 10)

**Output**: Normalised score on a 0–10 scale.

---

## Variable Definitions

### T — Technique Breadth (weight: 0.25)

The total number of unique MITRE ATT&CK techniques identified in the attack. This is the single most informative indicator of operational complexity, as it reflects the range of capabilities deployed.

**Normalisation**: The raw count is mapped to a 0–10 scale using a reference maximum. Based on the most complex known operations (e.g., SolarWinds SUNBURST with 18+ techniques), the reference maximum is set at 20 techniques. Attacks using 20 or more techniques score 10.

### A — Tactic Coverage (weight: 0.20)

The number of distinct ATT&CK tactics (out of 14) covered by the attack. This captures the operational breadth — whether the attacker operated across the full kill chain or focused on a narrow phase.

**Normalisation**: Raw count divided by 14, multiplied by 10.

### Z — Zero-Day Exploitation (weight: 0.20)

Whether the attack exploited one or more zero-day vulnerabilities (previously unknown flaws). Zero-days indicate a higher level of sophistication and resource investment.

**Scoring**: Binary — 0 (no zero-day) or 10 (zero-day used). If the attack used multiple zero-days, the score remains 10 (the variable captures presence, not quantity).

### M — Custom Malware (weight: 0.15)

Whether the attack used custom-developed malware or tools, as opposed to publicly available commodity malware (e.g., Cobalt Strike, Mimikatz).

**Scoring**: Binary — 0 (commodity tools only) or 10 (custom malware present). Mixed cases (custom + commodity) score 10, as the presence of custom tooling is the discriminating factor.

### S — Stealth Level (weight: 0.10)

The proportion of Defense Evasion techniques relative to the total number of techniques used. A higher ratio indicates that the attacker invested more effort in avoiding detection.

**Normalisation**: (Defense Evasion technique count / total technique count) × 10.

### D — Attribution Difficulty (weight: 0.10)

A qualitative assessment of how difficult it was for the international community to attribute the attack to a specific actor. This reflects the operational security (OPSEC) of the attacker.

**Scoring scale**:
- Confirmed attribution (government statements, indictments) = 2
- Probable attribution (strong technical evidence, multiple Tier 2 sources agree) = 4
- Suspected attribution (limited evidence, single-source claims) = 7
- Unknown / unattributed = 10

---

## Design Rationale

### Why these weights?

The weights reflect the relative importance of each dimension in determining overall technical complexity, calibrated through iterative analysis of known cyber operations:

- **Technique breadth (0.25)**: The strongest single predictor of operational complexity
- **Tactic coverage (0.20)**: Captures kill chain breadth, closely correlated with but distinct from technique count
- **Zero-day (0.20)**: High weight because zero-day usage is the clearest signal of state-level or advanced capability
- **Custom malware (0.15)**: Important but less discriminating than zero-days, since some sophisticated operations use modified commodity tools
- **Stealth (0.10)**: Relevant but derivative — it is partially captured by technique count
- **Attribution difficulty (0.10)**: Important for the thesis's communication dimension, but partially subjective

### Why MITRE ATT&CK as the coding framework?

ATT&CK provides a standardised, community-maintained taxonomy of adversarial behaviours. Using it as the coding framework ensures:

1. Reproducibility — any researcher can apply the same coding to the same attack
2. Comparability — different attacks are measured on the same scale
3. Granularity — 691 techniques across 14 tactics provide fine-grained measurement
4. Credibility — ATT&CK is the de facto industry standard, recognised by ENISA, CISA, and NATO

### Limitations

- The TCI measures technical complexity as observable from post-incident reporting. Attacks with limited public analysis may receive artificially low scores.
- Binary variables (Z, M) lose nuance. An attack using 5 zero-days scores the same as one using 1.
- The weights are author-defined based on analytical reasoning, not statistically derived. A sensitivity analysis should be performed to test robustness.
- Attribution difficulty (D) involves qualitative judgment and may evolve over time as new evidence emerges.

---

## Implementation

The TCI is computed automatically in ORYX's backend (`server/models/attack.js`, line 24). When a case study is saved with its ATT&CK technique mapping, the system calculates all six variables from the stored data and returns the normalised score.

The TCI score is displayed in:
- The Case Study detail view
- The TCI Analytics dashboard (radar chart, comparative bars, scatter plot)
- The Comparative Analysis view (delta calculations between case studies)

---

## Planned Extensions (Chapter 3)

The TCI is designed as the independent variable for a subsequent correlation analysis with crisis communication dynamics. Planned dependent variables include:

- Institutional response time (hours between attack discovery and first official communication)
- Narrative competition intensity (number of competing narratives in the first 72 hours)
- Public comprehension index (to be operationalised — potential survey or media framing analysis)
- Attribution narrative stability (how often the attribution changed in public discourse)

This correlation will form the core of Chapter 3 of the thesis.
