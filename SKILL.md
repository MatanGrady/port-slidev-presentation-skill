---
name: slidev-presentation
description: Create Markdown-based presentations using Slidev with live preview and export to PDF/PNG. Use when building technical presentations, internal decks, or version-controlled slides. Triggers include "create a presentation", "build slides for [topic]", "Slidev deck", or "technical presentation".
---

# Slidev presentation

Create Markdown-based presentations using Slidev with live preview, syntax highlighting, and export capabilities.

## Required information

Gather before starting:
- Presentation topic/title
- Target audience
- Key points (3-7 main ideas)
- Code examples needed (yes/no)
- Brand style: **Port branded** (default) or generic

## Process

### 1. Set up the presentation with Port theme

Create the presentation folder and set up the theme:

```bash
mkdir -p outputs/presentations/[name]
```

Create `slides.md` with this frontmatter (adjust the relative path based on location):

```yaml
---
theme: ../../../.claude/skills/slidev-presentation/themes/port
title: Presentation Title
---
```

The Port theme provides:
- Pre-styled layouts (cover, section, default)
- Reusable components (Grid, FeatureCard, MetricCard, Tag, StepItem, ImpactBox, etc.)
- Consistent brand colors and typography

**See:** [themes/port/README.md](themes/port/README.md) for full component documentation.

### 2. Use template components (not custom CSS)

**CRITICAL: Never use inline Tailwind classes in slides.md.** All styling must go through theme components. This ensures consistency and makes slides easy to maintain.

| Instead of... | Use... |
|---------------|--------|
| `<div class="grid grid-cols-3 gap-4">` | `<Grid cols="3" gap="4">` |
| `<p class="text-lg text-gray-600">` | `<Paragraph>` |
| `<div class="mt-8">` | `<Space size="large" />` |
| `<p class="text-xl font-bold text-center">` | `<Highlight>` |
| `<img class="max-h-96 rounded-lg">` | `<Image size="large" />` |
| `<div class="bg-blue-100 rounded-xl p-5">` | `<FeatureCard color="blue">` |
| `<div class="bg-black text-white p-6">` | `<ImpactBox>` |
| `<span class="bg-blue-100 px-3 py-1 rounded-full">` | `<Tag color="blue">` |
| Video/content placeholder div | `<Placeholder title="..." />` |

**Available components:**

**Layout:**
- `Grid` - Responsive grid layout (cols, gap props)
- `Stack` - Vertical stacking with consistent gaps (gap: small/medium/large)
- `Space` - Vertical spacing between elements (size: small/medium/large)

**Text:**
- `Subtitle` - Muted text below headings
- `Paragraph` - Body text with proper margins (center, bold props)
- `Highlight` - Centered emphasized text for key questions (weight: light/normal/bold)
- `Note` - Italic muted text for caveats

**Cards:**
- `FeatureCard` - Colored card with icon (color, variant: default/pillar, size: default/compact)
- `MetricCard` - Big number with label
- `StepItem` - Numbered step with title
- `AgendaItem` - Colored agenda boxes

**Media:**
- `Image` - Images with consistent styling (src, size: small/medium/large/full, center, rounded)
- `PortLogo` - Port logo (type: svg/png, color: black/white, size)
- `Placeholder` - Content placeholder (title, subtitle)

**Accents:**
- `Tag` - Pill-shaped labels
- `ImpactBox` - Black box for key takeaways (center, spacing: default/small/none)
- `ColorDots` - Decorative cover element

**Example slide using components:**

```markdown
# Slide title

<Subtitle>Supporting context for the title</Subtitle>

<Space size="large" />

<Grid cols="2" gap="4">
  <Image src="/images/example.png" alt="Description" />
  <Stack>
    <FeatureCard icon="🎯" title="Point one" color="blue" size="compact">
      Brief description
    </FeatureCard>
    <FeatureCard icon="💡" title="Point two" color="green" size="compact">
      Another description
    </FeatureCard>
  </Stack>
</Grid>

<ImpactBox center>
  Key takeaway for the audience.
</ImpactBox>

<Note>Optional caveat or footnote.</Note>
```

### 3. Apply layouts

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

### 4. Add code blocks

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

### 5. Add speaker notes

Include notes below each slide using HTML comment:

```markdown
# Slide Title

Visible content

<!--
Speaker notes go here.
Only visible in presenter mode.
-->
```

### 6. Preview and export

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

## Output format

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

## Multi-slide editing

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

## Quality checklist

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

## Extending the theme

**Rule: If you can't build it with existing components, create a new component.**

When you need a pattern that doesn't exist:

1. **First check if existing components can work** - Most layouts use Grid + Stack + existing components
2. **If not, create a new component** in `themes/port/components/`
   - Add props for variations (size, color, spacing)
   - Include scoped styles in the component
   - Test it works in isolation
3. **Document the component** in `themes/port/README.md`

**Never:**
- Add inline Tailwind classes (`class="..."`) to slides.md
- Add inline `<style>` blocks to individual presentations
- Use raw HTML tags (`<div>`, `<p>`, `<img>`) with custom styling

**Why:** Theme components ensure consistency across all presentations, handle responsive behavior, and make maintenance easier. One style change in a component updates all slides using it.

## References

- [Port theme README](themes/port/README.md) - Full component documentation with examples
- [Layout troubleshooting](references/layout-troubleshooting.md) - Fixes for overflow, alignment, and common issues
- [Narrative framework](references/narrative-framework.md) - Andy Raskin's five-act structure for compelling presentations
- [Export guide](references/export-guide.md) - PDF, PNG, and PowerPoint export options
