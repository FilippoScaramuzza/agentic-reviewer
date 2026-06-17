---
name: review-writing-style
description: >
  Reviews writing quality, clarity, structure, and content-level style
  of an academic paper in Markdown format. Focuses on writing and
  argumentation rather than formatting lost in Markdown conversion.
license: MIT
compatibility: opencode
metadata:
  audience: writing-style-reviewer
  phase: review
  category: writing
---

## Goal
Assess the writing quality, clarity, structure, and content-level style of an academic paper. The paper is in Markdown format, so formatting checks (fonts, margins, DPI, page layout) are not applicable.

## Prerequisites
Before starting the review, read:
1. The paper file (provided by the user)
2. `context/<journal-slug>/style-guide.md` (journal content and structural expectations)

## What to Review

### Focus On (content-level)
- **Clarity & Readability**: Is the writing clear, concise, and appropriate for the audience?
- **Structure & Organization**: Does the paper follow a logical structure? Does it have the sections the journal expects?
- **Grammar & Language**: Are there grammatical errors, awkward phrasing, or inconsistent terminology?
- **Content-Level Style Compliance**: Required sections present? Appropriate length for the journal? Abstract style?
- **Abstract Quality**: Does the abstract cover the key elements (background, methods, results, conclusions)?
- **Argumentation & Flow**: Does the paper present a coherent argument from introduction through conclusion?
- **Figures & Tables Description**: Are they well-described and referenced in text?
- **References**: Are references comprehensive, current, and covering key works in the field?

### Do NOT Review (formatting-level, lost in Markdown)
- Font, fontsize, or typeface
- Margin sizes or page layout
- Figure resolution or file format requirements
- Page numbering or line numbering
- Line spacing or paragraph indentation
- Reference formatting style (APA, Vancouver, etc.) — assess completeness only

## Checklist

### Clarity & Readability
- [ ] Is the writing clear and concise?
- [ ] Is jargon used appropriately for the target audience?
- [ ] Are complex ideas explained accessibly?

### Structure & Organization
- [ ] Does the paper have the sections the journal expects?
- [ ] Are sections well-organized with clear transitions?
- [ ] Is the narrative coherent from introduction through conclusion?

### Grammar & Language
- [ ] Are there grammatical errors?
- [ ] Is terminology used consistently?
- [ ] Is the language appropriate for an academic context?

### Content-Level Compliance
- [ ] Does the paper appear to be an appropriate length for this journal?
- [ ] Are all required sections present?
- [ ] Is the abstract structured or unstructured per journal expectations?
- [ ] Are keywords provided?

### Abstract Quality
- [ ] Does the abstract summarize the key elements?
- [ ] Is it self-contained and informative?

### Argumentation & Flow
- [ ] Does the introduction motivate the research question?
- [ ] Do the methods connect to the research question?
- [ ] Do the results support the conclusions?

### References
- [ ] Are references comprehensive and covering the field?
- [ ] Are references reasonably current?
- [ ] Are key works in the field cited?

## Rating Scale
- 5/5: Excellent writing, well-organized, compelling argument
- 4/5: Good writing with minor style issues
- 3/5: Adequate writing with notable improvements needed
- 2/5: Poor writing or significant organizational problems
- 1/5: Unacceptable writing quality

## Output Location
Save to `<report-directory>/07-writing-style-review.md`