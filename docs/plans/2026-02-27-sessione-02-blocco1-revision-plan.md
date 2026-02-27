# Sessione 02 Block 1 Revision — Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Revise Block 1 of sessione-02 to remove basic search (already known), keep JQL fundamentals, and add multi-condition filters with parent hierarchy, WAS/CHANGED operators, and role-based scenarios.

**Architecture:** Two markdown files to edit: the session outline and the fundamentals exercise. Block 2 and the advanced exercise are untouched. No code — docs only.

**Tech Stack:** Markdown (Italian language)

**Design doc:** `docs/plans/2026-02-27-sessione-02-blocco1-revision-design.md`

---

### Task 1: Update session objectives in outline.md

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-02-filtri-ricerche-jql/outline.md:7-12`

**Step 1: Replace the objectives list**

Replace lines 7-12 (the four bullet points under "Obiettivi della sessione") with:

```markdown
Al termine di questa sessione i partecipanti saranno in grado di:

- Scrivere query JQL (Jira Query Language) per ricerche mirate
- Comporre query multi-condizione con operatori logici e raggruppamento
- Utilizzare i campi di gerarchia (`parent`) e cronologia (`WAS`, `CHANGED`) nelle query
- Salvare, condividere e gestire filtri personali e di team
- Configurare sottoscrizioni email sui filtri
```

**Step 2: Verify**

Read lines 5-13 of the file and confirm the new objectives are in place.

**Step 3: Commit**

```bash
git add jira-confluence-best-practices-2026/sessione-02-filtri-ricerche-jql/outline.md
git commit -m "docs: update sessione-02 objectives to reflect Block 1 revision"
```

---

### Task 2: Rewrite Block 1 theory in outline.md

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-02-filtri-ricerche-jql/outline.md:18-41`

**Step 1: Replace Block 1 header and all theory content**

Replace from line 18 (`### Blocco 1 — Ricerca base e introduzione a JQL (0:00 - 1:00)`) through line 41 (the last Tyvak example) with the following new Block 1:

```markdown
### Blocco 1 — JQL: dai fondamenti ai filtri complessi (0:00 - 1:00)

#### 2.1 Introduzione a JQL (30 min)

- Cos'è JQL e perché è fondamentale
- Anatomia di una query JQL: `campo operatore valore`
- Campi principali: `space` (alias: `project`), `status`, `assignee`, `reporter`, `priority`, `type` (alias: `issuetype`), `created`, `updated`, `resolved`, `labels`, `component`
- Operatori di confronto: `=`, `!=`, `>`, `<`, `>=`, `<=`
- Operatori logici: `AND`, `OR`, `NOT`
- Operatore `IN` / `NOT IN`: `status IN ("To Do", "In Progress")`
- Operatore `IS EMPTY` / `IS NOT EMPTY`: `assignee IS EMPTY`
- Ordinamento: `ORDER BY created DESC`
- Esempi pratici contestualizzati Tyvak:
  - `space = "IT-HELPDESK" AND status = "Open" ORDER BY priority DESC`
  - `assignee = currentUser() AND status != Done`
  - `labels = "onboarding" AND created >= -7d`

#### 2.2 Filtri multi-condizione e scenari per ruolo (20 min)

**Parte 1 — Building incrementale (5 min)**

Partire da una query semplice e aggiungere condizioni passo dopo passo:

1. `space = "IT-HELPDESK"`
2. `space = "IT-HELPDESK" AND status != Done`
3. `space = "IT-HELPDESK" AND status != Done AND (priority = Critical OR priority = High)`
4. `space = "IT-HELPDESK" AND status != Done AND (priority = Critical OR priority = High) AND assignee = currentUser() ORDER BY created ASC`

Concetto chiave: precedenza degli operatori (`AND` ha priorità su `OR`), perché servono le parentesi.

**Parte 2 — Condizioni annidate: gerarchia e cronologia (7 min)**

- Campo `parent`: `parent IS NOT EMPTY`, `parent IS EMPTY`
- Status storico: `status WAS "In Review"`, `status CHANGED FROM "To Do" TO "In Progress"`
- Date range: `created >= startOfMonth(-1) AND created <= endOfMonth(-1)`
- Combinazione gerarchia + cronologia + date

Demo incrementale:

1. `type = Task AND space = "IT-HELPDESK"`
2. `type = Task AND space = "IT-HELPDESK" AND parent IS NOT EMPTY`
3. `type = Task AND space = "IT-HELPDESK" AND parent IS NOT EMPTY AND status WAS "In Review"`
4. `type = Task AND space = "IT-HELPDESK" AND parent IS NOT EMPTY AND status WAS "In Review" AND created >= startOfMonth(-1) AND created <= endOfMonth(-1)`

> ℹ️ **Nota per il formatore:** JQL standard non supporta `parent.status` (non è un campo valido). Workaround: creare un filtro salvato sui parent e incrociare i risultati su board o dashboard.

**Parte 3 — Uno scenario per ruolo (8 min)**

- **IT Manager** — Subtask aperti con storia "In Review", ultimo mese:
  `type = Task AND space = "IT-HELPDESK" AND parent IS NOT EMPTY AND status WAS "In Review" AND status != Done AND created >= -30d`
- **Admin & Finance** — Ordini con cambio stato e scadenza imminente:
  `labels IN ("acquisti", "fatturazione") AND (status CHANGED FROM "In attesa approvazione" OR due <= 7d) AND status NOT IN ("Done", "Cancelled")`
- **HR Generalist** — Task onboarding figli, in ritardo o revisionati:
  `labels = "onboarding" AND parent IS NOT EMPTY AND (due < now() OR status WAS "In Review") AND status != Done ORDER BY due ASC`
- **Facility Manager** — Manutenzioni con passaggio di stato questo mese:
  `space = "FACILITY" AND labels = "manutenzione" AND status CHANGED FROM "Open" TO "In Progress" AFTER startOfMonth() ORDER BY priority DESC`
```

**Step 2: Verify**

Read lines 18-70 (approx) and confirm: Block 1 header says "JQL: dai fondamenti ai filtri complessi", section 2.1 has no "Ricerca in Jira: panoramica", section 2.2 contains the three parts.

**Step 3: Commit**

```bash
git add jira-confluence-best-practices-2026/sessione-02-filtri-ricerche-jql/outline.md
git commit -m "docs: rewrite sessione-02 Block 1 — drop basic search, add multi-condition JQL"
```

---

### Task 3: Add Livello 4 to esercizio-02-jql-fondamentali.md

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-jql-fondamentali.md:57-65`

**Step 1: Insert Livello 4 after Livello 3 (after line 56) and update result counts**

Insert the following block between the end of Livello 3 (line 56) and the "Risultato atteso" section (line 58):

```markdown

**Livello 4 — Condizioni annidate e cronologia:**

11. Trova tutti i subtask (elementi di lavoro con un parent) del tuo spazio che non sono completati:
    ```
    space = "___" AND parent IS ___ AND status != "Done"
    ```

12. Trova gli elementi di lavoro il cui status è passato per "In Review" nell'ultimo mese:
    ```
    status ___ "In Review" AND created >= ___
    ```

13. Trova gli elementi di lavoro con priorità Critical OPPURE con scadenza entro 7 giorni, nello spazio IT, ordinati per scadenza:
    ```
    space = "IT-HELPDESK" AND (___ = Critical ___ due <= ___) AND status != Done ORDER BY ___ ASC
    ```

14. **Sfida finale**: Scrivi una query per il tuo ruolo che combini almeno 4 condizioni, includa parentesi di raggruppamento e utilizzi `WAS` o `CHANGED`. Discuti la query con il gruppo.

```

Then update the "Risultato atteso" section to reflect 14 queries:

```markdown
## Risultato atteso

- 14 query JQL scritte e funzionanti
- Comprensione degli operatori `=`, `!=`, `IN`, `>=`, `IS EMPTY`, `WAS` e dell'ordinamento
- Capacità di comporre query multi-condizione con raggruppamento tramite parentesi
```

**Step 2: Verify**

Read the full file and confirm: Livello 4 appears after Livello 3, contains queries 11-14, and "Risultato atteso" says 14 queries.

**Step 3: Commit**

```bash
git add jira-confluence-best-practices-2026/sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-jql-fondamentali.md
git commit -m "docs: add Livello 4 (nested conditions) to sessione-02 JQL exercise"
```

---

### Task 4: Final review and consistency check

**Files:**
- Read: `jira-confluence-best-practices-2026/sessione-02-filtri-ricerche-jql/outline.md` (full file)
- Read: `jira-confluence-best-practices-2026/sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-jql-fondamentali.md` (full file)
- Read: `jira-confluence-best-practices-2026/sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-jql-avanzato.md` (full file, check for overlap)

**Step 1: Verify outline structure**

Confirm:
- [ ] Block 1 title: "JQL: dai fondamenti ai filtri complessi"
- [ ] No "2.1 Ricerca in Jira: panoramica" section exists
- [ ] Section 2.1 is "Introduzione a JQL (30 min)" — no `WAS`/`CHANGED` here
- [ ] Section 2.2 is "Filtri multi-condizione e scenari per ruolo (20 min)" — has 3 parts
- [ ] Block 2 is unchanged (sections 2.3, 2.4, 2.5)
- [ ] Timings add up: 30 + 20 + 10 (pause) = 60 min for Block 1

**Step 2: Verify exercise**

Confirm:
- [ ] Livelli 1-3 are unchanged
- [ ] Livello 4 has queries 11-14
- [ ] "Risultato atteso" says 14 queries

**Step 3: Check for overlap with esercizio-02-jql-avanzato.md**

Read the advanced exercise and confirm no duplication with the new Livello 4 content. The advanced exercise focuses on functions (`startOfDay()`, `text ~`, `reporter vs assignee`) and filter management — no overlap expected.

**Step 4: No commit** (read-only task)
