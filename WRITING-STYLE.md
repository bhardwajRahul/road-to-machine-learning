# Writing Style Guide

Use this guide when you add or edit lessons in Road to ML.

## Voice

Write like one teacher talking to a student. Prefer short sentences. Explain why a topic matters before listing details.

## Punctuation

Do **not** join two sentence clauses with:

- Semicolons (`;`)
- Colons (`:`) mid-sentence
- Em-dashes (`—`) or hyphens (`-`) as clause glue

**Avoid:** "Phase 0 is Python; Phase 1 is Pandas; Phase 2 is ML."

**Prefer:** "Stage 0 covers Python. Stage 1 covers Pandas. Stage 2 covers ML."

Colons are fine for labels before lists (`**Goal:**`, `**Note:**`) and for headers.

## Openings and closings

**Avoid:** "Comprehensive guide to…" as the default first line.

**Prefer:** "This guide covers…" or a plain sentence about what the reader will be able to do.

**Avoid:** Generic `**Try next:** Understanding the fundamentals is crucial…` closers.

**Prefer:** `**Try next:**` with one concrete action (a project, module, or exercise).

## Structure

- Use bullets for reference and checklists.
- Use prose paragraphs to connect ideas between sections.
- Mark **Core path** vs **Optional depth** when a module has extra topics.

## Numbering

- **Module NN** = folder name (`09-neural-networks-basics`)
- **Stage N** = recommended learning order in the main README

Never use "Phase" for both. Module 09 is not Stage 9.

## Project tutorials

Every project tutorial must be runnable or labeled **Outline only** at the top. Do not reference undefined variables. Do not end with "Congratulations" after three code snippets.

## Review checklist

Before you commit a lesson:

1. No semicolon or em-dash clause chains in body prose
2. Opening line is specific, not template boilerplate
3. Internal links work (`python tools/check_links.py path/to/file.md`)
4. Prerequisites use **Module NN**, not "Phase NN"
