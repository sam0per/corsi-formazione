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
- **Work item creati di recente** (Recently Created Work Items): elementi di lavoro creati di recente — utile per monitorare il volume di nuovo lavoro
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

#### 3.5 Report integrati di Jira (15 min)

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

#### 3.7 Condivisione e permessi dashboard (20 min)

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
