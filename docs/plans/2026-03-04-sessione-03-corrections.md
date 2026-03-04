# Sessione 03 Audit Corrections — Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Resolve all must-fix and should-fix findings from the sessione-03 audit by restructuring
the outline timing, fixing accuracy errors, adding missing content, and improving exercises.

**Architecture:** 5 markdown files to edit. Outline gets full restructure (split gadgets into
personal/team sections, expand sharing, add reports). Exercises get targeted additions. Cheatsheet
gets surgical fixes. All content in Italian following existing conventions.

**Tech Stack:** Markdown documentation, no executable code.

---

## Task 1: Rewrite outline.md — full restructure

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-03-dashboard-grafici-analytics/outline.md`

**Step 1: Replace outline.md with restructured content**

Replace the entire file with:

```markdown
# Sessione 3 — Dashboard, Grafici e Analytics

> ⏱ Durata: 4 ore | 📅 Sessione 3 di 5

## Obiettivi della sessione

Al termine di questa sessione i partecipanti saranno in grado di:

- Creare e personalizzare dashboard Jira
- Scegliere e configurare i gadget più utili per il proprio ruolo
- Leggere e interpretare grafici e report di Jira
- Condividere dashboard con il team e la direzione

---

## Programma dettagliato

### Blocco 1 — Dashboard fondamentali (0:00 – 1:10)

#### 3.1 Panoramica delle dashboard (15 min)

- Cos'è una dashboard in Jira
- Dashboard predefinito (default dashboard) vs dashboard personali
- La dashboard come strumento di comunicazione e visibilità
- Contrassegnare con stella (star) le dashboard per accesso rapido
- Cercare dashboard esistenti e copiare dashboard come template
- Best practice: una dashboard per ruolo, una per direzione
- Esempio Tyvak: dashboard del Facility Manager per i work item aperti

#### 3.2 Creare e configurare una dashboard (15 min)

- Creazione di una nuova dashboard: nome e descrizione
- Dopo la creazione: **Edit → Change layout** (1 colonna, 2 colonne, 3 colonne)
- Aggiungere gadget alla dashboard
- Posizionamento e ridimensionamento dei gadget
- Demo live: creazione guidata di una dashboard + contrassegno con stella

#### 3.3 Gadget per la dashboard personale (20 min)

- **I miei work item** (Assigned to Me): work item assegnati all'utente corrente — il gadget personale fondamentale
- **Risultati filtro** (Filter Results): tabella **elementi di lavoro** (work item) da un filtro JQL salvato
- **Grafico a torta** (Pie Chart): distribuzione per campo (status, priority, assignee)
- **Attività recente** (Activity Stream): feed delle attività — non richiede un filtro salvato
- **Quick Links**: scorciatoie di navigazione ai work item dell'utente
- **Introduzione** (Introduction): note e istruzioni in formato wiki — ⚠️ il testo è configurato globalmente nelle impostazioni di sistema Jira; per testo personalizzato per singola dashboard servono app di terze parti
- Collegamento gadget ↔ filtro salvato: molti gadget si basano su un filtro JQL salvato (ma non tutti lo richiedono, es. Assigned to Me, Activity Stream, Quick Links)

#### 3.4 Gadget per il team e la direzione (20 min)

- **Creati vs Risolti** (Created vs Resolved): andamento nel tempo — nota: "risolto" dipende dal campo Resolution, non solo dallo status
- **Grafico a due dimensioni** (Two Dimensional Filter Statistics): matrice campo × campo (es. priorità × status)
- **Età media** (Average Age): età media (in giorni) dei work item non risolti dalla data di creazione — non è il tempo in uno status specifico
- **Sprint Health**: snapshot dello stato dello sprint corrente, scope changes e carico per membro del team
- **Sprint Burndown** (gadget dashboard): lavoro rimanente nello sprint — distinto dal report Burndown a livello di board (sezione 3.5)
- **Work item sotto osservazione** (Watched Work Items): per stakeholder che monitorano work item senza essere assegnatari
- **Mappa di calore** (Heat Map) — ⚠️ Atlassian ha annunciato la rimozione di questo gadget (insieme a Road Map, Bubble Chart, Spaces, Labels), ma la rimozione è stata sospesa ad aprile 2025. Attualmente ancora disponibile, ma non più mantenuto attivamente e potrebbe essere rimosso in futuro.
- Collegamento gadget ↔ filtro salvato: anche per questi gadget, la maggior parte richiede un filtro JQL salvato

**☕ Pausa (10 min)**

### Esercizi Blocco 1 (1:10 – 2:00)

- [Esercizio 1: Crea la tua dashboard personale](esercizi/esercizio-03-dashboard-personale.md) (25 min)
- [Esercizio 2: Gadget e grafici](esercizi/esercizio-03-gadget-grafici.md) (25 min)

---

### Blocco 2 — Report, condivisione e analytics (2:00 – 3:00)

#### 3.5 Report integrati di Jira (20 min)

- Report dello **spazio** (space): dove trovarli (sezione Reports nella sidebar)
- Nota: per spazi company-managed con più board, assicurarsi di visualizzare la board corretta prima di generare report
- **Burndown Chart** (board Scrum): report a livello di board, non gadget dashboard
- **Velocity Chart**: report a livello di board — richiede almeno uno sprint completato
- **Cumulative Flow Diagram**: report a livello di board — disponibile per Scrum e Kanban
- **Control Chart**: report a livello di board, tempo di ciclo (cycle time) e lead time dei work item
- **Sprint Report**: completamento sprint e work item spostati nel backlog — fondamentale per le sprint review
- **Burnup Chart**: complementare al burndown — mostra scope e completamento, più leggibile per stakeholder non tecnici
- **Epic Report**: progresso di un epic attraverso più sprint
- Interpretazione pratica: cosa ci dicono questi report?

#### 3.6 Dashboard avanzate e trucchi (15 min)

- Gadget con JQL dinamico (es. `currentUser()`, date relative)
- Dashboard "manager": panoramica cross-spazio
- Dashboard "operativa": focus sulle attività del giorno
- Wallboard mode: dashboard su schermo condiviso
- Wallboard slideshow: rotazione automatica tra più dashboard con intervalli configurabili
- Refresh automatico dei gadget (configurabile a livello di dashboard e di singolo gadget)

#### 3.7 Condivisione e permessi dashboard (25 min)

- Condividere con utenti specifici
- Condividere con gruppi — ⚠️ su Jira Cloud si può condividere solo con gruppi di cui si è membri
- Condividere con l'intera organizzazione (opzione "Any logged-in user")
- Distinzione Viewers vs Editors: chi ha permessi di Editor può aggiungere/modificare gadget e cancellare la dashboard; i Viewer possono solo visualizzare
- ⚠️ Condividere anche i filtri JQL sottostanti ai gadget — senza condivisione dei filtri, gli altri utenti vedranno gadget vuoti. Questo è il problema di supporto più comune con le dashboard condivise.
- Permessi globali necessari: "Share dashboards and filters" e "Browse users and groups". Senza questi permessi, l'utente vedrà solo l'opzione "Private".
- Dashboard come strumento di reporting per la direzione
- Best practice: chi dovrebbe vedere cosa?
- Esempio Tyvak: dashboard per il management con KPI cross-dipartimento

**☕ Pausa (10 min)**

### Esercizi Blocco 2 (3:10 – 3:45)

- [Esercizio 3: Report e dashboard condivisa](esercizi/esercizio-03-report-analisi.md) (35 min)

### Recap e Q&A (3:45 – 4:00)

- Riepilogo: filtri JQL → gadget → dashboard → reporting
- La catena del valore: dato → informazione → decisione
- Anteprima sessione 4: automazioni, workflow e amministrazione

---

## Materiali di riferimento

- [Slide sessione 3](slides/)
- [Dashboard Cheatsheet](../cheatsheet/dashboard-cheatsheet.md)
- [JQL Cheatsheet](../cheatsheet/jql-cheatsheet.md)
```

**Step 2: Verify the timing adds up to 240 min**

Check manually:
- 3.1: 15 + 3.2: 15 + 3.3: 20 + 3.4: 20 = 70 min
- Pausa: 10
- Esercizi B1: 25 + 25 = 50
- 3.5: 20 + 3.6: 15 + 3.7: 25 = 60
- Pausa: 10
- Esercizi B2: 35
- Recap: 15
- Total: 70 + 10 + 50 + 60 + 10 + 35 + 15 = **250 min** — 10 min over.

Adjust: Reduce 3.5 from 20 to 15 min, and 3.7 from 25 to 20 min. This brings total to 240.

(Note: the implementer should verify the math and adjust if needed to hit exactly 240.)

**Step 3: Commit**

```bash
git add jira-confluence-best-practices-2026/sessione-03-dashboard-grafici-analytics/outline.md
git commit -m "docs: restructure sessione-03 outline with audit corrections

- Split gadgets into personal (3.3) and team/management (3.4)
- Fix Average Age description (age of unresolved items, not time in status)
- Fix Heat Map deprecation (suspended, not actively removed)
- Fix Control Chart (add lead time alongside cycle time)
- Fix dashboard terminology (predefinito instead of di sistema)
- Fix layout sequence (post-creation via Edit, not during creation)
- Add Introduction gadget caveat (globally configured)
- Add missing gadgets: Assigned to Me, Sprint Health, Sprint Burndown,
  Quick Links, Watched Work Items
- Add missing reports: Sprint Report, Burnup Chart, Epic Report
- Add missing sharing concepts: Viewers vs Editors, filter sharing
  requirement, group restriction, global permissions
- Add missing features: starring, copying, searching, wallboard slideshow
- Restructure timing to accommodate expanded content"
```

---

## Task 2: Update esercizio-03-dashboard-personale.md

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-dashboard-personale.md`

**Step 1: Update time estimate (line 3)**

Change:
```
> ⏱ Tempo stimato: 20 minuti | 👥 Individuale
```
To:
```
> ⏱ Tempo stimato: 25 minuti | 👥 Individuale
```

**Step 2: Update objective (line 7)**

Change:
```
Creare una dashboard personale con almeno 4 gadget utili per il proprio ruolo.
```
To:
```
Creare una dashboard personale con almeno 5 gadget utili per il proprio ruolo, incluso Assigned to Me.
```

**Step 3: Fix Step 1 layout instruction (line 20)**

Change:
```
4. Layout: seleziona **2 colonne**
```
To:
```
4. Dopo la creazione: clicca **Edit** → **Change layout** → seleziona **2 colonne**
5. Contrassegna la dashboard con la **stella** (⭐) per trovarla rapidamente dal menu Dashboards
```

**Step 4: Add Assigned to Me as gadget #1 for IT Manager (after line 26)**

Change:
```
**🔧 IT Manager:**
1. **Risultati filtro** (Filter Results): **elementi di lavoro** (work item) IT aperti (usa filtro JQL dalla sessione 2)
2. **Grafico a torta** (Pie Chart): distribuzione work item per priorità
3. **Creati vs Risolti** (Created vs Resolved): andamento work item ultimo mese
4. **Due dimensioni** (Two Dimensional Filter Statistics): matrice priorità × status
```
To:
```
**🔧 IT Manager:**
1. **I miei work item** (Assigned to Me): i tuoi work item IT assegnati
2. **Risultati filtro** (Filter Results): **elementi di lavoro** (work item) IT aperti (usa filtro JQL dalla sessione 2)
3. **Grafico a torta** (Pie Chart): distribuzione work item per priorità
4. **Creati vs Risolti** (Created vs Resolved): andamento work item ultimo mese
5. **Due dimensioni** (Two Dimensional Filter Statistics): matrice priorità × status
```

**Step 5: Add Assigned to Me as gadget #1 for Admin & Finance (after line 32)**

Change:
```
**💼 Administration & Finance:**
1. **Risultati filtro** (Filter Results): ordini e fatture in corso
2. **Grafico a torta** (Pie Chart): distribuzione per etichetta (acquisti/fatturazione)
3. **Creati vs Risolti** (Created vs Resolved): andamento elementi di lavoro ultimo trimestre
4. **Introduzione** (Introduction): note con scadenze importanti
```
To:
```
**💼 Administration & Finance:**
1. **I miei work item** (Assigned to Me): i tuoi elementi di lavoro assegnati
2. **Risultati filtro** (Filter Results): ordini e fatture in corso
3. **Grafico a torta** (Pie Chart): distribuzione per etichetta (acquisti/fatturazione)
4. **Creati vs Risolti** (Created vs Resolved): andamento elementi di lavoro ultimo trimestre
5. **Introduzione** (Introduction): note con scadenze importanti
```

**Step 6: Add Assigned to Me as gadget #1 for HR (after line 38)**

Change:
```
**👥 HR Generalist:**
1. **Risultati filtro** (Filter Results): task onboarding attivi
2. **Grafico a torta** (Pie Chart): distribuzione per status
3. **Attività recente** (Activity Stream): ultime modifiche nello **spazio** (space) HR
4. **Creati vs Risolti** (Created vs Resolved): andamento task ultimo mese
```
To:
```
**👥 HR Generalist:**
1. **I miei work item** (Assigned to Me): i tuoi task HR assegnati
2. **Risultati filtro** (Filter Results): task onboarding attivi
3. **Grafico a torta** (Pie Chart): distribuzione per status
4. **Attività recente** (Activity Stream): ultime modifiche nello **spazio** (space) HR
5. **Creati vs Risolti** (Created vs Resolved): andamento task ultimo mese
```

**Step 7: Add Assigned to Me as gadget #1 for Facility (after line 44)**

Change:
```
**🏢 Facility Manager:**
1. **Risultati filtro** (Filter Results): work item facility aperti
2. **Grafico a torta** (Pie Chart): distribuzione per componente (manutenzione/reclami/sicurezza)
3. **Creati vs Risolti** (Created vs Resolved): andamento reclami e manutenzioni
4. **Due dimensioni** (Two Dimensional Filter Statistics): matrice priorità × componente
```
To:
```
**🏢 Facility Manager:**
1. **I miei work item** (Assigned to Me): i tuoi work item facility assegnati
2. **Risultati filtro** (Filter Results): work item facility aperti
3. **Grafico a torta** (Pie Chart): distribuzione per componente (manutenzione/reclami/sicurezza)
4. **Creati vs Risolti** (Created vs Resolved): andamento reclami e manutenzioni
5. **Due dimensioni** (Two Dimensional Filter Statistics): matrice priorità × componente
```

**Step 8: Update expected results (lines 50-54)**

Change:
```
## Risultato atteso

- 1 dashboard personale funzionante con almeno 4 gadget
- I gadget devono essere collegati a filtri JQL reali
- Il layout deve essere ordinato e leggibile
```
To:
```
## Risultato atteso

- 1 dashboard personale funzionante con almeno 5 gadget (incluso Assigned to Me)
- I gadget devono essere collegati a filtri JQL reali
- Il layout deve essere ordinato e leggibile
- La dashboard è contrassegnata con stella per accesso rapido
```

**Step 9: Commit**

```bash
git add jira-confluence-best-practices-2026/sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-dashboard-personale.md
git commit -m "docs: add Assigned to Me and starring to exercise 1

- Add Assigned to Me as gadget #1 for all 4 roles
- Add dashboard starring step
- Fix layout instruction (post-creation via Edit)
- Update time from 20 to 25 minutes"
```

---

## Task 3: Update esercizio-03-gadget-grafici.md

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-gadget-grafici.md`

**Step 1: Add Parte C after Parte B (after line 39)**

After the "Domande di riflessione" section (or before it), insert:

```markdown
### Parte C — Modifica le impostazioni di un gadget (5 min)

1. Scegli un gadget esistente sulla tua dashboard (es. Pie Chart o Created vs Resolved)
2. Clicca sui tre puntini (**⋯**) del gadget e seleziona **"Edit"**
3. Cambia una impostazione:
   - Per **Pie Chart**: cambia il campo di raggruppamento (es. da Status a Priority)
   - Per **Created vs Resolved**: cambia il periodo temporale (es. da 30 a 90 giorni)
4. Salva e osserva come cambia la visualizzazione
5. Domanda: come cambiano le informazioni mostrate? Quale configurazione è più utile per il tuo ruolo?
```

**Step 2: Update expected results (lines 41-45)**

Change:
```
## Risultato atteso

- 3 nuovi gadget aggiunti alla dashboard
- Capacità di interpretare i grafici con occhio critico
- Discussione in coppia completata
```
To:
```
## Risultato atteso

- 3 nuovi gadget aggiunti alla dashboard
- 1 modifica alle impostazioni di un gadget esistente
- Capacità di interpretare i grafici con occhio critico
- Discussione in coppia completata
```

**Step 3: Commit**

```bash
git add jira-confluence-best-practices-2026/sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-gadget-grafici.md
git commit -m "docs: add gadget settings modification to exercise 2

Add Parte C teaching participants to edit existing gadget settings"
```

---

## Task 4: Update esercizio-03-report-analisi.md

**Files:**
- Modify: `jira-confluence-best-practices-2026/sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-report-analisi.md`

**Step 1: Update time estimate (line 3)**

Change:
```
> ⏱ Tempo stimato: 25 minuti | 👥 Di gruppo (tutti e 4 i partecipanti)
```
To:
```
> ⏱ Tempo stimato: 35 minuti | 👥 Di gruppo (tutti e 4 i partecipanti)
```

**Step 2: Expand Step 1 with sharing mechanics (after line 15)**

Change:
```
1. L'IT Manager crea la dashboard e la condivide con il gruppo
```
To:
```
1. L'IT Manager crea la dashboard:
   - Nome: `Tyvak — Panoramica operativa`
   - Dopo la creazione: **Edit → Change layout** → 2 colonne
2. L'IT Manager condivide la dashboard con il gruppo:
   - Clicca **⋯** (More actions) → **Share dashboard**
   - Nella sezione **Editors**, aggiungi i partecipanti del gruppo (per nome o email)
   - ⚠️ **Importante**: condividi anche i filtri JQL usati dai tuoi gadget — altrimenti gli altri vedranno gadget vuoti. Per ogni filtro: **Filters** → trova il filtro → **⋯** → **Share**
```

And renumber subsequent steps (2→3, 3→4, 4→5).

**Step 3: Add navigation note to Parte B (before line 26)**

Insert before the numbered list in Parte B:

```markdown
> Per trovare i report: dalla sidebar, seleziona il tuo spazio → **Reports**.
> Per spazi company-managed con più board, assicurati di visualizzare la board corretta prima di aprire i report.
```

**Step 4: Add Parte C — Wallboard mode (after Parte B, before "Risultato atteso")**

Insert:

```markdown
### Parte C — Wallboard mode (5 min)

1. Tornate alla dashboard condivisa "Tyvak — Panoramica operativa"
2. Clicca **⋯** (More actions) → **View as wallboard**
3. Osservate come la dashboard appare a schermo intero senza menu di navigazione
4. Premete **Esc** per tornare alla vista normale
5. Discutete: in quale contesto usereste il wallboard mode? (riunioni di team, monitor condiviso in ufficio?)
```

**Step 5: Update expected results (lines 36-40)**

Change:
```
## Risultato atteso

- 1 dashboard condivisa con 5+ gadget, visibile a tutto il gruppo
- Comprensione di almeno 2 report nativi di Jira
- Discussione di gruppo su come usare i dati per migliorare i processi
```
To:
```
## Risultato atteso

- 1 dashboard condivisa con 5+ gadget, visibile a tutto il gruppo
- Comprensione pratica della meccanica di condivisione (Editors, filtri)
- Comprensione di almeno 2 report nativi di Jira
- Esperienza pratica con wallboard mode
- Discussione di gruppo su come usare i dati per migliorare i processi
```

**Step 6: Commit**

```bash
git add jira-confluence-best-practices-2026/sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-report-analisi.md
git commit -m "docs: add sharing mechanics and wallboard to exercise 3

- Add explicit sharing steps (Editors, filter sharing)
- Add report navigation instructions
- Add Parte C with wallboard mode
- Update time from 25 to 35 minutes"
```

---

## Task 5: Fix dashboard-cheatsheet.md

**Files:**
- Modify: `jira-confluence-best-practices-2026/cheatsheet/dashboard-cheatsheet.md`

**Step 1: Fix creation sequence (line 9)**

Change:
```
3. Scegliere il layout (1, 2, o 3 colonne)
```
To:
```
3. Dopo la creazione: **Edit** → **Change layout** (1, 2, o 3 colonne)
```

**Step 2: Fix Average Age description (line 21)**

Change:
```
| **Average Age** | Età media degli elementi di lavoro | Identificare work item stagnanti |
```
To:
```
| **Average Age** | Età media (in giorni) dei work item non risolti | Identificare work item stagnanti |
```

**Step 3: Fix deprecation list (lines 26-27)**

Change:
```
> ⚠️ **Gadget in fase di rimozione** (rimozione sospesa, ma potrebbero non essere disponibili):
> Heat Map, Resolution Time, Time Since Chart, Time to First Response, Workload Pie Chart
```
To:
```
> ⚠️ **Gadget con rimozione annunciata** (rimozione sospesa ad aprile 2025 — attualmente ancora disponibili, ma non più mantenuti):
> Heat Map, Road Map, Bubble Chart, Spaces (ex Projects), Labels
```

**Step 4: Add Viewers vs Editors note to sharing section (after line 99)**

After "**Come condividere**: Dashboard → ⋯ → Edit → Share → Aggiungi utenti/gruppi", add:

```markdown
> **Viewers vs Editors**: i Viewer possono solo visualizzare; gli Editor possono modificare
> gadget e cancellare la dashboard. Condividi anche i filtri JQL sottostanti ai gadget!
```

**Step 5: Fix wallboard section (lines 103-106)**

Change:
```
Per visualizzare la dashboard su uno schermo condiviso:
- Aggiungi `?wallboard` all'URL della dashboard
- Esempio: `https://tyvak.atlassian.net/jira/dashboards/10001?wallboard`
- I gadget si aggiornano automaticamente
```
To:
```
Per visualizzare la dashboard su uno schermo condiviso:
- **Via menu** (consigliato): Dashboard → **⋯** → **View as wallboard**
- **Via URL** (alternativa): aggiungi `?wallboard` all'URL della dashboard
- Wallboard slideshow: rotazione automatica tra più dashboard con intervalli configurabili
- I gadget si aggiornano automaticamente
```

**Step 6: Commit**

```bash
git add jira-confluence-best-practices-2026/cheatsheet/dashboard-cheatsheet.md
git commit -m "docs: fix cheatsheet audit findings

- Fix creation sequence (layout is post-creation)
- Fix Average Age description
- Fix incorrect deprecation list (was Resolution Time etc, now correct 5 gadgets)
- Add Viewers vs Editors note
- Add menu-driven wallboard access as primary method"
```

---

## Task 6: Update audit checklist

**Files:**
- Modify: `docs/audit/sessione-03-audit.md`

**Step 1: Check off all completed items in section 9**

Change all `- [ ]` checkboxes in section 9 (CHECKLIST CORREZIONI) to `- [x]` for the
items completed in Tasks 1-5. This should cover all must-fix and should-fix items.

**Step 2: Update the status line at the top of the file**

Change:
```
> Stato: **da correggere** — 6 errori di accuratezza, 13 gap di completezza, 5 problemi esercizi
```
To:
```
> Stato: **corretto** — tutti i must-fix e should-fix risolti (2026-03-04)
```

**Step 3: Commit**

```bash
git add docs/audit/sessione-03-audit.md
git commit -m "docs: mark audit findings as resolved"
```

---

## Task 7: Final cross-check validation

**Step 1: Verify all internal links work**

Check that these links in the outline resolve to existing files:
- `esercizi/esercizio-03-dashboard-personale.md`
- `esercizi/esercizio-03-gadget-grafici.md`
- `esercizi/esercizio-03-report-analisi.md`
- `slides/`
- `../cheatsheet/dashboard-cheatsheet.md`
- `../cheatsheet/jql-cheatsheet.md`

**Step 2: Verify terminology consistency**

Grep all modified files for stale terminology:
- No "dashboard di sistema" (should be "dashboard predefinito")
- No "media tempo in status" (should be "età media")
- "spazio" used consistently (not "progetto" in Jira context)
- "work item" or "elementi di lavoro" used consistently (not "issue")

**Step 3: Verify timing totals**

Re-add all section durations in the outline and confirm they sum to exactly 240 minutes.

**Step 4: Spot-check cheatsheet-outline alignment**

Verify the cheatsheet gadget table includes all gadgets mentioned in outline sections 3.3-3.4,
and the deprecation lists match.
