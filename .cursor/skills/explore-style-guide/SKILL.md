---
name: explore-style-guide
description: Extracts detailed formatting and style requirements from a journal's author guidelines. Use when style-guide context is missing or needs refreshing before a paper review.
disable-model-invocation: true
---

# Explore Style Guide

Extract and document all formatting and style requirements from a journal's author guidelines.

## Search Strategy
1. Search for `"<journal name> author guidelines"`
2. Search for `"<journal name> submission instructions"`
3. Search for `"<journal name> manuscript formatting"`
4. Fetch the official author guidelines page

## Information to Extract

### Document Structure
- Required sections (IMRAD or custom), abstract requirements (word limit, structured vs. unstructured), keywords requirements

### Word & Page Limits
- Total word count limit, abstract word limit, per-section limits, reference list limits

### Reference Style
- Citation format (APA, Vancouver, Harvard, IEEE, etc.), in-text citation style, DOI requirements, maximum reference count

### Figure & Table Requirements
- Accepted formats (TIFF, EPS, PNG, etc.), minimum resolution (DPI), caption formatting, color vs. grayscale, maximum count

### Title & Author Formatting
- Title length limits, author name and affiliation formatting, corresponding author designation, ORCID requirements

### Supplementary Material
- Allowed formats, file size limits, submission process

### General Formatting
- Font, line spacing, margin, page numbering, line numbering requirements

## Quality Checks
- Verify all requirements come from the official journal website
- Note version/date of the guidelines if available
- Flag any ambiguous or contradictory requirements
- Note what couldn't be found

## Output Location
Save to `context/<journal-slug>/style-guide.md` (cache)
AND `<report-directory>/03-style-guide.md` (session artifact)
