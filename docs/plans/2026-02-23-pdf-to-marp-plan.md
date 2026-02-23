# PDF to Marp Markdown Conversion — Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Convert the sessione-01 slide deck from PDF to a Marp markdown file, applying all audit fixes during conversion.

**Architecture:** Single Marp markdown file replaces the PDF. All 16 slides converted with corrected terminology (spazio/space, elemento di lavoro/work item, tipo di lavoro/work type), updated navigation (left sidebar), and fixed priority values (Highest instead of Critical).

**Tech Stack:** Marp (markdown-based slide tool), no build scripts or custom themes.

---

### Task 1: Create the Marp markdown slide deck

**Files:**
- Create: `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/slides/sessione-01-fondamenti-jira.md`

**Step 1: Write the complete Marp markdown file**

Create the file at the path above with the following complete content (all 16 slides, audit fixes already applied):

````markdown
---
marp: true
theme: default
paginate: true
title: Sessione 1 — Fondamenti di Jira Cloud
---

<!-- _class: lead -->

# Sessione 1 — Fondamenti di Jira Cloud

**Architettura, navigazione, tipi di lavoro (work type) e workflow base**

Corso Atlassian: Jira e Confluence Best Practices 2026
Tyvak International

---

# Agenda

| Blocco | Argomento | Durata |
|--------|-----------|--------|
| **1.1** | Panoramica ecosistema Atlassian | 15 min |
| **1.2** | Architettura di Jira | 20 min |
| **1.3** | Navigazione dell'interfaccia | 15 min |
| | ☕ Pausa + Esercizi Blocco 1 | 55 min |
| **2.1** | Tipi di spazio (space type) | 20 min |
| **2.2** | Elementi di lavoro in profondità | 20 min |
| **2.3** | Workflow base | 20 min |
| | ☕ Pausa + Esercizi Blocco 2 + Recap | 75 min |

---

<!-- _class: lead -->

# Blocco 1
## Architettura e Navigazione

---

# Cos'è Jira Cloud

- Piattaforma Atlassian per il **tracciamento del lavoro** e la gestione dei flussi operativi
- Utilizzata da team software, IT, HR, finance, facility e altri
- **Cloud-native**: aggiornamenti automatici, accessibile via browser
- Parte dell'ecosistema Atlassian: Jira, Confluence, Jira Service Management

### Jira Cloud vs Data Center

| | Cloud | Data Center |
|---|-------|-------------|
| **Hosting** | Atlassian gestisce tutto | Self-hosted |
| **Aggiornamenti** | Automatici e continui | Manuali |
| **Personalizzazione** | Tramite Marketplace e automazioni | Completa (plugin, DB) |
| **Ideale per** | Team che vogliono semplicità | Organizzazioni con requisiti specifici |

---

# Architettura di Jira

### Gerarchia

```
Sito Atlassian (tyvak.atlassian.net)
  └── Spazio (Space) → contenitore logico per il lavoro
       └── Board (Scrum / Kanban) → visualizzazione del lavoro
            └── Elemento di lavoro (Work Item) → unità di lavoro
```

### Schema

Ogni **spazio** è collegato a uno **schema** che definisce:
- Quali **tipi di lavoro** (work type) sono disponibili
- Quale **workflow** si applica a ciascun tipo
- Quali **schermate** (screen) mostrare per creazione/modifica
- Quali **permessi** regolano l'accesso

---

# Tipi di lavoro (Work Type)

| Tipo | Descrizione | Esempio Tyvak |
|------|-------------|---------------|
| **Epic** | Iniziativa ampia, raggruppa altri elementi | Missione MILANI |
| **Story** | Requisito o funzionalità da realizzare | "Definire checklist onboarding" |
| **Task** | Attività operativa concreta | "Configurare VPN nuovo dipendente" |
| **Bug** | Problema da risolvere | "Stampante non raggiungibile" |
| **Sub-task** | Sotto-attività di un elemento di lavoro padre | Singolo step di una Task |

I tipi di lavoro sono configurabili: è possibile crearne di **custom** per esigenze specifiche.

---

<!-- _class: lead -->

# ☕ Pausa (10 min)

---

# Navigazione dell'interfaccia

### Sidebar di navigazione sinistra

La navigazione principale di Jira Cloud è nella **sidebar sinistra**:

- **Spazi recenti** — accesso rapido agli spazi visitati
- **Board** — visualizzazione Scrum o Kanban
- **Backlog** — gestione del backlog dello spazio
- **Code** — integrazione con repository (se configurata)
- **Impostazioni dello spazio** — configurazione (in basso)

### Elementi chiave

- **Your Work** — la tua area di lavoro personale (elementi assegnati, recenti, preferiti)
- **Notifiche** — avvisi su menzioni, assegnazioni, aggiornamenti
- **Ricerca globale rapida** — cerca ovunque in Jira

### Shortcut utili

| Shortcut | Azione |
|----------|--------|
| `/` | Ricerca globale rapida |
| `c` | Crea nuovo elemento di lavoro |

---

<!-- _class: lead -->

# Blocco 2
## Tipi di spazio, Elementi di lavoro e Workflow

---

# Tipi di spazio (Space Type)

### Team-managed (ex "Next-gen")

- Configurazione **semplificata**, gestita dal team
- Workflow, campi e permessi indipendenti dallo schema globale
- Ideale per team autonomi con esigenze specifiche

### Company-managed (ex "Classic")

- Configurazione **centralizzata** dall'amministratore
- Workflow, schermate e permessi gestiti tramite schemi condivisi
- Ideale per processi aziendali standardizzati

### Quando usare quale?

| Criterio | Team-managed | Company-managed |
|----------|-------------|-----------------|
| **Controllo** | Il team decide | L'admin decide |
| **Complessità** | Bassa | Media-alta |
| **Standardizzazione** | Flessibile | Uniforme |
| **Esempio Tyvak** | Piccoli team operativi | Processi aziendali (IT, HR, Facility) |

---

<!-- _class: lead -->

# Elementi di lavoro in profondità

---

# Anatomia di un elemento di lavoro (work item)

### Campi standard

| Campo | Descrizione |
|-------|-------------|
| **Summary** | Titolo dell'elemento di lavoro |
| **Tipo di lavoro** | Task, Bug, Story, Epic, Sub-task |
| **Status** | Stato nel workflow (es. To Do, In Progress, Done) |
| **Assegnatario** | Persona responsabile |
| **Reporter** | Chi ha creato l'elemento |
| **Priorità** | Lowest → Low → Medium → High → Highest |
| **Etichette** | Tag liberi per categorizzare |
| **Componente** | Area funzionale (es. Infrastruttura, HR) |
| **Sprint** | Iterazione di riferimento (spazi Scrum) |

Oltre ai campi standard, è possibile aggiungere **campi custom**.

---

# Relazioni tra elementi di lavoro

### Tipi di relazione

- **Sotto-attività** — elemento figlio di un elemento padre
- **Collegamento** (link) — relazione tra elementi indipendenti
  - "is related to" — relazione generica
  - "is blocked by" / "blocks" — dipendenza
  - "is cloned by" / "clones" — copia
- **Epic link** — collegamento di un elemento alla sua Epic

### Interazioni

- **Commenti** — discussione sull'elemento, con supporto per menzioni (`@nome`)
- **Allegati** — file, screenshot, documenti
- **Cronologia** (Activity) — registro di tutte le modifiche

---

# Workflow base

### Cos'è un workflow?

Un workflow definisce il **ciclo di vita** di un elemento di lavoro attraverso **stati** e **transizioni**.

### Workflow predefinito di Jira

```
┌──────────┐     ┌──────────────┐     ┌──────────┐
│  To Do   │ ──→ │ In Progress  │ ──→ │   Done   │
└──────────┘     └──────────────┘     └──────────┘
```

- Ogni **elemento di lavoro** attraversa questi stati
- Le **transizioni** definiscono i passaggi permessi tra stati
- Ogni **spazio** può avere il proprio workflow

### Stati personalizzati

Si possono aggiungere stati custom (es. "In Review", "Waiting for Approval") per adattare il workflow al proprio processo.

---

# Best practice per i workflow

- **Semplicità**: massimo 6-7 stati per workflow
- **Nomi chiari**: ogni stato deve essere comprensibile a tutti
- **Transizioni esplicite**: definire chiaramente chi può spostare e quando
- **Coerenza**: stessi nomi di stato tra spazi simili

### Nota sul workflow editor

Il vecchio editor di workflow sarà rimosso a partire da **giugno 2026** ([JRACLOUD-83818](https://jira.atlassian.com/browse/JRACLOUD-83818)). Il nuovo editor è già disponibile e funzionalmente completo.

### Esempio Tyvak

Un work item IT (IT Manager) potrebbe seguire:

```
Aperto → In Lavorazione → In Verifica → Completato
```

---

# Recap — Sessione 1

### Concetti chiave

- **Architettura**: Sito → Spazio → Board → Elemento di lavoro
- **Tipi di spazio**: Team-managed vs Company-managed
- **Tipi di lavoro**: Epic, Story, Task, Bug, Sub-task
- **Elementi di lavoro**: campi, priorità, etichette, relazioni
- **Workflow**: stati, transizioni, personalizzazione

### Prossima sessione

**Sessione 2 — Filtri, Ricerche e JQL**
- Ricerca base e avanzata
- Sintassi JQL (operatori, funzioni)
- Filtri salvati e sottoscrizioni

> **Nota:** in JQL i termini `project` e `issuetype` restano validi per retrocompatibilità, anche se l'interfaccia ora usa "spazio" e "tipo di lavoro".
````

**Step 2: Verify the file was created correctly**

Read the file and confirm:
- Marp front matter present (`marp: true`, `theme: default`, `paginate: true`)
- 16 slides separated by `---`
- No instances of the old terminology: "progetto" (as Jira concept), "issue" (as Jira concept), "issue type"
- Slide 8 describes left sidebar navigation (not top bar)
- Slide 12 priorities end with "Highest" (not "Critical")

**Step 3: Commit**

```bash
git add jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/slides/sessione-01-fondamenti-jira.md
git commit -m "docs: convert sessione-01 slides from PDF to Marp markdown with audit fixes"
```

---

### Task 2: Delete the old PDF and update .gitignore

**Files:**
- Delete: `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/slides/sessione-01-fondamenti-jira.pdf`

**Step 1: Delete the old PDF**

```bash
git rm jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/slides/sessione-01-fondamenti-jira.pdf
```

**Step 2: Commit**

```bash
git commit -m "chore: remove old PDF slides replaced by Marp markdown source"
```

---

### Task 3: Verify Marp renders correctly (optional, if marp-cli is installed)

**Step 1: Check if marp-cli is available**

```bash
npx @marp-team/marp-cli --version
```

If available, generate a PDF to verify:

```bash
npx @marp-team/marp-cli jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/slides/sessione-01-fondamenti-jira.md --pdf --allow-local-files
```

If not available, skip this task — the markdown is valid Marp and can be verified with the VS Code Marp extension or by installing marp-cli later.

---

## Task Summary

| # | Description | Automated? |
|---|-------------|------------|
| 1 | Create Marp markdown with all 16 slides + audit fixes | Yes |
| 2 | Delete old PDF | Yes |
| 3 | Verify Marp rendering | Optional |
