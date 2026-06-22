---
name: generate-pdf
description: Converts a Markdown review report to a professionally formatted PDF using pandoc with XeLaTeX. Use after the final review report Markdown has been compiled to produce the PDF deliverable.
disable-model-invocation: true
---

# Generate PDF

Convert a Markdown report file into a professionally formatted, readable PDF.

## Prerequisites
- pandoc: `brew install pandoc` (macOS) or see pandoc.org
- LaTeX engine: `brew install --cask mactex` or use tectonic (`brew install tectonic`)
- Check: `which pandoc && which xelatex`

## Primary Command (pandoc + XeLaTeX)

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
  -V toccolor=gray \
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
PDF saved alongside the Markdown file in the same report directory, same base filename with `.pdf` extension.
Example: `10-final-review-report.md` → `10-final-review-report.pdf`
