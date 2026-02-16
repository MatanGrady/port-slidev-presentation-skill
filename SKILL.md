---
name: slidev-presentation
description: Create Markdown-based presentations using Slidev with live preview and export to PDF/PNG. Use when building technical presentations, internal decks, or version-controlled slides. Triggers include "create a presentation", "build slides for [topic]", "Slidev deck", or "technical presentation".
---

# Slidev Presentation

Create Markdown-based presentations using Slidev with live preview, syntax highlighting, and export capabilities.

## Required Information

Gather before starting:
- Presentation topic/title
- Target audience
- Key points (3-7 main ideas)
- Code examples needed (yes/no)
- Brand style: **Port branded** (default) or generic

## Process

### 1. Copy the Port template

Start by copying the Port template to your presentation folder:

```bash
mkdir -p outputs/presentations/[name]
cp .claude/skills/slidev-presentation/templates/port-template.md outputs/presentations/[name]/slides.md
```

The template includes:
- **4 title slide variations** (cover, section divider, numbered section, quote opener)
- **7 content slide variations** (two-column, before/after, feature cards, stats, takeaways, comparison table, code)
- **3 creative slides** (timeline, workflow comparison, architecture diagram)

Delete unused slides and customize the remaining ones for your presentation.

### 2. Customize frontmatter

Update the frontmatter at the top of your slides.md:

```yaml
---
theme: default
title: Presentation Title
info: |
  Port - Agentic Engineering Platform
author: Matan Grady
fonts:
  sans: Inter
  mono: Fira Code
  weights: '400,500,600,700'
highlighter: shiki
transition: slide-left
exportFilename: presentation-name
---
```

Each `---` on its own line creates a new slide.

### 2. Add Port Brand Styles

Add this style block to your first slide for Port branding:

```html
<style>
:root {
  --port-bg: #f8f9fa;
  --port-card: #ffffff;
  --port-black: #000000;
  --port-muted: #6b7c93;
  --port-border: #e5e7eb;
}

.slidev-layout { background: var(--port-bg); }
h1 { font-weight: 700; color: var(--port-black); }
h2, h3 { font-weight: 600; color: var(--port-black); }
</style>
```

See [references/port-theme.md](references/port-theme.md) for complete brand guidelines including case study templates.

### 3. Apply Layouts

Add `layout` frontmatter per slide:

| Layout | Purpose |
|--------|---------|
| `cover` | Title slide |
| `default` | Standard content |
| `two-cols` | Two columns |
| `image-right` | Image on right side |
| `center` | Centered content |
| `section` | Section divider |

Two-column example:

```markdown
---
layout: two-cols
---

# Left Column

Content here

::right::

# Right Column

More content
```

### 4. Add Code Blocks

Use line highlighting for step-by-step reveals:

```markdown
```python {1-3|5-7}
# Lines 1-3 highlighted first
def example():
    pass

# Then lines 5-7
def another():
    pass
```
```

### 5. Add Speaker Notes

Include notes below each slide using HTML comment:

```markdown
# Slide Title

Visible content

<!--
Speaker notes go here.
Only visible in presenter mode.
-->
```

### 6. Preview and Export

When the user asks to "run" the presentation:

1. **Verify the slides compile** by running Slidev once to check for errors
2. **Provide the terminal command** for the user to run themselves (don't run it in background)
3. **Always use a random port** (e.g., 3031-3099) since port 3030 is often occupied when working with multiple presentations

```bash
# Verify slides compile (run this to check for errors)
cd outputs/presentations/[name] && npx @slidev/cli slides.md --port [random-port] --open false

# Then provide user with command to run:
cd outputs/presentations/[name] && npx @slidev/cli slides.md --port [random-port]
```

The dev server provides:
- **Slides**: http://localhost:[port]/
- **Presenter mode**: http://localhost:[port]/presenter/
- **Overview**: http://localhost:[port]/overview/

**Export commands:**

```bash
# Export to PDF
npx @slidev/cli export slides.md --output presentation.pdf

# Export to PNG (one per slide)
npx @slidev/cli export slides.md --format png

# Export with click animations expanded
npx @slidev/cli export slides.md --with-clicks --output detailed.pdf
```

See [references/export-guide.md](references/export-guide.md) for complete export options.

## Port Brand Quick Reference

| Element | Value |
|---------|-------|
| Page Background | `#f8f9fa` (light gray) |
| Cards | `#ffffff` with `border-gray-200` |
| Impact Boxes | `#000000` bg, white text |
| Muted Text | `#4b5563` (gray-600, readable on light bg) |
| Card Text | `text-gray-800` or `text-gray-700` |
| Tag Blue | `#dbeafe` |
| Tag Pink | `#fce7f3` |
| Tag Green | `#dcfce7` |
| Font | Inter (sans), Fira Code (mono) |

### Readability rules

1. **Use explicit text colors on cards** - Don't rely on inheritance. Add `text-gray-800` for headings, `text-gray-700` for body text.
2. **Muted text must be `#4b5563`** - The old `#6b7c93` is too light on `#f8f9fa` background.
3. **For multi-row layouts, use compact padding** - Use `py-2` instead of `py-4` when stacking rows vertically.
4. **Test light backgrounds** - If text looks faint, add explicit `text-gray-700` or darker.

Port case study card:
```html
<div class="bg-white p-6 rounded-lg border border-gray-200">
  <p class="text-[#6b7c93] font-semibold mb-2">Before</p>
  <p>Problem with <strong>key pain bolded</strong>.</p>
</div>
```

Port impact box:
```html
<div class="bg-black text-white p-6 rounded-lg">
  Impact: Metric X → Y; outcome achieved.
</div>
```

## Output Format

Each presentation folder contains:

```
outputs/presentations/[name]/
├── slides.md          # Main presentation file
├── [name].pdf         # Exported PDF
├── public/            # Images and assets
│   └── images/
│       └── port-logo.svg
└── components/        # Custom Vue components (optional)
```

## Multi-slide editing workflow

When making changes across multiple slides, use the Task tool to spawn sub-agents. This preserves your main context and allows parallel edits.

**Pattern:**
```
Task(subagent_type="general-purpose", prompt="Edit slide X in [file] to [specific change]")
```

**When to use sub-agents:**
- 3+ slides need changes
- Each slide has independent fixes
- User provides a list of feedback items

**Instructions for sub-agents:**
- Give specific, text-only instructions (no code blocks needed)
- Describe the exact change: what element, what property, what value
- Reference line numbers or slide numbers for clarity

## Quality standards

**Structure:**
- [ ] One main idea per slide
- [ ] Port brand colors applied
- [ ] Consistent layout usage throughout
- [ ] No walls of text (max 5-7 bullet points)

**Layout:**
- [ ] No panel overflow (see [troubleshooting guide](references/layout-troubleshooting.md))
- [ ] Cards align horizontally (use flex-col + min-height + mt-auto)
- [ ] Compact sizing for 4+ items (py-2, gap-2 instead of py-8, gap-8)

**Content:**
- [ ] Text is specific, not generic
- [ ] Descriptions are down-to-earth
- [ ] No marketing speak or inflated language
- [ ] Follow writing guidelines for all text

## Port theme

The Port theme is a reusable Slidev theme with Port branding, custom layouts, and pre-built components.

**Location:** `.claude/skills/slidev-presentation/themes/port/`

**Usage:** In your presentation's frontmatter, reference the theme with a relative path:

```yaml
---
theme: ../../../.claude/skills/slidev-presentation/themes/port
title: Your Presentation
---
```

Adjust the relative path based on your presentation's location.

**Available layouts:**
- `cover` - Title slides (props: `showLogo`, `showDots`)
- `section` - Section dividers with optional big number (props: `number`)
- `two-cols` - Two-column layout (props: `gap`)
- `center` - Centered content
- `statement` - Bold statement slides (props: `dark`)
- `default` - Standard content slides

**See:** [themes/port/README.md](themes/port/README.md) for full component documentation and usage examples.

## References

- [Port template](templates/port-template.md) - Complete slide template with 14 layout variations
- [Port theme README](themes/port/README.md) - Full theme documentation with layouts and components
- [Layout troubleshooting](references/layout-troubleshooting.md) - Fixes for overflow, alignment, and common issues
- [Narrative framework](references/narrative-framework.md) - Andy Raskin's five-act structure for compelling presentations
- [Port theme guide](references/port-theme.md) - Complete brand colors, styles, and templates
- [Export guide](references/export-guide.md) - PDF, PNG, and PowerPoint export options

## Adding new slide styles

When you create a new slide layout that works well, consider adding it back to the template. The template should grow over time to include more variations that match Port's brand.
