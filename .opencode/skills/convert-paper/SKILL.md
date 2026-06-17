---
name: convert-paper
description: >
  Converts non-Markdown papers (PDF, DOCX, PPTX, XLSX, HTML, etc.) to
  Markdown using the markitdown CLI tool. Ensures all papers are in a
  uniform format before the review pipeline processes them.
license: MIT
compatibility: opencode
metadata:
  audience: paper-converter
  phase: conversion
  category: conversion
---

## Goal
Convert any non-Markdown paper file into Markdown format so that all downstream review agents can read and analyze it.

## Prerequisites
- markitdown must be installed: `pip install markitdown[all]`
- If not installed, install it first before attempting conversion

## Supported Input Formats
- PDF (.pdf)
- Word documents (.docx)
- PowerPoint (.pptx)
- Excel spreadsheets (.xlsx, .xls)
- HTML (.html, .htm)
- Plain text (.txt) — straight copy
- Images with text — limited support via OCR extras
- Other formats supported by markitdown

## Conversion Process

### Step 1: Check if conversion is needed
- If the paper file ends in `.md` or `.markdown`, no conversion is needed
- If the paper file is in any other format, proceed with conversion

### Step 2: Install markitdown (if needed)
```bash
pip install "markitdown[all]"
```
The `[all]` extra installs format-specific dependencies (PDF, DOCX, PPTX, XLSX, etc.).

### Step 3: Convert the paper
```bash
markitdown <input-file> > <output-file>.md
```

Example:
```bash
markitdown papers/my-paper.pdf > papers/my-paper.md
```

The output filename should match the input filename with the extension changed to `.md`.

### Step 4: Verify conversion
After conversion, read the beginning of the output file to verify:
- The file is not empty
- The content looks like valid Markdown (has headings, paragraphs, etc.)
- Key sections of the paper (title, abstract, body) are present

### Step 5: Report results
- If conversion succeeded: report the path of the Markdown file and proceed
- If conversion failed: report the error and suggest the user provide a Markdown version manually

## Quality Notes
- markitdown converts documents to Markdown but the quality depends on the source format
- PDF conversion may lose some formatting (figures, complex layouts)
- DOCX conversion generally preserves structure well
- For best results, review the converted Markdown for any obvious conversion artifacts
- If the conversion quality is poor, recommend the user provide a pre-made Markdown version

## Output Convention
- Converted papers are saved alongside the original in the same `papers/` directory
- The filename uses the same base name with `.md` extension
- Example: `papers/my-paper.pdf` → `papers/my-paper.md`