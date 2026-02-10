# markitdown-skill

📄 OpenClaw agent skill for converting documents to Markdown.

Wrapper and documentation for Microsoft's [MarkItDown](https://github.com/microsoft/markitdown) library.

**Author:** Karman Verma

## Features

- **10+ formats**: PDF, Word, PowerPoint, Excel, HTML, images, audio, YouTube
- **OCR support**: Extract text from images and scanned documents
- **Audio transcription**: Convert speech to text
- **YouTube transcripts**: Extract video captions
- **Batch processing**: Included Python script

## Install

### Via ClawHub
```bash
clawhub install markitdown-skill
```

### Manual
```bash
cd ~/.openclaw/skills
git clone https://github.com/karmanverma/markitdown-skill.git markitdown
pip install 'markitdown[all]'
```

## Quick Start

```bash
# Convert PDF
markitdown document.pdf -o output.md

# Fetch web docs
markitdown https://example.com/docs -o docs.md

# Batch convert
for file in docs/*.pdf; do
  markitdown "$file" -o "${file%.pdf}.md"
done
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

## Documentation

- [SKILL.md](SKILL.md) - Main skill documentation
- [USAGE-GUIDE.md](USAGE-GUIDE.md) - Detailed examples
- [reference.md](reference.md) - Full API reference
- [POST_INSTALL.md](POST_INSTALL.md) - Setup guide

## Why Use This?

**Use markitdown INSTEAD of curl/wget for documentation:**

| Tool | Output | Structure |
|------|--------|-----------|
| curl/wget | Raw HTML | ❌ Tags, scripts |
| **markitdown** | Clean markdown | ✅ Preserved |

## Credits

Built on [Microsoft MarkItDown](https://github.com/microsoft/markitdown) by the AutoGen Team.

## License

MIT
