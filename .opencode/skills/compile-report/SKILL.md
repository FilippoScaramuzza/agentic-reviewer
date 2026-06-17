---
name: compile-report
description: >
  Merges all individual reviewer assessments into a single comprehensive
  review report with ratings, recommendations, and actionable feedback.
  Used by the report-compiler agent.
license: MIT
compatibility: opencode
metadata:
  audience: report-compiler
  phase: compilation
  category: report
---

## Goal
Synthesize all individual reviewer assessments into one unified, comprehensive, actionable review report.

## Prerequisites
Before compiling, read ALL individual review files:
1. `reviews/<paper-name>-scope-review.md`
2. `reviews/<paper-name>-methodology-review.md`
3. `reviews/<paper-name>-writing-style-review.md`
4. `reviews/<paper-name>-statistics-review.md`
5. `reviews/<paper-name>-ethics-review.md`

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

### Be Fair
- Highlight strengths as well as weaknesses
- Don't let one weak dimension dominate the entire assessment
- Consider the overall balance of issues

### Determining the Recommendation
- **ACCEPT**: All dimensions ≥ 4/5, no blocking issues
- **REVISE (MINOR)**: Most dimensions ≥ 4/5, minor issues that can be addressed
- **REVISE (MAJOR)**: Several dimensions 3/5, significant issues that need substantial work
- **REJECT**: Multiple dimensions ≤ 2/5, fundamental problems, or scope misfit

### Handle Contradictions
If reviewers disagree on something:
- Present both perspectives fairly
- Note the disagreement explicitly
- Provide your own assessment based on the evidence

### Overall Rating
Calculate the overall rating as the mean of all dimension ratings.
Use the trend icons:
- ✅ (4-5): Strong, no major concerns
- ⚠️ (3): Adequate with concerns
- ❌ (1-2): Problematic, needs significant work

## Output Location
Save to `reviews/<paper-name>-review.md`