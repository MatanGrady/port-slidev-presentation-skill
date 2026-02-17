# Port Slidev theme

A reusable Slidev theme with Port branding, custom layouts, and pre-built components.

## Usage

Reference the theme in your presentation's frontmatter:

```yaml
---
theme: ../../../.claude/skills/slidev-presentation/themes/port
title: Your Presentation
---
```

Adjust the relative path based on your presentation's location.

## Layouts

| Layout | Props | Purpose |
|--------|-------|---------|
| `cover` | - | Title slide with centered content |
| `section` | `number` | Section divider with optional big number |
| `default` | - | Standard content slide |

### Section layout example

```markdown
---
layout: section
number: "01"
---

# Section title

<Subtitle>Optional subtitle</Subtitle>
```

## Components

### Grid

Responsive grid layout for organizing content.

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `cols` | Number/String | 2 | Number of columns |
| `gap` | Number/String | 6 | Gap between items (multiplied by 0.25rem) |

```html
<Grid cols="3" gap="4">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</Grid>
```

### Subtitle

Muted text positioned below the heading.

```html
# Slide title

<Subtitle>Supporting context for the heading</Subtitle>
```

### MetricCard

Big number with label, for statistics.

| Prop | Type | Required | Description |
|------|------|----------|-------------|
| `value` | String | Yes | The big number or metric |
| `label` | String | Yes | Description of the metric |

```html
<Grid cols="3">
  <MetricCard value="1000+" label="Microservices" />
  <MetricCard value="10k" label="Cloud resources" />
  <MetricCard value="7" label="Observability tools" />
</Grid>
```

### FeatureCard

Colored card with icon, title, and description. Supports optional tags.

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `icon` | String | "✨" | Emoji icon |
| `title` | String | Required | Card title |
| `color` | String | "blue" | blue, pink, green, purple, yellow, orange |
| `variant` | String | "default" | "default" or "pillar" (centered, white bg) |

```html
<Grid cols="3">
  <FeatureCard icon="👥" title="For teams" color="blue">
    Description text here
    <template #tags>
      <Tag color="purple">Tag 1</Tag>
    </template>
  </FeatureCard>
</Grid>
```

### StepItem

Numbered step with title and description. Use in a Grid for aligned steps.

| Prop | Type | Required | Description |
|------|------|----------|-------------|
| `n` | Number/String | Yes | Step number |
| `title` | String | Yes | Step title |

```html
<Grid cols="3">
  <StepItem n="1" title="Discovery">
    Understand customer problems
  </StepItem>
  <StepItem n="2" title="Definition">
    Define solutions with metrics
  </StepItem>
  <StepItem n="3" title="Delivery">
    Build and ship incrementally
  </StepItem>
</Grid>
```

### Tag

Pill-shaped label for categories or features.

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `color` | String | "blue" | blue, pink, green, yellow, purple, orange, dark |

```html
<div class="flex flex-wrap gap-2">
  <Tag color="blue">Context Lake</Tag>
  <Tag color="purple">Collaboration</Tag>
  <Tag color="green">Guardrails</Tag>
</div>
```

### AgendaItem

Colored box with icon and text, for agenda slides.

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `icon` | String | "📌" | Emoji icon |
| `color` | String | "blue" | blue, pink, green, purple, yellow, orange |

```html
<Grid cols="2">
  <div class="space-y-4">
    <AgendaItem icon="🏢" color="blue">Who we are</AgendaItem>
    <AgendaItem icon="🔥" color="pink">The problem</AgendaItem>
  </div>
  <div class="space-y-4">
    <AgendaItem icon="💡" color="green">The solution</AgendaItem>
    <AgendaItem icon="⚙️" color="yellow">How it works</AgendaItem>
  </div>
</Grid>
```

### ImpactBox

Black box with white text for key takeaways.

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `center` | Boolean | false | Center the text |

```html
<ImpactBox center>
  Key insight or outcome statement goes here
</ImpactBox>
```

### ColorDots

Decorative element for cover slides.

```html
# Presentation title

<Subtitle>Subtitle here</Subtitle>

<ColorDots />
```

## Brand colors

| Element | Background | Text |
|---------|------------|------|
| Page | `#f8f9fa` | - |
| Cards | `#ffffff` | `#1f2937` (gray-800) |
| Impact boxes | `#000000` | `#ffffff` |
| Muted text | - | `#6b7280` (gray-500) |

Tag colors: blue (`#dbeafe`), pink (`#fce7f3`), green (`#dcfce7`), yellow (`#fef3c7`), purple (`#f3e8ff`), orange (`#ffedd5`)

## Demo

See [slides.md](slides.md) for a complete example presentation using all components.

## Extending the theme

If you need a new component or layout that would be useful across presentations:

1. Create the component in `components/` folder
2. Test it in `slides.md`
3. Document it in this README
4. Update the SKILL.md if it represents a new pattern

Prefer extending the theme over adding custom inline styles to individual presentations.
