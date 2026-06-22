---
name: review-statistics
description: Evaluates statistical methods, analysis rigor, data presentation, effect sizes, multiple comparisons, and reproducibility of quantitative findings in an academic paper. Use when assessing the statistics dimension of a paper under review.
disable-model-invocation: true
---

# Review Statistics

Evaluate the statistical rigor and data presentation quality of an academic paper.

## Prerequisites
Before starting, read:
1. The paper file
2. `context/<journal-slug>/scope-and-criteria.md` if the journal has specific statistical requirements

## Review Checklist

### Study Design & Power
- [ ] Was an a priori power analysis conducted?
- [ ] Is the sample size adequate for the claimed effects?
- [ ] Were there multiple comparisons that required correction?

### Statistical Methods
- [ ] Are the statistical tests appropriate for the data type and research question?
- [ ] Are assumptions of the tests checked and reported (normality, homoscedasticity, independence)?
- [ ] Are non-parametric alternatives used when assumptions are violated?
- [ ] Are model fit indices reported (for regression/SEM models)?
- [ ] Is the software/package used for analysis stated?

### Effect Sizes & Confidence Intervals
- [ ] Are effect sizes reported (not just p-values)?
- [ ] Are confidence intervals provided?
- [ ] Is practical significance discussed, not just statistical significance?

### Multiple Comparisons
- [ ] Are multiple comparison corrections applied where needed (Bonferroni, FDR, etc.)?
- [ ] Is the family-wise error rate controlled?
- [ ] Are pre-registered analyses distinguished from post-hoc analyses?

### Data Presentation
- [ ] Are results clearly presented in tables and figures?
- [ ] Is there redundancy between text, tables, and figures?
- [ ] Are standard deviations, not just means, reported?
- [ ] Are exact p-values reported rather than just significance thresholds?

### Reproducibility
- [ ] Is analysis code available or described in sufficient detail?
- [ ] Are data availability statements included?
- [ ] Could the analysis be replicated from the information provided?

### Red Flags
- [ ] p-hacking indicators (optional stopping, selective reporting)
- [ ] HARKing (Hypothesizing After Results are Known)
- [ ] Data dredging or fishing expeditions
- [ ] Selective reporting of analyses
- [ ] Overinterpretation of marginal results

## Rating Scale
- 5/5: Exemplary statistical analysis, fully transparent and rigorous
- 4/5: Sound analysis with minor issues
- 3/5: Adequate analysis with notable concerns
- 2/5: Significant statistical problems
- 1/5: Fundamentally flawed analysis

## Note
If the paper is primarily qualitative or theoretical (no quantitative analysis), mark the review as N/A and provide a brief explanation.

## Output Location
Save to `<report-directory>/08-statistics-review.md`
