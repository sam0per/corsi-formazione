# Multi-Course Repository Restructure — Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Restructure the repo so each course lives in its own top-level folder, starting by moving the existing Tableau course into `tableau-modello-dati-trimestrale/`.

**Architecture:** Flat directory layout — one folder per course at the root, a shared root README as index, shared root `.gitignore`. No nesting beyond course folders.

**Tech Stack:** Git (file moves), Markdown

**Design doc:** `docs/plans/2026-02-23-multi-course-restructure-design.md`

---

### Task 1: Move the existing README into the course folder

**Files:**
- Move: `README.md` → `tableau-modello-dati-trimestrale/README.md`

**Step 1: Create the course directory and move the file**

```bash
mkdir -p tableau-modello-dati-trimestrale
git mv README.md tableau-modello-dati-trimestrale/README.md
```

**Step 2: Verify the move**

```bash
ls tableau-modello-dati-trimestrale/README.md
git status
```

Expected: `README.md` shows as renamed, file exists at new path.

**Step 3: Commit**

```bash
git add tableau-modello-dati-trimestrale/README.md
git commit -m "refactor: move Tableau course README into its own folder"
```

---

### Task 2: Update paths in the moved course README

**Files:**
- Modify: `tableau-modello-dati-trimestrale/README.md`

The "Struttura del Repository" section (line ~321) uses `/training-tableau-quarterly-model/` as the root. Update it to show paths relative to the course folder. Also update path references in "Setup Iniziale" and "Risorse Aggiuntive" sections.

**Step 1: Update the "Struttura del Repository" tree diagram**

Replace the root label `/training-tableau-quarterly-model/` with `tableau-modello-dati-trimestrale/` (line 322).

Old:
```
/training-tableau-quarterly-model/
│
├── README.md (questo file)
```

New:
```
tableau-modello-dati-trimestrale/
│
├── README.md (questo file)
```

**Step 2: Update path references in "Setup Iniziale"**

- Line 410: `/setup/installazione-tableau.md` → `setup/installazione-tableau.md`
- Line 412: `/sessione-01-fondamenti-tableau-intro/` → `sessione-01-fondamenti-tableau-intro/`
- Line 415: `/setup/configurazione-database.md` → `setup/configurazione-database.md`

These are already relative within the course folder — just remove the leading `/` to make them unambiguously relative.

**Step 3: Update path reference in "Risorse Aggiuntive"**

- Line 431: `/risorse/` → `risorse/`

**Step 4: Verify the file reads correctly**

Skim the changed sections to confirm paths are consistent.

**Step 5: Commit**

```bash
git add tableau-modello-dati-trimestrale/README.md
git commit -m "docs: update paths in Tableau course README to be relative"
```

---

### Task 3: Create the root README as a course index

**Files:**
- Create: `README.md`

**Step 1: Write the root README**

```markdown
# Corsi di Formazione

Repository contenente i materiali per i corsi di formazione.

## Corsi Disponibili

| Corso | Descrizione | Durata |
|-------|-------------|--------|
| [Tableau e Modello Dati Trimestrale](tableau-modello-dati-trimestrale/) | Data Visualization con Tableau e modello dati della trimestrale | 24 ore (6 sessioni) |

## Struttura

Ogni corso ha la propria cartella con README, sessioni, esercizi e risorse.

## Formatore

**Samuel Perini, PhD**
Data Scientist & Formatore

- Email: prnsml@gmail.com
- LinkedIn: [samuelperini](https://www.linkedin.com/in/samuel-perini/)
```

**Step 2: Verify the link works**

Confirm the relative link `tableau-modello-dati-trimestrale/` points to the correct folder.

**Step 3: Commit**

```bash
git add README.md
git commit -m "docs: add root README as course index"
```

---

### Task 4: Update the shared .gitignore

**Files:**
- Modify: `.gitignore`

**Step 1: Replace contents with general patterns**

Current `.gitignore` only contains `training_readme_italiano.md`. Replace with patterns useful across all courses:

```gitignore
# OS files
.DS_Store
Thumbs.db

# Tableau temp files
*.twbr
~$*.twbx

# Editor files
*.swp
*~
.vscode/
.idea/

# Draft/working files
training_readme_italiano.md
```

**Step 2: Verify**

```bash
cat .gitignore
```

**Step 3: Commit**

```bash
git add .gitignore
git commit -m "chore: update .gitignore with general patterns for multi-course repo"
```

---

### Task 5: Move docs/plans into the repo root (outside course folders)

**Files:**
- Keep: `docs/plans/` at root level (already there, no move needed)

The `docs/plans/` directory contains repo-level design documents, not course-specific content. It's already at the root level. No action needed — just verify it's correctly placed.

**Step 1: Verify**

```bash
ls docs/plans/
```

Expected: `2026-02-23-multi-course-restructure-design.md` and `2026-02-23-multi-course-restructure-plan.md`

---

### Task 6: Final verification and cleanup

**Step 1: Verify final directory structure**

```bash
find . -not -path './.git/*' -not -path './.claude/*' | sort
```

Expected:
```
.
./.gitignore
./README.md
./docs
./docs/plans
./docs/plans/2026-02-23-multi-course-restructure-design.md
./docs/plans/2026-02-23-multi-course-restructure-plan.md
./tableau-modello-dati-trimestrale
./tableau-modello-dati-trimestrale/README.md
```

**Step 2: Verify git log shows clean history**

```bash
git log --oneline
```

**Step 3: Note for user — repo rename**

The GitHub repo rename from `corso-formazione-tableau` to `corsi-formazione` is a manual operation:
- GitHub → Settings → Repository name → change to `corsi-formazione`
- Update any local remotes: `git remote set-url origin <new-url>`
