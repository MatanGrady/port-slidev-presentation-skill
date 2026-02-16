# Slidev Export Guide

Complete guide for exporting presentations to PDF, PNG, and other formats.

## Quick Export Commands

```bash
# Export to PDF (default)
npx @slidev/cli export slides.md

# Export with custom filename
npx @slidev/cli export slides.md --output my-presentation.pdf

# Export to PNG (one image per slide)
npx @slidev/cli export slides.md --format png

# Export to PowerPoint
npx @slidev/cli export slides.md --format pptx
```

## PDF Export Options

### Basic PDF Export

```bash
npx @slidev/cli export slides.md --output presentation.pdf
```

### High-Quality PDF

For print or professional distribution:

```bash
npx @slidev/cli export slides.md \
  --output presentation.pdf \
  --timeout 60000 \
  --with-clicks
```

### Export Specific Pages

```bash
# Export pages 1, 4-5, and 6
npx @slidev/cli export slides.md --range "1,4-5,6"

# Export first 5 slides only
npx @slidev/cli export slides.md --range "1-5"
```

### Dark Mode Export

```bash
npx @slidev/cli export slides.md --dark --output presentation-dark.pdf
```

### Transparent Background

For slides to overlay on other content:

```bash
npx @slidev/cli export slides.md --omit-background
```

## PNG Export Options

Export individual slides as images:

```bash
# Basic PNG export
npx @slidev/cli export slides.md --format png

# PNG with dark mode
npx @slidev/cli export slides.md --format png --dark

# PNG including click animations
npx @slidev/cli export slides.md --format png --with-clicks
```

## Click Animations

The `--with-clicks` flag creates separate pages/images for each click step:

```bash
# PDF with click animations expanded
npx @slidev/cli export slides.md --with-clicks --output animated.pdf
```

A slide with 3 click steps becomes 4 pages in the exported PDF.

## Frontmatter Configuration

Set default export filename in your slides:

```yaml
---
exportFilename: port-agentic-platform-overview
---
```

## Export Workflow Example

```bash
# 1. Navigate to presentation folder
cd outputs/presentations/my-deck

# 2. Preview first (optional)
npx @slidev/cli slides.md

# 3. Export PDF for sharing
npx @slidev/cli export slides.md --output my-deck.pdf

# 4. Export PNG for social media thumbnails
npx @slidev/cli export slides.md --format png --range "1"

# 5. Export with animations for detailed review
npx @slidev/cli export slides.md --with-clicks --output my-deck-detailed.pdf
```

## Troubleshooting

### Timeout Errors

For complex slides with many animations:

```bash
npx @slidev/cli export slides.md --timeout 120000
```

### Missing Fonts

Ensure fonts are loaded via CDN or locally available:

```yaml
---
fonts:
  sans: Inter
  provider: google
---
```

### Code Block Rendering Issues

If code blocks don't render correctly, ensure Shiki is configured:

```yaml
---
highlighter: shiki
---
```

## File Organization

After export, organize deliverables:

```
outputs/presentations/my-deck/
├── slides.md              # Source
├── my-deck.pdf            # Full PDF
├── my-deck-detailed.pdf   # PDF with click animations
├── slides-001.png         # Cover slide image
├── public/
│   └── images/
└── components/
```

## Best Practices

1. **Always preview before export**: `npx @slidev/cli slides.md`
2. **Use descriptive filenames**: Include date or version
3. **Export both PDF and title PNG**: PNG works for thumbnails/previews
4. **Increase timeout for complex decks**: Default 30s may not be enough
5. **Test click animations**: Use `--with-clicks` if animations are important
6. **Check font rendering**: Ensure chosen fonts work in PDF
