---
name: Word / DOCX
slug: word-docx
version: 1.0.0
homepage: https://github.com/openclaw/word-docx-skill
description: Create, read, and edit Microsoft Word documents (.docx) with proper formatting, styles, tables, images, and cross-platform compatibility.
changelog: Initial release - DOCX creation and editing capability
metadata: {"openclaw":{"emoji":"📄","requires":{"bins":[]},"os":["linux","darwin","win32"]}}
---

## When to Use

User needs to create, read, or edit Microsoft Word documents (.docx). Agent handles document formatting, styles, paragraphs, tables, images, headers/footers, and Office Open XML generation.

## Quick Reference

| Topic | File |
|-------|------|
| Setup | `setup.md` |
| Memory template | `memory-template.md` |

## Core Rules

### 1. DOCX is ZIP + XML
DOCX files are actually ZIP archives containing XML files. Never manually edit the XML; use proper libraries (python-docx, docx4j, etc.).

### 2. Paragraphs vs Runs
- **Paragraph**: Block-level container (line break)
- **Run**: Inline styling within paragraph
- Mixed styles require multiple runs in one paragraph

### 3. Styles Are Powerful
Use built-in styles (Normal, Heading 1-9) when possible. Custom styles require style definitions in document.xml.

### 4. Tables Are Grid Structures
Tables in DOCX are row-based. Each row contains cells, each cell contains paragraphs. Border styling requires explicit configuration.

### 5. Images Need Proper Relationship
Images must be added to the document's relationships (Part 2). Raw image data in media folder won't display without XML reference.

### 6. Track Changes and Comments
These are stored in separate XML parts. Use libraries that support reading/writing these if user needs them.

### 7. Cross-Platform Testing
LibreOffice may render DOCX differently than Word. Test with both when generating documents for wide distribution.

## Common Traps

- **Empty paragraphs** → Often appear as spacing; check run content
- **Numbering lists** → Complex numbering.xml; use libraries that handle it
- **Page breaks** → Section breaks vs page breaks; different XML types
- **Field codes** → MERGEFIELD, etc. stored as field instructions, not plain text
- **Embedded fonts** → May not render correctly on systems without those fonts
- **DOC vs DOCX** → DOC is binary (legacy); always prefer DOCX

## Format Limits

| Format | Max Size | Notes |
|--------|----------|-------|
| DOCX | ~512MB | Practical limit depends on content |
| DOC | ~32MB | Legacy binary format, avoid |

## Security & Privacy

**Data that stays local:**
- All document processing happens locally
- No external services called

**This skill does NOT:**
- Send data to external endpoints
- Require network access

## Related Skills

- `excel-xlsx` — Excel file handling
- `pdf` — PDF generation and manipulation

## Feedback

- Stay updated: `clawhub sync word-docx`
