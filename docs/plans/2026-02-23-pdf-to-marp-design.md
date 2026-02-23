# PDF to Marp Markdown Conversion — Design

> Date: 2026-02-23 | Scope: `sessione-01-fondamenti-jira/slides/`

## Goal

Convert the sessione-01 slide deck from PDF (generated from an external PowerPoint source) to a Marp-based markdown file. The markdown becomes the editable source of truth. All audit fixes (C1, C2, I1, I2, I3 from the content accuracy audit) are applied during conversion.

## Approach

Single Marp markdown file with `---` slide separators. Default Marp theme, no custom CSS. 16 slides matching the current PDF structure.

## Output file

`sessione-01-fondamenti-jira/slides/sessione-01-fondamenti-jira.md`

The old PDF (`sessione-01-fondamenti-jira.pdf`) is deleted from the repo. PDF generation becomes: `marp sessione-01-fondamenti-jira.md --pdf`.

## Marp structure

```yaml
---
marp: true
theme: default
paginate: true
title: "Sessione 1 — Fondamenti di Jira Cloud"
---
```

Slides separated by `---`. Markdown features used:
- `#` / `##` for titles and section headings
- Tables, bullet lists, bold/italic for content
- `<!-- _class: lead -->` for title/section-break slides

## Audit fixes applied

| Finding | Fix |
|---------|-----|
| C1 — Old terminology (11 slides) | "progetto" → "spazio (space)", "issue" → "elemento di lavoro (work item)", "issue type" → "tipo di lavoro (work type)" |
| C2 — Old navigation (slide 8) | Replace top-bar description with left sidebar navigation |
| I1 — Priority values (slide 12) | "Critical" → "Highest" |
| I2 — "ticket" term (slide 4) | Replace with official terminology |
| I3 — Subtitle language (slide 1) | Italian subtitle with new terminology |

## Scope boundaries

- Only sessione-01 slides
- No custom CSS theme (Marp default)
- No build scripts or CI automation
- No changes to other sessions' slides
