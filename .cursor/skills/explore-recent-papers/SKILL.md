---
name: explore-recent-papers
description: Downloads and deeply analyzes the full text of recent papers from an academic journal using markitdown to convert PDFs to Markdown. Use when recent-papers context is missing or needs refreshing before a paper review.
disable-model-invocation: true
---

# Explore Recent Papers

Download and analyze the full text of up to 20 recent publications from the target journal/conference. Read the complete papers — not just abstracts.

## Search Strategy

### Finding Recent Papers
1. Search arxiv for recent papers matching the journal name or conference proceedings
2. Search PubMed Central (open access) for biomedical journals
3. Search Semantic Scholar for papers with open-access PDFs
4. Search Google Scholar for the journal's recent publications
5. Check the journal's website for recent issue tables of contents

For each paper found, collect: title, authors, year, DOI, and PDF URL.

### Priority Order for Full-Text Access
1. **arxiv preprint** — `https://arxiv.org/pdf/<arxiv-id>.pdf`
2. **bioRxiv / medRxiv preprint**
3. **PubMed Central**
4. **Author's institutional page**
5. **Semantic Scholar** — links to open-access PDFs

If no full text is available after all attempts, fall back to abstract-only analysis for that paper.

## Download Process

### Create Paper Directory
```bash
mkdir -p "context/<journal-slug>/recent-papers"
```

### Download PDFs
```bash
curl -L -o "context/<journal-slug>/recent-papers/<slugified-title>.pdf" "<pdf-url>"
```

Use a slugified version of the paper title (lowercase, hyphens, remove special characters) for filenames.

### Convert PDFs to Markdown
```bash
markitdown "context/<journal-slug>/recent-papers/<slugified-title>.pdf" > "context/<journal-slug>/recent-papers/<slugified-title>.md"
```

After conversion, read the full Markdown text of each paper.

### Verify Downloads
After downloading, verify each file:
```bash
ls -la "context/<journal-slug>/recent-papers/"
```
Check that files are not empty and have reasonable sizes (> 10KB for full papers).

## Analysis Methodology

### What to Extract from Full Papers

After reading the full text of each paper, analyze:

### Topics & Themes
- What subjects are currently popular?
- What emerging trends exist?
- Which research gaps are being addressed?

### Methodology Patterns
- Common research designs (experimental, observational, computational, etc.)
- Dominant data collection methods
- Popular analysis techniques and statistical approaches
- Typical sample sizes and study populations

### Structural Conventions
- Typical paper sections and their organization
- Average paper length (in pages or word count)
- Abstract style (structured vs. unstructured, typical length)
- Figure and table usage patterns (how many, what types)

### Citation Practices
- Citation style used by the journal (APA, Vancouver, etc.)
- Typical number of references
- Commonly cited frameworks, methods, or foundational works

### Novelty Bar
- What counts as a sufficient contribution in this venue?
- Types of novelty valued (empirical, theoretical, methodological, practical)
- What is clearly insufficient for acceptance?

## Sample Size
Aim for 20 papers with full text. If fewer full texts are available, supplement with abstract-only papers and clearly note the limitation.

## Quality Checks
- Focus on RECENT publications (last 1-2 years)
- Verify papers are actually from the target journal
- Note how many papers were read in full vs. abstract-only
- Save all downloaded files for reproducibility

## Output Location
Save to `context/<journal-slug>/recent-papers-analysis.md` (cache)
AND `<report-directory>/02-recent-papers-analysis.md` (session artifact)

Keep all downloaded PDFs and converted Markdown files in `context/<journal-slug>/recent-papers/` for future reference.
