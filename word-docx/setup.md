# Word / DOCX Skill Setup

## Prerequisites

This skill uses `python-docx` library for DOCX file handling.

## Installation

### Method 1: pip (Recommended)

```bash
pip install python-docx
```

### Method 2: conda

```bash
conda install -c conda-forge python-docx
```

## Library Options by Language

### Python
- **python-docx**: Most popular, actively maintained
- **docx2txt**: Extract text from DOCX
- **pypandoc**: Convert between formats via Pandoc

### Node.js
- **docx**: Programmatic DOCX generation
- **mammoth**: DOCX to HTML conversion

### Java
- **docx4j**: Full DOCX manipulation
- **Apache POI**: Supports DOCX (limited)

### R
- **officer**: Create and edit DOCX
- **readxl**: Read DOCX tables

## Verification

Test installation:
```python
from docx import Document
doc = Document()
doc.add_paragraph("Hello, World!")
doc.save("test.docx")
print("DOCX skill ready!")
```

## Common Issues

1. **"cannot import name 'Document'"** → Install python-docx correctly
2. **"Invalid or corrupt file"** → File may be DOC (not DOCX)
3. **"No style named 'Normal'"** → Use default paragraph style

## Next Steps

After setup, update your memory:
```
Edit ~/word-docx/memory.md with your preferences
```
