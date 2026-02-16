# Strategic narrative framework

Use this framework when structuring presentation content. The Slidev skill handles technical implementation; this guide shapes the story.

## The five-act structure

Based on Andy Raskin's strategic narrative approach, every compelling presentation follows this arc:

### Act 1: old world (problem)
Set the scene for how things used to work. Make the pain relatable.

**Slide focus:** Describe the status quo and its limitations
**Example:** "For years, platform teams coordinated through Slack, Jira, and tribal knowledge..."

### Act 2: insight (why now)
Reveal what changed that makes this moment critical. Create urgency.

**Slide focus:** The shift that changes everything
**Example:** "AI agents changed the game. Now engineering work happens autonomously, but without governance, it's chaos."

### Act 3: new world (vision)
Paint a picture of what's now possible. Inspire the audience.

**Slide focus:** The opportunity unlocked by this shift
**Example:** "Organizations that govern AI agents will ship faster while maintaining quality. Those that don't will drown in technical debt."

### Act 4: stakes (urgency)
Make clear what's at stake: winning big or losing. Drive the decision.

**Slide focus:** Win big or lose, consequences of action vs inaction
**Example:** "Companies adopting Autonomous SDLC see 10x deployment velocity. Those clinging to manual processes will lose engineers and market share."

### Act 5: your role (solution)
Position your product/idea as the path to winning in the new world.

**Slide focus:** How you help them win
**Example:** "Port enables Autonomous SDLC by providing context, guardrails, and human-in-the-loop controls..."

## Applying this to your presentations

### Title slide (cover layout)
Use the Act 3 vision as your title, the new world possibility.

**Bad:** "Port Product Overview"
**Good:** "Engineering at the speed of thought"

### Section structure
Map sections to acts. Use Slidev's `layout: section` for dividers, with `layout: default` for content slides between them.

**Section flow:**
1. "The old way" (Act 1: 2-3 slides on current pain)
2. "What changed" (Act 2: 1-2 slides on the insight)
3. "The opportunity" (Act 3: 2-3 slides on what's possible)
4. "Why now" (Act 4: 1-2 slides on stakes)
5. "How Port helps" (Act 5: 3-5 slides on solution)

### Key principle
**The customer is the hero, not your product.**

Your product enables their success. Frame every benefit as something *they* achieve, not something *you* provide.

**Bad:** "Port provides a unified catalog"
**Good:** "Your developers find any service in seconds"

## Quick reference checklist

When structuring any presentation:

- [ ] Act 1 is relatable (audience recognizes the pain)
- [ ] Act 2 creates "why now" urgency
- [ ] Act 3 paints an inspiring vision
- [ ] Act 4 makes stakes clear (win/lose)
- [ ] Act 5 positions solution as path to winning
- [ ] Customer is the hero throughout
- [ ] Emotional hook first, logical details follow
- [ ] Clear call-to-action at the end

## Example slide content

**Cover slide:**
- Title: "Ship features 10x faster"
- Subtitle: "The era of autonomous engineering"

**Act 1 slide (the old way):**
Platform teams spent 60% of time on tickets: "Where does this service deploy?", "Who owns this API?", "Can I provision a new database?" Manual work, slow answers, frustrated developers.

**Act 2 slide (what changed):**
AI coding assistants arrived (Copilot, Cursor, Claude). Developers can now code 10x faster, but they're blocked waiting for answers that live in your head.

**Act 3 slide (the opportunity):**
Imagine if AI agents had access to organizational context. Every question answered instantly, every action governed automatically, every developer unblocked.

**Act 4 slide (the stakes):**
Teams adopting autonomous engineering: 10x deployment frequency, 70% reduction in MTTR, 90% developer satisfaction. Teams that don't: losing engineers to competitors who have.

**Act 5 slide (how Port enables this):**
Context Lake gives AI agents knowledge of your services, owners, and dependencies. Guardrails enforce policies automatically. Human-in-the-Loop ensures critical decisions require approval. Your path to Autonomous SDLC.

## Sources

- Andy Raskin: "The Greatest Sales Deck I've Ever Seen"
- Nancy Duarte: "Resonate" and "The Secret Structure of Great Talks"
