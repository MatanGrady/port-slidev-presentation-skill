# Port Slidev presentation skill

A Claude Code skill for creating professional Markdown-based presentations using [Slidev](https://sli.dev/). Includes Port-branded templates, a custom theme, and best practices for technical presentations.

## What's included

- **SKILL.md** - Claude Code skill definition for AI-assisted presentation creation
- **Port theme** - Custom Slidev theme with Port branding, layouts, and components
- **Templates** - Ready-to-use slide templates for common presentation patterns
- **References** - Export guide, layout troubleshooting, and narrative framework

## Quick start

### Option 1: As a Claude Code skill

Copy to your Claude Code skills directory:

```bash
# Clone the repo
git clone https://github.com/MatanGrady/port-slidev-presentation-skill.git

# Copy to your skills folder
cp -r port-slidev-presentation-skill ~/.claude/skills/slidev-presentation
```

Then in Claude Code, just ask: "Create a presentation about [topic]"

### Option 2: As a standalone Slidev theme

Use the Port theme directly in any Slidev project:

```bash
# In your presentation folder
mkdir -p themes
cp -r port-slidev-presentation-skill/themes/port themes/

# Reference in your slides.md frontmatter
# theme: ./themes/port
```

### Option 3: Copy the template

Start from the template file:

```bash
cp port-slidev-presentation-skill/templates/port-template.md ./slides.md
npx @slidev/cli slides.md
```

## Port theme features

### Layouts

| Layout | Purpose |
|--------|---------|
| `cover` | Title slides with logo and decorative dots |
| `section` | Section dividers with optional big number |
| `default` | Standard content slides |
| `two-cols` | Two-column layout |
| `center` | Centered content |
| `statement` | Bold statement slides |

### Components

Pre-built Vue components for consistent styling:

- **MetricCard** - Display stats with labels
- **FeatureCard** - Feature highlights with icons
- **Tag** - Colored category pills (blue, pink, green, yellow, purple)
- **ImpactBox** - Black boxes for key outcomes
- **Grid** - Responsive grid layouts
- **StepNumber** - Numbered step indicators

### Color palette

| Element | Hex |
|---------|-----|
| Background | `#f8f9fa` |
| Cards | `#ffffff` |
| Primary text | `#000000` |
| Muted text | `#4b5563` |
| Border | `#e5e7eb` |

Tag colors (pastel):
- Blue: `#dbeafe`
- Pink: `#fce7f3`
- Green: `#dcfce7`
- Yellow: `#fef3c7`
- Purple: `#f3e8ff`

## Usage with Slidev

### Preview your presentation

```bash
npx @slidev/cli slides.md --port 3031
```

Access:
- Slides: http://localhost:3031/
- Presenter mode: http://localhost:3031/presenter/
- Overview: http://localhost:3031/overview/

### Export to PDF

```bash
npx @slidev/cli export slides.md --output presentation.pdf
```

### Export with click animations

```bash
npx @slidev/cli export slides.md --with-clicks --output detailed.pdf
```

### Export to PNG

```bash
npx @slidev/cli export slides.md --format png
```

## Template slide types

The template includes 17 slide variations:

**Title slides:**
1. Cover with gradient accent
2. Big statement (dark variant)
3. Section divider with number
4. Section divider (gradient background)

**Content slides:**
5. Icon grid (4 columns)
6. Quote slide
7. Big number reveal
8. Three pillars (aligned cards)
9. Before/After comparison
10. Stats grid with progress bars
11. Case study slide
12. Key takeaways

**Board-style slides:**
13. Metrics with chart placeholder
14. Two-column categories with avatars
15. Split metrics grid
16. Big centered statement
17. Timeline roadmap

## Customization

### Brand colors

Edit the CSS variables in your slides:

```css
:root {
  --port-bg: #f8f9fa;      /* Your background */
  --port-card: #ffffff;     /* Card backgrounds */
  --port-black: #000000;    /* Primary text */
  --port-muted: #4b5563;    /* Secondary text */
}
```

### Fonts

Change fonts in frontmatter:

```yaml
---
fonts:
  sans: Inter           # or your preferred font
  mono: Fira Code
  weights: '400,500,600,700'
---
```

### Add your logo

Place your logo in `public/images/` and update references:

```html
<img src="/images/your-logo.png" class="h-8" />
```

## Narrative framework

The skill includes Andy Raskin's five-act structure for compelling presentations:

1. **Old World** - Describe the problem
2. **Insight** - What changed (why now)
3. **New World** - Paint the vision
4. **Stakes** - Win big or lose
5. **Your Role** - How you help them win

See [references/narrative-framework.md](references/narrative-framework.md) for detailed guidance.

## Troubleshooting

Common issues and fixes are documented in [references/layout-troubleshooting.md](references/layout-troubleshooting.md):

- Panel overflow (content cut off)
- Horizontal alignment across cards
- Text wrapping in headers
- Impact box positioning

## Requirements

- Node.js 18+
- npx (comes with npm)

No global installation needed. Slidev runs via npx.

## File structure

```
slidev-presentation/
├── SKILL.md                    # Claude Code skill definition
├── README.md                   # This file
├── templates/
│   ├── port-template.md        # Full slide template (17 variations)
│   └── images/
│       └── port-logo.png
├── themes/
│   └── port/                   # Custom Slidev theme
│       ├── package.json
│       ├── styles/
│       ├── layouts/
│       └── components/
└── references/
    ├── export-guide.md         # PDF/PNG export options
    ├── layout-troubleshooting.md
    ├── narrative-framework.md
    └── port-theme.md           # Brand guidelines
```

## License

MIT

## Contributing

Feel free to open issues or PRs for:
- New slide layouts
- Theme improvements
- Bug fixes
- Documentation updates

---

Built for use with [Claude Code](https://claude.ai/claude-code) and [Slidev](https://sli.dev/).
