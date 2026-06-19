---
name: compile-report
description: Merges all individual reviewer assessments into a single comprehensive review report with ratings, recommendations, and actionable feedback. Use when all five reviewer outputs exist and the final report needs to be compiled.
disable-model-invocation: true
---

# Compile Report

Synthesize all individual reviewer assessments into one unified, comprehensive, actionable review report.

## Prerequisites

Before compiling, read ALL individual review files from the report directory:
1. `<report-directory>/05-scope-review.md`
2. `<report-directory>/06-methodology-review.md`
3. `<report-directory>/07-writing-style-review.md`
4. `<report-directory>/08-statistics-review.md`
5. `<report-directory>/09-ethics-review.md`

If any file is missing, note the gap in the report but compile what is available.

## Compilation Guidelines

### Synthesize, Don't Copy
- Read all reviews and create a cohesive narrative
- Resolve contradictions between reviewers fairly
- Present the most critical issues upfront

### Prioritize Issues
- Rank issues by impact on acceptance/rejection
- Distinguish between blocking issues (must fix) and improvements (should fix)
- Consider the journal's typical threshold when making recommendations

### Determining the Recommendation
- **ACCEPT**: All dimensions ≥ 4/5, no blocking issues
- **REVISE (MINOR)**: Most dimensions ≥ 4/5, minor issues addressable in revision
- **REVISE (MAJOR)**: Several dimensions 3/5, significant issues needing substantial work
- **REJECT**: Multiple dimensions ≤ 2/5, fundamental problems, or scope misfit

### Handle Contradictions
If reviewers disagree: present both perspectives, note the disagreement explicitly, and provide your own assessment.

### Overall Rating
Calculate the overall rating as the mean of all dimension ratings. Use trend icons:
- ✅ (4–5): Strong, no major concerns
- ⚠️ (3): Adequate with concerns
- ❌ (1–2): Problematic, needs significant work

## Output Location

Save to `<report-directory>/10-final-review-report.md`, then generate the PDF using the `generate-pdf` skill.
