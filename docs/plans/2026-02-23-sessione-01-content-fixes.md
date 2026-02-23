# Sessione 01 Content Fixes — Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Fix all WARNING and INFO findings from the content accuracy audit (`docs/plans/2026-02-23-sessione-01-content-audit.md`) in the markdown files. CRITICAL slide issues are flagged as manual tasks.

**Architecture:** Straight edits to 3 markdown files in `sessione-01-fondamenti-jira/`. No code, no tests — verification is by reading the file after each edit.

**Tech Stack:** Markdown only. All files under `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/`.

---

### Task 1: Move workflow deprecation note from objectives to section 2.3 (W4)

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/outline.md:14` and `:75-81`

**Step 1: Remove the misplaced note from objectives**

In `outline.md`, delete line 14 (`- Nota: il vecchio editor di workflow sarà rimosso a giugno 2026`) from the "Obiettivi della sessione" list.

**Step 2: Add the note to section 2.3 Workflow base**

In `outline.md`, after line 81 (`- Esempio Tyvak: workflow di un work item IT (IT Manager)`), add:

```markdown
- **Nota**: il vecchio editor di workflow sarà rimosso a partire da giugno 2026 ([JRACLOUD-83818](https://jira.atlassian.com/browse/JRACLOUD-83818)) — il nuovo editor è già disponibile e funzionalmente completo
```

**Step 3: Verify**

Read `outline.md` and confirm:
- The objectives list (lines 7-13) no longer contains the workflow note
- Section 2.3 now includes the workflow note with source link

**Step 4: Commit**

```bash
git add jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/outline.md
git commit -m "docs: move workflow deprecation note to section 2.3 in sessione-01 outline"
```

---

### Task 2: Restructure exercise placement — move Esercizio 3 to Blocco 2 (W2)

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/outline.md:48-52` and `:85-87`

**Step 1: Remove Esercizio 3 from Blocco 1 exercises**

In `outline.md`, remove line 52 (`- [Esercizio 3: Creazione e gestione work item](esercizi/esercizio-01-creazione-work-item.md)`) from the "Esercizi Blocco 1" section.

**Step 2: Replace Blocco 2 placeholder with Esercizio 3**

Replace line 87 (`*Nessun esercizio assegnato — sessione di discussione guidata e Q&A*`) with:

```markdown
- [Esercizio 3: Creazione e gestione work item](esercizi/esercizio-01-creazione-work-item.md)

*Dopo l'esercizio: discussione guidata e Q&A sui work item creati*
```

**Step 3: Verify**

Read `outline.md` and confirm:
- Blocco 1 exercises list only Esercizio 1 (navigazione) and Esercizio 2 (ricerca)
- Blocco 2 exercises list Esercizio 3 (creazione work item) followed by discussion note

**Step 4: Commit**

```bash
git add jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/outline.md
git commit -m "docs: move work item exercise to Blocco 2 to align with theory sequence"
```

---

### Task 3: Fix broken glossary link (W1)

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/outline.md:100`

**Step 1: Update the glossary link**

The link `[Glossario Jira](../glossario.md)` is broken — the file doesn't exist. Replace line 100 with:

```markdown
- Glossario Jira *(in preparazione)*
```

This honestly signals the glossary isn't available yet, rather than linking to a missing file.

**Step 2: Verify**

Read `outline.md` final lines and confirm the broken link is replaced.

**Step 3: Commit**

```bash
git add jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/outline.md
git commit -m "docs: replace broken glossary link with placeholder note in sessione-01"
```

---

### Task 4: Fix English navigation labels in ricerca-base exercise (W3)

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/esercizi/esercizio-01-ricerca-base.md:17`

**Step 1: Update the navigation label**

Replace line 17:

```markdown
2. Dalla sidebar di navigazione sinistra, accedi alla "Ricerca avanzata" (Filters → Advanced issue search)
```

with:

```markdown
2. Dalla sidebar di navigazione sinistra, accedi a **Filtri** e poi seleziona **Ricerca avanzata**
```

This uses Italian labels matching the current UI and removes the old English path reference.

**Step 2: Verify**

Read `esercizio-01-ricerca-base.md` and confirm line 17 uses Italian labels.

**Step 3: Commit**

```bash
git add jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/esercizi/esercizio-01-ricerca-base.md
git commit -m "docs: use Italian UI labels for navigation in ricerca-base exercise"
```

---

### Task 5: Update priority value in creazione-work-item exercise (I1)

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/esercizi/esercizio-01-creazione-work-item.md:32`

**Step 1: Replace "Critical" with "Highest"**

Replace line 32:

```markdown
1. Task: "Manutenzione impianto climatizzazione clean room" — Priorità: Critical, Etichetta: `manutenzione`, Componente: `Facilities`
```

with:

```markdown
1. Task: "Manutenzione impianto climatizzazione clean room" — Priorità: Highest, Etichetta: `manutenzione`, Componente: `Facilities`
```

"Highest" is the standard Jira Cloud default priority. "Critical" is not part of the default scheme.

**Step 2: Verify**

Read `esercizio-01-creazione-work-item.md` line 32 and confirm it says "Highest".

**Step 3: Commit**

```bash
git add jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/esercizi/esercizio-01-creazione-work-item.md
git commit -m "docs: use standard Jira priority 'Highest' instead of non-default 'Critical'"
```

---

### Task 6: Add JQL backward compatibility note to outline (I5)

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/outline.md` — after the Blocco 2 workflow section

**Step 1: Add a callout box before the Recap section**

After the "Esercizi Blocco 2" section and before "Recap e Q&A", add:

```markdown
> **Nota sulla terminologia JQL e automazioni:** nonostante l'interfaccia di Jira ora utilizzi "spazio" e "elemento di lavoro", il linguaggio JQL continua a usare `project` e `issuetype` per retrocompatibilità. Anche gli smart value delle automazioni usano ancora `{{project}}`. Questi aspetti saranno approfonditi nella sessione 2.
```

**Step 2: Verify**

Read `outline.md` and confirm the callout appears between Esercizi Blocco 2 and Recap.

**Step 3: Commit**

```bash
git add jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/outline.md
git commit -m "docs: add JQL backward compatibility note to sessione-01 outline"
```

---

### Task 7: MANUAL — Rebuild slide deck (C1, C2, I2, I3)

**This task cannot be automated.** The slide deck is a PDF generated from an external source (likely PowerPoint).

**Checklist for manual slide rebuild:**

- [ ] **All slides**: Replace "progetto" → "spazio (space)", "issue" → "elemento di lavoro (work item)", "issue type" → "tipo di lavoro (work type)" on slides 1, 2, 4, 5, 6, 8, 9, 10, 11, 12, 14
- [ ] **Slide 1**: Update subtitle to "Architettura, navigazione, tipi di lavoro (work type) e workflow base"
- [ ] **Slide 4**: Replace "ticket" with "elemento di lavoro" or add "(informale: ticket)" qualifier
- [ ] **Slide 5**: Update hierarchy to "Sito → Spazio (Space) → Board → Elemento di lavoro (Work Item)"
- [ ] **Slide 8**: Redesign navigation section — replace "Barra superiore" with "Sidebar di navigazione sinistra"; update notification location; remove "g poi d" shortcut; keep "/" and "c" shortcuts
- [ ] **Slide 9**: Rename "Tipi di progetto" to "Tipi di spazio (Space Type)"
- [ ] **Slide 12**: Fix priorities from "Lowest → Low → Medium → High → Critical" to "Lowest → Low → Medium → High → Highest"
- [ ] **Optional — Slide for Cloud vs Data Center**: Add a slide covering "Jira Cloud vs Data Center: differenze chiave" to match outline section 1.1 (I4)
- [ ] Regenerate PDF and commit to `slides/sessione-01-fondamenti-jira.pdf`

---

## Task Summary

| # | Finding | File | Automated? |
|---|---------|------|------------|
| 1 | W4 — Workflow note placement | outline.md | Yes |
| 2 | W2 — Exercise/theory alignment | outline.md | Yes |
| 3 | W1 — Broken glossary link | outline.md | Yes |
| 4 | W3 — English navigation labels | esercizio-01-ricerca-base.md | Yes |
| 5 | I1 — Priority value | esercizio-01-creazione-work-item.md | Yes |
| 6 | I5 — JQL compat note | outline.md | Yes |
| 7 | C1+C2+I2+I3+I4 — Slide rebuild | slides/*.pdf | **MANUAL** |

Tasks 1-3 and 6 all touch `outline.md` — execute them in order on the same file.
