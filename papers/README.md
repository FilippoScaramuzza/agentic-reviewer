# Papers

Place your paper files in this directory before running a review.

## Supported Formats
- **Markdown** (`.md`) — recommended, no conversion needed
- **PDF** (`.pdf`) — automatically converted to Markdown via markitdown
- **Word** (`.docx`) — automatically converted to Markdown via markitdown
- **PowerPoint** (`.pptx`) — automatically converted to Markdown via markitdown
- **Plain text** (`.txt`) — no conversion needed

## Usage
```bash
# Example: review a PDF paper for submission to Nature
# (run from the Editor-in-Chief agent in OpenCode)
Review papers/my-paper.pdf for submission to Nature
```

The paper-converter agent will automatically convert non-Markdown files to `.md` before the review pipeline processes them.

## Note
Files placed in this directory are **not** committed to the repository (see `.gitignore`). This keeps your unpublished papers private.