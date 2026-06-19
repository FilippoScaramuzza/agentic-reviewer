---
name: review-paper
description: Run the Agentic Reviewer academic paper review pipeline for a paper and target journal or conference.
license: MIT
---

# Review Paper

Run the repository's paper review workflow from `prompts/editor-in-chief.txt`.

Inputs required from the user:
- Paper path, usually under `papers/`
- Target journal or conference name

If either input is missing, ask for it before starting.

## Workflow

1. Create `reports/<journal-slug>/<YYYY-MM-DD-HHMMSS>/`.
2. Write `00-session-info.md`.
3. If the paper is not Markdown, use the `paper-converter` agent to convert it.
4. Check `context/<journal-slug>/` for cached journal context.
5. Unless the user says `re-explore`, reuse cached context only when all four files exist:
   - `scope-and-criteria.md`
   - `recent-papers-analysis.md`
   - `style-guide.md`
   - `reputation-profile.md`
6. If context is missing, stale, or incomplete, run only the exploration agents needed to produce missing or stale files:
   - `scope-explorer`
   - `recent-papers-explorer`
   - `style-guide-explorer`
   - `reputation-explorer`
7. After exploration is complete, run the reviewer agents:
   - `scope-reviewer`
   - `methodology-reviewer`
   - `writing-style-reviewer`
   - `statistics-reviewer`
   - `ethics-reviewer`
8. After all reviewer outputs exist, use `report-compiler`.

## Output Contract

All session artifacts must be written to the timestamped report directory:

```text
reports/<journal-slug>/<YYYY-MM-DD-HHMMSS>/
```

Do not write review artifacts to `reviews/`.

Do not commit changes unless the user explicitly asks.
