---
name: review-ethics
description: >
  Checks ethical compliance in academic papers including IRB, consent,
  conflicts of interest, and data availability. Used by the
  ethics-reviewer agent.
license: MIT
compatibility: opencode
metadata:
  audience: ethics-reviewer
  phase: review
  category: ethics
---

## Goal
Check ethical compliance of an academic paper, identifying any issues that could lead to rejection.

## Prerequisites
Before starting the review, read:
1. The paper file (provided by the user)
2. `context/<journal-slug>/scope-and-criteria.md` (journal-specific ethics requirements)

## Review Checklist

### IRB/Ethics Board Approval
- [ ] Is institutional review board (IRB) or ethics committee approval documented?
- [ ] Is the approval number or reference provided?
- [ ] Does the approval cover the specific study conducted?
- [ ] For studies not requiring IRB, is this justified?

### Informed Consent
- [ ] Is informed consent documented for human subjects research?
- [ ] Is the consent process described (written, verbal, etc.)?
- [ ] Are consent forms available if required?
- [ ] For vulnerable populations, are additional protections described?

### Animal Research Ethics
- [ ] For animal studies, is ethical approval documented?
- [ ] Are animal welfare guidelines followed (ARRIVE guidelines, etc.)?
- [ ] Is the 3R principle (Replace, Reduce, Refine) addressed?
- [ ] Are euthanasia methods described and humane?
- [ ] Mark as N/A if the paper does not involve animal research

### Conflicts of Interest
- [ ] Is a conflicts of interest statement present?
- [ ] Are all potential COIs disclosed (financial, personal, professional)?
- [ ] Are there undisclosed COIs implied by author affiliations or funding?
- [ ] Is the funding source declared?

### Data Availability & Sharing
- [ ] Is a data availability statement included?
- [ ] Are data deposited in a public repository (with DOI/accession number)?
- [ ] If data cannot be shared, are restrictions justified?
- [ ] Is analysis code available?

### Authorship Ethics
- [ ] Does the author list seem appropriate for the contribution?
- [ ] Are author contributions described (CRediT taxonomy)?
- [ ] Is there evidence of honorary/gift authorship?
- [ ] Is corresponding author clearly designated?

### Privacy & Anonymization
- [ ] Are participants properly anonymized?
- [ ] Is sensitive data protected (no identifiable information)?
- [ ] Are there privacy risks in data sharing?
- [ ] Is GDPR or relevant data protection legislation addressed?

### Dual Use & Harm
- [ ] Could the research be misused or cause harm?
- [ ] Are dual-use concerns acknowledged?
- [ ] Is there a risk-benefit discussion?
- [ ] Are mitigation strategies proposed?

## Rating Scale
- 5/5: Full ethical compliance with exemplary transparency
- 4/5: Ethical compliance with minor documentation gaps
- 3/5: Basic compliance with some concerns
- 2/5: Significant ethical gaps that need addressing
- 1/5: Major ethical violations

## Special Considerations
- If an ethics dimension doesn't apply (e.g., no animal research), mark as N/A rather than giving a low score
- Absence of a required statement (e.g., no COI declaration) is itself an ethical concern
- Some journals have specific ethics requirements — check the scope context

## Output Location
Save to `reviews/<paper-name>-ethics-review.md`