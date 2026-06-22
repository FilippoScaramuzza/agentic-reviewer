---
name: convert-paper
description: Converts non-Markdown papers (PDF, DOCX, PPTX, XLSX, HTML, etc.) to Markdown using markitdown. Use when a paper file needs to be converted before the review pipeline can process it.
disable-model-invocation: true
---

# Convert Paper

Convert any non-Markdown paper file into Markdown format so all downstream review steps can read and analyze it.

## Prerequisites

markitdown must be installed:
```bash
pip install "markitdown[all]"
```

## Conversion Process

### Step 1: Check if conversion is needed
If the paper file ends in `.md` or `.markdown`, no conversion is needed.

### Step 2: Convert the paper
```bash
markitdown <input-file> > <output-file>.md
```

Example:
```bash
markitdown papers/my-paper.pdf > papers/my-paper.md
```

Output filename: same base name as input with extension changed to `.md`.

### Step 3: Verify conversion
Read the beginning of the output file and check:
- File is not empty
- Content looks like valid Markdown (has headings, paragraphs, etc.)
- Key sections (title, abstract, body) are present

### Step 4: Report results
- Success: report the path of the Markdown file and proceed
- Failure: report the error and suggest the user provide a Markdown version manually

## Quality Notes
- PDF conversion may lose some formatting (figures, complex layouts)
- DOCX conversion generally preserves structure well
- If conversion quality is poor, recommend the user provide a pre-made Markdown version

## Output Convention
Converted papers are saved alongside the original in the same `papers/` directory.
Example: `papers/my-paper.pdf` → `papers/my-paper.md`
