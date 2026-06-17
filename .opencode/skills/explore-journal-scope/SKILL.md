---
name: explore-journal-scope
description: >
  Researches a journal's aims, scope, acceptance criteria, article types,
  target audience, and editorial policies. Used by the scope-explorer agent.
license: MIT
compatibility: opencode
metadata:
  audience: scope-explorer
  phase: exploration
  category: scope
---

## Goal
Systematically gather and document a journal's scope, aims, and acceptance criteria.

## Search Strategy
1. Search for `"<journal name> aims and scope"`
2. Search for `"<journal name> author guidelines"`
3. Search for `"<journal name> acceptance criteria"`
4. Fetch the official journal website's scope/aims page
5. Cross-reference with any supplementary scope documents

## Information to Extract
- Mission statement and editorial focus
- Subject areas and domains covered
- Types of contributions accepted (original research, reviews, case studies, letters, etc.)
- Target audience description
- What topics are explicitly in scope and out of scope
- Acceptance criteria or editorial priorities
- Any special sections or calls for papers

## Quality Checks
- Verify information comes from the official journal website
- Note when information is unavailable or ambiguous
- Cross-check scope statements across multiple pages for consistency

## Output Location
Save to `context/<journal-slug>/scope-and-criteria.md`