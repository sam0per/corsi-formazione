---
marp: true
theme: default
paginate: true
title: Sessione 5 Confluence Integrazione e Knowledge Sharing
---

<!-- _class: lead -->

# Sessione 5: Confluence, Integrazione e Knowledge Sharing

**Documentazione, integrazione Jira-Confluence e piano di knowledge sharing**

Corso Atlassian: Jira e Confluence Best Practices 2026
Tyvak International

> Samuel Perini, docente a Kinetikon

---

<style scoped>
  section { font-size: 26px; }
</style>

# Agenda

| Blocco | Argomento | Dettaglio |
|--------|-----------|-----------|
| **1** | Confluence essenziali | Panoramica, editor, template, ricerca, permessi |
| | Esercizi Blocco 1 | Creare pagine Confluence |
| **2** | Integrazione e KT | Macro Jira, smart link, best practice, piano KT |
| | Esercizi Blocco 2 | Integrazione Jira-Confluence, piano di knowledge sharing |

---

<!-- _class: lead -->

# Blocco 1
## Confluence essenziali

---

# Cos'è Confluence?

- **Wiki aziendale** per la documentazione e la collaborazione
- **Knowledge base** per procedure, FAQ e guide operative
- Parte dell'ecosistema Atlassian: Jira + Confluence + JSM
- Complementare a Jira: **Confluence documenta**, **Jira traccia il lavoro**

---

<style scoped>
  section { font-size: 22px; }
</style>

# Struttura di Confluence

```
Sito Atlassian (tyvak.atlassian.net)
  └── Spazio (Space)
       ├── Pagina (Page) → documento con pubblicazione
       ├── Live Doc → collaborazione in tempo reale
       ├── Blog Post → aggiornamenti cronologici
       ├── Whiteboard → lavagna collaborativa
       ├── Database → dati strutturati in tabelle
       └── Cartella (Folder) → organizzazione
```

### Tipi di spazio

| Tipo | Quando usare |
|------|-------------|
| **Collaboration** | Lavoro di team, progetti |
| **Knowledge base** | FAQ, guide, procedure |
| **Custom** | Struttura personalizzata |

---

<style scoped>
  section { font-size: 24px; }
</style>

# L'editor cloud di Confluence

### Comandi rapidi — digita `/` + nome

| Comando | Elemento |
|---------|---------|
| `/tabella` | Tabella |
| `/espansione` | Sezione espandibile |
| `/pannello` | Pannello (info, note, warning, error, success) |
| `/azione` | Task con checkbox |
| `/immagine` | Immagine |
| `/jira` | Macro Jira |

> I comandi sopra sono per istanze con UI in italiano. Con UI in inglese usare: `/table`, `/expand`, `/panel`, `/action`, `/image`, `/jira`.

### Pagine vs Live Doc

- **Pagina**: workflow di pubblicazione (bozza → pubblica)
- **Live Doc**: modifiche visibili istantaneamente, fino a 30 editor simultanei

---

<style scoped>
  section { font-size: 24px; }
</style>

# Template predefiniti

| Template | Scopo |
|----------|-------|
| **Meeting notes** | Verbale riunione |
| **Decision** | Documentare decisioni |
| **How-to article** | Guide passo-passo |
| **Retrospettiva** | Start / Stop / Keep |
| **DevOps Runbook** | Procedure operative IT |
| **ITSM Runbook** | Gestione alert |

> Confluence Cloud offre **100+ template** nella galleria

---

# Organizzazione dei contenuti

- **Gerarchia**: pagine → sotto-pagine (drag & drop nel content tree)
- **Etichette (label)**: tag per categorizzare e trovare pagine
- **Cartelle (folder)**: raggruppare contenuti correlati
- **Allegati**: file, immagini, documenti (max 100 MB)
- **Commenti**: a livello di pagina o inline su testo selezionato
- **Menzioni**: `@nome` per notificare colleghi
- **Versioni**: ogni pubblicazione crea una nuova versione (con diff e ripristino)

---

# Ricerca e navigazione

| Metodo | Come |
|--------|------|
| Ricerca globale | Barra di ricerca in alto |
| Per etichetta | Clicca su un'etichetta o filtra per label |
| Recenti | Sidebar → **Recent** |
| Starred | Sidebar → **Starred** (icona stella) |
| Content tree | Sidebar dello spazio (albero, A-Z, ultimi aggiornamenti) |

---

<style scoped>
  section { font-size: 24px; }
</style>

# Permessi e notifiche

### Permessi — tre livelli

| Livello | Cosa controlla | Chi gestisce |
|---------|---------------|--------------|
| **Globale** | Accesso all'intera istanza Confluence | Site admin |
| **Spazio** | Accesso a tutto lo spazio | Space admin |
| **Pagina** | Restrizioni su singola pagina | Autore / space admin |

> **Gruppi**: non sono un livello di permesso, ma un meccanismo per assegnare permessi a insiemi di utenti a tutti e tre i livelli.

### Notifiche

- **Watch** (seguire): ricevi notifiche quando una pagina cambia
- **Watch spazio**: segui tutte le pagine di uno spazio
- Gestione: profilo → **Settings** → **Email** (per preferenze email) oppure "Watch" sulla singola pagina

---

# Esercizi Blocco 1

### 1. Creare pagine Confluence

Crea 2 pagine (una da zero, una da template) + ricerca e navigazione

---

<!-- _class: lead -->

# Blocco 2
## Integrazione Jira-Confluence e Knowledge Sharing

---

<style scoped>
  section { font-size: 24px; }
</style>

# Integrazione: da Confluence a Jira

### Macro Jira Work Items (`/jira`)
- Tabella di work item da query JQL o filtro salvato
- Colonne configurabili (Key, Summary, Status, Priority, Assignee)
- Si aggiorna **ad ogni caricamento della pagina**

### Macro Jira Chart (`/jira chart`)
- Grafico a torta, creati vs risolti, 2D
- Collegato a filtro salvato

### Creare work item da Confluence
- `/jira` → Create Jira work item
- Seleziona testo → "+ Jira work item"

### Smart Link
- Incolla URL di un work item → preview automatica con titolo e status

---

<style scoped>
  section { font-size: 24px; }
</style>

# Integrazione: da Jira a Confluence

### Collegare pagine Confluence
- Nel work item Jira: "+" o "Link" → "Existing Confluence page"
- Il collegamento è **bidirezionale**: appare sia in Jira che in Confluence

### Smart Link nella descrizione
- Incolla URL Confluence nella descrizione del work item
- Preview automatica del titolo della pagina

### Knowledge base (Jira Service Management)
- In JSM: collega uno spazio Confluence come knowledge base self-service
- I clienti/dipendenti trovano risposte prima di aprire un ticket

> **Nota**: la knowledge base integrata richiede **Jira Service Management**

---

<style scoped>
  section { font-size: 24px; }
</style>

# Casi d'uso Tyvak

| Scenario | Come |
|----------|------|
| Stato ordini | Pagina Confluence con macro Jira Work Items |
| Procedure IT | Documentazione su Confluence con link ai workflow Jira |
| Report facility | Pagina con Jira Chart (grafici incorporati) |
| Onboarding HR | Guida Confluence + checklist come work item Jira |

---

<style scoped>
  section { font-size: 24px; }
</style>

# Best practice Jira + Confluence

- **Documentare i workflow** su Confluence con link ai processi Jira
- **Runbook** per processi ricorrenti (template DevOps / ITSM)
- **Shortcut bidirezionali** tra spazi Jira e Confluence
- **Dashboard Jira + pagine Confluence** = reporting completo
- **Page ownership**: ogni pagina ha un proprietario responsabile
- **Ciclo di vita**: crea → mantieni → archivia → revisiona

---

<style scoped>
  section { font-size: 24px; }
</style>

# Piano di Knowledge Sharing

### 5 domande chiave

| # | Domanda | Output |
|---|---------|--------|
| 1 | **A chi?** | Gruppi target (team lead, operativi, nuovi assunti) |
| 2 | **Cosa?** | 3 argomenti prioritari per gruppo |
| 3 | **Come?** | Formato (live, video, Confluence, 1:1, cheat sheet) |
| 4 | **Quando?** | Calendario 4-8 settimane |
| 5 | **Funziona?** | Metriche di successo e follow-up |

---

# Esercizi Blocco 2

### 2. Integrazione Jira-Confluence
Macro Jira in Confluence + link bidirezionali + runbook

### 3. Piano di Knowledge Sharing
Piano concreto con target, contenuti, formati, calendario e metriche

---

<style scoped>
  section { font-size: 24px; }
</style>

# Recap: il percorso completo

| Sessione | Competenza acquisita |
|----------|---------------------|
| **1. Fondamenti** | Come è strutturato Jira |
| **2. JQL** | Trovare qualsiasi informazione |
| **3. Dashboard** | Visualizzare e comunicare i dati |
| **4. Automazioni** | Ottimizzare i processi |
| **5. Confluence + KT** | Documentare e condividere |

---

<style scoped>
  section { font-size: 24px; }
</style>

# Risorse per continuare

- [Atlassian Community](https://community.atlassian.com/)
- [Atlassian University](https://university.atlassian.com/) — certificazione **Confluence Essentials (ACA-920)**
- [Atlassian Documentation](https://support.atlassian.com/)
- [Confluence Resource Center](https://www.atlassian.com/software/confluence/resources)
- [Confluence Templates](https://www.atlassian.com/software/confluence/templates)

### Prossimi passi

- Completare il piano di knowledge sharing
- Creare/strutturare lo spazio Confluence "Formazione Jira — Tyvak"
- Condurre la prima sessione di formazione interna entro 2 settimane
