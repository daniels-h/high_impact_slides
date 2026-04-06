# High-Impact Slides Skill

A custom skill built on top of the existing `pptx` built-in tool to create more effective, polished, and story-driven slides. It prioritizes narrative strategy and robust visual design systems before executing the final file creation.

## Overview
This skill produces presentations that are clear, cohesive, and visually calm. It is highly suited for business pitches, academic class presentations, and data or analytics reports.

## Key Features
* **Story-Driven Structure**: Organizes content using proven narrative frameworks like SCR (Situation, Complication, Resolution) or SCQA.
* [cite_start]**Warm-Neutral Theme**: Employs a cohesive design system using soft whites (`#FAFAF8`) [cite: 8][cite_start], warm creams (`#F2EFE9`) [cite: 9][cite_start], and a single carefully chosen accent color[cite: 13].
* [cite_start]**Insight-Led Data Visualization**: Ensures charts make one point obvious [cite: 70][cite_start], stripping out visual noise and relying on clean geometric icons[cite: 31].
* **Gate-Driven Process**: Pauses for explicit user confirmation before moving between strategy, data collection, and slide generation to prevent hallucinated content.

## How It Works
The skill operates in three mandatory phases:
1. **Phase 1 - Narrative Strategy**: Clarifies the goal and audience, identifies the core message, chooses an appropriate narrative structure, and builds a slide-by-slide blueprint for user approval.
2. **Phase 1.5 - Data Audit**: Scans the approved blueprint for missing metrics and requests the required data from the user before building.
3. **Phase 2+ - Design System & Execution**: Applies the strict design philosophy and chart styling rules, then uses the standard `pptx` skill to generate the final file.

## Core Design Principles
* [cite_start]**Cohesion**: The design supports the content quietly, ensuring every slide looks like part of the same family[cite: 5].
* [cite_start]**Restraint**: Limits accent colors to a maximum of 4 to 6 uses per deck to prevent visual competition[cite: 68].
* [cite_start]**Purposeful Space**: Every zone on a slide must have a declared purpose, actively avoiding accidental white space[cite: 48].

## Reference Files
* `SKILL.md`: The core operational logic, gating rules, and prompt instructions.
* `theme`: The full design system encompassing the color palette, typography rules, layout patterns, and icon vocabulary.
* `data-visualization`: The chart selection guide, styling rules, and code implementation patterns for `pptxgenjs`.
