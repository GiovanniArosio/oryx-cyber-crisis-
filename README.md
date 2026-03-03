# ORYX — Cyber Crisis Observatory

**A purpose-built research instrument for measuring the technical dimension of European cyber crises through the MITRE ATT&CK framework.**

Named after the oryx — a species known for its exceptional long-range vision in harsh environments — ORYX is designed to observe, structure, and measure cyber threats across the European landscape where complexity obscures clarity.

## Why ORYX exists

The study of crisis communication in the context of cyber attacks faces a fundamental methodological gap: while the discursive and narrative dimensions of cyber crises have received growing scholarly attention, the technical complexity of the attacks themselves remains largely unmeasured — treated as background context rather than as an independent variable.

This creates what the underlying thesis calls an *interpretive void*: the more technically complex an attack, the harder it becomes for institutional communicators, media, and the public to make sense of what happened, who is responsible, and what it means. Yet there was no standardised way to quantify that complexity and correlate it with communication dynamics.

ORYX was designed to fill this gap.

## What ORYX does

ORYX is the experimental research tool for a master's thesis in International Relations & Security. It transforms cyber attacks from unstructured narratives into structured, measurable phenomena by:

- **Mapping attacks onto MITRE ATT&CK** — each incident is coded against the full ATT&CK Enterprise matrix (14 tactics, 691 techniques), with source-level evidence and confidence ratings
- **Computing a Technical Complexity Index (TCI)** — an original composite metric that quantifies attack complexity across six weighted dimensions: technique breadth, tactic coverage, zero-day exploitation, custom tooling, stealth level, and attribution difficulty
- **Enabling structured comparison** — side-by-side ATT&CK mappings, Jaccard similarity between technique sets, and delta analysis across all variables
- **Visualising the European cyber threat landscape** — a 3D interactive globe with 38 historical European cyber incidents (2007–2025), origin-target attack arcs, and impact zone overlays
- **Integrating live OSINT feeds** — real-time data from NVD/CVE, AlienVault OTX, abuse.ch (URLhaus, MalwareBazaar, ThreatFox), and MITRE ATT&CK updates

## The Technical Complexity Index (TCI)

The TCI is the thesis's original methodological contribution. It operationalises "technical complexity" as a measurable variable through the following weighted formula:
TCI = (num_techniques × 0.25) + (num_tactics × 0.20) + (zero_day × 0.20) +
(custom_malware × 0.15) + (stealth_level × 0.10) + (attribution_difficulty × 0.10)

Normalised on a 0–10 scale. The index is designed to serve as the independent variable in a subsequent correlation with crisis communication dynamics (narrative competition, institutional response timing, public comprehension).

## Research context

ORYX supports Chapter 2 of the thesis — *"The Technical Dimension of Chaos: Analysing Cyber-Attacks through MITRE ATT&CK"* — which argues that technical analysis is not merely a prerequisite for understanding cyber crises, but a structuring variable that shapes how those crises are communicated, interpreted, and contested in the European public space.

The thesis is supervised by Professor Donatella Selva and examines the intersection of cybersecurity, crisis communication theory (Sturges, Coombs/SCCT), and European public discourse.

## Tech stack

- **Frontend:** React.js, Tailwind CSS, Three.js / globe.gl, Recharts, D3.js
- **Backend:** Node.js, Express.js
- **Database:** SQLite (MITRE ATT&CK corpus + structured case study data)
- **OSINT APIs:** NVD, AlienVault OTX, abuse.ch, GitHub (MITRE CTI)

## Development note

ORYX was conceptualised, designed, and directed by the author as part of the thesis research process. The codebase was developed with AI-assisted tools (OpenAI Codex, Anthropic Claude) under continuous author supervision. The research design, variable operationalisation, case selection criteria, ATT&CK coding methodology, and the TCI formula are entirely the author's intellectual contribution.

## License

MIT
