---
name: explore-style-guide
description: >
  Extracts detailed formatting and style requirements from a journal's
  author guidelines. Used by the style-guide-explorer agent.
license: MIT
compatibility: opencode
metadata:
  audience: style-guide-explorer
  phase: exploration
  category: style
---

## Goal
Extract and document all formatting and style requirements from a journal's author guidelines.

## Search Strategy
1. Search for `"<journal name> author guidelines"`
2. Search for `"<journal name> submission instructions"`
3. Search for `"<journal name> manuscript formatting"`
4. Fetch the official author guidelines page
5. If a downloadable PDF guide exists, note the URL for reference

## Information to Extract

### Document Structure
- Required sections (IMRAD, or custom structure)
- Section heading formatting
- Abstract requirements (word limit, structured vs. unstructured)
- Keywords requirements (number, format, vocabulary)

### Word & Page Limits
- Total word count limit
- Abstract word limit
- Per-section limits (if any)
- Reference list limits (if any)

### Reference Style
- Citation format (APA, Vancouver, Harvard, IEEE, etc.)
- In-text citation style (numbered, author-year)
- Reference list formatting
- DOI requirements
- Maximum/typical reference count

### Figure & Table Requirements
- Accepted formats (TIFF, EPS, PNG, etc.)
- Minimum resolution (DPI)
- Caption formatting and placement
- Color vs. grayscale requirements
- Maximum number of figures/tables

### Title & Author Formatting
- Title length limits
- Author name formatting
- Affiliation formatting
- Corresponding author designation
- ORCID requirements

### Supplementary Material
- Allowed formats
- File size limits
- Submission process for supplements

### General Formatting
- Font requirements
- Line spacing
- Margin requirements
- Page numbering
- Line numbering requirements

## Quality Checks
- Verify all requirements come from the official journal website
- Note version/date of the guidelines if available
- Flag any ambiguous or contradictory requirements
- If information is missing, note what couldn't be found

## Output Location
Save to `context/<journal-slug>/style-guide.md`