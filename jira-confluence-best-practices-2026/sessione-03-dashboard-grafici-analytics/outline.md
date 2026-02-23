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

### Blocco 1 — Dashboard e Gadget (0:00 - 1:00)

#### 3.1 Panoramica delle dashboard (15 min)

- Cos'è una dashboard in Jira
- Dashboard di sistema vs dashboard personali
- La dashboard come strumento di comunicazione e visibilità
- Best practice: una dashboard per ruolo, una per direzione
- Esempio Tyvak: dashboard del Facility Manager per i work item aperti

#### 3.2 Creare e configurare una dashboard (20 min)

- Creazione di una nuova dashboard
- Layout: 1 colonna, 2 colonne, 3 colonne
- Aggiungere gadget alla dashboard
- Posizionamento e ridimensionamento dei gadget
- Demo live: creazione guidata di una dashboard

#### 3.3 Gadget principali (25 min)

- **Risultati filtro** (Filter Results): tabella **elementi di lavoro** (work item) da un filtro JQL
- **Grafico a torta** (Pie Chart): distribuzione per campo (status, priority, assignee)
- **Creati vs Risolti** (Created vs Resolved): andamento nel tempo
- **Grafico a due dimensioni** (Two Dimensional Filter Statistics): matrice campo × campo
- **Attività recente** (Activity Stream): feed delle attività
- **Media tempo in status** (Average Age): tempo medio di permanenza
- **Mappa di calore** (Heat Map) — ⚠️ gadget in fase di rimozione, potrebbe non essere disponibile
- **Introduzione** (Introduction): note e istruzioni in formato wiki
- Collegamento gadget ↔ filtro salvato: molti gadget si basano su un filtro JQL salvato (ma non tutti lo richiedono)

**☕ Pausa (10 min)**

### Esercizi Blocco 1 (1:00 - 1:45)

- [Esercizio 1: Crea la tua dashboard personale](esercizi/esercizio-03-dashboard-personale.md)
- [Esercizio 2: Gadget e grafici](esercizi/esercizio-03-gadget-grafici.md)

---

### Blocco 2 — Report, Analytics e condivisione (1:45 - 2:45)

#### 3.4 Report integrati di Jira (20 min)

- Report dello **spazio** (space): dove trovarli (sezione Reports nella sidebar)
- **Burndown Chart** (board Scrum): report a livello di board, non gadget dashboard
- **Velocity Chart**: report a livello di board
- **Cumulative Flow Diagram**: report a livello di board
- **Control Chart**: report a livello di board, tempo di ciclo dei work item
- Interpretazione pratica: cosa ci dicono questi report?

#### 3.5 Dashboard avanzate e trucchi (15 min)

- Gadget con JQL dinamico (es. `currentUser()`, date relative)
- Dashboard "manager": panoramica cross-spazio
- Dashboard "operativa": focus sulle attività del giorno
- Wallboard mode: dashboard su schermo condiviso
- Refresh automatico dei gadget

#### 3.6 Condivisione e permessi dashboard (15 min)

- Condividere con utenti specifici
- Condividere con gruppi
- Condividere con l'intera organizzazione
- Dashboard come strumento di reporting per la direzione
- Best practice: chi dovrebbe vedere cosa?
- Esempio Tyvak: dashboard per il management con KPI cross-dipartimento

**☕ Pausa (10 min)**

### Esercizi Blocco 2 (2:45 - 3:30)

- [Esercizio 3: Report e dashboard condivisa](esercizi/esercizio-03-report-analisi.md)

### Recap e Q&A (3:30 - 4:00)

- Riepilogo: filtri JQL → gadget → dashboard → reporting
- La catena del valore: dato → informazione → decisione
- Anteprima sessione 4: automazioni, workflow e amministrazione

---

## Materiali di riferimento

- [Slide sessione 3](slides/)
- [Dashboard Cheatsheet](../cheatsheet/dashboard-cheatsheet.md)
- [JQL Cheatsheet](../cheatsheet/jql-cheatsheet.md)
