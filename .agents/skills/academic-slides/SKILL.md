---
name: academic-slides
description: Create, recreate, inspect, and revise academic PowerPoint presentations (.pptx) from research papers, PDFs, figures, tables, and structured notes. Use whenever a presentation is requested or a PPTX is involved.
license: Apache-2.0
metadata:
  short-description: "Academic PowerPoint authoring and quality assurance"
  upstream-author: OpenAI
  upstream-source: https://github.com/openai/skills/tree/e6afb0d74cc75d220df2faf3dd6c635c2dc6a108/skills/.curated/slides
  adapted-for: "xijinlong420/Graduation-paper"
---

# Academic Slides Skill

## Purpose

Create accurate, readable, editable academic presentations from source papers. The source document is authoritative: do not silently add, remove, reconcile, or replace its claims, terminology, sample details, statistics, or limitations with general knowledge.

## Preferred authoring approach

- Use **PptxGenJS** for creating or rebuilding decks. Avoid `python-pptx` for authoring unless the task is inspection-only.
- Use a task-local working directory. Keep the generator source (`.js`), source-derived assets, and final `.pptx` together.
- Default to 16:9 unless the source or user requests another aspect ratio.
- Use editable PowerPoint text, shapes, tables, and native charts whenever practical.
- For an academic minimalist deck, follow the user’s requested style. If unspecified, use a white background, black/dark text, restrained typography, consistent margins, generous whitespace, and minimal decoration.

## Source fidelity

1. Read the complete source paper before drafting the deck.
2. Build a claim-to-source outline: research question, theory/concepts, hypotheses, samples, procedure, measures, analyses, results, limitations, and implications.
3. Preserve reported statistical notation and exact values. Do not invent missing statistics or infer significance from a chart.
4. Distinguish authors’ interpretations from results directly tested by the study.
5. Do not turn correlational or vignette findings into causal claims or real-world behavior claims.
6. Cite the paper on relevant slides; include full reference and DOI when supplied and verified.
7. When the user asks for original figures/tables, insert faithful crops from the source PDF. Do not redraw or alter data unless explicitly requested. Preserve captions/axes/legends and note the source page.

## Recommended academic deck structure

Adapt to the paper rather than forcing a fixed template:
- Title and bibliographic information
- Research background / problem
- Research question and conceptual framework
- Study design and sample
- Measures and operationalization
- One or more results slides per study, using original figures/tables where appropriate
- Discussion and theoretical contribution
- Limitations and alternative explanations
- Implications for the user's project (clearly labeled as inference, not source findings)
- Take-home conclusions and references

## Build and quality assurance workflow

1. Identify audience, presentation duration, slide count, and requested visual style from the conversation. Ask only for essential missing details.
2. Extract the source content and record all key values before slide authoring.
3. Create the deck with PptxGenJS; set theme fonts explicitly and size text boxes deliberately. Do not rely on automatic fitting as a substitute for layout design.
4. Preserve figure aspect ratios using intentional crop/contain calculations.
5. Render every slide to PNG or PDF using available LibreOffice/Poppler tooling; inspect a montage and individual dense/result slides.
6. Run overflow checks and verify no clipped text, overlaps, missing glyphs, substituted fonts, unreadable figures, or broken references.
7. Re-check all numbers, p values, effect sizes, sample sizes, figure labels, and DOI against the source paper.
8. Deliver the editable `.pptx` and the authoring `.js`; state what checks were actually completed. Never claim QA passed if rendering/inspection was not performed.

## Research integrity and privacy

- Never fabricate references, data, participants, ethics approvals, results, or quotations.
- Do not upload unpublished manuscripts, student records, identifiable data, consent forms, or copyrighted source PDFs to a public repository.
- Store only reusable skill instructions and non-sensitive scripts in this repository. Keep research source files and generated decks in private/local storage unless the user explicitly approves an appropriate destination.
- This skill is a project-level instruction file. Adding it to GitHub versions the instructions; it does not automatically install it into ChatGPT's runtime or make it globally available in every conversation.

## Upstream attribution

Adapted from the OpenAI-authored `slides` skill. Upstream source and author attribution are recorded in the metadata above. Consult the upstream source for changes and bundled utilities before updating this adaptation.
