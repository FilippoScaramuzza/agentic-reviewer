---
name: review-journal-paper
description: Run the full academic paper peer review pipeline for a paper targeting a specific journal. Alias for the review-paper skill. Use when the user asks to review, evaluate, or assess a paper for a specific journal.
---

# Review Journal Paper

Alias for the `review-paper` skill. Follow the `review-paper` workflow exactly.

Inputs required from the user:
- Paper path, usually under `papers/`
- Target journal name

If either input is missing, ask for it before starting.

## Workflow

See `.cursor/skills/review-paper/SKILL.md` for the full workflow.
