---
theme: default
title: Port presentation template
info: |
  Port - Agentic Engineering Platform
  Template with all slide variations
author: Matan Grady
fonts:
  sans: DM Sans
  mono: Fira Code
  weights: '400,500,600,700'
highlighter: shiki
lineNumbers: true
transition: fade-out
exportFilename: port-presentation
---

<!--
Port Slidev Template - Enhanced

This template contains all standard slide layouts for Port presentations.
Copy this file to start a new presentation, then delete unused slides.

Sections:
1. Title/cover slides (4 variations)
2. Content slides (8 variations)
3. Board-style slides (5 variations)

Usage:
- Copy this template to outputs/presentations/[name]/slides.md
- Copy port-logo.png to outputs/presentations/[name]/public/images/
- Delete slides you don't need
- Customize content
- Run: npx @slidev/cli slides.md
-->

<style>
/* Port brand styles - Enhanced */

:root {
  /* Core colors */
  --port-bg: #f8f9fa;
  --port-card: #ffffff;
  --port-black: #000000;
  --port-muted: #4b5563;  /* Darker gray for readability on light bg */
  --port-border: #e5e7eb;

  /* Text colors - use these explicitly on cards */
  --text-primary: #1f2937;   /* gray-800 - main content */
  --text-secondary: #4b5563; /* gray-600 - descriptions */
  --text-muted: #6b7280;     /* gray-500 - subtle text */

  /* Tag colors (pastel) */
  --port-blue: #dbeafe;
  --port-pink: #fce7f3;
  --port-green: #dcfce7;
  --port-yellow: #fef3c7;
  --port-purple: #f3e8ff;
  --port-orange: #ffedd5;

  /* Accent colors */
  --accent-blue: #3b82f6;
  --accent-green: #10b981;
  --accent-purple: #8b5cf6;
  --accent-orange: #f97316;
  --accent-pink: #ec4899;
  --accent-red: #ef4444;
}

/* Default background */
.slidev-layout { background: var(--port-bg); }

/* Dark slide variant */
.dark-slide {
  background: linear-gradient(135deg, #0f0f0f 0%, #1a1a2e 100%);
  color: white;
}
.dark-slide h1, .dark-slide h2, .dark-slide p { color: white; }
.dark-slide .text-muted { color: #94a3b8; }

/* Gradient slide variants */
.gradient-blue {
  background: linear-gradient(135deg, var(--port-blue) 0%, #bfdbfe 50%, var(--port-purple) 100%);
}
.gradient-pink {
  background: linear-gradient(135deg, var(--port-pink) 0%, #fbcfe8 50%, var(--port-orange) 100%);
}
.gradient-green {
  background: linear-gradient(135deg, var(--port-green) 0%, #bbf7d0 50%, var(--port-blue) 100%);
}

/* Typography */
h1 { font-weight: 700; color: var(--port-black); }
h2, h3 { font-weight: 600; color: var(--port-black); }

/* Big number accent */
.big-number {
  font-size: 8rem;
  font-weight: 800;
  line-height: 1;
  background: linear-gradient(135deg, var(--accent-blue), var(--accent-purple));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

/* Card styles */
.card {
  background: var(--port-card);
  border-radius: 16px;
  padding: 1.5rem;
  border: 1px solid var(--port-border);
  box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.05);
}
.card-hover { transition: transform 0.2s, box-shadow 0.2s; }
.card-hover:hover { transform: translateY(-2px); box-shadow: 0 8px 25px -5px rgb(0 0 0 / 0.1); }

/* Accent variants */
.accent-blue { border-left: 4px solid var(--accent-blue); }
.accent-green { border-left: 4px solid var(--accent-green); }
.accent-purple { border-left: 4px solid var(--accent-purple); }
.accent-orange { border-left: 4px solid var(--accent-orange); }
.accent-pink { border-left: 4px solid var(--accent-pink); }
.accent-red { border-left: 4px solid var(--accent-red); }

/* Colored cards */
.card-blue { background: var(--port-blue); border: none; }
.card-pink { background: var(--port-pink); border: none; }
.card-green { background: var(--port-green); border: none; }
.card-yellow { background: var(--port-yellow); border: none; }
.card-purple { background: var(--port-purple); border: none; }

/* Impact box */
.impact-box {
  background: var(--port-black);
  color: white;
  padding: 1.5rem;
  border-radius: 16px;
}

/* Success box */
.success-box {
  background: var(--port-green);
  color: #166534;
  padding: 1.25rem;
  border-radius: 16px;
  font-weight: 600;
}

/* Quote box */
.quote-box {
  background: var(--port-card);
  border-left: 4px solid var(--accent-purple);
  border-radius: 0 16px 16px 0;
  padding: 1.5rem;
}

/* Tags */
.tag {
  display: inline-block;
  padding: 0.25rem 0.875rem;
  border-radius: 9999px;
  font-size: 0.875rem;
  font-weight: 500;
}
.tag-blue { background: var(--port-blue); color: #1e40af; }
.tag-pink { background: var(--port-pink); color: #9d174d; }
.tag-green { background: var(--port-green); color: #166534; }
.tag-yellow { background: var(--port-yellow); color: #92400e; }
.tag-purple { background: var(--port-purple); color: #6b21a8; }
.tag-orange { background: var(--port-orange); color: #c2410c; }
.tag-dark { background: var(--port-black); color: white; }
.tag-neutral { background: #f3f4f6; color: #374151; }

/* Text utilities - use explicit colors on cards for readability */
.text-muted { color: var(--port-muted); }  /* #4b5563 - readable on light bg */
.text-primary { color: var(--text-primary); }  /* #1f2937 - main content */
.text-secondary { color: var(--text-secondary); }  /* #4b5563 - descriptions */

/* Compact card variant - use for multi-row layouts */
.card-compact { padding: 0.75rem; }
.card-compact .text-xl { font-size: 1rem; }
.card-compact .text-2xl { font-size: 1.25rem; }

/* Step number */
.step-number {
  width: 3rem;
  height: 3rem;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--accent-blue), var(--accent-purple));
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  font-size: 1.25rem;
}

/* Icon circle */
.icon-circle {
  width: 4rem;
  height: 4rem;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.75rem;
}
.icon-blue { background: var(--port-blue); }
.icon-pink { background: var(--port-pink); }
.icon-green { background: var(--port-green); }
.icon-purple { background: var(--port-purple); }
.icon-yellow { background: var(--port-yellow); }
.icon-orange { background: var(--port-orange); }

/* Stat styles */
.stat-number {
  font-size: 3.5rem;
  font-weight: 800;
  line-height: 1;
  background: linear-gradient(135deg, var(--port-black), #374151);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
.stat-label {
  color: var(--port-muted);
  font-size: 0.875rem;
  margin-top: 0.5rem;
  font-weight: 500;
}

/* Header logo */
.header-logo {
  position: absolute;
  top: 1.5rem;
  right: 2rem;
}
.header-logo img { height: 2rem; }

/* Slide footer (board style) */
.slide-footer {
  position: absolute;
  bottom: 1.5rem;
  left: 2rem;
  right: 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.slide-footer img { height: 1.5rem; }
.slide-footer .meeting-name { color: var(--port-muted); font-size: 0.875rem; }

/* Decorative elements */
.dots-accent {
  position: absolute;
  bottom: 1.5rem;
  right: 2rem;
  display: flex;
  gap: 0.375rem;
}
.dots-accent span {
  width: 0.625rem;
  height: 0.625rem;
  border-radius: 50%;
}

/* Floating shapes */
.shape-circle {
  position: absolute;
  border-radius: 50%;
  opacity: 0.6;
}
.shape-square {
  position: absolute;
  border-radius: 16px;
  opacity: 0.5;
  transform: rotate(15deg);
}

/* Progress indicator style */
.progress-bar {
  height: 8px;
  border-radius: 4px;
  background: var(--port-border);
}
.progress-fill {
  height: 100%;
  border-radius: 4px;
  background: linear-gradient(90deg, var(--accent-blue), var(--accent-purple));
}

/* Emoji badge */
.emoji-badge {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: white;
  padding: 0.5rem 1rem;
  border-radius: 9999px;
  border: 1px solid var(--port-border);
  font-weight: 600;
}

/* Board-style components */

/* Metric card (large rounded) */
.metric-card {
  background: var(--port-card);
  border-radius: 24px;
  padding: 2rem;
  text-align: center;
  border: 1px solid var(--port-border);
}
.metric-label {
  color: var(--port-muted);
  font-size: 0.875rem;
  font-weight: 500;
  margin-bottom: 0.5rem;
}
.metric-value {
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--port-black);
  line-height: 1.2;
}
.metric-sub {
  color: var(--port-muted);
  font-size: 0.75rem;
  margin-top: 0.25rem;
}

/* Category pill with avatar stack */
.category-pill {
  display: inline-flex;
  align-items: center;
  gap: 0.75rem;
  background: white;
  padding: 0.75rem 1.25rem;
  border-radius: 9999px;
  border: 1px solid var(--port-border);
  font-weight: 600;
}
.avatar-stack {
  display: flex;
  margin-left: 0.5rem;
}
.avatar-stack img, .avatar-stack span {
  width: 1.75rem;
  height: 1.75rem;
  border-radius: 50%;
  border: 2px solid white;
  margin-left: -0.5rem;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.75rem;
}
.avatar-stack span:first-child, .avatar-stack img:first-child { margin-left: 0; }

/* Light gradient area (for split layouts) */
.gradient-area-light {
  background: linear-gradient(135deg, #f0f9ff 0%, #f8fafc 50%, #faf5ff 100%);
  border-radius: 24px;
  padding: 2rem;
}

/* Statement card */
.statement-card {
  background: white;
  border: 1px solid var(--port-border);
  border-radius: 24px;
  padding: 1.5rem 3rem;
  font-size: 1.25rem;
  font-weight: 500;
}
</style>

<!-- ================================================ -->
<!-- Section 1: Title/cover slides -->
<!-- ================================================ -->

<!-- Cover slide with gradient accent -->
# Your presentation title here

<p class="text-xl text-muted mt-4">Subtitle or tagline goes here</p>

<div class="header-logo">
  <img src="/images/port-logo.png" alt="Port" />
</div>

<div class="dots-accent">
  <span class="bg-blue-400"></span>
  <span class="bg-purple-400"></span>
  <span class="bg-pink-400"></span>
  <span class="bg-orange-400"></span>
  <span class="bg-green-400"></span>
</div>

---
transition: slide-up
---

<!-- Big statement (dark variant) -->
<div class="dark-slide absolute inset-0 flex flex-col items-center justify-center text-center px-16">
  <div class="text-6xl mb-8">🚀</div>
  <h1 class="text-5xl font-bold mb-6">Your bold statement here</h1>
  <p class="text-xl text-muted">Supporting context or data point</p>
</div>

---
transition: slide-left
---

<!-- Section divider with number -->
<div class="flex items-center justify-center h-full gap-16">
  <div class="big-number">01</div>
  <div>
    <h1 class="text-4xl font-bold">Section title</h1>
    <p class="text-xl text-muted mt-4">Brief description of this section</p>
    <div class="flex gap-2 mt-6">
      <span class="tag tag-blue">Tag 1</span>
      <span class="tag tag-pink">Tag 2</span>
      <span class="tag tag-purple">Tag 3</span>
    </div>
  </div>
</div>

---
transition: fade
---

<!-- Section divider (gradient background) -->
<div class="gradient-blue absolute inset-0 flex flex-col items-center justify-center text-center">
  <div class="big-number mb-4">02</div>
  <h1 class="text-4xl font-bold">Section title</h1>
  <p class="text-xl text-muted mt-4">Section description</p>
</div>

---
transition: fade-out
---

<!-- ================================================ -->
<!-- Section 2: Content slides -->
<!-- ================================================ -->

<!-- Icon grid (4 columns) -->
# Slide title

<div class="text-lg text-muted mb-10">Subtitle or context</div>

<div class="grid grid-cols-4 gap-6">
  <div class="text-center">
    <div class="icon-circle icon-blue mx-auto mb-4">🎫</div>
    <strong>Point 1</strong>
    <p class="text-sm text-muted mt-2">Description here</p>
  </div>
  <div class="text-center">
    <div class="icon-circle icon-pink mx-auto mb-4">📚</div>
    <strong>Point 2</strong>
    <p class="text-sm text-muted mt-2">Description here</p>
  </div>
  <div class="text-center">
    <div class="icon-circle icon-green mx-auto mb-4">🧠</div>
    <strong>Point 3</strong>
    <p class="text-sm text-muted mt-2">Description here</p>
  </div>
  <div class="text-center">
    <div class="icon-circle icon-purple mx-auto mb-4">⏰</div>
    <strong>Point 4</strong>
    <p class="text-sm text-muted mt-2">Description here</p>
  </div>
</div>

---
transition: slide-right
---

<!-- Quote slide -->
<div class="flex flex-col items-center justify-center h-full px-20">
  <div class="quote-box max-w-3xl">
    <div class="text-4xl text-purple-300 mb-4">"</div>
    <p class="text-2xl font-medium leading-relaxed">
      Your quote text goes here. Make it impactful and memorable.
    </p>
    <div class="flex items-center gap-4 mt-8">
      <div class="w-12 h-12 rounded-full bg-purple-100 flex items-center justify-center text-xl">👤</div>
      <div>
        <p class="font-semibold">Person Name</p>
        <p class="text-muted text-sm">Title, Company</p>
      </div>
    </div>
  </div>
</div>

---
transition: slide-up
---

<!-- Big number reveal -->
<div class="flex items-center justify-center h-full">
  <div class="text-center">
    <div class="big-number mb-4">47%</div>
    <h2 class="text-3xl font-bold mb-4">Supporting headline for the stat</h2>
    <p class="text-muted text-lg max-w-xl mx-auto">Additional context explaining what this number means</p>
    <div class="flex justify-center gap-3 mt-8">
      <span class="tag tag-blue">Source</span>
      <span class="tag tag-purple">Category</span>
    </div>
  </div>
</div>

---
transition: slide-left
---

<!-- Three pillars (aligned cards) - titles, descriptions, and tags align horizontally -->
# Slide title

<div class="text-lg text-muted mb-8">Subtitle here</div>

<div class="grid grid-cols-3 gap-6">
  <div class="card card-blue flex flex-col" style="min-height: 180px;">
    <div>
      <div class="text-3xl mb-2">🌊</div>
      <h3 class="text-lg font-bold mb-1">Pillar 1</h3>
      <p class="text-sm text-gray-700">Description that may vary in length</p>
    </div>
    <div class="mt-auto pt-2">
      <span class="tag tag-dark">Label</span>
    </div>
  </div>

  <div class="card card-pink flex flex-col" style="min-height: 180px;">
    <div>
      <div class="text-3xl mb-2">🔧</div>
      <h3 class="text-lg font-bold mb-1">Pillar 2</h3>
      <p class="text-sm text-gray-700">Shorter description</p>
    </div>
    <div class="mt-auto pt-2">
      <span class="tag tag-dark">Label</span>
    </div>
  </div>

  <div class="card card-green flex flex-col" style="min-height: 180px;">
    <div>
      <div class="text-3xl mb-2">🤖</div>
      <h3 class="text-lg font-bold mb-1">Pillar 3</h3>
      <p class="text-sm text-gray-700">Another description with different length</p>
    </div>
    <div class="mt-auto pt-2">
      <span class="tag tag-dark">Label</span>
    </div>
  </div>
</div>

---
transition: slide-down
---

<!-- Before/After comparison -->
# Slide title

<div class="grid grid-cols-2 gap-8 mt-8">
  <div>
    <div class="emoji-badge mb-6">
      <span>👥</span>
      <span>Before</span>
    </div>
    <div class="space-y-3">
      <div class="card accent-orange">
        <span class="text-muted">Metric 1:</span> <strong>Old value</strong>
      </div>
      <div class="card accent-orange">
        <span class="text-muted">Metric 2:</span> <strong>Old value</strong>
      </div>
      <div class="card accent-orange">
        <span class="text-muted">Metric 3:</span> <strong>Old value</strong>
      </div>
    </div>
    <div class="impact-box mt-6 text-center">
      Summary of old state
    </div>
  </div>

  <div>
    <div class="emoji-badge mb-6">
      <span>🤖</span>
      <span>After</span>
    </div>
    <div class="space-y-3">
      <div class="card accent-green">
        <span class="text-muted">Metric 1:</span> <strong class="text-green-600">New value</strong>
      </div>
      <div class="card accent-green">
        <span class="text-muted">Metric 2:</span> <strong class="text-green-600">New value</strong>
      </div>
      <div class="card accent-green">
        <span class="text-muted">Metric 3:</span> <strong class="text-blue-600">New value</strong>
      </div>
    </div>
    <div class="success-box mt-6 text-center">
      Summary of new state ✓
    </div>
  </div>
</div>

---
transition: fade
---

<!-- Stats grid with progress bars -->
# Slide title

<div class="text-lg text-muted mb-10">Subtitle here</div>

<div class="grid grid-cols-4 gap-6">
  <div class="card text-center py-8">
    <div class="stat-number">90%</div>
    <div class="stat-label">Metric label</div>
    <div class="progress-bar mt-4 w-full">
      <div class="progress-fill" style="width: 90%"></div>
    </div>
  </div>

  <div class="card text-center py-8">
    <div class="stat-number">10x</div>
    <div class="stat-label">Metric label</div>
    <div class="progress-bar mt-4 w-full">
      <div class="progress-fill" style="width: 100%"></div>
    </div>
  </div>

  <div class="card text-center py-8">
    <div class="stat-number">50%</div>
    <div class="stat-label">Metric label</div>
    <div class="progress-bar mt-4 w-full">
      <div class="progress-fill" style="width: 50%"></div>
    </div>
  </div>

  <div class="card text-center py-8">
    <div class="stat-number">2hrs</div>
    <div class="stat-label">Metric label</div>
    <div class="progress-bar mt-4 w-full">
      <div class="progress-fill" style="width: 75%"></div>
    </div>
  </div>
</div>

---
transition: slide-up
---

<!-- Case study slide -->
<div class="flex items-center justify-between mb-6">
  <div class="emoji-badge">
    <span>🏢</span>
    <span>Customer Story</span>
  </div>
  <div class="flex gap-2">
    <span class="tag bg-white border border-gray-200">Industry</span>
    <span class="tag bg-white border border-gray-200">Size</span>
  </div>
</div>

<div class="grid grid-cols-2 gap-6 mb-4">
  <div class="card card-pink">
    <p class="font-semibold mb-2">Before</p>
    <p>Problem description with <strong>key pain points bolded</strong>.</p>
  </div>
  <div class="card card-green">
    <p class="font-semibold mb-2">After</p>
    <p>Solution with <strong>key benefits bolded</strong>.</p>
  </div>
</div>

<div class="impact-box">
  <div class="flex items-center justify-between">
    <div>
      <p class="text-lg font-bold">Impact</p>
      <p>Key result achieved</p>
    </div>
    <div class="text-5xl">📈</div>
  </div>
</div>

---
transition: slide-right
---

<!-- Key takeaways -->
# Key takeaways

<div class="grid grid-cols-3 gap-8 mt-12">
  <div class="text-center">
    <div class="step-number mx-auto mb-4">1</div>
    <h3 class="font-bold text-lg mb-2">Takeaway 1</h3>
    <p class="text-muted text-sm">Supporting explanation</p>
  </div>

  <div class="text-center">
    <div class="step-number mx-auto mb-4">2</div>
    <h3 class="font-bold text-lg mb-2">Takeaway 2</h3>
    <p class="text-muted text-sm">Supporting explanation</p>
  </div>

  <div class="text-center">
    <div class="step-number mx-auto mb-4">3</div>
    <h3 class="font-bold text-lg mb-2">Takeaway 3</h3>
    <p class="text-muted text-sm">Supporting explanation</p>
  </div>
</div>

<div class="absolute bottom-12 left-0 right-0 flex justify-center">
  <div class="flex gap-2">
    <span class="tag tag-blue">Tag 1</span>
    <span class="tag tag-pink">Tag 2</span>
    <span class="tag tag-green">Tag 3</span>
  </div>
</div>

---
transition: fade-out
---

<!-- ================================================ -->
<!-- Section 3: Board-style slides -->
<!-- ================================================ -->

<!-- Metrics with chart placeholder -->
<div class="grid grid-cols-2 gap-8 h-full items-center">
  <div>
    <h1 class="text-4xl font-bold mb-12">Question or title here?</h1>

    <div class="space-y-6">
      <div class="metric-card">
        <div class="metric-label">Metric name</div>
        <div class="metric-value">$16.1M</div>
        <div class="metric-sub">2.64X YoY</div>
      </div>

      <div class="metric-card">
        <div class="metric-label">Another metric</div>
        <div class="metric-value">$3M</div>
      </div>
    </div>
  </div>

  <div class="card h-80 flex items-center justify-center">
    <p class="text-muted">[Chart placeholder]</p>
  </div>
</div>

<div class="slide-footer">
  <img src="/images/port-logo.png" alt="Port" />
  <span class="meeting-name">Meeting name here</span>
</div>

---
transition: fade
---

<!-- Two-column categories with avatars -->
# Slide title here

<div class="grid grid-cols-2 gap-16 mt-12">
  <div class="text-center">
    <div class="category-pill mx-auto mb-8">
      <span>Category 1</span>
      <div class="avatar-stack">
        <span class="bg-blue-100">👨‍💻</span>
        <span class="bg-green-100">👩‍💻</span>
        <span class="bg-purple-100">🧑‍💻</span>
      </div>
    </div>
    <div class="flex flex-wrap gap-2 justify-center">
      <span class="tag tag-blue">Item 1</span>
      <span class="tag tag-blue">Item 2</span>
      <span class="tag tag-blue">Item 3</span>
      <span class="tag tag-blue">Item 4</span>
    </div>
  </div>

  <div class="text-center">
    <div class="category-pill mx-auto mb-8">
      <span>Category 2</span>
      <div class="avatar-stack">
        <span class="bg-yellow-100">🤖</span>
        <span class="bg-pink-100">⚡</span>
        <span class="bg-green-100">🔧</span>
      </div>
    </div>
    <div class="flex flex-wrap gap-2 justify-center">
      <span class="tag tag-blue">Item 1</span>
      <span class="tag tag-blue">Item 2</span>
      <span class="tag tag-blue">Item 3</span>
      <span class="tag tag-blue">Item 4</span>
    </div>
  </div>
</div>

<div class="impact-box mt-12 text-center text-xl">
  Unifying statement
</div>

<div class="slide-footer">
  <img src="/images/port-logo.png" alt="Port" />
  <span class="meeting-name">Meeting name here</span>
</div>

---
transition: slide-up
---

<!-- Split metrics grid -->
<div class="grid grid-cols-2 gap-0 h-full">
  <div class="flex items-center pr-12">
    <h1 class="text-4xl font-bold">Question or title here</h1>
  </div>

  <div class="gradient-area-light flex items-center">
    <div class="grid grid-cols-3 gap-4 w-full">
      <div class="metric-card">
        <div class="metric-label">Metric 1</div>
        <div class="metric-value">$37M</div>
        <div class="metric-sub">130% YoY</div>
      </div>
      <div class="metric-card">
        <div class="metric-label">Metric 2</div>
        <div class="metric-value">95%</div>
      </div>
      <div class="metric-card">
        <div class="metric-label">Metric 3</div>
        <div class="metric-value">130%</div>
      </div>
      <div class="metric-card col-span-1">
        <div class="metric-label">Metric 4</div>
        <div class="metric-value">$21.7M</div>
      </div>
      <div class="metric-card col-span-2">
        <div class="metric-label">Metric 5</div>
        <div class="metric-value">$20.9M</div>
      </div>
    </div>
  </div>
</div>

<div class="slide-footer">
  <img src="/images/port-logo.png" alt="Port" />
  <span class="meeting-name">Meeting name here</span>
</div>

---
transition: fade-out
---

<!-- Big centered statement -->
<div class="flex flex-col items-center justify-center h-full">
  <h1 class="text-4xl font-medium text-center mb-8">
    Statement with <strong>key word</strong> emphasized
  </h1>

  <div class="statement-card">
    Supporting statement or equation
  </div>
</div>

<div class="slide-footer">
  <img src="/images/port-logo.png" alt="Port" />
  <span class="meeting-name">Meeting name here</span>
</div>

---
transition: slide-right
---

<!-- Timeline roadmap -->
# Timeline title here

<div class="relative h-64 mt-16">
  <!-- Timeline axis -->
  <div class="absolute left-0 right-0 top-1/2 h-0.5 bg-gray-200"></div>

  <!-- Quarter markers -->
  <div class="absolute left-[10%] top-1/2 -translate-y-1/2 w-2 h-2 bg-gray-300 rounded-full"></div>
  <div class="absolute left-[10%] top-[60%] text-xs text-muted">Q4 25</div>

  <div class="absolute left-[30%] top-1/2 -translate-y-1/2 w-2 h-2 bg-gray-300 rounded-full"></div>
  <div class="absolute left-[30%] top-[60%] text-xs text-muted">Q1 26</div>

  <div class="absolute left-[50%] top-1/2 -translate-y-1/2 w-2 h-2 bg-gray-300 rounded-full"></div>
  <div class="absolute left-[50%] top-[60%] text-xs text-muted">Q2 26</div>

  <div class="absolute left-[70%] top-1/2 -translate-y-1/2 w-2 h-2 bg-gray-300 rounded-full"></div>
  <div class="absolute left-[70%] top-[60%] text-xs text-muted">Q3 26</div>

  <div class="absolute left-[90%] top-1/2 -translate-y-1/2 w-2 h-2 bg-gray-300 rounded-full"></div>
  <div class="absolute left-[90%] top-[60%] text-xs text-muted">Q4 26</div>

  <!-- Cards above timeline -->
  <div class="absolute left-[15%] bottom-[55%] flex items-center gap-2 bg-white border border-gray-200 rounded-full px-4 py-2 text-sm">
    Item 1
    <div class="avatar-stack">
      <span class="bg-blue-100 text-xs">👤</span>
      <span class="bg-green-100 text-xs">👤</span>
    </div>
  </div>

  <div class="absolute left-[45%] bottom-[55%] flex items-center gap-2 bg-white border border-gray-200 rounded-full px-4 py-2 text-sm">
    Item 2
    <span class="tag tag-neutral text-xs">Status</span>
  </div>

  <!-- Cards below timeline -->
  <div class="absolute left-[25%] top-[55%] flex items-center gap-2 bg-white border border-gray-200 rounded-full px-4 py-2 text-sm">
    Item 3
    <div class="avatar-stack">
      <span class="bg-purple-100 text-xs">👤</span>
    </div>
  </div>

  <div class="absolute left-[60%] top-[55%] flex items-center gap-2 bg-white border border-gray-200 rounded-full px-4 py-2 text-sm">
    Item 4
    <span class="tag tag-neutral text-xs">Status</span>
  </div>
</div>

<div class="slide-footer">
  <img src="/images/port-logo.png" alt="Port" />
  <span class="meeting-name">Meeting name here</span>
</div>

---
transition: fade-out
---

<!-- ================================================ -->
<!-- Closing slides -->
<!-- ================================================ -->

<!-- Closing (dark variant) -->
<div class="dark-slide absolute inset-0 flex flex-col items-center justify-center text-center px-16">
  <h1 class="text-5xl font-bold mb-6">Call to action here?</h1>
  <p class="text-xl text-muted mb-10">Supporting statement</p>

  <div class="flex gap-4">
    <div class="px-8 py-4 bg-white text-black rounded-full font-semibold">
      Primary CTA
    </div>
    <div class="px-8 py-4 border border-white/30 rounded-full">
      Secondary CTA
    </div>
  </div>

  <div class="absolute bottom-8 flex gap-6 text-muted text-sm">
    <span>getport.io</span>
    <span>•</span>
    <span>docs.port.io</span>
  </div>
</div>

---
layout: center
transition: slide-up
---

<!-- Q&A slide -->
<div class="text-center">
  <div class="text-8xl mb-8">💬</div>
  <h1 class="text-5xl font-bold mb-4">Questions?</h1>
  <p class="text-xl text-muted">Closing line here</p>

  <div class="flex justify-center gap-3 mt-10">
    <span class="tag tag-blue">Tag 1</span>
    <span class="tag tag-pink">Tag 2</span>
    <span class="tag tag-green">Tag 3</span>
    <span class="tag tag-purple">Tag 4</span>
  </div>
</div>
