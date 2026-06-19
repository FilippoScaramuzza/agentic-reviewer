# Agentic Reviewer

> An OpenCode-based agentic framework for academic paper peer review — a team of AI agents explores a target journal, then reviews your paper before submission.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![OpenCode](https://img.shields.io/badge/OpenCode-compatible-blue)](https://opencode.ai)

## What It Does

Given a paper and a target journal/conference, a team of 12 specialized agents:

1. **Converts** your paper to Markdown (PDF, DOCX → `.md` via [markitdown](https://github.com/microsoft/markitdown))
2. **Explores** the journal — downloads & reads recent papers, extracts scope/style/reputation
3. **Reviews** your paper across 5 dimensions: scope fit, methodology, writing, statistics, ethics
4. **Compiles** a final report with ratings and a recommendation (Accept / Revise / Reject)

Every review session produces a **timestamped report directory** with all artifacts.

## Quick Start

### Prerequisites

1. Install [OpenCode](https://opencode.ai):
   ```bash
   curl -fsSL https://opencode.ai/install | bash
   ```

2. Install [markitdown](https://github.com/microsoft/markitdown) for paper conversion:
   ```bash
   pip install "markitdown[all]"
   ```

3. Install [pandoc](https://pandoc.org/installing.html) and a LaTeX engine for PDF report generation:
   ```bash
   # macOS
   brew install pandoc
   brew install --cask mactex
   ```

4. Configure an LLM provider in OpenCode (run `/connect` in the TUI).

### Run a Review

1. Clone this repo:
   ```bash
   git clone https://github.com/<your-username>/agentic-reviewer.git
   cd agentic-reviewer
   ```

2. Place your paper in `papers/` (any format: PDF, DOCX, Markdown):
   ```bash
   cp ~/my-paper.pdf papers/
   ```

3. Start OpenCode:
   ```bash
   opencode
   ```

4. Switch to the **Editor-in-Chief** agent (press `Tab`)

5. Ask for a review:
   ```
   Review papers/my-paper.pdf for submission to Nature
   ```

The Editor-in-Chief will orchestrate the full pipeline automatically.

## How It Works

```
Phase 0: Conversion        Paper Converter (PDF/DOCX → Markdown)
    ↓
Phase 1: Exploration       Scope Explorer ─┐
                           Recent Papers Explorer (downloads & reads full PDFs) ─┤
                           Style Guide Explorer ─┤
                           Reputation Explorer ─┘
    ↓                          (cached in context/<journal>/)
Phase 2: Review            Scope Reviewer ─┐
                           Methodology Reviewer ─┤
                           Writing & Style Reviewer ─┤
                           Statistics Reviewer ─┤
                           Ethics Reviewer ─┘
    ↓
Phase 3: Compilation       Report Compiler → Markdown report + PDF (pandoc)
```

## Report Structure

Every review session generates a timestamped directory:

```
reports/<journal-slug>/<YYYY-MM-DD-HHMMSS>/
├── 00-session-info.md            # Session metadata
├── 01-scope-and-criteria.md      # Journal scope analysis
├── 02-recent-papers-analysis.md   # Recent papers (full-text analysis)
├── 03-style-guide.md             # Style guide extraction
├── 04-reputation-profile.md      # Reputation profile
├── 05-scope-review.md            # Scope review
├── 06-methodology-review.md      # Methodology review
├── 07-writing-style-review.md     # Writing & style review
├── 08-statistics-review.md        # Statistics review
├── 09-ethics-review.md            # Ethics review
├── 10-final-review-report.md      # Compiled final report (Markdown)
└── 10-final-review-report.pdf     # Compiled final report (PDF)
```

## Agents

| Agent | Role | Phase |
|-------|------|-------|
| Editor-in-Chief | Orchestrates the full pipeline, creates report directory | All |
| Paper Converter | Converts non-Markdown papers to Markdown | Conversion |
| Scope Explorer | Gathers journal aims & scope | Exploration |
| Recent Papers Explorer | Downloads & reads full text of recent papers | Exploration |
| Style Guide Explorer | Extracts formatting requirements | Exploration |
| Reputation Explorer | Profiles journal reputation | Exploration |
| Scope Reviewer | Assesses paper-journal fit | Review |
| Methodology Reviewer | Evaluates research methods | Review |
| Writing & Style Reviewer | Checks writing quality and content structure | Review |
| Statistics Reviewer | Evaluates statistical rigor | Review |
| Ethics Reviewer | Checks ethical compliance | Review |
| Report Compiler | Merges all reviews into final report (Markdown + PDF) | Compilation |

## Project Structure

```
agentic-reviewer/
├── opencode.json               # Agent & permission configuration
├── AGENTS.md                   # Project rules for all agents
├── LICENSE                     # MIT License
├── prompts/                    # Agent prompt files (.txt)
├── .opencode/
│   └── skills/                 # Skill definitions (SKILL.md)
├── papers/                     # Place your paper here (gitignored)
├── context/                    # Cached journal context (gitignored)
└── reports/                    # Timestamped review reports (gitignored)
```

## Key Features

- **Caching**: Journal exploration context is cached in `context/<journal-slug>/` and reused across reviews. Say "re-explore" to force a refresh.
- **Full-text analysis**: The Recent Papers Explorer downloads and reads complete papers — not just abstracts.
- **Timestamped reports**: Every session produces a self-contained report directory with all artifacts.
- **Domain-agnostic**: Works for any journal or conference across CS, biomed, humanities, etc.
- **Tool execution**: All agents have bash access for running tools and commands.

## Customization

### Adding a New Reviewer Agent

1. Create a prompt file in `prompts/<agent-name>.txt`
2. Add the agent definition to `opencode.json` under `"agent"`
3. Create a skill in `.opencode/skills/<skill-name>/SKILL.md`
4. Add the agent to the Editor-in-Chief's `task` permissions in `opencode.json`

### Changing the Model

Agents use whatever model is globally configured in OpenCode. To use a specific model per agent, add a `"model"` field to the agent config in `opencode.json` (e.g., `"model": "anthropic/claude-sonnet-4-20250514"`).

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. See the [LICENSE](LICENSE) file for details.

## License

[MIT](LICENSE)