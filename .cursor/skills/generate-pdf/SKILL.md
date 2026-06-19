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

## Fallbacks

**pdflatex (if xelatex unavailable):**
```bash
pandoc <input.md> -o <output.pdf> \
  --pdf-engine=pdflatex \
  -V geometry:margin=2.5cm \
  -V fontsize=11pt \
  -V colorlinks=true \
  --metadata title="Peer Review Report" \
  --toc
```

**wkhtmltopdf:**
```bash
pandoc <input.md> -o <output.pdf> --pdf-engine=wkhtmltopdf
```

## Output Convention
PDF saved alongside the Markdown file in the same report directory, same base filename with `.pdf` extension.
Example: `10-final-review-report.md` → `10-final-review-report.pdf`
