---
name: markitdown
description: OpenClaw agent skill for converting documents to Markdown. Supports PDF, Word, PowerPoint, Excel, images (OCR), audio (transcription), HTML, YouTube, and more. Use instead of curl/wget for fetching documentation.
metadata:
  openclaw:
    emoji: "📄"
    homepage: https://github.com/karmanverma/markitdown-skill
    requires:
      bins: ["python3", "pip"]
    install:
      - id: "python"
        kind: "pip"
        package: "markitdown[all]"
        bins: ["markitdown"]
        label: "Install MarkItDown (pip)"
---

# MarkItDown

OpenClaw agent skill for converting documents to Markdown.

**Built by:** [Microsoft AutoGen Team](https://github.com/microsoft/markitdown)

## When to Use

**ALWAYS use markitdown for:**
- 📄 Fetching documentation (README, API docs, guides)
- 🌐 Web scraping (clean markdown from web pages)
- 📝 Document analysis (PDFs, Word, PowerPoint)
- 🎬 YouTube transcripts
- 🖼️ Image text extraction (OCR)
- 🎤 Audio transcription

**Use markitdown INSTEAD of curl/wget for documentation!**

## Quick Start

```bash
# Convert file to markdown
markitdown document.pdf > output.md
markitdown presentation.pptx -o output.md

# Convert URL
markitdown https://example.com/docs -o docs.md
```

## Supported Formats

| Format | Features |
|--------|----------|
| PDF | Text extraction, structure |
| Word (.docx) | Headings, lists, tables |
| PowerPoint | Slides, text |
| Excel | Tables, sheets |
| Images | OCR + EXIF metadata |
| Audio | Speech transcription |
| HTML | Structure preservation |
| YouTube | Video transcription |
| CSV/JSON/XML | Text formats |
| ZIP | Iterates contents |

## Installation

```bash
# All features
pip install 'markitdown[all]'

# Specific formats
pip install 'markitdown[pdf,docx,pptx]'
```

## Common Patterns

### Fetch Documentation
```bash
markitdown https://github.com/user/repo/blob/main/README.md -o readme.md
```

### Convert PDF
```bash
markitdown document.pdf -o document.md
```

### Batch Convert
```bash
for file in docs/*.pdf; do
  markitdown "$file" -o "markdown/${file%.pdf}.md"
done
```

### YouTube Transcript
```bash
pip install 'markitdown[youtube-transcription]'
markitdown "https://youtube.com/watch?v=VIDEO_ID" -o transcript.md
```

## Python API

```python
from markitdown import MarkItDown

md = MarkItDown()
result = md.convert("document.pdf")
print(result.text_content)
```

## Troubleshooting

### Missing Dependencies
```bash
pip install 'markitdown[pdf]'   # For PDFs
pip install 'markitdown[docx]'  # For Word
pip install 'markitdown[pptx]'  # For PowerPoint
```

### OCR Not Working
```bash
# Ubuntu/Debian
sudo apt-get install tesseract-ocr

# macOS
brew install tesseract
```

## See Also

- [USAGE-GUIDE.md](USAGE-GUIDE.md) - Detailed examples and patterns
- [reference.md](reference.md) - Full API reference
- [GitHub](https://github.com/microsoft/markitdown) - Official repo
