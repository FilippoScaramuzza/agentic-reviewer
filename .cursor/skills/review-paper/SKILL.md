---
name: review-paper
description: Run the Agentic Reviewer academic paper review pipeline for a paper and target journal or conference. Use when the user asks to review, assess, or evaluate a paper for submission to a journal or conference.
---

# Review Paper

Run the repository's paper review workflow.

Inputs required from the user:
- Paper path, usually under `papers/`
- Target journal or conference name

If either input is missing, ask for it before starting.

## Workflow

1. Create `reports/<journal-slug>/<YYYY-MM-DD-HHMMSS>/`.
2. Write `00-session-info.md`.
3. If the paper is not Markdown, use the `convert-paper` skill to convert it.
4. Check `context/<journal-slug>/` for cached journal context.
5. Unless the user says `re-explore`, reuse cached context only when all four files exist:
   - `scope-and-criteria.md`
   - `recent-papers-analysis.md`
   - `style-guide.md`
   - `reputation-profile.md`
6. If context is missing, stale, or incomplete, run only the exploration skills needed to produce missing or stale files:
   - `explore-journal-scope`
   - `explore-recent-papers`
   - `explore-style-guide`
   - `explore-reputation`
7. After exploration is complete, run the reviewer skills:
   - `review-scope`
   - `review-methodology`
   - `review-writing-style`
   - `review-statistics`
   - `review-ethics`
8. After all reviewer outputs exist, use `compile-report`.

## Output Contract

All session artifacts must be written to the timestamped report directory:

```text
reports/<journal-slug>/<YYYY-MM-DD-HHMMSS>/
```

Do not commit changes unless the user explicitly asks.
