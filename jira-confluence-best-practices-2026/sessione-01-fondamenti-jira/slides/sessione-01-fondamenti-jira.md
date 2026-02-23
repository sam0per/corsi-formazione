---
marp: true
theme: default
paginate: true
title: Sessione 1 Fondamenti di Jira
---

<!-- _class: lead -->

# Sessione 1: Fondamenti di Jira

**Architettura, navigazione, tipi di lavoro (work type) e workflow base**

Corso Atlassian: Jira e Confluence Best Practices 2026
Tyvak International

---

<style scoped>
  section { font-size: 26px; }
</style>

# Agenda

| Blocco | Argomento | Dettaglio |
|--------|-----------|-----------|
| **1** | Architettura e Navigazione | Panoramica Atlassian, architettura Jira, navigazione dell'interfaccia |
| | Esercizi Blocco 1 |  |
| **2** | Elementi Jira | Tipi di spazio, di lavoro e workflow |
| | Esercizi Blocco 2 |  |

---

<!-- _class: lead -->

# Blocco 1
## Architettura e Navigazione

---

# Cos'è Jira

- Piattaforma Atlassian per il **tracciamento del lavoro** e la gestione dei flussi operativi
- Utilizzata da team software, IT, HR, finance e altri
- **Cloud-native**: aggiornamenti automatici, accessibile via browser
- Parte dell'ecosistema Atlassian: Jira, Confluence, Jira Service Management

---

<style scoped>
  section { font-size: 22px; }
</style>

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

# Tipi di schema

---

<style scoped>
  section { font-size: 24px; }
</style>

# Tipi di lavoro (Work Type)

| Tipo | Descrizione | Esempio Tyvak |
|------|-------------|---------------|
| **Epic** | Iniziativa ampia, raggruppa altri elementi | Missione KINETIKON |
| **Story** | Requisito o funzionalità da realizzare | "Definire checklist onboarding" |
| **Task** | Attività operativa concreta | "Configurare VPN nuovo dipendente" |
| **Bug** | Problema da risolvere | "Stampante non raggiungibile" |
| **Sub-task** | Sotto-attività di un elemento di lavoro padre | Singolo step di una Task |

I tipi di lavoro sono configurabili: è possibile crearne di **custom** per esigenze specifiche.

---

# Tipi di workflow

---

# Tipi di schermata (Screen)

---

# Tipi di permesso (Permission)

---

<style scoped>
  section { font-size: 24px; }
</style>

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

<style scoped>
  section { font-size: 24px; }
</style>

# Tipi di spazio (Space Type)

### Team-managed (ex "Next-gen")

- Configurazione **semplificata**, gestita dal team
- Workflow, campi e permessi indipendenti dallo schema globale
- Ideale per team autonomi con esigenze specifiche

### Company-managed (ex "Classic")

- Configurazione **centralizzata** dall'amministratore
- Workflow, schermate e permessi gestiti tramite schemi condivisi
- Ideale per processi aziendali standardizzati

---

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
