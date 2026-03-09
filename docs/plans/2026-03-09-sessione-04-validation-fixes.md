# Sessione 04 Validation Fixes — Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Fix all technical errors, content gaps, and polish items identified by the 5-agent validation audit of sessione-04 materials against official Atlassian documentation (March 2026).

**Architecture:** Each task targets a single file, enabling full parallel execution. Tasks are grouped by severity within each file: high-priority technical errors first, then medium-priority content accuracy, then low-priority polish. Every step specifies exact line numbers and replacement text.

**Tech Stack:** Markdown editing only — no executable code in this repository.

---

## Scope Summary

| Severity | Count | Description |
|----------|-------|-------------|
| HIGH | 3 | Admin & Finance exercise flawed, automation limits missing key fact, outdated terminology |
| MEDIUM | 12 | Trigger/condition/action names, workflow editor claims, admin clarifications, time allocation |
| LOW | 14 | Missing topics, measurable outcomes, glossary links, fallback instructions, troubleshooting |

**Files affected (5):**

| # | File | Task |
|---|------|------|
| 1 | `sessione-04-.../outline.md` | Task 1 (16 edits) |
| 2 | `sessione-04-.../esercizi/esercizio-0401-regole-automazione.md` | Task 2 (8 edits) |
| 3 | `sessione-04-.../esercizi/esercizio-0402-workflow-personalizzato.md` | Task 3 (5 edits) |
| 4 | `sessione-04-.../esercizi/esercizio-0403-admin-permessi.md` | Task 4 (5 edits) |
| 5 | `sessione-04-.../esercizi/esercizio-0404-tipi-space-workflow.md` | Task 5 (3 edits) |

All file paths below are relative to:
`jira-confluence-best-practices-2026/sessione-04-automazioni-workflow-admin/`

---

## Task 1: Fix outline.md

**File:**
- Modify: `outline.md`

This is the largest task. It addresses 3 high/medium technical errors, several content gaps, and polish items.

### Step 1: Add "single-space rules unlimited" to execution limits (HIGH) — lines 26-30

The limits are correct for global rules but critically omit that **single-space rules are unlimited on all plans**.

Replace lines 26-30:
```
- Limiti di esecuzione mensili per piano Cloud:
  - Free: ~100 esecuzioni globali/mese
  - Standard: ~1.700 totali/mese (500 globali)
  - Premium: 1.000 per utente/mese (pool condiviso)
  - Enterprise: illimitato
```
With:
```
- Limiti di esecuzione mensili per piano Cloud (regole globali/multi-spazio):
  - Free: ~100 esecuzioni/mese
  - Standard: ~1.700 totali/mese (500 globali)
  - Premium: 1.000 per utente/mese (pool condiviso)
  - Enterprise: illimitato
  - > **Nota**: le regole di singolo spazio sono **illimitate** su tutti i piani. I limiti sopra si applicano solo alle regole globali e multi-spazio.
```

### Step 2: Fix trigger name "Comment added" (MEDIUM) — line 37

Replace line 37:
```
- **Comment added**: quando viene aggiunto un commento con specifiche parole chiave
```
With:
```
- **Work item commented**: quando viene aggiunto un commento (con possibilità di filtrare per parole chiave)
```

### Step 3: Add missing commonly-used triggers (LOW) — after line 39

After the "Manual trigger" line, add before the Tyvak examples:
```
- **Work item updated**: quando un work item viene modificato (più ampio di "Field value changed")
- **Webhook**: per integrazioni con sistemi esterni
```

### Step 4: Fix "User condition" — doesn't exist (MEDIUM) — line 46

Replace line 46:
```
- **Condizioni**: Work item fields condition, JQL condition, User condition, Related work items condition
```
With:
```
- **Condizioni**: Work item fields condition, JQL condition, If/else block, Advanced compare condition, Related work items condition
```

### Step 5: Fix "Modifica campo" action name (MEDIUM) — line 49

Replace line 49:
```
  - Modifica campo (assegna, cambia data di scadenza, aggiungi etichetta)
```
With:
```
  - Edit work item (modifica campo: assegna, cambia data di scadenza, aggiungi etichetta)
```

### Step 6: Add missing commonly-used actions (LOW) — after line 53

After "Link work items", add:
```
  - Create work item (crea un nuovo elemento di lavoro, non solo sotto-attività)
  - Send web request (invio richiesta HTTP a sistemi esterni)
  - Log action (utile per il debug delle regole)
```

### Step 7: Clarify audit log access and retention (MEDIUM) — line 57

Replace line 57:
```
- **Debug e audit log**: Space settings → Automation → Audit log. Ogni esecuzione mostra trigger, condizioni valutate e azioni eseguite. Strumento fondamentale per il troubleshooting.
```
With:
```
- **Debug e audit log**: Space settings → Automation → [seleziona regola] → scheda Audit log. Ogni esecuzione mostra trigger, condizioni valutate e azioni eseguite. Le voci vengono conservate per 90 giorni. Strumento fondamentale per il troubleshooting.
```

### Step 8: Add global automation path (LOW) — after line 25

After "Automazioni di spazio (space) vs automazioni globali", add:
```
  - Spazio: Space settings → Automation
  - Globali: Settings (ingranaggio) → System → Automation rules
```

### Step 9: Add "Request input" as 4th workflow rule type (MEDIUM) — lines 71-74

Replace lines 71-74:
```
- Configurare transizioni nel nuovo editor — tre tipi di regole:
  - **Restrict transition**: chi può eseguire la transizione (es. solo l'assegnatario, un ruolo specifico)
  - **Validate details**: cosa deve essere vero prima della transizione (es. campo obbligatorio compilato)
  - **Perform action**: cosa succede dopo la transizione (es. assegnazione automatica, aggiornamento campo)
```
With:
```
- Configurare transizioni nel nuovo editor — quattro tipi di regole (in ordine di esecuzione):
  - **Restrict transition**: chi può eseguire la transizione (es. solo l'assegnatario, un ruolo specifico)
  - **Request input**: quali campi/schermate mostrare all'utente durante la transizione
  - **Validate details**: cosa deve essere vero prima della transizione (es. campo obbligatorio compilato)
  - **Perform action**: cosa succede dopo la transizione (es. assegnazione automatica, aggiornamento campo)
```

### Step 10: Tighten best practice from "6-7" to "max 6" (LOW) — line 76

Replace line 76:
```
- Best practice: semplicità, chiarezza, non più di 6-7 stati
```
With:
```
- Best practice: semplicità, chiarezza, non più di 6 stati (il consenso della community Atlassian indica 4-6 come intervallo ottimale)
```

### Step 11: Rename "Issue security schemes" to current term (HIGH) — line 113

Replace line 113:
```
- **Issue security schemes**: controllano la *visibilità* dei singoli work item (chi può vedere cosa). Complementari ai permission schemes, che controllano le *azioni*. Particolarmente rilevanti per dati sensibili o riservati.
```
With:
```
- **Work item security schemes**: controllano la *visibilità* dei singoli work item (chi può vedere cosa). Complementari ai permission schemes, che controllano le *azioni*. Particolarmente rilevanti per dati sensibili o riservati.
```

### Step 12: Clarify scheme configuration tiers (MEDIUM) — lines 98-102

The current text mixes org-level and Jira-admin-level configuration without distinguishing them clearly. Replace lines 98-102:
```
- **Gestione utenti e gruppi**:
  - *Livello organizzazione* (admin.atlassian.com): invitare utenti, creare gruppi, gestire licenze
  - *Livello spazio* (Space settings → People): assegnare ruoli di spazio ai gruppi/utenti
  - Esempio concreto di come creare un gruppo "Data Analisi", invitare i membri e assegnare ruoli specifici.
- > **Nota**: i seguenti schemi (permission, notification, work type, screen) si applicano solo a spazi **Company-managed**. Gli spazi Team-managed usano configurazioni semplificate integrate.
```
With:
```
- **Gestione utenti e gruppi** — tre livelli di amministrazione:
  - *Livello organizzazione* (admin.atlassian.com): invitare utenti, creare gruppi, gestire licenze
  - *Livello prodotto Jira* (Settings → Work items): configurare schemi (permission, notification, work type, screen)
  - *Livello spazio* (Space settings → People): assegnare ruoli di spazio ai gruppi/utenti
  - Esempio concreto di come creare un gruppo "Data Analisi", invitare i membri e assegnare ruoli specifici.
- > **Nota**: i seguenti schemi (permission, notification, work type, screen) si applicano solo a spazi **Company-managed**. Gli spazi Team-managed usano configurazioni semplificate integrate (es. permessi via Space settings → Access, notifiche via Space settings → Notifications).
```

### Step 13: Verify the file reads correctly end-to-end

Read the full file to confirm all edits are coherent, no lines are duplicated, and the flow is natural.

### Step 14: Commit

```bash
cd jira-confluence-best-practices-2026/sessione-04-automazioni-workflow-admin
git add outline.md
git commit -m "docs: fix technical errors and content gaps in sessione-04 outline

- Add unlimited single-space rules note to execution limits
- Rename 'Comment added' trigger to 'Work item commented'
- Replace non-existent 'User condition' with actual conditions
- Rename 'Modifica campo' action to official 'Edit work item'
- Clarify audit log is per-rule with 90-day retention
- Add 'Request input' as 4th workflow transition rule type
- Rename 'Issue security schemes' to 'Work item security schemes'
- Clarify three-tier admin hierarchy (org/Jira/space)
- Add commonly-used triggers, conditions, and actions
- Tighten state count best practice from 6-7 to max 6"
```

---

## Task 2: Fix esercizio-0401-regole-automazione.md

**File:**
- Modify: `esercizi/esercizio-0401-regole-automazione.md`

### Step 1: Rewrite Admin & Finance example — flawed trigger and condition (HIGH) — lines 36-40

The current example uses "Field value changed (Due date)" + "Due date <= {{now.plusDays(3)}}" which is wrong: (1) the trigger fires on manual field edit, not approaching deadline; (2) the condition syntax is invalid for Jira Automation.

Replace lines 36-40:
```
**💼 Admin & Finance — Notifica scadenza:**
- **Trigger**: Field value changed (Due date)
- **Condizione**: Due date <= `{{now.plusDays(3)}}`
- **Azione**: Notifica (email o chat) al responsabile del work item → "Il work item {{issue.key}} - {{issue.summary}} scade tra 3 giorni. Verifica lo stato."
- **Azione**: Transition work item → "Urgente" (se lo status esiste)
```
With:
```
**💼 Admin & Finance — Notifica scadenza:**
- **Trigger**: Scheduled (ogni giorno alle 9:00)
- **Condizione**: JQL `project = "ADMIN-FINANCE" AND duedate <= startOfDay("+3d") AND duedate >= startOfDay() AND statusCategory != Done`
- **Azione**: Notifica (email o chat) all'assegnatario → "Il work item {{issue.key}} - {{issue.summary}} scade entro 3 giorni. Verifica lo stato."
- **Azione aggiuntiva**: Transition work item → "Urgente" (se lo status esiste)
```

### Step 2: Add note about adapting priority name (MEDIUM) — after line 32

The IT example uses `priority = Critical` which may not exist on all instances. After line 32 (the JQL line), add:

```
  > Adattate il nome della priorità alla vostra istanza (es. `Critical`, `Highest` o `Critica`).
```

### Step 3: Fix JQL date quoting style (LOW) — line 32

Replace in the JQL on line 32:
```
created <= "-24h"
```
With:
```
created <= -24h
```
This matches standard Atlassian documentation style (unquoted).

### Step 4: Clarify training space in preparation (MEDIUM) — line 13

Replace line 13:
```
Vai su **Space settings → Automation → Create rule** nello **spazio** (space) di training (oppure in un progetto dell'istanza Tyvak in cui è sicuro sperimentare).
```
With:
```
Vai su **Space settings → Automation → Create rule** nello **spazio** (space) di training assegnato dal formatore.
```

### Step 5: Make "Risultato atteso" measurable (LOW) — line 62

Replace line 62:
```
- Comprensione del pattern Trigger → Condizione → Azione
```
With:
```
- Saper descrivere a voce il pattern Trigger → Condizione → Azione della propria regola
```

### Step 6: Add glossary reference (LOW) — after line 67

After the "Consiglio" section, add:
```

> Per la terminologia, consulta il [glossario](../../glossario.md).
```

### Step 7: Add "stuck" guidance (LOW) — after line 67

After the "Consiglio" section (and after the glossary reference added in Step 6), add:
```

> Se non riesci a completare un passaggio entro 3 minuti, chiedi aiuto al formatore.
```

### Step 8: Verify and commit

Read the full file to confirm coherence.

```bash
cd jira-confluence-best-practices-2026/sessione-04-automazioni-workflow-admin
git add esercizi/esercizio-0401-regole-automazione.md
git commit -m "docs: fix flawed Admin/Finance example and improve exercise 0401

- Rewrite Admin & Finance example: use Scheduled trigger + JQL condition
- Add note about adapting priority name to instance
- Fix JQL date quoting to match Atlassian documentation style
- Clarify training space in preparation section
- Make 'Risultato atteso' items measurable
- Add glossary reference and 'stuck' guidance"
```

---

## Task 3: Fix esercizio-0402-workflow-personalizzato.md

**File:**
- Modify: `esercizi/esercizio-0402-workflow-personalizzato.md`

### Step 1: Fix misleading "immediate changes" claim (MEDIUM) — line 46

Replace line 46:
```
4. Cliccate **Update workflow** per applicare le modifiche (nel nuovo editor non esiste il concetto di bozza: le modifiche diventano attive immediatamente)
```
With:
```
4. Cliccate **Update workflow** per applicare le modifiche (nel nuovo editor non esiste il concetto di bozza: le modifiche si applicano in un unico passaggio cliccando "Update workflow", senza bisogno di una pubblicazione separata)
```

### Step 2: Add March 30 milestone to deprecation warning (MEDIUM) — line 5

Replace line 5:
```
> ⚠️ Il vecchio editor di workflow sarà rimosso a giugno 2026. Questo esercizio usa il nuovo editor.
```
With:
```
> ⚠️ Dal 30 marzo 2026 il vecchio editor non sarà più impostabile come default; dal 26 giugno 2026 sarà rimosso completamente. Questo esercizio usa il nuovo editor.
```

### Step 3: Tighten state count recommendation (LOW) — line 24

Replace in line 24:
```
   - Quali **stati** servono? (massimo 6-7)
```
With:
```
   - Quali **stati** servono? (massimo 6)
```

### Step 4: Add glossary reference, "stuck" guidance, and improve time allocation (LOW) — after line 58

After the last "Domande di riflessione" line, add:
```

> Per la terminologia, consulta il [glossario](../../glossario.md).

> Se non riesci a completare un passaggio entro 3 minuti, chiedi aiuto al formatore. Se il tempo per la Parte B non è sufficiente, concentratevi su aggiungere 2-3 stati e 2 transizioni piuttosto che l'intero workflow.
```

### Step 5: Verify and commit

Read the full file to confirm coherence.

```bash
cd jira-confluence-best-practices-2026/sessione-04-automazioni-workflow-admin
git add esercizi/esercizio-0402-workflow-personalizzato.md
git commit -m "docs: fix workflow editor claims and add guidance in exercise 0402

- Clarify that 'Update workflow' click is required (not automatic)
- Add March 30 2026 milestone to deprecation warning
- Tighten state count recommendation from 6-7 to max 6
- Add glossary reference, stuck guidance, and scope fallback for Part B"
```

---

## Task 4: Fix esercizio-0403-admin-permessi.md

**File:**
- Modify: `esercizi/esercizio-0403-admin-permessi.md`

### Step 1: Fix "progetto (project)" reference in objective (MEDIUM) — line 7

Replace line 7:
```
Comprendere la gestione dei permessi, degli schemi e delle configurazioni di **spazio** (space) o progetto (project).
```
With:
```
Comprendere la gestione dei permessi, degli schemi e delle configurazioni di **spazio** (space).
```

### Step 2: Fix admin.atlassian.com error for notification schemes (MEDIUM) — line 29

Replace line 29:
```
> ℹ️ Alcune configurazioni (work type scheme, notification scheme) sono gestite a livello di **Jira admin** (admin.atlassian.com o Jira settings), non dallo spazio. Dallo spazio si vede quale schema è associato ma per modificarlo serve accesso admin.
```
With:
```
> ℹ️ Alcune configurazioni (work type scheme, notification scheme) sono gestite a livello di **Jira admin** (Settings → Work items), non dallo spazio. Dallo spazio si vede quale schema è associato ma per modificarlo serve accesso admin Jira. Nota: admin.atlassian.com è per la gestione utenti/gruppi a livello organizzazione, non per gli schemi di prodotto.
```

### Step 3: Add fallback for single-space access (LOW) — after line 23

After step 5 ("Confrontate con un secondo spazio..."), add:
```
   > Se avete accesso a un solo spazio, annotate le configurazioni e confrontatele con un collega.
```

### Step 4: Fix "progetti" terminology in Part C (LOW) — line 42

Replace line 42:
```
Identificare le **convenzioni di base** per i progetti a cui fate parte nell'istanza Tyvak:
```
With:
```
Identificare le **convenzioni di base** per gli spazi a cui fate parte nell'istanza Tyvak:
```

### Step 5: Add glossary reference and "stuck" guidance (LOW) — after line 62

After the last checkbox in the Extra section, add:
```

> Per la terminologia, consulta il [glossario](../../glossario.md).

> Se non riesci a completare un passaggio entro 3 minuti, chiedi aiuto al formatore.
```

### Step 6: Verify and commit

Read the full file to confirm coherence.

```bash
cd jira-confluence-best-practices-2026/sessione-04-automazioni-workflow-admin
git add esercizi/esercizio-0403-admin-permessi.md
git commit -m "docs: fix admin paths and terminology in exercise 0403

- Remove legacy 'progetto (project)' reference
- Fix admin.atlassian.com error: notification schemes are at Jira Settings
- Add fallback for single-space access scenario
- Fix 'progetti' to 'spazi' in Part C
- Add glossary reference and stuck guidance"
```

---

## Task 5: Fix esercizio-0404-tipi-space-workflow.md

**File:**
- Modify: `esercizi/esercizio-0404-tipi-space-workflow.md`

### Step 1: Add fallback if Team-managed space unavailable (LOW) — after line 13

After "Apri uno **spazio** Team-managed (se disponibile) e uno Company-managed", add:
```
   > Se non è disponibile uno spazio Team-managed nell'istanza di training, utilizzate le informazioni della lezione per compilare la colonna Team-managed della tabella e concentrate la Parte B sullo spazio Company-managed.
```

### Step 2: Add glossary reference and "stuck" guidance (LOW) — after line 50

After the last reflection question, add:
```

> Per la terminologia, consulta il [glossario](../../glossario.md).

> Se non riesci a completare un passaggio entro 3 minuti, chiedi aiuto al formatore.
```

### Step 3: Verify and commit

Read the full file to confirm coherence.

```bash
cd jira-confluence-best-practices-2026/sessione-04-automazioni-workflow-admin
git add esercizi/esercizio-0404-tipi-space-workflow.md
git commit -m "docs: add fallback instructions and guidance to exercise 0404

- Add fallback if Team-managed space is unavailable
- Add glossary reference and stuck guidance"
```

---

## Execution Order

Tasks 1-5 are **fully independent** (each touches a different file) and can be executed in parallel.

Recommended grouping:

- **Wave 1** (all 5 tasks in parallel): Tasks 1, 2, 3, 4, 5
- **Wave 2** (sequential): Final review — read all 5 modified files end-to-end, run verification checklist

---

## Verification Checklist

After all tasks complete, verify:

- [ ] `grep -rn "Issue security scheme" sessione-04-automazioni-workflow-admin/` → zero matches (should be "Work item security schemes")
- [ ] `grep -rn "Comment added" sessione-04-automazioni-workflow-admin/outline.md` → zero matches (should be "Work item commented")
- [ ] `grep -rn "User condition" sessione-04-automazioni-workflow-admin/outline.md` → zero matches
- [ ] `grep -rn "Modifica campo" sessione-04-automazioni-workflow-admin/outline.md` → zero matches (should be "Edit work item")
- [ ] `grep -rn "Field value changed (Due date)" sessione-04-automazioni-workflow-admin/esercizi/esercizio-0401` → zero matches (replaced with Scheduled trigger)
- [ ] `grep -rn "progetto (project)" sessione-04-automazioni-workflow-admin/esercizi/esercizio-0403` → zero matches
- [ ] `grep -rn "admin.atlassian.com o Jira settings" sessione-04-automazioni-workflow-admin/esercizi/esercizio-0403` → zero matches
- [ ] `grep -rn "6-7 stati" sessione-04-automazioni-workflow-admin/` → zero matches (should be "max 6" or "4-6")
- [ ] `grep -rn "diventano attive immediatamente" sessione-04-automazioni-workflow-admin/esercizi/esercizio-0402` → zero matches
- [ ] Every exercise file contains a glossary link (`glossario.md`)
- [ ] Every exercise file contains stuck guidance ("chiedi aiuto al formatore")
- [ ] All 5 files read coherently with no duplicate lines or broken formatting
- [ ] Git log shows 5 clean commits with conventional `docs:` prefix
