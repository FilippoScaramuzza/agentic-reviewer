---
name: generate-pdf
description: >
  Converts a Markdown report to a nicely formatted, readable PDF using
  pandoc with XeLaTeX. Includes proper margins, fonts, tables, and
  clickable links. Used by the report-compiler agent to produce the
  final PDF deliverable.
license: MIT
compatibility: opencode
metadata:
  audience: report-compiler
  phase: compilation
  category: pdf
---

## Goal
Convert a Markdown report file into a professionally formatted, readable PDF.

## Prerequisites
- `pandoc` must be installed (`brew install pandoc` on macOS)
- A LaTeX engine must be installed (`brew install --cask mactex` or use `tectonic`)
- Check availability: `which pandoc && which xelatex`

## Conversion Command

### Primary: pandoc + XeLaTeX
```bash
pandoc <input.md> -o <output.pdf> \
  --pdf-engine=xelatex \
  -V geometry:margin=2.5cm \
  -V fontsize=11pt \
  -V mainfont="Helvetica" \
  -V monofont="Menlo" \
  -V colorlinks=true \
  -V linkcolor=blue \
  -V urlcolor=blue \
  -V toccolor=gray \
  --metadata title="Peer Review Report" \
  --metadata date="$(date +%Y-%m-%d)" \
  --highlight-style=tango \
  --toc \
  --toc-depth=2
```

### Explanation of Options
- `--pdf-engine=xelatex` — XeLaTeX handles Unicode and custom fonts
- `-V geometry:margin=2.5cm` — readable margins (not too narrow)
- `-V fontsize=11pt` — comfortable reading size
- `-V mainfont="Helvetica"` — clean sans-serif body text
- `-V monofont="Menlo"` — readable monospace for code/tables
- `-V colorlinks=true` — clickable links in blue
- `--highlight-style=tango` — pleasant code syntax highlighting
- `--toc` — table of contents for navigation
- `--toc-depth=2` — include H1 and H2 in TOC

### Fallback: pandoc + HTML + wkhtmltopdf
If XeLaTeX is not available:
```bash
pandoc <input.md> -o <output.pdf> --pdf-engine=wkhtmltopdf
```

### Fallback: pandoc + LaTeX (pdflatex)
If XeLaTeX is not available but pdflatex is:
```bash
pandoc <input.md> -o <output.pdf> \
  --pdf-engine=pdflatex \
  -V geometry:margin=2.5cm \
  -V fontsize=11pt \
  -V colorlinks=true \
  -V linkcolor=blue \
  --metadata title="Peer Review Report" \
  --toc
```

### Fallback: Install tools if missing
```bash
# Install pandoc
brew install pandoc

# Install LaTeX (large download)
brew install --cask mactex

# Or use tectonic (lighter alternative)
brew install tectonic
```

## Quality Notes
- The PDF should be readable when printed (good contrast, reasonable font size)
- Tables should render properly (pandoc handles Markdown tables natively)
- The table of contents makes longer reports navigable
- Links (URLs, internal references) should be clickable

## Output Convention
- The PDF is saved alongside the Markdown file in the same report directory
- Same base filename with `.pdf` extension
- Example: `10-final-review-report.md` → `10-final-review-report.pdf`