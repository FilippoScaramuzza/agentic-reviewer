---
name: review-ethics
description: Checks ethical compliance in academic papers including IRB approval, informed consent, conflicts of interest, data availability, and authorship ethics. Use when assessing the ethics dimension of a paper under review.
disable-model-invocation: true
---

# Review Ethics

Check ethical compliance of an academic paper, identifying any issues that could lead to rejection.

## Prerequisites
Before starting, read:
1. The paper file
2. `context/<journal-slug>/scope-and-criteria.md` (journal-specific ethics requirements)

## Review Checklist

### IRB/Ethics Board Approval
- [ ] Is IRB or ethics committee approval documented?
- [ ] Is the approval number or reference provided?
- [ ] For studies not requiring IRB, is this justified?

### Informed Consent
- [ ] Is informed consent documented for human subjects research?
- [ ] Is the consent process described?
- [ ] For vulnerable populations, are additional protections described?

### Animal Research Ethics
- [ ] For animal studies, is ethical approval documented?
- [ ] Are animal welfare guidelines followed (ARRIVE, 3R principle)?
- [ ] Mark as N/A if no animal research involved

### Conflicts of Interest
- [ ] Is a conflicts of interest statement present?
- [ ] Are all potential COIs disclosed (financial, personal, professional)?
- [ ] Is the funding source declared?

### Data Availability & Sharing
- [ ] Is a data availability statement included?
- [ ] Are data deposited in a public repository (with DOI/accession number)?
- [ ] Is analysis code available?

### Authorship Ethics
- [ ] Does the author list seem appropriate for the contribution?
- [ ] Are author contributions described (CRediT taxonomy)?
- [ ] Is corresponding author clearly designated?

### Privacy & Anonymization
- [ ] Are participants properly anonymized?
- [ ] Is sensitive data protected?
- [ ] Is GDPR or relevant data protection legislation addressed?

### Dual Use & Harm
- [ ] Could the research be misused or cause harm?
- [ ] Are dual-use concerns acknowledged and mitigation strategies proposed?

## Rating Scale
- 5/5: Full ethical compliance with exemplary transparency
- 4/5: Ethical compliance with minor documentation gaps
- 3/5: Basic compliance with some concerns
- 2/5: Significant ethical gaps that need addressing
- 1/5: Major ethical violations

## Special Considerations
- If an ethics dimension doesn't apply (e.g., no animal research), mark N/A rather than giving a low score
- Absence of a required statement (e.g., no COI declaration) is itself an ethical concern

## Output Location
Save to `<report-directory>/09-ethics-review.md`
