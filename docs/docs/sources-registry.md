# Sources Registry

Authoritative sources used to verify ORYX data and support the thesis methodology. Organised by type and reliability tier.

---

## Tier 1 — Institutional / Primary Sources

These are the most authoritative sources. Data from these sources requires no additional verification.

### European Union

- **ENISA Threat Landscape** (annual reports): https://www.enisa.europa.eu/topics/cyber-threats/threat-landscape
- **CERT-EU** (advisories and reports): https://cert.europa.eu/publications
- **EU Cyber Direct**: https://eucyberdirect.eu
- **European Council conclusions on cyber**: https://www.consilium.europa.eu

### National CERTs and Agencies

- **NCSC UK** (advisories): https://www.ncsc.gov.uk/section/keep-up-to-date/threat-reports
- **ANSSI France** (publications): https://www.ssi.gouv.fr/en/
- **BSI Germany**: https://www.bsi.bund.de/EN/
- **CISA USA** (advisories and KEV list): https://www.cisa.gov/known-exploited-vulnerabilities-catalog

### Attribution and Legal

- **US DOJ indictments** (for confirmed attributions): https://www.justice.gov/criminal/criminal-ccips
- **EU sanctions decisions**: https://www.consilium.europa.eu/en/policies/sanctions/cyber-attacks/
- **NCSC / NSA joint advisories**: published case-by-case

---

## Tier 2 — Private Sector / Technical Analysis

Reputable cybersecurity firms. Highly reliable for technical details (TTPs, malware analysis, IOCs). Attribution claims should be cross-referenced with Tier 1 sources.

- **Mandiant / Google Threat Intelligence**: https://www.mandiant.com/resources
- **CrowdStrike** (adversary reports): https://www.crowdstrike.com/blog/
- **Recorded Future**: https://www.recordedfuture.com/resources
- **ESET** (white papers): https://www.welivesecurity.com/
- **Kaspersky GReAT**: https://securelist.com/
- **Microsoft Threat Intelligence**: https://www.microsoft.com/en-us/security/blog/topic/threat-intelligence/
- **Symantec / Broadcom**: https://symantec-enterprise-blogs.security.com/
- **Palo Alto Unit 42**: https://unit42.paloaltonetworks.com/
- **Dragos** (ICS/OT specific): https://www.dragos.com/resources/

---

## Tier 3 — Aggregators and Databases

Useful for cross-referencing and discovery. Data should be verified against Tier 1 or Tier 2.

- **MITRE ATT&CK Groups**: https://attack.mitre.org/groups/
- **MITRE ATT&CK Software**: https://attack.mitre.org/software/
- **CSIS Significant Cyber Incidents**: https://www.csis.org/programs/strategic-technologies-program/significant-cyber-incidents
- **CFR Cyber Operations Tracker**: https://www.cfr.org/cyber-operations
- **APT Groups and Operations** (Google Sheet by Florian Roth): https://apt.etda.or.th/cgi-bin/listgroups.cgi
- **Malpedia**: https://malpedia.caad.fkie.fraunhofer.de/

---

## Tier 4 — OSINT and Open Sources

Used for supplementary context. Should never be the sole source for any data point.

- **NVD / CVE**: https://nvd.nist.gov/
- **AlienVault OTX**: https://otx.alienvault.com/
- **abuse.ch** (URLhaus, MalwareBazaar, ThreatFox): https://abuse.ch/
- **VirusTotal**: https://www.virustotal.com/
- **Shodan**: https://www.shodan.io/

---

## Usage Rules for the Thesis

1. Every data point in the verified attacks database must cite at least one Tier 1 or Tier 2 source
2. Attribution claims require a Tier 1 source (government statement, indictment, or official advisory)
3. Economic impact figures must cite the original source (company annual report, government estimate, or reputable journalistic investigation)
4. Technical details (TTPs, malware, IOCs) can rely on Tier 2 sources
5. Tier 3 and 4 sources are used for discovery and cross-referencing only
