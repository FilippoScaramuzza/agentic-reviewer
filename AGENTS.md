# Agentic Reviewer — Journal Paper Review Framework

## Project Overview
An OpenCode-based agentic framework for academic paper peer review. Given a paper and a target journal/conference, a team of agents:
1. **Converts** non-Markdown papers (PDF, DOCX, etc.) to Markdown using markitdown
2. **Explores** the journal's requirements, recent publications, style guide, and reputation
3. **Reviews** the paper against those requirements across five dimensions
4. **Compiles** a final structured review report with ratings and recommendation

Every review session produces a timestamped report directory containing all artifacts.

## Directory Structure
- `papers/` — Place paper files here (PDF, DOCX, Markdown, etc.)
- `context/<journal-slug>/` — Cached exploration results per journal (auto-generated)
  - `scope-and-criteria.md`
  - `recent-papers-analysis.md`
  - `style-guide.md`
  - `reputation-profile.md`
  - `recent-papers/` — Downloaded full-text papers (PDFs + converted Markdown)
    - `<slugified-title>.pdf` — Downloaded paper PDFs
    - `<slugified-title>.md` — Markitdown-converted versions
- `reports/<journal-slug>/<YYYY-MM-DD-HHMMSS>/` — Timestamped report directory (auto-generated)
  - `00-session-info.md` — Session metadata (journal, paper, date, timestamp)
  - `01-scope-and-criteria.md` — Journal scope analysis
  - `02-recent-papers-analysis.md` — Recent papers analysis
  - `03-style-guide.md` — Style guide extraction
  - `04-reputation-profile.md` — Reputation profile
  - `05-scope-review.md` — Scope review
  - `06-methodology-review.md` — Methodology review
  - `07-writing-style-review.md` — Writing & style review
  - `08-statistics-review.md` — Statistics review
  - `09-ethics-review.md` — Ethics review
  - `10-final-review-report.md` — Compiled final report (Markdown)
  - `10-final-review-report.pdf` — Compiled final report (PDF, generated via pandoc)

## Workflow

### Phase 0: Setup & Paper Conversion
- Editor-in-Chief creates the timestamped report directory
- If the paper is not Markdown (.md), `@paper-converter` converts it using markitdown
- Session metadata is saved to `00-session-info.md`

### Phase 1: Exploration
The exploration team gathers journal context:
- `@scope-explorer` — analyzes aims & scope, acceptance criteria → `01-scope-and-criteria.md`
- `@recent-papers-explorer` — downloads & reads full text of recent papers → `02-recent-papers-analysis.md`
- `@style-guide-explorer` — extracts formatting requirements → `03-style-guide.md`
- `@reputation-explorer` — profiles impact factor, indexing → `04-reputation-profile.md`

Results are cached in `context/<journal-slug>/`. If context already exists, exploration is skipped unless the user requests "re-explore".

### Phase 2: Review
The review team assesses the paper using the gathered context:
- `@scope-reviewer` — paper-journal fit → `05-scope-review.md`
- `@methodology-reviewer` — research design and validity → `06-methodology-review.md`
- `@writing-style-reviewer` — writing quality and formatting → `07-writing-style-review.md`
- `@statistics-reviewer` — statistical rigor → `08-statistics-review.md`
- `@ethics-reviewer` — ethical compliance → `09-ethics-review.md`

### Phase 3: Compilation
- `@report-compiler` — merges all reviews into `10-final-review-report.md`, then converts to `10-final-review-report.pdf` using pandoc

## Prerequisites
- Install markitdown for paper conversion: `pip install "markitdown[all]"`
- Install pandoc for PDF report generation: `brew install pandoc` (macOS) or see [pandoc.org](https://pandoc.org/installing.html)
- Install a LaTeX engine for pandoc PDF output: `brew install --cask mactex` (macOS) or use [tectonic](https://tectonic-typesetting.github.io/)
- These enable automatic conversion of papers to Markdown and final report PDF generation

## Conventions
- Journal names are slugified for directory names (e.g., "Nature Medicine" → "nature-medicine")
- Timestamps use `YYYY-MM-DD-HHMMSS` format (e.g., `2025-01-15-143022`)
- Always read `context/<journal-slug>/` files before reviewing a paper
- Each review agent writes its individual assessment to the numbered file in the report directory
- All agents have bash access for tool execution capabilities
- Use the "re-explore" keyword to force refreshing journal context

## How to Use
1. Place your paper in `papers/` (any format: PDF, DOCX, Markdown, etc.)
2. Switch to the Editor-in-Chief agent (Tab key)
3. Say: "Review papers/my-paper.pdf for submission to Nature"
4. The Editor-in-Chief will create a timestamped report directory, convert the paper if needed, then orchestrate the full pipeline

## Cached Context
Exploration results are cached per journal in `context/<journal-slug>/`. If you're reviewing multiple papers for the same journal, the context is reused. To force a refresh, say "re-explore" to the Editor-in-Chief.

Downloaded full-text papers are stored in `context/<journal-slug>/recent-papers/` as both PDFs and converted Markdown files. The recent-papers-explorer reads the complete papers — not just abstracts and metadata.

## Agent Permissions
All agents have bash access enabled for tool execution. The exploration agents also have webfetch/websearch access. The exploration context is saved to both the cache directory and the timestamped report directory.