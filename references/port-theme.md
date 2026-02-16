# Port brand theme for slidev

Use this configuration to create presentations matching Port's official pitch deck style.

## Port pitch deck design system

### Color palette

| Element | Color | Hex |
|---------|-------|-----|
| Background | Light gray | `#f8f9fa` |
| Cards/Content boxes | White | `#ffffff` |
| Primary text | Black | `#000000` |
| Secondary text (Before/After labels) | Muted gray | `#4b5563` |
| Impact boxes | Solid black | `#000000` |
| Impact text | White | `#ffffff` |
| Borders | Light gray | `#e5e7eb` |

### Tag/chip colors (pastel)

| Category | Background | Use for |
|----------|------------|---------|
| Blue | `#dbeafe` | Context, Permissions, primary concepts |
| Pink | `#fce7f3` | Actions, Automations |
| Green | `#dcfce7` | Guardrails, positive outcomes |
| Yellow | `#fef3c7` | API, MCP, technical elements |
| Purple | `#f3e8ff` | Collaboration, human elements |
| Orange | `#ffedd5` | Warnings, attention items |

### Typography

- **Font**: Inter (or system sans-serif)
- **Headings**: Bold/Semibold, black
- **Body**: Regular weight, black or dark gray
- **Tags**: Medium weight, darker shade of tag color

## Frontmatter configuration

```yaml
---
theme: default
title: Your Presentation Title
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

## Global styles

Add to your first slide:

```html
<style>
:root {
  --port-bg: #f8f9fa;
  --port-card: #ffffff;
  --port-black: #000000;
  --port-text-muted: #4b5563;
  --port-border: #e5e7eb;

  /* Tag colors */
  --port-tag-blue: #dbeafe;
  --port-tag-pink: #fce7f3;
  --port-tag-green: #dcfce7;
  --port-tag-yellow: #fef3c7;
  --port-tag-purple: #f3e8ff;
}

/* Page background */
.slidev-layout {
  background: var(--port-bg);
}

/* Headings */
h1 { font-weight: 700; color: var(--port-black); }
h2, h3 { font-weight: 600; color: var(--port-black); }

/* Muted labels */
.text-muted { color: var(--port-text-muted); }
</style>
```

## Slide templates

### Cover slide

```markdown
---
layout: cover
class: bg-[#f8f9fa]
---

<div class="flex items-center gap-4 absolute top-8 left-12">
  <img src="/images/port-logo.svg" class="h-8" />
</div>

<div class="flex flex-col items-start justify-center h-full pl-12">
  <img src="/images/port-logo.svg" class="h-24 mb-8" />
  <h1 class="text-5xl font-bold text-black">Accelerate your</h1>
  <h1 class="text-5xl font-bold text-black">engineering <span class="font-normal">velocity</span></h1>
</div>
```

### Before/after case study

```markdown
---
class: bg-[#f8f9fa]
---

<div class="flex items-center justify-between mb-8">
  <img src="/images/customer-logo.svg" class="h-8" />
  <div class="flex gap-2">
    <span class="px-3 py-1 bg-white border border-gray-200 rounded-full text-sm">Industry</span>
    <span class="px-3 py-1 bg-white border border-gray-200 rounded-full text-sm">~1K employees</span>
    <span class="px-3 py-1 bg-white border border-gray-200 rounded-full text-sm">X Engineers</span>
  </div>
</div>

<div class="grid grid-cols-2 gap-6 mb-6">
  <div class="bg-white p-6 rounded-lg border border-gray-200">
    <p class="text-[#6b7c93] font-semibold mb-3">Before</p>
    <p class="text-black">Problem description with <strong>key pain points bolded</strong>.</p>
  </div>
  <div class="bg-white p-6 rounded-lg border border-gray-200">
    <p class="text-[#6b7c93] font-semibold mb-3">After</p>
    <p class="text-black">Solution with <strong>key benefits bolded</strong>.</p>
  </div>
</div>

<div class="bg-black text-white p-6 rounded-lg mb-6">
  <p class="text-lg">Impact: Metric went from X → Y; additional outcome.</p>
</div>

<div class="bg-white p-6 rounded-lg border border-gray-200">
  <p class="text-black italic">"Customer quote that shows the key value."</p>
  <p class="text-right text-gray-600 mt-4 font-medium">Role Title</p>
</div>
```

### Tag/chip components

```html
<!-- Blue tag -->
<span class="px-3 py-1 bg-[#dbeafe] text-blue-800 rounded-full text-sm font-medium">
  Software catalog & Context
</span>

<!-- Pink tag -->
<span class="px-3 py-1 bg-[#fce7f3] text-pink-800 rounded-full text-sm font-medium">
  Self-service actions
</span>

<!-- Green tag -->
<span class="px-3 py-1 bg-[#dcfce7] text-green-800 rounded-full text-sm font-medium">
  Guardrails
</span>

<!-- Yellow tag -->
<span class="px-3 py-1 bg-[#fef3c7] text-yellow-800 rounded-full text-sm font-medium">
  API
</span>
```

### Impact box

```html
<div class="bg-black text-white p-6 rounded-lg">
  <p class="text-lg font-medium">
    Impact: MTTR went from 2 weeks → 30 min; ~50% of tech-debt workload automated.
  </p>
</div>
```

### Quote box

```html
<div class="bg-white p-6 rounded-lg border border-gray-200">
  <p class="text-black italic text-lg">
    "We offloaded repetitive tickets while keeping humans in the loop for approvals—so
    <strong>engineers could focus on high-value tasks</strong>."
  </p>
  <p class="text-right text-gray-600 mt-4 font-medium">Head of Platform</p>
</div>
```

### Two workflow columns

```markdown
---
class: bg-[#f8f9fa]
---

# Platform teams are assigned 2 separate projects

<div class="grid grid-cols-2 gap-8 mt-12">
  <div class="text-center">
    <div class="inline-flex items-center gap-2 bg-white px-6 py-3 rounded-full border border-gray-200 mb-6">
      <span class="font-semibold">Engineering workflows</span>
      <span>👥</span>
    </div>
    <div class="flex flex-wrap gap-2 justify-center">
      <span class="px-3 py-1 bg-[#dbeafe] rounded-full text-sm">Measure engineering</span>
      <span class="px-3 py-1 bg-[#dbeafe] rounded-full text-sm">Resources provisioning</span>
      <span class="px-3 py-1 bg-[#dbeafe] rounded-full text-sm">Env management</span>
      <span class="px-3 py-1 bg-[#dbeafe] rounded-full text-sm">Meeting standards</span>
      <span class="px-3 py-1 bg-[#dbeafe] rounded-full text-sm">Service ownership</span>
    </div>
  </div>

  <div class="text-center">
    <div class="inline-flex items-center gap-2 bg-white px-6 py-3 rounded-full border border-gray-200 mb-6">
      <span class="font-semibold">Agentic workflows</span>
      <span>🤖</span>
    </div>
    <div class="flex flex-wrap gap-2 justify-center">
      <span class="px-3 py-1 bg-[#fce7f3] rounded-full text-sm">Self healing incidents</span>
      <span class="px-3 py-1 bg-[#fce7f3] rounded-full text-sm">Auto-fix security issues</span>
      <span class="px-3 py-1 bg-[#fce7f3] rounded-full text-sm">Autonomous Jira resolution</span>
      <span class="px-3 py-1 bg-[#fce7f3] rounded-full text-sm">RCA report generation</span>
    </div>
  </div>
</div>
```

### Footer with logo

```html
<div class="absolute bottom-6 left-8">
  <img src="/images/port-logo.svg" class="h-6" />
</div>

<!-- Optional: colorful dots accent (bottom right) -->
<div class="absolute bottom-6 right-8 flex gap-1">
  <div class="w-2 h-2 rounded-full bg-blue-400"></div>
  <div class="w-2 h-2 rounded-full bg-green-400"></div>
  <div class="w-2 h-2 rounded-full bg-yellow-400"></div>
  <div class="w-2 h-2 rounded-full bg-orange-400"></div>
  <div class="w-2 h-2 rounded-full bg-red-400"></div>
</div>
```

## Design principles (from Port pitch deck)

1. **Light gray backgrounds** (`#f8f9fa`) - not pure white
2. **White content cards** with subtle gray borders
3. **Black impact boxes** for key metrics/outcomes
4. **Pastel tags** for categorization (blue, pink, green, yellow)
5. **Before/After layouts** for case studies
6. **Bold key phrases** within quotes and descriptions
7. **Muted blue** (`#6b7c93`) for secondary labels like "Before"/"After"
8. **Rounded corners** on everything (cards, tags, buttons)
9. **Generous whitespace** between elements
10. **Port logo** bottom-left on most slides

## Assets to include

Store in `public/images/`:
- `port-logo.svg` - Port logo (black version)
- Customer logos for case studies
- Integration icons if needed

## Complete example slide

```markdown
---
class: bg-[#f8f9fa]
---

<div class="flex items-center justify-between mb-6">
  <img src="/images/dlocal-logo.svg" class="h-6" />
  <div class="flex gap-2">
    <span class="px-3 py-1 bg-white border border-gray-200 rounded-full text-sm">Financial Services</span>
    <span class="px-3 py-1 bg-white border border-gray-200 rounded-full text-sm">~1K employees</span>
    <span class="px-3 py-1 bg-white border border-gray-200 rounded-full text-sm">500 Engineers</span>
  </div>
</div>

<div class="grid grid-cols-2 gap-4 mb-4">
  <div class="bg-white p-5 rounded-lg border border-gray-200">
    <p class="text-[#6b7c93] font-semibold mb-2">Before</p>
    <p>Tech-debt tickets piled up; <strong>engineers lost time for feature work</strong>.</p>
  </div>
  <div class="bg-white p-5 rounded-lg border border-gray-200">
    <p class="text-[#6b7c93] font-semibold mb-2">After</p>
    <p>Port orchestrates an autonomous ticket workflow: <strong>PM agent → Tech lead agent → PR</strong>, with human approvals.</p>
  </div>
</div>

<div class="bg-black text-white p-5 rounded-lg mb-4">
  <p>Impact: MTTR went from 2 weeks → 30 min; ~50% of tech-debt workload automated.</p>
</div>

<div class="bg-white p-5 rounded-lg border border-gray-200">
  <p class="italic">"We offloaded repetitive tickets while keeping humans in the loop—so <strong>engineers could focus on high-value tasks</strong>."</p>
  <p class="text-right text-gray-500 mt-3">Head of Platform</p>
</div>

<div class="absolute bottom-6 left-8">
  <img src="/images/port-logo.svg" class="h-5" />
</div>
