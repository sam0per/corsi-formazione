# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Training materials repository ("corsi-formazione") for professional courses by Kinetikon. All content is written in **Italian**. The repository contains no executable code — it is purely documentation and educational materials.

Currently one course exists: **Tableau e Modello Dati Trimestrale** (24 hours, 6 sessions on Tableau data visualization and a quarterly data model for project control).

## Repository Structure

```
/
├── README.md                              # Course index (lists all courses)
└── tableau-modello-dati-trimestrale/
    └── README.md                          # Full syllabus for the Tableau course
```

Each course lives in its own directory with a planned structure of `sessione-NN-*/` subdirectories containing `slides/`, `esercizi/`, `dati/`, `soluzioni/`, and `note-sessione.md`. The session materials are planned but not yet populated.

## Conventions

- **Language**: All documentation, file names, and directory names are in Italian
- **Naming**: Kebab-case for directories and files (e.g., `sessione-01-fondamenti-tableau-intro`)
- **Commit messages**: Use conventional prefixes — `docs:`, `chore:`, `refactor:` — followed by English descriptions
- **New courses**: Add a new top-level directory and update the root `README.md` course index table
- **Tableau files**: `.twbr` and `~$*.twbx` are gitignored as temporary Tableau artifacts
