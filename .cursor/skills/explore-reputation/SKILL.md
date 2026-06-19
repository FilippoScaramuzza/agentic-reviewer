---
name: explore-reputation
description: Profiles a journal's reputation, impact factor, indexing status, editorial board, acceptance rates, and predatory status. Use when journal reputation context is missing or needs refreshing before a paper review.
disable-model-invocation: true
---

# Explore Reputation

Profile the reputation, impact, and standing of an academic journal or conference.

## Search Strategy
1. Search for `"<journal name> impact factor"`
2. Search for `"<journal name> Scopus"` or `"<journal name> Web of Science"`
3. Search for `"<journal name> acceptance rate"`
4. Search for `"<journal name> predatory"` or check Beall's list
5. Search for `"<journal name> editorial board"`
6. Fetch the journal's official page for metrics
7. Check SCImago (scimagojr.com) for ranking data

## Information to Extract

### Impact & Metrics
- Journal Impact Factor (JIF) — most recent year
- CiteScore, h-index
- SCImago quartile ranking (Q1–Q4)
- Eigenfactor or other influence metrics

### Indexing Status
Check: Scopus, Web of Science (SCI/SSCI/AHCI), ESCI, PubMed/MEDLINE, Engineering Index/Compendex, other relevant databases.

### Editorial Board
Editor-in-Chief (name, affiliation), key associate editors, geographic distribution.

### Publisher
Publisher name and reputation, open access model, APC if applicable, self-archiving policies.

### Acceptance & Review
Estimated acceptance rate, review model (single/double-blind/open), typical turnaround time.

### Predatory Status
Is it on Beall's list? Red flags? Overall assessment: **Safe / Caution / Avoid**.

### Field Standing
Journal perception in its domain, comparison to similar journals, notable recent papers.

## Quality Checks
- Only cite verified metrics from official sources
- Note when information is estimated or from informal sources
- Be honest about predatory indicators — don't gloss over red flags

## Output Location
Save to `context/<journal-slug>/reputation-profile.md` (cache)
AND `<report-directory>/04-reputation-profile.md` (session artifact)
