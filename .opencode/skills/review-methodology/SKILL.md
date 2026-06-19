---
name: review-methodology
description: >
  Evaluates research design, methods, validity, and rigor of an
  academic paper's methodology. Used by the methodology-reviewer agent.
license: MIT
compatibility: opencode
metadata:
  audience: methodology-reviewer
  phase: review
  category: methodology
---

## Goal
Rigorously evaluate the research methodology of an academic paper.

## Prerequisites
Before starting the review, read:
1. The paper file (provided by the user)
2. `context/<journal-slug>/recent-papers-analysis.md` (to compare methods to journal norms)

## Review Checklist

### Research Design
- [ ] Is the research design appropriate for the research question?
- [ ] Is the design clearly described and justified?
- [ ] Are there obvious design flaws or confounds?

### Sample & Data Collection
- [ ] Is the sample size adequate for the claims being made?
- [ ] Is the sampling method appropriate?
- [ ] Are inclusion/exclusion criteria clearly stated?
- [ ] Is data collection methodology clearly described?
- [ ] Are potential sources of bias identified and addressed?

### Analysis Methods
- [ ] Are the analytical methods appropriate for the data and research questions?
- [ ] Are the methods clearly described with sufficient detail for replication?
- [ ] Are methodological choices justified?
- [ ] Are alternative methods considered and ruled out (with justification)?

### Validity
- [ ] Internal validity: Do the design and methods support the claims?
- [ ] External validity: Can findings be generalized beyond the study?
- [ ] Construct validity: Are the constructs well-defined and measured?
- [ ] Are threats to validity acknowledged and addressed?

### Reproducibility
- [ ] Could another researcher reproduce this study from the information provided?
- [ ] Are protocols, materials, and code sufficiently detailed?
- [ ] Is data availability stated?

### Journal Methodology Norms
- [ ] Does the methodology match what is typical for this journal?
- [ ] Are there methodological standards specific to this field that are met?

## Rating Scale
- 5/5: Exemplary methodology, no significant concerns
- 4/5: Sound methodology with minor issues
- 3/5: Adequate methodology with notable concerns
- 2/5: Methodology has significant flaws
- 1/5: Methodology is fundamentally flawed

## Output Location
Save to `<report-directory>/06-methodology-review.md`