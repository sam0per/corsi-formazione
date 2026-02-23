# Complete Slides 6, 8, 9, 10 — Sessione 01 Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Fill four empty slides (6, 8, 9, 10) in the Sessione 01 Marp deck with concise, table-centric content about Jira schema types, workflow types, screen types, and permission types.

**Architecture:** Each slide gets a scoped font-size style, intro sentence, Markdown table, and optional footer note. All edits target a single file. No code, no tests — documentation only.

**Tech Stack:** Marp Markdown

**Design doc:** `docs/plans/2026-02-23-sessione-01-slides-6-8-9-10-design.md`

---

### Task 1: Complete Slide 6 — Tipi di schema

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/slides/sessione-01-fondamenti-jira.md:75-77`

**Step 1: Replace the empty slide content**

Replace lines 74–77 (the `---`, title, blank line, `---` block) with:

```markdown
---

<style scoped>
  section { font-size: 22px; }
</style>

# Tipi di schema

Gli **schemi** (scheme) sono configurazioni riutilizzabili che definiscono il comportamento di uno spazio **company-managed**.

| Schema | Definisce |
|--------|-----------|
| **Work Type Scheme** | Quali tipi di lavoro sono disponibili nello spazio |
| **Workflow Scheme** | Quale workflow si applica a ciascun tipo di lavoro |
| **Screen Scheme** | Quali campi mostrare per creazione, modifica e visualizzazione |
| **Permission Scheme** | Chi può fare cosa nello spazio |
| **Notification Scheme** | Chi riceve notifiche per quali eventi |

> Negli spazi **team-managed**, queste configurazioni sono gestite direttamente senza schemi espliciti.

---
```

**Step 2: Verify rendering**

Run: `grep -n "Tipi di schema" jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/slides/sessione-01-fondamenti-jira.md`
Expected: one match with content following the title (not just the title alone).

---

### Task 2: Complete Slide 8 — Tipi di workflow

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/slides/sessione-01-fondamenti-jira.md` (the `# Tipi di workflow` empty slide)

**Step 1: Replace the empty slide content**

Replace the `# Tipi di workflow` empty slide block with:

```markdown
---

<style scoped>
  section { font-size: 24px; }
</style>

# Tipi di workflow

Il **Workflow Scheme** collega ogni tipo di lavoro al suo workflow.

| Tipo di workflow | Descrizione | Uso tipico |
|------------------|-------------|------------|
| **Predefinito** | To Do → In Progress → Done | Nuovi spazi, processi semplici |
| **Personalizzato** | Stati e transizioni su misura | Processi con approvazione, review, ecc. |

- **Team-managed**: workflow configurabile direttamente nella board
- **Company-managed**: workflow gestito tramite scheme, condivisibile tra spazi

> Approfondimento: personalizzazione workflow in **Sessione 4**.

---
```

---

### Task 3: Complete Slide 9 — Tipi di schermata (Screen)

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/slides/sessione-01-fondamenti-jira.md` (the `# Tipi di schermata (Screen)` empty slide)

**Step 1: Replace the empty slide content**

Replace the `# Tipi di schermata (Screen)` empty slide block with:

```markdown
---

<style scoped>
  section { font-size: 24px; }
</style>

# Tipi di schermata (Screen)

Lo **Screen Scheme** definisce quali campi sono visibili per ciascuna operazione su un work item.

| Contesto | Quando appare | Esempio campi |
|----------|---------------|---------------|
| **Create** | Creazione di un nuovo work item | Summary, Tipo, Priorità, Assegnatario |
| **Edit** | Modifica di un work item | Tutti i campi modificabili |
| **View** | Visualizzazione di un work item | Tutti i campi inclusi quelli di sola lettura |

- **Team-managed**: campi gestiti direttamente per tipo di lavoro
- **Company-managed**: schermate configurate tramite scheme centralizzati

---
```

---

### Task 4: Complete Slide 10 — Tipi di permesso (Permission)

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/slides/sessione-01-fondamenti-jira.md` (the `# Tipi di permesso (Permission)` empty slide)

**Step 1: Replace the empty slide content**

Replace the `# Tipi di permesso (Permission)` empty slide block with:

```markdown
---

<style scoped>
  section { font-size: 22px; }
</style>

# Tipi di permesso (Permission)

I permessi in Jira si dividono in due livelli:
- **Globali** — azioni a livello di sito (es. creare spazi, gestire utenti)
- **Di spazio** — azioni all'interno di un singolo spazio, definite dal **Permission Scheme**

| Permesso di spazio | Azione |
|--------------------|--------|
| **Browse** | Visualizzare lo spazio e i work item |
| **Create** | Creare nuovi work item |
| **Edit** | Modificare work item esistenti |
| **Assign** | Assegnare work item ad altri utenti |
| **Transition** | Cambiare lo stato di un work item |

> Approfondimento: gestione permessi e ruoli in **Sessione 4**.

---
```

---

### Task 5: Final verification and commit

**Step 1: Count slides**

Run: `grep -c "^---$" jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/slides/sessione-01-fondamenti-jira.md`
Expected: same number of `---` separators as before (20), confirming no slides were accidentally added or removed.

**Step 2: Check Marp rendering (optional)**

Run: `npx @marp-team/marp-cli@latest jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/slides/sessione-01-fondamenti-jira.md --html -o /tmp/sessione-01-check.html`
Open `/tmp/sessione-01-check.html` in browser to verify slides render correctly.

**Step 3: Commit**

```bash
git add jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/slides/sessione-01-fondamenti-jira.md
git commit -m "docs: complete slides 6, 8, 9, 10 with schema, workflow, screen, and permission type overviews"
```
