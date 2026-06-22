---
name: review-scope
description: Reviews a paper's fit with a target journal based on scope, aims, recent publications, and acceptance criteria. Use when assessing the scope dimension of a paper under review.
disable-model-invocation: true
---

# Review Scope

Assess whether a paper fits the aims, scope, and typical content of a target journal.

## Prerequisites
Before starting, read:
1. The paper file
2. `context/<journal-slug>/scope-and-criteria.md`
3. `context/<journal-slug>/recent-papers-analysis.md`

## Review Checklist

### Topic Alignment
- [ ] Does the paper's primary subject fall within the journal's stated scope?
- [ ] Is the research domain explicitly mentioned in the aims & scope?
- [ ] Would the paper's topic be of interest to the journal's target audience?

### Contribution Level
- [ ] Is the level of contribution appropriate for this venue?
- [ ] Does the novelty meet the journal's typical threshold?
- [ ] Is the paper type accepted by the journal (research, review, etc.)?

### Competitive Fit
- [ ] How does this paper compare to recent publications in the journal?
- [ ] Are there similar papers already published? Does this offer enough differentiation?
- [ ] Would this paper strengthen or weaken the journal's portfolio?

### Specific Concerns
- [ ] Are there scope misalignments that could lead to desk rejection?
- [ ] Would a different journal be a better fit? Which one(s)?

## Rating Scale
- 5/5: Excellent fit, clearly within scope and contribution level
- 4/5: Good fit with minor scope questions
- 3/5: Adequate fit with some concerns about alignment
- 2/5: Poor fit, likely to be desk-rejected or require major reframing
- 1/5: Does not fit this venue at all

## Output Location
Save to `<report-directory>/05-scope-review.md`
