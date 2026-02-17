# Port theme roadmap

Future enhancements to reduce inline HTML and improve slide authoring.

## Completed

- [x] Move CSS from template to theme (`styles/index.css`)

## High priority components

These patterns appear frequently in the template and would benefit most from componentization.

### BigNumber

Full-slide stat reveal with headline and context.

**Current pattern:**
```html
<div class="flex items-center justify-center h-full">
  <div class="text-center">
    <div class="big-number mb-4">47%</div>
    <h2 class="text-3xl font-bold mb-4">Supporting headline</h2>
    <p class="text-muted text-lg max-w-xl mx-auto">Context</p>
  </div>
</div>
```

**Proposed:**
```html
<BigNumber value="47%" headline="Supporting headline" context="Context" />
```

### Quote

Testimonial with avatar and attribution.

**Current pattern:**
```html
<div class="quote-box max-w-3xl">
  <div class="text-4xl text-purple-300 mb-4">"</div>
  <p class="text-2xl font-medium leading-relaxed">Quote text</p>
  <div class="flex items-center gap-4 mt-8">
    <div class="w-12 h-12 rounded-full bg-purple-100 flex items-center justify-center text-xl">👤</div>
    <div>
      <p class="font-semibold">Name</p>
      <p class="text-muted text-sm">Title</p>
    </div>
  </div>
</div>
```

**Proposed:**
```html
<Quote author="Name" title="Title" avatar="👤">
  Quote text here
</Quote>
```

### Comparison

Before/after two-column layout.

**Current pattern:** ~40 lines of HTML with emoji-badge, cards, impact-box

**Proposed:**
```html
<Comparison beforeLabel="Before" afterLabel="After">
  <template #before>
    <ComparisonItem label="Metric 1" value="Old" />
    <ComparisonItem label="Metric 2" value="Old" />
  </template>
  <template #after>
    <ComparisonItem label="Metric 1" value="New" positive />
    <ComparisonItem label="Metric 2" value="New" positive />
  </template>
</Comparison>
```

### IconGrid

4-column layout with icon circles and descriptions.

**Current pattern:**
```html
<div class="grid grid-cols-4 gap-6">
  <div class="text-center">
    <div class="icon-circle icon-blue mx-auto mb-4">🎫</div>
    <strong>Point 1</strong>
    <p class="text-sm text-muted mt-2">Description</p>
  </div>
  <!-- repeat 3 more times -->
</div>
```

**Proposed:**
```html
<IconGrid>
  <IconGridItem icon="🎫" color="blue" title="Point 1">Description</IconGridItem>
  <IconGridItem icon="📚" color="pink" title="Point 2">Description</IconGridItem>
  <IconGridItem icon="🧠" color="green" title="Point 3">Description</IconGridItem>
  <IconGridItem icon="⏰" color="purple" title="Point 4">Description</IconGridItem>
</IconGrid>
```

## Medium priority components

### SectionDivider

Big number with section title (currently exists as layout, could be enhanced).

**Proposed enhancement:**
```html
<SectionDivider number="01" title="Section" subtitle="Description">
  <Tag color="blue">Tag 1</Tag>
  <Tag color="pink">Tag 2</Tag>
</SectionDivider>
```

### Badge

Emoji badge with label (the `.emoji-badge` pattern).

**Current pattern:**
```html
<div class="emoji-badge">
  <span>🏢</span>
  <span>Customer Story</span>
</div>
```

**Proposed:**
```html
<Badge icon="🏢">Customer Story</Badge>
```

### StatCard

Stat with optional progress bar.

**Current pattern:**
```html
<div class="card text-center py-8">
  <div class="stat-number">90%</div>
  <div class="stat-label">Metric label</div>
  <div class="progress-bar mt-4 w-full">
    <div class="progress-fill" style="width: 90%"></div>
  </div>
</div>
```

**Proposed:**
```html
<StatCard value="90%" label="Metric label" progress="90" />
```

### SlideFooter

Footer with logo and meeting name (board style).

**Current pattern:**
```html
<div class="slide-footer">
  <img src="/images/port-logo.png" alt="Port" />
  <span class="meeting-name">Meeting name</span>
</div>
```

**Proposed:**
```html
<SlideFooter meeting="Meeting name" />
```

## Lower priority

### Timeline

Roadmap with quarter markers and positioned items. Complex layout that would benefit from abstraction but is used less frequently.

### CaseStudy

Customer story slide with before/after and impact. Specific layout that combines several patterns.

### DarkSlide

Wrapper component or layout for dark background slides. Currently uses `.dark-slide` class on a div.

### CategoryPill

Pill with avatar stack. Niche use case but repeated in board-style slides.

## Implementation notes

When creating new components:

1. Add component to `themes/port/components/`
2. Export props interface for type safety
3. Use CSS classes from `styles/index.css` (don't add new inline styles)
4. Update `themes/port/README.md` with usage examples
5. Update template to demonstrate the component
6. Keep slot-based flexibility where content varies

## CSS classes available

These classes are defined in `styles/index.css` and available for use in components:

**Layout:** `.dark-slide`, `.gradient-blue`, `.gradient-pink`, `.gradient-green`, `.gradient-area-light`

**Typography:** `.big-number`, `.stat-number`, `.stat-label`, `.text-muted`, `.text-primary`, `.text-secondary`

**Cards:** `.card`, `.card-hover`, `.card-compact`, `.card-blue`, `.card-pink`, `.card-green`, `.card-yellow`, `.card-purple`, `.accent-*`

**Boxes:** `.impact-box`, `.success-box`, `.quote-box`, `.statement-card`

**Tags:** `.tag`, `.tag-blue`, `.tag-pink`, `.tag-green`, `.tag-yellow`, `.tag-purple`, `.tag-orange`, `.tag-dark`, `.tag-neutral`

**Icons:** `.step-number`, `.icon-circle`, `.icon-*`

**Badges:** `.emoji-badge`, `.category-pill`, `.avatar-stack`

**Metrics:** `.metric-card`, `.metric-label`, `.metric-value`, `.metric-sub`

**Progress:** `.progress-bar`, `.progress-fill`

**Layout elements:** `.header-logo`, `.slide-footer`, `.dots-accent`, `.shape-circle`, `.shape-square`
