# Slidev Port theme: fresh start

## The problem

The current approach to building Slidev presentations requires writing verbose HTML:

```html
<!-- Too complex for LLMs to reliably reproduce -->
<p class="text-xl text-muted mt-4">Session for HR team</p>

<div class="grid grid-cols-2 gap-8 mt-8">
  <div class="space-y-4">
    <div class="card card-blue flex items-center gap-4">
      <span class="text-2xl">🏢</span>
      <span class="font-semibold text-gray-800">Who we are</span>
    </div>
  </div>
</div>
```

**Issues:**
1. Verbose - too many classes and nested divs
2. Error-prone - easy to forget or mistype classes
3. Hard for LLMs - complex patterns are unreliable to reproduce
4. No IntelliSense - no autocomplete for valid combinations

## The goal

Slides that look like this:

```markdown
---
layout: cover
---

# Port product overview

<Subtitle>Session for HR team | February 17, 2026</Subtitle>

---

# Agenda

<Grid cols="2">
  <AgendaItem icon="🏢" color="blue">Who we are</AgendaItem>
  <AgendaItem icon="👥" color="purple">R&D team structure</AgendaItem>
  <AgendaItem icon="🔥" color="pink">The problem we solve</AgendaItem>
  <AgendaItem icon="⚙️" color="yellow">Tech stack</AgendaItem>
</Grid>
```

---

## Proven technical approach (2026-02-15)

### What works

**1. Styles go IN the layout files, not separate CSS**

This is the critical insight. Previous sessions failed for 30+ minutes trying:
- `styles/index.css` - not loaded automatically
- `setup/main.ts` importing CSS - breaks the page completely

**What works:** Non-scoped `<style>` block directly in the layout Vue file:

```vue
<!-- layouts/cover.vue - THE WORKING PATTERN -->
<template>
  <div class="slidev-layout cover h-full flex flex-col justify-center px-12">
    <slot />
  </div>
</template>

<style>
:root {
  --port-bg: #f8f9fa;
}

.slidev-layout {
  background: var(--port-bg);
}

.slidev-layout h1 {
  font-weight: 700;
  font-size: 2.5rem;
  color: #000;
}
</style>
```

**2. Theme reference for local development**

```yaml
---
theme: ./
title: Port Theme Test
layout: cover
---
```

The `theme: ./` tells Slidev to use the current directory as the theme.

**3. Component auto-registration works**

Components in `components/` folder are auto-registered. No manual imports needed:
- `components/Subtitle.vue` → `<Subtitle>`
- `components/Grid.vue` → `<Grid>`

**4. Tailwind classes in templates**

Use Tailwind utility classes directly in the template, matching Slidev's built-in patterns:
- `h-full` for height inheritance (not `100%` or `100vh`)
- `flex flex-col justify-center` for vertical centering
- `px-12` for horizontal padding

### What doesn't work

| Approach | Result |
|----------|--------|
| `styles/index.css` separate file | Not loaded |
| `setup/main.ts` importing CSS | Breaks page completely |
| Scoped styles in layouts | Breaks Slidev's scaling |
| `min-height: 100vh` | Doesn't work with Slidev |
| `100%` height | Doesn't inherit correctly |

---

## Current progress

### Phase 1: COMPLETE ✅

Working theme with:
- `layouts/cover.vue` - vertical centering, h1 styling
- `layouts/default.vue` - top-aligned content
- `components/Subtitle.vue` - gray subtitle text

**Verified:** Screenshot shows title vertically centered, bold, with styled subtitle.

### Phase 2: COMPLETE ✅

Components added:
- [x] `Grid.vue` - responsive grid wrapper with cols prop
- [x] `AgendaItem.vue` - icon + text card with color variants (blue, pink, green, purple, yellow, orange)

**Verified:** Agenda slide renders correctly with 2-column grid of colored cards.

### Phase 3: COMPLETE ✅

Components added:
- [x] `MetricCard.vue` - number + label, centered (padding adjusted for compact height)
- [x] `FeatureCard.vue` - icon + title + description with color variants
- [x] `ImpactBox.vue` - dark background callout with center option
- [x] `Tag.vue` - pill labels with color variants
- [x] `StepNumber.vue` - numbered gradient circle

**Verified:** Slide 3 (Engineering chaos) renders correctly with 3x2 grid of MetricCards and ImpactBox at bottom with proper spacing.

---

## Phase 4: visual parity gaps (2026-02-15)

Comparison of theme (port 3031) vs HR original (port 3032) revealed these gaps:

### Gap 1: cover slide (slide 1) - h1 too small ✅ FIXED
- **HR**: Title ~4rem, has colored dots bottom-right
- **Theme**: Title ~2.5rem, no dots
- **Fix**: Increased h1 in cover.vue to 3.5rem, added ColorDots component

### Gap 2: section divider missing (HR slide 3) ✅ FIXED
- **HR**: Big "01" number left + title/subtitle right, centered
- **Theme**: Created `layouts/section.vue`
- **Usage**: `layout: section` + `number: "01"` in frontmatter

### Gap 3: FeatureCard missing tags (theme slide 4 vs HR slide 10) ✅ FIXED
- **HR**: Cards have tags at bottom, side by side
- **Theme**: Added `#tags` named slot to FeatureCard
- **Usage**: `<template #tags><Tag color="blue">Label</Tag></template>`
- **Also fixed**: H1 size reduced to 2.5rem for non-cover slides
- **Also fixed**: Tags side by side with smaller gap (0.375rem)
- **Also fixed**: Consistent vertical spacing
  - h1 has `margin-bottom: 2.5rem`
  - Subtitle uses `margin-top: -2rem` + `margin-bottom: 0.25rem`
  - Content starts at same position with or without subtitle

### Gap 4: StepItem component (theme slide 6 vs HR slide 11) ✅ FIXED
- **HR**: Numbered steps with large titles, horizontally aligned rows
- **Theme**: Created `StepItem.vue` component with CSS subgrid
- **Key insight**: Use `display: grid; grid-template-rows: subgrid; grid-row: span 3;` to align number/title/description rows across items
- **Usage**: `<StepItem n="1" title="Context Lake">Description here</StepItem>`
- **Supports**: 3-column (1x3) and 2-column (2x2) grid layouts

---

## Phase 5: session update (2026-02-16)

### Section layout refined
- Fixed subtitle positioning in `layouts/section.vue`
- Subtitle now properly appears below title (not overlapping)
- Large gradient number preserved (6rem, blue-purple gradient)

### StepItem component created
New component combining number + title + description with CSS subgrid alignment:
- Numbers align horizontally across all items
- Titles align horizontally (even when wrapping)
- Descriptions align horizontally
- Gradient circles match HR design
- Max-width 300px with `margin: 0 2rem auto` for compact, centered items

### Test slides updated
- Slide 6: 3-column StepItem layout
- Slide 7: 2x2 StepItem variation demo (narrower items with breathing room)

---

## HR slides to implement (minimum CSS)

| HR Slide | Content | Priority |
|----------|---------|----------|
| 4 | Who we are (company stats) | P1 |
| 6 | Developer role changing (timeline) | P2 |
| 8 | Agentic chaos | P2 |
| 12 | Product pillars (6 cards) | P1 |
| 14 | Data team | P2 |
| 15 | Platform team | P2 |
| 16 | AI Solutions team | P2 |
| 18 | Tech stack | P1 |
| 20 | What makes Port R&D unique | P1 |
| 21 | What we look for in candidates | P1 |
| 22 | Questions slide | P1 |

---

## Workflow for continuing

### Iterative slide-by-slide approach

1. **Pick one slide** from the HR presentation
2. **Duplicate it** into the theme's test slides.md
3. **Identify components needed** (what HTML patterns repeat?)
4. **Build the component** in `components/`
5. **Replace HTML with component** in the slide
6. **Screenshot to verify** it looks correct
7. **Move to next slide**

### When to use tasks

This work consumes significant context. Use Task agents when:
- Starting a new phase after completing previous one
- Building multiple components in parallel
- Searching for Slidev patterns or documentation

### Session handoff

When ending a session, update this plan with:
1. Which slides are converted
2. Which components exist
3. Any new patterns discovered
4. What to do next

---

## Theme file structure

```
themes/port/
├── package.json           # Theme metadata
├── slides.md              # Test presentation (8 slides)
├── components/
│   ├── Subtitle.vue       # ✅ Gray subtitle text
│   ├── Grid.vue           # ✅ Responsive grid (cols, gap props)
│   ├── AgendaItem.vue     # ✅ Icon + text card with colors
│   ├── MetricCard.vue     # ✅ Number + label card
│   ├── FeatureCard.vue    # ✅ Icon + title + description + tags slot
│   ├── ImpactBox.vue      # ✅ Dark background callout
│   ├── Tag.vue            # ✅ Pill labels with colors
│   ├── StepNumber.vue     # ✅ Numbered gradient circle (standalone)
│   ├── StepItem.vue       # ✅ Number + title + description with subgrid alignment
│   └── ColorDots.vue      # ✅ Decorative dots for cover slides
├── layouts/
│   ├── cover.vue          # ✅ Vertical centering (includes global styles)
│   ├── default.vue        # ✅ Top-aligned content
│   └── section.vue        # ✅ Section divider (big number + title/subtitle)
└── styles/
    └── index.css          # ⚠️ Not used (styles are in cover.vue)
```

---

## Reference slides

Source: `projects/hr-product-presentation/resources/presentations/hr-session/slides.md`

| Slide | Type | Components needed |
|-------|------|-------------------|
| 1 | Cover | Subtitle |
| 2 | Agenda | Grid, AgendaItem |
| 3 | Company stats | Grid, MetricCard |
| 4 | Problem | ImpactBox, list |
| ... | ... | ... |

---

## Prompt for new session

Copy this to start fresh:

---

**Task: Continue building Slidev Port theme**

**Context:**
- Theme location: `.claude/skills/slidev-presentation/themes/port/`
- Plan: `.claude/skills/slidev-presentation/REBUILD-PLAN.md`
- Reference design: `projects/hr-product-presentation/resources/presentations/hr-session/slides.md`

**Current state:**
- Phase 1-4 COMPLETE: All core components and layouts working
- Phase 5 COMPLETE (2026-02-16): StepItem with subgrid, section layout refined

**All 11 components working:**
`Subtitle`, `Grid`, `AgendaItem`, `MetricCard`, `FeatureCard`, `ImpactBox`, `Tag`, `StepNumber`, `StepItem`, `ColorDots`

**3 layouts working:**
`cover`, `default`, `section`

**Critical technical notes (learned from previous failures):**
1. Put styles in layout Vue files using non-scoped `<style>` blocks
2. Do NOT create setup/main.ts - it breaks the page
3. Do NOT rely on styles/index.css - it won't be loaded
4. Use `theme: ./` in slides.md frontmatter for local testing
5. Use `h-full` for height, not `100%` or `100vh`
6. Import `computed` from `vue` when using computed styles in Grid.vue
7. Use CSS subgrid (`grid-template-rows: subgrid; grid-row: span 3;`) for row alignment across grid items

**Workflow:**
1. Start Slidev: `cd themes/port && npx @slidev/cli --port 3031`
2. Make changes to components/layouts
3. Screenshot to verify (hot reload works)
4. One component at a time, test before adding more

**HR slides to implement (P1 first):**
4, 12, 18, 20, 21, 22 (P1) then 6, 8, 14, 15, 16 (P2)

---
