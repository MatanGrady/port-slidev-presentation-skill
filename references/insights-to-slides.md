# Insights-to-slides workflow

Transform raw content (meeting notes, research, analysis) into a structured presentation through a guided workflow.

## Input sources

Accept any of these as starting material:
- Meeting notes or call transcripts
- Research findings or analysis documents
- Strategy documents or planning notes
- Existing markdown files with insights
- Pasted text content

## Workflow

### Phase 1: Understand the content

Read the source material and identify:
- Core themes and messages
- Key data points or evidence
- Potential story arc or narrative flow
- Natural section breaks

### Phase 2: Plan the presentation (use plan mode)

Enter plan mode and gather requirements:

**Questions to ask:**
1. **Audience**: Who will see this? (internal team, executives, customers, mixed)
2. **Goal**: What should the audience do/think/feel after? (align, decide, learn, approve)
3. **Length**: How many slides? (5-10 short, 10-15 standard, 15-25 detailed)
4. **Format**: Live presentation, async reading, or both?

**Plan structure to propose:**
```
## Presentation plan

### Audience and goal
[Who and why]

### Narrative arc
1. [Opening hook/problem statement]
2. [Section 1: Title - key message]
3. [Section 2: Title - key message]
4. [Section 3: Title - key message]
5. [Closing/call to action]

### Visual opportunities
- Slide X: [diagram type] showing [concept]
- Slide Y: [chart type] with [data]
- Slide Z: [visual] to emphasize [point]

### Open questions
[Anything needing clarification before building]
```

Save the plan to the project folder as `presentation-plan.md`.

### Phase 3: Review visual opportunities

For each visual opportunity identified:
- **Excalidraw diagrams**: Architecture, flows, comparisons, concepts
- **Charts/data viz**: Metrics, trends, comparisons with numbers
- **Screenshots/images**: Product UI, external references
- **Tables**: Feature comparisons, matrices

Ask: "I've identified these visual opportunities. Should I create Excalidraw diagrams for any of them?"

### Phase 4: Build the slides

Use the main slidev-presentation process to create the actual slides:

1. Copy Port template to presentation folder
2. Implement the planned structure
3. Apply visual elements
4. Add speaker notes where helpful

## Output location

Presentations go in one of:
- `projects/[project-name]/resources/presentations/[name]/` (if part of a project)
- `outputs/presentations/[name]/` (standalone)

Each presentation folder contains:
```
[name]/
├── presentation-plan.md   # The plan from phase 2
├── slides.md              # Slidev presentation
├── public/images/         # Visual assets
└── [exported files]       # PDF/PNG when exported
```

## Quality checklist (content-specific)

Before delivering:

**Content:**
- [ ] Clear narrative arc from opening to close
- [ ] One main idea per slide
- [ ] Evidence supports claims
- [ ] No walls of text (max 5-7 bullets)

**Visuals:**
- [ ] Diagrams created for complex concepts
- [ ] Port brand applied consistently
- [ ] Images sized appropriately

**Polish:**
- [ ] Speaker notes on complex slides
- [ ] Transitions feel natural
- [ ] Plan document saved alongside slides

## Plan template

See below for the full plan template to use when structuring a presentation from raw content.

### Example: [presentation title]

#### Context
**Source material**: [What content this is based on]
**Created**: [Date]

#### Audience and goal
**Audience**: [Who will see this - be specific about their role and context]
**Goal**: [What should happen after they see it - action, alignment, decision]
**Format**: [Live presentation / async reading / both]

#### Narrative arc

**Opening** (1-2 slides)
- Hook or problem statement that creates tension
- Why this matters now

**Section 1: [Title]** (2-3 slides)
- Key message: [One sentence summary]
- Supporting points:
  - [Point 1]
  - [Point 2]
  - [Point 3 if needed]

**Section 2: [Title]** (2-3 slides)
- Key message: [One sentence summary]
- Supporting points:
  - [Point 1]
  - [Point 2]

**Section 3: [Title]** (2-3 slides)
- Key message: [One sentence summary]
- Supporting points:
  - [Point 1]
  - [Point 2]

**Closing** (1-2 slides)
- Key takeaway or call to action
- Open questions or next steps

#### Visual opportunities

| Slide | Visual type | Purpose |
|-------|-------------|---------|
| [#] | Excalidraw diagram | Show [concept/flow] |
| [#] | Before/after cards | Contrast [X] vs [Y] |
| [#] | Data visualization | Highlight [metric/trend] |
| [#] | Quote callout | Emphasize [key insight] |

#### Content to include

**Must include:**
- [Key point that must appear]
- [Evidence that supports the narrative]
- [Data point that makes the case]

**Consider including:**
- [Nice-to-have if space allows]
- [Supporting example]

**Explicitly exclude:**
- [Topic to avoid]
- [Detail that's too granular]

#### Open questions

Before building slides, clarify:
1. [Question about scope/depth]
2. [Question about specific content]
3. [Question about visual treatment]
