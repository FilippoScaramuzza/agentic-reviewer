---
name: explore-reputation
description: >
  Profiles a journal's reputation, impact factor, indexing status,
  editorial board, acceptance rates, and predatory status.
  Used by the reputation-explorer agent.
license: MIT
compatibility: opencode
metadata:
  audience: reputation-explorer
  phase: exploration
  category: reputation
---

## Goal
Profile the reputation, impact, and standing of an academic journal or conference.

## Search Strategy
1. Search for `"<journal name> impact factor"`
2. Search for `"<journal name> Scopus" or "<journal name> Web of Science"`
3. Search for `"<journal name> acceptance rate"`
4. Search for `"<journal name> predatory"` or check Beall's list
5. Search for `"<journal name> editorial board"`
6. Fetch the journal's official page for metrics
7. Check SCImago (scimagojr.com) for ranking data

## Information to Extract

### Impact & Metrics
- Journal Impact Factor (JIF) — most recent year
- CiteScore (if available)
- h-index
- SCImago quartile ranking (Q1, Q2, Q3, Q4)
- Eigenfactor or other influence metrics

### Indexing Status
Check and document whether the journal is indexed in:
- Scopus
- Web of Science (SCI, SSCI, AHCI)
- ESCI (Emerging Sources Citation Index)
- PubMed / MEDLINE
- Engineering Index / Compendex
- Other relevant databases

### Editorial Board
- Editor-in-Chief: name, affiliation, reputation
- Key associate editors
- Notable advisory board members
- Geographic distribution of editorial board

### Publisher
- Publisher name and reputation
- Open access model (Gold OA, hybrid, subscription)
- APC (Article Processing Charge) if applicable
- Publisher policies on self-archiving

### Acceptance & Review
- Estimated acceptance rate (if publicly available)
- Review model (single-blind, double-blind, open peer review)
- Typical turnaround time from submission to first decision
- Number of reviewers typically assigned

### Predatory Status
- Is it on Beall's list or other predatory watchlists?
- Are there red flags (fake editorial boards, no proper peer review, etc.)?
- Overall predatory assessment: Safe / Caution / Avoid

### Field Standing
- How is the journal perceived by researchers in its domain?
- Comparison to similar journals in the same field
- Notable papers published in recent years

## Quality Checks
- Only cite verified metrics from official sources
- Note when information is estimated or from informal sources
- Be honest about predatory indicators — don't gloss over red flags
- If the journal is a conference, adjust the assessment framework accordingly

## Output Location
Save to `context/<journal-slug>/reputation-profile.md`