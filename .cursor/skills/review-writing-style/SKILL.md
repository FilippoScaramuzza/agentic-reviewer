---
name: review-writing-style
description: Reviews writing quality, clarity, structure, grammar, argumentation, and content-level style compliance of an academic paper in Markdown format. Use when assessing the writing and style dimension of a paper under review.
disable-model-invocation: true
---

# Review Writing Style

Assess the writing quality, clarity, structure, and content-level style of an academic paper. The paper is in Markdown format, so formatting checks (fonts, margins, DPI, page layout) are not applicable.

## Prerequisites
Before starting, read:
1. The paper file
2. `context/<journal-slug>/style-guide.md` (journal content and structural expectations)

## What to Review

### Focus On (content-level)
- **Clarity & Readability**: Is the writing clear, concise, and appropriate for the audience?
- **Structure & Organization**: Does the paper follow a logical structure? Are expected sections present?
- **Grammar & Language**: Are there grammatical errors, awkward phrasing, or inconsistent terminology?
- **Content-Level Style Compliance**: Required sections present? Appropriate length? Abstract style?
- **Abstract Quality**: Does the abstract cover background, methods, results, and conclusions?
- **Argumentation & Flow**: Is there a coherent argument from introduction through conclusion?
- **References**: Are references comprehensive, current, and covering key works in the field?

### Do NOT Review (formatting-level, lost in Markdown)
- Font, font size, or typeface
- Margin sizes or page layout
- Figure resolution or file format requirements
- Line spacing or paragraph indentation
- Reference formatting style — assess completeness only, not format

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
