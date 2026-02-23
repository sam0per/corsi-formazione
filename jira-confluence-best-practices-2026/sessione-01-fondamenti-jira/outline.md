# Sessione 1: Fondamenti di Jira Cloud

> ⏱ Durata: 4 ore | 📅 Sessione 1 di 5

## Obiettivi della sessione

Al termine di questa sessione i partecipanti saranno in grado di:

- Comprendere l'architettura di Jira Cloud (Sito → Spazio → Board → Elemento di lavoro)
- Navigare con sicurezza l'interfaccia di Jira Cloud
- Distinguere tra spazi Team-managed e Company-managed
- Creare e configurare **elementi di lavoro** (work item) con campi, priorità, etichette e componenti
- Comprendere il concetto di workflow e status

---

## Programma dettagliato

### Blocco 1: Architettura e Navigazione (0:00 - 1:00)

#### 1.1 Panoramica dell'ecosistema Atlassian (10 min)

- Jira, Confluence, e le integrazioni principali
- Il concetto di "Sito Atlassian" e come è strutturato
- Ruoli globali vs ruoli dello **spazio** (space)

#### 1.2 Architettura di Jira (25 min)

- **Gerarchia**: Sito → Space → Board → Work Item
- **Spazi** (Space): contenitori logici per il lavoro
- **Tipi di lavoro** (Work Type): Epic, Story, Task, Sub-task, Bug (e tipi custom)
- **Schemi** (scheme): configurazioni riutilizzabili per spazi company-managed
  - Tipi di schema: Work Type, Workflow, Screen, Permission, Notification Scheme
  - Tipi di workflow: predefinito vs personalizzato
  - Tipi di schermata (screen): contesti Create, Edit, View
  - Tipi di permesso: globali vs di spazio (Browse, Create, Edit, Assign, Transition)
  - Differenze tra spazi team-managed e company-managed
- Esempio Tyvak: come uno spazio di missione satellitare (es. MILANI) si mappa su Jira

#### 1.3 Navigazione dell'interfaccia (15 min)

- **Sidebar di navigazione sinistra**
- Navigazione contestuale dello spazio
- Ricerca globale rapida
- La tua area di lavoro (For You)
- Notifiche e menzioni
- Demo live: tour guidato dell'istanza Tyvak

**☕ Pausa (10 min)**

### Esercizi Blocco 1 (1:00 - 1:45)

- [Esercizio 1: Navigazione e esplorazione spazio](./esercizi/esercizio-0101-navigazione-space.md)
- [Esercizio 2: Ricerca base](./esercizi/esercizio-0102-ricerca-base.md)

---

### Blocco 2: Tipi di Space, Work Items e Workflows (1:45 - 2:45)

#### 2.1 Tipi di Space in Jira Cloud (20 min)

- **Team-managed**: configurazione semplificata, ideale per team autonomi
- **Company-managed**: configurazione centralizzata dall'admin
- Quando usare quale tipo
- Differenze pratiche: workflow, campi, permessi
- Esempio Tyvak: Team-managed per piccoli team operativi, Company-managed per processi aziendali

#### 2.2 Elementi di lavoro in profondità (20 min)

- Anatomia di un elemento di lavoro (work item): campi standard e custom
- Priorità, etichette, componenti, versioni
- Relazioni tra elementi di lavoro: collegamento, clonazione, sotto-attività
- Allegati e commenti
- Menzioni e notifiche
- Esempio Tyvak: creare un ordine forniture per il laboratorio (Facility Manager)

#### 2.3 Workflow base (20 min)

- Cos'è un workflow: stati e transizioni
- Workflow predefiniti di Jira
- Visualizzazione del workflow di uno spazio
- Stati personalizzati: quando e perché
- Esempio Tyvak: workflow di un work item

**☕ Pausa (10 min)**

### Esercizi Blocco 2 (2:45 - 3:30)

- [Esercizio 3: Creazione e gestione work item](./esercizi/esercizio-0103-creazione-work-item.md)

*Dopo l'esercizio: discussione guidata e Q&A sui work item creati*

> **Nota sulla terminologia JQL e automazioni:** nonostante l'interfaccia di Jira ora utilizzi "spazio" e "elemento di lavoro", il linguaggio JQL continua a usare `project` e `issuetype` per retrocompatibilità. Anche gli smart value delle automazioni usano ancora `{{project}}`. Questi aspetti saranno approfonditi nella sessione 2.

### Recap e Q&A (3:30 - 4:00)

- Riepilogo concetti chiave
- Domande e risposte
- Anteprima sessione 2: filtri, ricerche e JQL

---

## Materiali di riferimento

- [Slide sessione 1](./slides/)
- [Glossario Jira](../glossario.md)