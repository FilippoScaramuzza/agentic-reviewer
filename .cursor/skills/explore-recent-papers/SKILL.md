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

```bash
mkdir -p "context/<journal-slug>/recent-papers"
curl -L -o "context/<journal-slug>/recent-papers/<slugified-title>.pdf" "<pdf-url>"
markitdown "context/<journal-slug>/recent-papers/<slugified-title>.pdf" > "context/<journal-slug>/recent-papers/<slugified-title>.md"
```

Use slugified titles (lowercase, hyphens, no special characters). Verify downloads are not empty (> 10KB).

## Analysis: What to Extract

After reading the full text, analyze:

- **Topics & Themes**: Popular subjects, emerging trends, gaps being addressed
- **Methodology Patterns**: Common research designs, data collection methods, analysis techniques, typical sample sizes
- **Structural Conventions**: Typical sections, average length, abstract style, figure/table usage
- **Citation Practices**: Reference style, typical count, commonly cited works
- **Novelty Bar**: What counts as sufficient contribution, types of novelty valued

## Sample Size
Aim for 20 papers with full text. Supplement with abstract-only papers if needed and note the limitation.

## Output Location
Save to `context/<journal-slug>/recent-papers-analysis.md` (cache)
AND `<report-directory>/02-recent-papers-analysis.md` (session artifact)

Keep downloaded PDFs and Markdown files in `context/<journal-slug>/recent-papers/`.
