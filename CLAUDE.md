# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Training materials repository ("corsi-formazione") for professional courses by Kinetikon. All content is written in **Italian**. The repository contains no executable code — it is purely documentation and educational materials.

Two courses exist:

- **Tableau e Modello Dati Trimestrale** — 24 hours, 6 sessions on Tableau data visualization and a quarterly data model for project control
- **Jira & Confluence Best Practices 2026** — 20 hours, 5 sessions on Jira Cloud and Confluence best practices for IT, HR, Finance, and Facility teams

## Repository Structure

```
/
├── README.md                              # Course index (lists all courses)
├── docs/plans/                            # Audit reports and implementation plans
├── tableau-modello-dati-trimestrale/
│   └── README.md                          # Full syllabus for the Tableau course
└── jira-confluence-best-practices-2026/
    ├── README.md                          # Syllabus for the Jira/Confluence course
    ├── glossario.md                       # Jira/Confluence glossary
    ├── cheatsheet/                        # Quick-reference guides
    └── sessione-01-fondamenti-jira/       # Session 1 (outline, slides, esercizi)
```

Each course lives in its own directory. Sessions use `sessione-NN-*/` subdirectories containing `slides/`, `esercizi/`, and an `outline.md`.

## Conventions

- **Language**: All documentation, file names, and directory names are in Italian
- **Naming**: Kebab-case for directories and files (e.g., `sessione-01-fondamenti-tableau-intro`)
- **Commit messages**: Use conventional prefixes — `docs:`, `chore:`, `refactor:` — followed by English descriptions
- **New courses**: Add a new top-level directory and update the root `README.md` course index table
- **Slides**: Use [Marp](https://marp.app/) markdown (`.md` with Marp front matter) as slide source format
- **Tableau files**: `.twbr` and `~$*.twbx` are gitignored as temporary Tableau artifacts
