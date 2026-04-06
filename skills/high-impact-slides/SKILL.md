---
name: high-impact-slides
description: >
  Create high-impact, story-driven PowerPoint (.pptx) presentations with a clean warm-neutral theme.
  Use this skill whenever the user wants to build a slide deck, pitch, presentation, or visual report —
  especially for business pitches, academic class presentations, or data/analytics reports.
  Trigger when the user says things like "make me a deck", "create slides", "build a presentation",
  "turn this into a pitch", "I need to present this", or uploads notes/a doc and wants slides from it.
  Always use this skill before the pptx skill when the goal is a polished, structured deck — not just
  a quick file conversion. This skill handles narrative strategy and slide design system first; the pptx
  skill handles file execution.
---

# High-Impact Slides Skill

## Overview

This skill produces presentations that are clear, cohesive, and visually calm. It works in three mandatory phases — each phase requires explicit user confirmation before the next begins. Never skip ahead.

1. **Phase 1** — Narrative strategy + slide blueprint (requires user approval before continuing)
2. **Phase 1.5** — Data audit (requires all data in hand before continuing)
3. **Phase 2+** — Design system review + file execution

> **PROCESS RULE:** This skill is gate-driven. Each gate requires a real response from the user — not an assumption, not a reasonable guess. If you are tempted to proceed without confirmation, do not. Stop. Send your message. Wait.

---

## Phase 1 — Narrative Strategy

### Step 1: Clarify before building

If the user hasn't explicitly provided all three of these, ask in a single message:

- **Goal**: What should the audience *do or believe* after seeing this deck?
- **Audience**: Who are they, and what do they already know?
- **Content**: Do they have raw notes, a doc, or should Claude generate content from scratch?

If the user uploads a document or notes, extract the story from it — don't just reformat it.

> **GATE 1 — HARD STOP.** Send your clarifying questions and end your response. Do not draft a blueprint. Do not guess at the content. Do not generate any slides. Do not continue to Step 2 until the user has replied to this message.

---

### Step 2: Identify the One Big Idea

Every deck has one sentence that, if the audience remembers nothing else, makes the presentation a success. Identify it explicitly. State it to the user before proceeding.

Example: *"Flow is the fastest way for early-stage Manila startups to find workspace without committing to a lease."*

---

### Step 3: Choose a narrative structure

Pick the structure that fits the deck type:

| Deck type | Structure | Shape |
|---|---|---|
| Business/marketing pitch | **SCR** (Situation → Complication → Resolution) | Problem exists → current solutions fail → we fix it |
| Academic / analytical | **SCQA** (Situation → Complication → Question → Answer) | Context → tension → "so what?" → insight |
| Data report | **Insight-first** | Lead with the finding, then show the evidence |
| General / exploratory | **Before → After → Bridge** | Where we are → where we want to be → how to get there |

Tell the user which structure you're using and why.

---

### Step 4: Build the slide blueprint

Produce a slide-by-slide plan. Format as a numbered list:

```
1. [HOOK] — Headline: "..." | Message: ... | Type: hook | Icon: none
2. [SITUATION] — Headline: "..." | Message: ... | Type: insight | Icon: circle-arrow (anchor, top-right)
3. [DATA] — Headline: "..." | Message: ... | Type: data | Icon: none (chart fills space)
4. [PROOF] — Headline: "..." | Message: ... | Type: proof | Icon: checkmark-shield (inline, per point)
```

**Icon field rules:**
- Hook and data/chart slides: always `Icon: none`
- All other slides: declare the icon concept + placement before building. Never leave this blank.
- Placement options: `anchor` (one large icon, top-right or right column), `inline` (small icon beside each bullet/row), `background` (large faint shape behind content, warm gray at 10% opacity)

**Slide types and their rules:**

- **Hook** — One bold statement or provocative question. No bullet points. Full-bleed background or large centered type.
- **Insight** — Headline = the insight itself, not a topic label. Supporting evidence below, minimal.
- **Data** — Chart or stat callout. Headline states what the data *means*, not what it *shows*. "Revenue grew 3× in 12 months" not "Revenue chart."
- **Proof / case** — Evidence for a claim. Logo, quote, or metric. One proof point per slide.
- **Process / flow** — Steps or timeline. Max 5 steps. Labels only, no paragraph text.
- **CTA / close** — Single ask or takeaway. Repeat the One Big Idea. Contact or next step.

**Hard rules for every slide:**
- One message per slide. If a slide tries to say two things, split it.
- Headline = the message, not the topic. "Why co-working?" is bad. "Co-working cuts overhead by 40%" is good.
- Max 40 words of body text per slide. If you need more, it's two slides.
- Every slide needs a visual element — stat callout, chart, icon, or image placeholder.
- **Never invent data.** If a data slide requires specific numbers the user hasn't provided, mark it `[DATA NEEDED]` in the blueprint — do not fill in placeholder numbers.

> **GATE 2 — HARD STOP.** Present the completed blueprint and ask the user explicitly: *"Does this blueprint look right? Any slides to add, remove, or reframe before I build the file?"*
>
> End your response after this question. Do not proceed to Phase 1.5. Do not read the pptx skill. Do not write any code. Wait for the user to confirm the blueprint in writing.

---

## Phase 1.5 — Data Audit

> **ENTER THIS PHASE ONLY AFTER THE USER HAS CONFIRMED THE BLUEPRINT.**

Scan every slide in the approved blueprint marked as a data or chart slide, or flagged `[DATA NEEDED]`. For each one, list:

- What data is required (metric name, time range, units, source)
- Whether the user has already provided it in this conversation

If **any** data is missing:

> **GATE 3 — HARD STOP.** Send a single message listing every missing data point. Example: *"Before I build, I need the following data: (1) monthly revenue Jan–Dec 2024, (2) number of co-working spaces in Metro Manila, (3) your current user count. Can you share these?"*
>
> Do not proceed to Phase 2. Do not guess values. Do not use illustrative numbers. Wait for the user to supply the data.

If all data is already present in the conversation, proceed to Phase 2 immediately — no need to message the user again.

---

## Phase 2 — Design System

Read `references/theme.md` in full before building the file.

**Non-negotiables:**
- Warm-neutral palette: soft white base `#FAFAF8`, cream/sand/warm gray surfaces, one accent color per deck
- No visually competing colors — all supporting elements stay neutral
- Accent used sparingly (4–6 times max across the full deck): one key stat, CTA, section divider
- Cohesion over variety: same fonts, same spacing, same color logic on every slide

Read `references/data-viz.md` for every slide that contains a chart or stat callout.

---

## Phase 3 — File Execution

> **ENTER THIS PHASE ONLY AFTER GATES 2 AND 3 ARE BOTH CLEARED.**

1. Read the pptx skill at `/mnt/skills/public/pptx/SKILL.md`
2. Follow its instructions to build the `.pptx` file
3. Apply the design system from `references/theme.md` exactly
4. Apply chart styling from `references/data-viz.md` for all data slides
5. Run the pptx skill's full QA process (content QA + visual QA)
6. Present the file to the user

---

## Reference files

- `references/theme.md` — Full design system: palette, typography, layout patterns, accent usage rules
- `references/data-viz.md` — Chart selection guide, styling rules, and pptxgenjs chart implementation patterns
