# Layout troubleshooting guide

Common issues and fixes for Slidev presentations.

## Panel overflow (content cut off at bottom)

**Symptom**: Cards or panels extend beyond the visible slide area.

**Cause**: Default spacing values are designed for 2-3 items. More items need compact sizing.

### Quick fixes (apply progressively until it fits)

| Element | Standard | Compact | Minimal |
|---------|----------|---------|---------|
| Grid gap | `gap-8` | `gap-4` | `gap-2` |
| Card padding | `py-8` | `py-4` | `py-2` |
| Top margin | `mt-12` | `mt-6` | `mt-2` |
| Bottom margin | `mb-8` | `mb-4` | `mb-2` |
| Icon size | `text-4xl` | `text-3xl` | `text-2xl` |
| Icon circle | `4rem` | `2.5rem` | `2rem` |

### Sizing guide by item count

| Items per slide | Recommended sizing |
|-----------------|-------------------|
| 2-3 cards | Standard (py-8, gap-8) |
| 4-6 cards | Compact (py-4, gap-4) |
| 6+ cards | Minimal (py-2, gap-2) |

### Example: compact 6-card grid

```html
<div class="grid grid-cols-3 gap-2 mt-2">
  <div class="card text-center py-2">
    <div class="icon-circle mx-auto mb-1" style="width: 2.5rem; height: 2.5rem; font-size: 1.25rem;">📚</div>
    <h3 class="font-semibold text-gray-800">Title</h3>
    <p class="text-xs text-muted mt-1">Description</p>
  </div>
  <!-- Repeat for other cards -->
</div>
```

## Horizontal alignment across cards

**Symptom**: Titles, descriptions, or tags don't align horizontally when cards have different content lengths.

**Cause**: Cards need flex-col + min-height + mt-auto pattern.

### The pattern

```html
<div class="grid grid-cols-3 gap-6">
  <div class="card flex flex-col" style="min-height: 180px;">
    <div>
      <div class="text-3xl mb-2">👥</div>
      <h3 class="text-lg font-bold mb-1">Title here</h3>
      <p class="text-sm text-gray-700">Description that may vary in length</p>
    </div>
    <div class="mt-auto pt-2">
      <span class="tag tag-blue">Label</span>
    </div>
  </div>
  <!-- Repeat for other cards with same structure -->
</div>
```

**Key elements:**
1. `flex flex-col` on card
2. `min-height: XXXpx` to ensure equal height
3. Wrap top content in a `<div>`
4. Use `mt-auto` on bottom element to push it down

### Min-height guidance

| Card content | Recommended min-height |
|-------------|------------------------|
| Icon + title + short desc + tag | 160-180px |
| Icon + title + long desc + tags | 200-220px |
| Just title + desc + tag | 120-140px |

## Text wrapping in headers

**Symptom**: Long text like "Human-Agent Collaboration" wraps to multiple lines.

**Fixes:**

1. **Prevent wrapping**: Add `whitespace-nowrap`
   ```html
   <h3 class="font-bold whitespace-nowrap">Human-AI Collaboration</h3>
   ```

2. **Shorten text**: "Human-Agent Collaboration" → "Human-AI Collaboration"

3. **Reduce font size**: `text-lg` → `text-base`

4. **Allow wrapping with min-height**: Set consistent min-height on text containers
   ```html
   <p class="text-sm" style="min-height: 40px;">Text that may wrap</p>
   ```

## Impact box positioning

**Symptom**: Black impact box not at bottom or cut off.

### Pattern: 2x2 grid with impact box below

```html
<div class="space-y-4">
  <div class="grid grid-cols-2 gap-4">
    <div class="card" style="padding: 0.75rem 1rem;">Card 1</div>
    <div class="card" style="padding: 0.75rem 1rem;">Card 2</div>
    <div class="card" style="padding: 0.75rem 1rem;">Card 3</div>
    <div class="card" style="padding: 0.75rem 1rem;">Card 4</div>
  </div>

  <div class="impact-box">
    <div class="grid grid-cols-2 gap-4 text-center">
      <div class="py-1">Point 1</div>
      <div class="py-1">Point 2</div>
    </div>
  </div>
</div>
```

**Key**: Use `space-y-4` wrapper to stack vertically, not `grid grid-cols-2` for the whole thing.

## Two-column "what they build / challenges" layout

Consistent pattern for team/pillar slides:

```html
<div class="grid grid-cols-2 gap-6 mt-8">
  <div class="card card-blue">
    <h3 class="font-bold text-gray-800 mb-3">What they build</h3>
    <p class="text-gray-700 mb-3">Subtitle here</p>
    <div class="space-y-2">
      <div class="flex items-center gap-2">
        <span class="tag bg-white text-gray-800 text-sm">Item 1</span>
        <span class="text-sm text-gray-700">Description</span>
      </div>
      <!-- More items -->
    </div>
  </div>

  <div class="card">
    <h3 class="font-bold text-gray-800 mb-3">Challenges they solve</h3>
    <div class="space-y-2 mt-4">
      <div class="flex items-center gap-2">
        <span class="text-lg">📈</span>
        <span class="text-sm text-gray-700">Challenge description</span>
      </div>
      <!-- More items -->
    </div>
  </div>
</div>
```

## Content quality checklist

Before finalizing slide text, check:

- [ ] Is it specific rather than generic? ("The market is dynamic, so is our work" not "Fast pace")
- [ ] Does it include concrete examples? ("from early discovery through enabling field teams")
- [ ] Is it down-to-earth? ("We're not afraid to ditch things we thought were right")
- [ ] Does it avoid marketing speak? (No inflated or promotional language)

See the writing guidelines in `reference/` for full standards.
