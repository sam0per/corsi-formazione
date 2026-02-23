# Corso di Formazione: Tableau e Modello Dati della Trimestrale

## 📑 Indice

- [Corso di Formazione: Tableau e Modello Dati della Trimestrale](#corso-di-formazione-tableau-e-modello-dati-della-trimestrale)
  - [📑 Indice](#-indice)
  - [📋 Panoramica del Corso](#-panoramica-del-corso)
    - [🎯 Obiettivi del Corso](#-obiettivi-del-corso)
  - [📚 Struttura del Corso](#-struttura-del-corso)
    - [Metodologia Didattica](#metodologia-didattica)
  - [📅 Programma Dettagliato](#-programma-dettagliato)
    - [**Sessione 1: Fondamenti e Introduzione a Tableau** (4 ore)](#sessione-1-fondamenti-e-introduzione-a-tableau-4-ore)
    - [**Sessione 2: Connessione ai Database e Preparazione Dati** (4 ore)](#sessione-2-connessione-ai-database-e-preparazione-dati-4-ore)
    - [**Sessione 3: Generazione di Output di Base** (4 ore)](#sessione-3-generazione-di-output-di-base-4-ore)
    - [**Sessione 4: Dashboard Interattive Efficaci** (4 ore)](#sessione-4-dashboard-interattive-efficaci-4-ore)
    - [**Sessione 5: Navigazione del Modello Dati Trimestrale** (4 ore)](#sessione-5-navigazione-del-modello-dati-trimestrale-4-ore)
    - [**Sessione 6: Sviluppo e Manutenzione del Modello Dati Trimestrale** (4 ore)](#sessione-6-sviluppo-e-manutenzione-del-modello-dati-trimestrale-4-ore)
  - [🗂️ Struttura del Repository](#️-struttura-del-repository)
  - [🔧 Prerequisiti e Setup](#-prerequisiti-e-setup)
    - [Prerequisiti per i Partecipanti](#prerequisiti-per-i-partecipanti)
    - [Setup Iniziale](#setup-iniziale)
  - [📖 Materiali del Corso](#-materiali-del-corso)
    - [Risorse Aggiuntive](#risorse-aggiuntive)
  - [🎓 Modalità di Valutazione](#-modalità-di-valutazione)
  - [👨‍🏫 Formatore](#-formatore)
  - [📞 Supporto e Comunicazione](#-supporto-e-comunicazione)
  - [📅 Calendar Indicativo](#-calendar-indicativo)
  - [📝 Note Finali](#-note-finali)

---

## 📋 Panoramica del Corso

Questo corso di formazione è progettato per fornire competenze pratiche e teoriche nella **Data Visualization con Tableau** e nell'utilizzo operativo del **modello dati della trimestrale** per il dipartimento di Programmazione e Controllo del progetto.

Il corso combina fondamenti metodologici, competenze tecniche su Tableau e formazione personalizzata sul modello dati proprietario, permettendo ai partecipanti di navigare, analizzare e sviluppare autonomamente report e dashboard per il controllo di progetto.

### 🎯 Obiettivi del Corso

Al termine della formazione, i partecipanti saranno in grado di:

- Comprendere e applicare i **principi fondamentali della Data Visualization** per creare output visivi efficaci
- Utilizzare **Tableau** in autonomia: dalla connessione ai database alla creazione di dashboard interattive
- **Navigare** con sicurezza all'interno della struttura del modello dati della trimestrale
- **Sviluppare e mantenere** il modello dati trimestrale, garantendo continuità operativa
- Creare **report, grafici e dashboard interattive** utilizzando i dati del progetto BBT
- Applicare best practice di governance dei dati e reportistica ciclica

---

## 📚 Struttura del Corso

**Durata Totale**: 24 ore  
**Formato**: 6 sessioni da 4 ore ciascuna  
**Modalità**: Online  
**Frequenza**: 1 sessione a settimana (indicativa)  
**Numero Partecipanti**: 5-10 persone

### Metodologia Didattica

Ogni sessione da 4 ore è strutturata come segue:

- **60 minuti**: Teoria e concetti fondamentali
- **90 minuti**: Esempi guidati e dimostrazioni pratiche dal formatore
- **90 minuti**: Esercizi pratici hands-on per i partecipanti

Ogni sessione include **2-3 esercizi pratici** di difficoltà progressiva per consolidare le competenze acquisite.

---

## 📅 Programma Dettagliato

### **Sessione 1: Fondamenti e Introduzione a Tableau** (4 ore)

**Obiettivi di Apprendimento**:
- Comprendere i principi fondamentali della Data Visualization
- Conoscere le funzionalità e capacità principali di Tableau
- Acquisire/rinfrescare competenze SQL di base
- Comprendere il contesto della reportistica trimestrale

**Contenuti**:

1. **Refresh: SQL di Base** (45 min)
   - Query SELECT, WHERE, JOIN
   - Aggregazioni: GROUP BY, COUNT, SUM, AVG
   - Filtraggio e ordinamento dati
   - *Esercizio 1*: Query SQL su database di esempio

2. **Fondamenti della Data Visualization** (45 min)
   - Principi di visualizzazione efficace (Tufte, Few)
   - Scelta del grafico giusto per il tipo di dato
   - Gestione di colori, legende e annotazioni
   - Errori comuni e best practice
   - *Esercizio 2*: Analisi critica di dashboard esistenti

3. **Panoramica di Tableau** (90 min)
   - Interfaccia: workspace, shelf, cards
   - Tipi di visualizzazioni disponibili
   - Tableau Desktop vs Tableau Server/Online
   - Workflow base: da dati a dashboard
   - *Esercizio 3*: Esplorazione guidata dell'interfaccia Tableau

4. **Introduzione alla Reportistica Trimestrale** (40 min)
   - Contesto: cicli di reporting e controllo progetto
   - Tipologie di KPI per la trimestrale
   - Stakeholder e utenti finali dei report
   - Esempio pratico di report trimestrale BBT

**Deliverable della Sessione**: Prima semplice visualizzazione in Tableau su dataset pubblico

---

### **Sessione 2: Connessione ai Database e Preparazione Dati** (4 ore)

**Obiettivi di Apprendimento**:
- Connettere Tableau a diverse fonti dati (database relazionali, Excel, CSV)
- Comprendere il data model di Tableau (relazioni vs join)
- Preparare e pulire i dati per l'analisi
- Creare connessioni live vs extract

**Contenuti**:

1. **Input sui Database** (60 min)
   - Connessione a SQL Server, PostgreSQL, Oracle
   - Connessione a file Excel e CSV
   - Differenza tra Live Connection ed Extract
   - Configurazione delle credenziali e sicurezza
   - *Esercizio 1*: Connessione a database di test

2. **Data Modeling in Tableau** (60 min)
   - Relazioni tra tabelle (Relationships)
   - Join fisici: Inner, Left, Right, Full Outer
   - Union di tabelle
   - Quando usare relazioni vs join
   - *Esercizio 2*: Creare un data model multi-tabella

3. **Preparazione e Pulizia Dati** (90 min)
   - Data Interpreter per pulizia automatica
   - Creazione di campi calcolati di base
   - Pivot di dati
   - Filtri a livello di data source
   - Gestione di valori NULL e duplicati
   - *Esercizio 3*: Preparazione di dataset "sporco" per analisi

4. **Best Practice per Performance** (30 min)
   - Quando usare Extract vs Live
   - Ottimizzazione delle query
   - Gestione di grandi volumi di dati

**Deliverable della Sessione**: Data source configurato e pulito pronto per l'analisi

---

### **Sessione 3: Generazione di Output di Base** (4 ore)

**Obiettivi di Apprendimento**:
- Creare tabelle, grafici e report strutturati
- Utilizzare campi calcolati e aggregazioni
- Applicare filtri e parametri
- Formattare output per presentazioni professionali

**Contenuti**:

1. **Creazione di Tabelle** (60 min)
   - Tabelle di testo semplici e crosstab
   - Formattazione condizionale
   - Totali e subtotali
   - Highlight tables
   - *Esercizio 1*: Generazione di tabelle utilizzando esempio BBT

2. **Grafici Fondamentali** (90 min)
   - Bar charts (orizzontali/verticali)
   - Line charts per serie temporali
   - Scatter plots e bubble charts
   - Pie charts e treemaps
   - Combinazione di tipi di grafico (dual axis)
   - *Esercizio 2*: Creare portfolio di 5 grafici diversi su dati progetto

3. **Campi Calcolati e LOD Expressions** (60 min)
   - Calcoli di base: aritmetici, logici, stringa
   - Aggregazioni: SUM, AVG, MIN, MAX, COUNT
   - Introduzione alle LOD (Level of Detail) expressions
   - FIXED, INCLUDE, EXCLUDE
   - *Esercizio 3*: Creare KPI calcolati per controllo progetto

4. **Filtri, Parametri e Formattazione** (30 min)
   - Quick filters, context filters
   - Parametri dinamici
   - Formattazione professionale: font, colori, allineamento
   - Tooltip personalizzati

**Deliverable della Sessione**: Set di report e grafici professionali per controllo progetto

---

### **Sessione 4: Dashboard Interattive Efficaci** (4 ore)

**Obiettivi di Apprendimento**:
- Progettare dashboard user-friendly e intuitive
- Implementare interattività: filtri, actions, parametri
- Ottimizzare il layout per diversi dispositivi
- Applicare principi di UX/UI alla dashboard design

**Contenuti**:

1. **Principi di Dashboard Design** (45 min)
   - Gerarchia visiva e layout
   - Densità informativa ottimale
   - Design per diversi stakeholder
   - Dashboard strategiche vs operative
   - Esempi di dashboard efficaci vs inefficaci

2. **Costruzione di Dashboard** (75 min)
   - Layout containers: horizontal, vertical, floating
   - Dimensionamento e posizionamento oggetti
   - Utilizzo di immagini, testo e web objects
   - Dashboard per desktop, tablet e mobile
   - *Esercizio 1*: Costruire struttura di dashboard multi-sheet

3. **Interattività Avanzata** (90 min)
   - Dashboard actions: filter, highlight, URL, parameter
   - Filtri globali vs filtri specifici per sheet
   - Show/hide containers dinamici
   - Navigation tra dashboard
   - Drill-down gerarchici
   - *Esercizio 2*: Implementare dashboard interattiva con drill-down

4. **Testing e Ottimizzazione** (30 min)
   - Testing della user experience
   - Performance dashboard: Analyze Performance
   - Pubblicazione e condivisione
   - *Esercizio 3*: Peer review e ottimizzazione dashboard

**Deliverable della Sessione**: Dashboard interattiva completa per monitoraggio progetto

---

### **Sessione 5: Navigazione del Modello Dati Trimestrale** (4 ore)

**Obiettivi di Apprendimento**:
- Comprendere la struttura del modello dati della trimestrale
- Navigare autonomamente tabelle, relazioni e metriche
- Identificare fonti dati per KPI specifici
- Interpretare la logica di business del modello

**Contenuti**:

1. **Architettura del Modello Dati Trimestrale** (60 min)
   - Overview della struttura: tabelle fact e dimension
   - Schema relazionale e dipendenze
   - Granularità dei dati (giornaliera, settimanale, mensile)
   - Storicizzazione e versioning trimestrale
   - Documentazione esistente del modello

2. **Esplorazione delle Tabelle Principali** (90 min)
   - Tabelle di progetto: attività, milestone, deliverable
   - Tabelle finanziarie: budget, costi effettivi, previsioni
   - Tabelle risorse: allocazione, ore lavorate
   - Tabelle KPI: indicatori di performance consolidati
   - *Esercizio 1*: Query SQL guidate sul modello trimestrale

3. **Relazioni e Join nel Modello** (60 min)
   - Chiavi primarie e chiavi esterne
   - Relazioni tra entità (1:1, 1:N, N:M)
   - Join critici per reportistica trimestrale
   - *Esercizio 2*: Costruire query complesse con multiple join

4. **Mappatura KPI su Modello Dati** (30 min)
   - Come i KPI trimestrali sono derivati dai dati
   - Logica di calcolo per metriche composite
   - Identificare fonte dati per nuovi KPI
   - *Esercizio 3*: Tracciare percorso dati per KPI specifico

**Deliverable della Sessione**: Mappa visuale del modello dati con annotazioni personali

---

### **Sessione 6: Sviluppo e Manutenzione del Modello Dati Trimestrale** (4 ore)

**Obiettivi di Apprendimento**:
- Modificare ed estendere il modello dati esistente
- Aggiungere nuove tabelle, campi e relazioni
- Implementare validazioni e data quality checks
- Documentare modifiche per la continuità operativa

**Contenuti**:

1. **Principi di Data Modeling per Reporting Ciclico** (45 min)
   - Star schema vs snowflake schema
   - Normalizzazione vs denormalizzazione
   - Slowly Changing Dimensions (SCD)
   - Design for performance in reportistica

2. **Estensione del Modello Trimestrale** (90 min)
   - Aggiunta di nuove tabelle al modello
   - Creazione di nuovi campi calcolati
   - Modifica di relazioni esistenti
   - Integrazione di nuove fonti dati
   - *Esercizio 1*: Aggiungere nuova dimensione al modello

3. **Data Quality e Validazione** (60 min)
   - Implementare constraint e validazioni
   - Identificare e gestire anomalie nei dati
   - Test di integrità referenziale
   - Monitoraggio continuo della qualità dati
   - *Esercizio 2*: Creare dashboard di data quality

4. **Documentazione e Governance** (45 min)
   - Documentare modifiche al modello
   - Versionamento e change management
   - Data dictionary e metadata
   - Handover e knowledge transfer
   - *Esercizio 3*: Documentare una modifica complessa al modello

**Deliverable della Sessione**: Proposta di estensione documentata del modello dati

---

## 🗂️ Struttura del Repository

```
/training-tableau-quarterly-model/
│
├── README.md (questo file)
│
├── /sessione-01-fondamenti-tableau-intro/
│   ├── slides/
│   │   └── sessione-01-presentazione.pdf
│   ├── esercizi/
│   │   ├── esercizio-01-sql-base.sql
│   │   ├── esercizio-02-analisi-dashboard.md
│   │   └── esercizio-03-tableau-intro.twbx
│   ├── dati/
│   │   └── dataset-esempio-pubblico.csv
│   ├── soluzioni/
│   │   └── soluzioni-esercizi-sessione-01.pdf
│   └── note-sessione.md
│
├── /sessione-02-database-connessioni/
│   ├── slides/
│   ├── esercizi/
│   ├── dati/
│   ├── soluzioni/
│   └── note-sessione.md
│
├── /sessione-03-output-base/
│   ├── slides/
│   ├── esercizi/
│   ├── dati/
│   ├── soluzioni/
│   └── note-sessione.md
│
├── /sessione-04-dashboard-interattive/
│   ├── slides/
│   ├── esercizi/
│   ├── dati/
│   ├── soluzioni/
│   └── note-sessione.md
│
├── /sessione-05-modello-trimestrale-navigazione/
│   ├── slides/
│   ├── esercizi/
│   ├── documentazione-modello/
│   │   └── schema-modello-dati.pdf
│   ├── soluzioni/
│   └── note-sessione.md
│
├── /sessione-06-modello-trimestrale-sviluppo/
│   ├── slides/
│   ├── esercizi/
│   ├── template/
│   │   └── template-documentazione-modifica.md
│   ├── soluzioni/
│   └── note-sessione.md
│
├── /risorse/
│   ├── cheat-sheet-tableau.pdf
│   ├── cheat-sheet-sql.pdf
│   ├── best-practice-data-viz.md
│   ├── glossario-termini.md
│   └── link-risorse-esterne.md
│
└── /setup/
    ├── installazione-tableau.md
    ├── configurazione-database.md
    └── requisiti-sistema.md
```

---

## 🔧 Prerequisiti e Setup

### Prerequisiti per i Partecipanti

**Conoscenze**:
- Familiarità di base con Excel e concetti di database
- Capacità di navigare file system e installare software
- *(Nota: SQL di base e Tableau introduttivo sono inclusi nella Sessione 1)*

**Hardware e Software Richiesti**:
- Computer con Windows 10/11 o macOS (minimo 8GB RAM, consigliato 16GB)
- Connessione internet stabile
- **Tableau Desktop** (versione 2023.1 o superiore) - licenza fornita
- Accesso al database del modello trimestrale (credenziali fornite prima della Sessione 2)
- Software per videoconferenza (Zoom/Teams)

### Setup Iniziale

**Prima della Sessione 1**:
1. Installare Tableau Desktop seguendo le istruzioni in `/setup/installazione-tableau.md`
2. Verificare accesso al repository GitHub del corso
3. Scaricare i materiali della Sessione 1 da `/sessione-01-fondamenti-tableau-intro/`

**Prima della Sessione 2**:
1. Configurare credenziali di accesso al database seguendo `/setup/configurazione-database.md`
2. Testare connessione database con query di test fornita

---

## 📖 Materiali del Corso

Ogni sessione include:

- **Slides**: Presentazioni con teoria e concetti
- **Esercizi**: File pronti per esercitazioni pratiche (`.twbx`, `.sql`, dataset)
- **Soluzioni**: Soluzioni dettagliate degli esercizi (disponibili dopo ogni sessione)
- **Note di Sessione**: Riepilogo, FAQ e risorse aggiuntive

### Risorse Aggiuntive

Nella cartella `/risorse/` troverete:
- Cheat sheet per riferimento rapido
- Glossario termini tecnici
- Link a documentazione ufficiale Tableau
- Best practice e linee guida

---

## 🎓 Modalità di Valutazione

Questo corso non prevede esami formali. La progressione è basata su:

- **Completamento degli esercizi pratici** (2-3 per sessione)
- **Partecipazione attiva** durante le sessioni
- **Deliverable finali** di ogni sessione

I partecipanti che completano tutti gli esercizi riceveranno:
- Attestato di partecipazione al corso (24 ore)
- Accesso permanente al repository per reference futuro

---

## 👨‍🏫 Formatore

**Samuel Perini, PhD**  
Data Scientist & Formatore | Specializzazione in Data Visualization e Modellazione Dati

- 9 anni di esperienza in data science e business intelligence
- PhD in Statistica con focus su machine learning e analisi dati complessi
- Certificato Tableau Desktop Specialist
- Esperienza comprovata in formazione tecnica e mentoring

📧 Contatto: prnsml@gmail.com  
🔗 LinkedIn: [samuelperini](https://www.linkedin.com/in/samuel-perini/)

---

## 📞 Supporto e Comunicazione

**Durante il Corso**:
- **Forum di discussione**: Utilizzare GitHub Issues per domande tecniche
- **Sessioni Q&A**: Ultimi 15 minuti di ogni sessione dedicati a domande
- **Email**: Per questioni private o logistiche

**Dopo il Corso**:
- Repository GitHub rimarrà accessibile indefinitamente
- Documentazione aggiornata periodicamente
- Community di ex-partecipanti per supporto peer-to-peer

---

## 📅 Calendar Indicativo

*(Da confermare in base alla disponibilità dei partecipanti)*

| Sessione | Argomento | Data Indicativa | Ore |
|----------|-----------|-----------------|-----|
| 1 | Fondamenti e Introduzione a Tableau | Settimana 1 | 4h |
| 2 | Connessione Database e Preparazione Dati | Settimana 2 | 4h |
| 3 | Generazione Output di Base | Settimana 3 | 4h |
| 4 | Dashboard Interattive Efficaci | Settimana 4 | 4h |
| 5 | Navigazione Modello Trimestrale | Settimana 5 | 4h |
| 6 | Sviluppo Modello Trimestrale | Settimana 6 | 4h |

---

## 📝 Note Finali

Questo corso è progettato per essere **pratico e applicabile immediatamente** al vostro lavoro quotidiano. L'enfasi è sull'autonomia operativa: al termine, sarete in grado di lavorare indipendentemente con Tableau e il modello dati trimestrale.

**Suggerimenti per massimizzare l'apprendimento**:
- Completate tutti gli esercizi pratici
- Sperimentate con Tableau tra una sessione e l'altra
- Portate domande specifiche relative al vostro lavoro
- Collaborate con i colleghi del corso
- Consultate regolarmente le risorse nel repository

---

**Benvenuti al corso! 🚀**

Per qualsiasi domanda prima dell'inizio, non esitate a contattare il formatore.