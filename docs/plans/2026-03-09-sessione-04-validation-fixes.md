# Sessione 04 Validation Fixes — Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Fix all critical errors, important issues, and missing content identified by the 5-agent validation audit of sessione-04 materials.

**Architecture:** Each task targets a single file, enabling full parallel execution. Tasks are grouped by severity: critical errors first, then important issues, then missing content additions. Within each file, all fixes are applied in a single task to avoid merge conflicts.

**Tech Stack:** Markdown editing only — no executable code in this repository.

---

## Scope Summary

| Severity | Count | Description |
|----------|-------|-------------|
| Critical | 3 | Smart values syntax, branch smart values, "Publish" terminology |
| Important | 6 | Automation model, JQL quoting, limits, navigation paths, admin hierarchy, company-managed flags |
| Missing content | 6 | Rule actor, audit log in theory, status categories, workflow editor rule types, issue security schemes, automation template library |

**Files affected (7):**

| # | File | Task |
|---|------|------|
| 1 | `sessione-04-.../outline.md` | Task 1 |
| 2 | `sessione-04-.../esercizi/esercizio-0401-regole-automazione.md` | Task 2 |
| 3 | `sessione-04-.../esercizi/esercizio-0402-workflow-personalizzato.md` | Task 3 |
| 4 | `sessione-04-.../esercizi/esercizio-0403-admin-permessi.md` | Task 4 |
| 5 | `sessione-04-.../esercizi/esercizio-0404-tipi-space-workflow.md` | Task 5 |
| 6 | `glossario.md` | Task 6 |
| 7 | `cheatsheet/automazioni-cheatsheet.md` | Task 7 |

All file paths below are relative to:
`jira-confluence-best-practices-2026/`

---

## Task 1: Fix outline.md (all issues)

**File:**
- Modify: `sessione-04-automazioni-workflow-admin/outline.md`

This is the largest task. It addresses critical errors, important issues, and adds missing content.

**Step 1: Fix smart values syntax (CRITICAL) — line 51**

Replace line 51:
```
- **Smart values**: `{{workItem.key}}`, `{{workItem.summary}}`, `{{now.plusDays(7)}}`, `{{workItem.assignee.displayName}}`
```
With:
```
- **Smart values**: `{{issue.key}}`, `{{issue.summary}}`, `{{now.plusDays(7)}}`, `{{issue.assignee.displayName}}`
- > **Nota terminologia**: nonostante la UI mostri "work item", gli smart values usano ancora la sintassi `{{issue.*}}`. La forma `{{workItem.*}}` non è supportata e causerebbe errori.
```

**Step 2: Fix core automation model (IMPORTANT) — line 24**

Replace line 24:
```
- Concetto chiave: **Trigger → Condizioni → Azioni**
```
With:
```
- Concetto chiave: **Trigger → Condizioni → Azioni** (+ **Branch** per work item collegati)
```

**Step 3: Fix automation limits (IMPORTANT) — line 26**

Replace line 26:
```
- Limiti del piano Cloud per aziende con <250 utenti (eg, numero di esecuzioni mensili)
```
With:
```
- Limiti di esecuzione mensili per piano Cloud:
  - Free: ~100 esecuzioni globali/mese
  - Standard: ~1.700 totali/mese (500 globali)
  - Premium: 1.000 per utente/mese (pool condiviso)
  - Enterprise: illimitato
```

**Step 4: Add missing content to section 4.3 (MISSING) — after line 50**

After the existing "Branch rule" bullet (line 50), add three new bullets before smart values:

```
- **Rule actor**: l'utente virtuale che esegue le azioni dell'automazione. Se il rule actor non ha i permessi necessari, la regola fallisce silenziosamente. Verificare sempre i permessi del rule actor.
- **Template di automazione**: Jira offre una libreria di regole predefinite (Automation templates). Punto di partenza consigliato prima di creare regole da zero.
- **Debug e audit log**: Space settings → Automation → Audit log. Ogni esecuzione mostra trigger, condizioni valutate e azioni eseguite. Strumento fondamentale per il troubleshooting.
```

**Step 5: Add status categories to section 4.4 (MISSING) — after line 61**

After "Aggiungere stati personalizzati" (line 61), add:

```
- **Categorie di status**: ogni stato deve appartenere a una delle tre categorie obbligatorie: *To Do*, *In Progress*, *Done*. Le categorie determinano il comportamento di board, report e sprint insights.
```

**Step 6: Add workflow editor rule types to section 4.4 (MISSING) — replace line 62**

Replace line 62:
```
- Configurare transizioni: regole (rules) nel nuovo editor
```
With:
```
- Configurare transizioni nel nuovo editor — tre tipi di regole:
  - **Restrict transition**: chi può eseguire la transizione (es. solo l'assegnatario, un ruolo specifico)
  - **Validate details**: cosa deve essere vero prima della transizione (es. campo obbligatorio compilato)
  - **Perform action**: cosa succede dopo la transizione (es. assegnazione automatica, aggiornamento campo)
```

**Step 7: Add admin hierarchy clarification (IMPORTANT) — replace lines 86-87**

Replace lines 86-87:
```
- **Gestione utenti e gruppi**: invitare utenti, creare gruppi, assegnare ruoli
  - Esempio concreto di come creare un gruppo "Data Analisi", invitare i membri e assegnare ruoli specifici.
```
With:
```
- **Gestione utenti e gruppi**:
  - *Livello organizzazione* (admin.atlassian.com): invitare utenti, creare gruppi, gestire licenze
  - *Livello spazio* (Space settings → People): assegnare ruoli di spazio ai gruppi/utenti
  - Esempio concreto di come creare un gruppo "Data Analisi", invitare i membri e assegnare ruoli specifici.
```

**Step 8: Flag company-managed-only features (IMPORTANT) — lines 88-95**

Add a note before the scheme list. After the "Gestione utenti e gruppi" block (after the replacement in Step 7), add:

```
- > **Nota**: i seguenti schemi (permission, notification, work type, screen) si applicano solo a spazi **Company-managed**. Gli spazi Team-managed usano configurazioni semplificate integrate.
```

**Step 9: Add issue security schemes (MISSING) — after line 98**

After "Configurazione spazio" (line 96-97), before the best practice bullet, add:

```
- **Issue security schemes**: controllano la *visibilità* dei singoli work item (chi può vedere cosa). Complementari ai permission schemes, che controllano le *azioni*. Particolarmente rilevanti per dati sensibili o riservati.
```

**Step 10: Verify the file reads correctly end-to-end**

Read the full file to confirm all edits are coherent, no lines are duplicated, and the flow is natural.

**Step 11: Commit**

```bash
git add sessione-04-automazioni-workflow-admin/outline.md
git commit -m "docs: fix critical errors and add missing content to sessione-04 outline

- Fix smart values syntax ({{issue.*}} not {{workItem.*}})
- Add Branches to core automation model
- Replace vague limits with per-plan execution numbers
- Add rule actor, automation templates, audit log to section 4.3
- Add status categories and workflow editor rule types to section 4.4
- Clarify admin hierarchy (org-level vs space-level)
- Flag company-managed-only features
- Add issue security schemes to section 4.5

Co-Authored-By: Claude Opus 4.6 <noreply@anthropic.com>"
```

---

## Task 2: Fix esercizio-0401-regole-automazione.md

**File:**
- Modify: `sessione-04-automazioni-workflow-admin/esercizi/esercizio-0401-regole-automazione.md`

**Step 1: Fix smart values in Finance example (CRITICAL) — line 39**

Replace line 39:
```
- **Azione**: Notifica (email o chat) al responsabile del work item → "Il work item {{workItem.key}} - {{workItem.summary}} scade tra 3 giorni. Verifica lo stato."
```
With:
```
- **Azione**: Notifica (email o chat) al responsabile del work item → "Il work item {{issue.key}} - {{issue.summary}} scade tra 3 giorni. Verifica lo stato."
```

**Step 2: Fix smart values in Facility example (CRITICAL) — line 55**

Replace line 55:
```
- **Azione**: Send email to reporter → "Il tuo reclamo {{workItem.key}} - {{workItem.summary}} è stato risolto. Ti preghiamo di verificare e confermare."
```
With:
```
- **Azione**: Send email to reporter → "Il tuo reclamo {{issue.key}} - {{issue.summary}} è stato risolto. Ti preghiamo di verificare e confermare."
```

**Step 3: Invert the alias note (CRITICAL) — line 57**

Replace line 57:
```
> ℹ️ Lo smart value `{{issue.key}}` funziona ancora come alias, ma `{{workItem.key}}` è il nome canonico.
```
With:
```
> ℹ️ Nonostante la UI dica "work item", gli smart values usano la sintassi `{{issue.*}}` (es. `{{issue.key}}`). La forma `{{workItem.*}}` non è attualmente supportata.
```

**Step 4: Fix JQL quoting (IMPORTANT) — line 32**

Replace line 32:
```
- **Condizione**: JQL `project = "IT-HELPDESK" AND priority = Critical AND status != Done AND created <= -24h`
```
With:
```
- **Condizione**: JQL `project = "IT-HELPDESK" AND priority = Critical AND status != Done AND created <= "-24h"`
```

**Step 5: Fix branch smart values (CRITICAL) — line 73**

Replace line 73:
```
- **Azione nel branch**: Aggiungi commento con il nome del reporter del work item bloccante → "@{{linkedIssue.reporter.displayName}} Il work item {{issue.key}} è in review ma è bloccato da {{linkedIssue.key}}. Verifica lo stato del blocco."
```
With:
```
- **Azione nel branch**: Aggiungi commento → "@{{issue.reporter.displayName}} Il work item {{triggerIssue.key}} è in review ma è bloccato da {{issue.key}}. Verifica lo stato del blocco."
- > **Nota branch**: dentro un branch, `{{issue.*}}` si riferisce al work item collegato (contesto del branch), mentre `{{triggerIssue.*}}` si riferisce al work item che ha attivato la regola.
```

**Step 6: Fix typo "opionale" — line 69**

Replace `(opionale)` with `(opzionale)`.

**Step 7: Verify and commit**

Read the full file to confirm coherence.

```bash
git add sessione-04-automazioni-workflow-admin/esercizi/esercizio-0401-regole-automazione.md
git commit -m "docs: fix smart values, branch syntax, and JQL quoting in exercise 0401

- Replace {{workItem.*}} with {{issue.*}} throughout
- Invert alias note: {{issue.*}} is canonical, not an alias
- Fix branch smart values: use {{issue.*}} for branch context, {{triggerIssue.*}} for trigger
- Quote relative JQL date: created <= \"-24h\"
- Fix typo: opionale → opzionale

Co-Authored-By: Claude Opus 4.6 <noreply@anthropic.com>"
```

---

## Task 3: Fix esercizio-0402-workflow-personalizzato.md

**File:**
- Modify: `sessione-04-automazioni-workflow-admin/esercizi/esercizio-0402-workflow-personalizzato.md`

**Step 1: Fix double `#` in title — line 1**

Replace line 1:
```
# # Sessione 4 Blocco 1 Esercizio 2 — Workflow personalizzato
```
With:
```
# Sessione 4 Blocco 1 Esercizio 2 — Workflow personalizzato
```

**Step 2: Fix "Publish" terminology (CRITICAL) — line 45**

Replace line 45:
```
4. Pubblicate il workflow (se in ambiente di test)
```
With:
```
4. Cliccate **Update workflow** per applicare le modifiche (nel nuovo editor non esiste il concetto di bozza: le modifiche diventano attive immediatamente)
```

**Step 3: Fix "in bozza" in results — line 50**

Replace line 50:
```
- 1 workflow implementato (o in bozza) nell'editor di Jira
```
With:
```
- 1 workflow implementato nell'editor di Jira
```

**Step 4: Add status categories note — after line 24, inside "Definite:" list**

After line 26 (the existing three "Definite" items), add a fourth:
```
   - Ogni stato appartiene a una **categoria** (To Do, In Progress, Done): a quale categoria appartiene ciascuno dei vostri stati?
```

**Step 5: Add navigation path clarification — replace line 39**

Replace line 39:
```
1. Andate su **Space settings → Workflows**
```
With:
```
1. Andate su **Space settings → Workflows** (spazi Company-managed) oppure **Space settings → Work types → [tipo] → Edit workflow** (spazi Team-managed)
```

**Step 6: Verify and commit**

```bash
git add sessione-04-automazioni-workflow-admin/esercizi/esercizio-0402-workflow-personalizzato.md
git commit -m "docs: fix workflow editor terminology and add navigation paths in exercise 0402

- Fix 'Pubblicate' to 'Update workflow' (new editor has no draft/publish)
- Remove 'in bozza' from expected results
- Add status categories question to design checklist
- Clarify navigation path for team-managed vs company-managed
- Fix double # in title

Co-Authored-By: Claude Opus 4.6 <noreply@anthropic.com>"
```

---

## Task 4: Fix esercizio-0403-admin-permessi.md

**File:**
- Modify: `sessione-04-automazioni-workflow-admin/esercizi/esercizio-0403-admin-permessi.md`

**Step 1: Add company-managed note (IMPORTANT) — after line 11**

After "### Parte A — Esplorazione permessi (10 min)" (line 11), before step 1, add:

```
> ℹ️ I permission scheme sono disponibili solo per spazi **Company-managed**. Per spazi Team-managed, i permessi si gestiscono da Space settings → Access.
```

**Step 2: Clarify admin levels in Parte B (IMPORTANT) — after line 25**

After "Esplorare le seguenti configurazioni:" (line 25), add:

```
> ℹ️ Alcune configurazioni (work type scheme, notification scheme) sono gestite a livello di **Jira admin** (admin.atlassian.com o Jira settings), non dallo spazio. Dallo spazio si vede quale schema è associato ma per modificarlo serve accesso admin.
```

**Step 3: Verify and commit**

```bash
git add sessione-04-automazioni-workflow-admin/esercizi/esercizio-0403-admin-permessi.md
git commit -m "docs: clarify admin levels and company-managed scope in exercise 0403

- Add note that permission schemes are company-managed only
- Clarify that some schemes require Jira admin access, not space admin

Co-Authored-By: Claude Opus 4.6 <noreply@anthropic.com>"
```

---

## Task 5: Fix esercizio-0404-tipi-space-workflow.md

**File:**
- Modify: `sessione-04-automazioni-workflow-admin/esercizi/esercizio-0404-tipi-space-workflow.md`

**Step 1: Add navigation path for both space types (IMPORTANT) — after line 13**

After "Apri uno **spazio** Team-managed (se disponibile) e uno Company-managed" (line 13), add:

```
   > **Percorsi di navigazione:**
   > - Company-managed: **Space settings → Workflows**
   > - Team-managed: **Space settings → Work types → [seleziona tipo] → Edit workflow**
```

**Step 2: Add row to comparison table (IMPORTANT) — after line 26**

After the last table row, add a new row:

```
| Limite campi personalizzati? | | |
```

**Step 3: Verify and commit**

```bash
git add sessione-04-automazioni-workflow-admin/esercizi/esercizio-0404-tipi-space-workflow.md
git commit -m "docs: add navigation paths and field limit row to exercise 0404

- Add explicit navigation paths for both space types
- Add custom field limit comparison row to table

Co-Authored-By: Claude Opus 4.6 <noreply@anthropic.com>"
```

---

## Task 6: Fix glossario.md

**File:**
- Modify: `glossario.md`

**Step 1: Fix smart values entry (CRITICAL) — line 117**

Replace line 117:
```
**Smart values**: Variabili dinamiche usate nelle automazioni (es. `{{workItem.key}}`, `{{now}}`). Nota: `{{issue.key}}` funziona ancora come alias.
```
With:
```
**Smart values**: Variabili dinamiche usate nelle automazioni (es. `{{issue.key}}`, `{{issue.summary}}`, `{{now}}`). Nota: nonostante la UI dica "work item", la sintassi degli smart values usa `{{issue.*}}`. La forma `{{workItem.*}}` non è attualmente supportata.
```

**Step 2: Verify and commit**

```bash
git add glossario.md
git commit -m "docs: fix smart values syntax in glossary — {{issue.*}} is canonical

Co-Authored-By: Claude Opus 4.6 <noreply@anthropic.com>"
```

---

## Task 7: Fix cheatsheet/automazioni-cheatsheet.md

**File:**
- Modify: `cheatsheet/automazioni-cheatsheet.md`

**Step 1: Fix core concept (IMPORTANT) — lines 7-9**

Replace lines 7-9:
```
```
TRIGGER (quando) → CONDIZIONE (se) → AZIONE (allora)
```
```
With:
```
```
TRIGGER (quando) → CONDIZIONE (se) → AZIONE (allora)
                                    ↘ BRANCH (per work item collegati)
```
```

**Step 2: Fix ALL smart values in the table (CRITICAL) — lines 55-61, 67**

Replace the smart values table rows (lines 55-61):

| Old | New |
|-----|-----|
| `{{workItem.key}}` | `{{issue.key}}` |
| `{{workItem.summary}}` | `{{issue.summary}}` |
| `{{workItem.status.name}}` | `{{issue.status.name}}` |
| `{{workItem.priority.name}}` | `{{issue.priority.name}}` |
| `{{workItem.assignee.displayName}}` | `{{issue.assignee.displayName}}` |
| `{{workItem.reporter.displayName}}` | `{{issue.reporter.displayName}}` |
| `{{workItem.url}}` | `{{issue.url}}` |

Also update the description column to remove "(alias: ...)" references and instead show the Italian label.

Replace the note on line 67:
```
> **Nota**: Gli smart value `{{issue.*}}` restano funzionanti come alias retrocompatibile. La forma canonica è `{{workItem.*}}`.
```
With:
```
> **Nota**: nonostante la UI dica "work item", la sintassi degli smart values usa `{{issue.*}}`. La forma `{{workItem.*}}` non è attualmente supportata da Jira Automation.
```

**Step 3: Fix JQL quoting in escalation recipe (IMPORTANT) — line 93**

Replace line 93:
```
Condizione: JQL → priority = Critical AND status != Done AND created <= -24h
```
With:
```
Condizione: JQL → priority = Critical AND status != Done AND created <= "-24h"
```

**Step 4: Fix smart value in notification recipe — line 111**

Replace line 111:
```
         Oggetto: "⏰ {{workItem.key}} scade tra meno di 2 giorni"
```
With:
```
         Oggetto: "⏰ {{issue.key}} scade tra meno di 2 giorni"
```

**Step 5: Verify and commit**

```bash
git add cheatsheet/automazioni-cheatsheet.md
git commit -m "docs: fix smart values syntax and core model in automazioni cheatsheet

- Replace all {{workItem.*}} with {{issue.*}}
- Invert alias note: {{issue.*}} is canonical
- Add Branch to core concept diagram
- Quote relative JQL date

Co-Authored-By: Claude Opus 4.6 <noreply@anthropic.com>"
```

---

## Execution Order

Tasks 1-7 are **fully independent** (each touches a different file) and can be executed in parallel.

Recommended grouping for parallel dispatch:

- **Wave 1** (all 7 tasks in parallel): Tasks 1, 2, 3, 4, 5, 6, 7
- **Wave 2** (sequential): Final review — read all 7 modified files end-to-end, then squash or rebase commits if desired

---

## Verification Checklist

After all tasks complete, verify:

- [ ] `grep -r "workItem\." jira-confluence-best-practices-2026/` returns zero matches
- [ ] `grep -r "linkedIssue\." jira-confluence-best-practices-2026/` returns zero matches
- [ ] `grep -r "Pubblicate" jira-confluence-best-practices-2026/` returns zero matches
- [ ] `grep -r "opionale" jira-confluence-best-practices-2026/` returns zero matches
- [ ] All 7 files read coherently with no duplicate lines or broken formatting
- [ ] Git log shows 7 clean commits with conventional `docs:` prefix
