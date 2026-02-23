# Multi-Course Repository Restructure

## Problem

The repo currently holds a single Tableau course at the root level. We need to restructure it so multiple courses can coexist, each in its own folder.

## Design

### Target structure

```
corsi-formazione/
├── README.md                           # Root index listing all courses
├── .gitignore                          # Shared across all courses
└── tableau-modello-dati-trimestrale/
    └── README.md                       # Existing course README (moved here)
```

Future courses are added as sibling folders to `tableau-modello-dati-trimestrale/`.

### Changes

1. **Move** `README.md` to `tableau-modello-dati-trimestrale/README.md`
2. **Update** the moved README's "Struttura del Repository" section to reflect paths relative to the course folder (remove the `/training-tableau-quarterly-model/` root reference)
3. **Create** a new root `README.md` as a course index with links to each course folder
4. **Update** `.gitignore` with general patterns useful across courses (replace the single-entry file)
5. **Rename the repo** from `corso-formazione-tableau` to `corsi-formazione` (GitHub operation, outside file restructuring)

### Conventions for future courses

- Each course lives in a top-level folder named descriptively (Italian, kebab-case)
- Each course folder contains its own `README.md` with syllabus and structure
- Session subfolders, resources, and setup docs live inside the course folder
- The root `README.md` is updated to list the new course
