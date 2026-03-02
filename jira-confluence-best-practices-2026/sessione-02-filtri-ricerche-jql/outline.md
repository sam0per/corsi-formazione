# Sessione 2 — Filtri, Ricerche e JQL

> ⏱ Durata: 4 ore | 📅 Sessione 2 di 5

## Obiettivi della sessione

Al termine di questa sessione i partecipanti saranno in grado di:

- Scrivere query JQL (Jira Query Language) per ricerche mirate
- Comporre query multi-condizione con operatori logici e raggruppamento
- Utilizzare i campi di gerarchia (`parent`) e cronologia (`WAS`, `CHANGED`) nelle query
- Salvare, condividere e gestire filtri personali e di team
- Configurare sottoscrizioni email sui filtri

---

## Programma dettagliato

### Blocco 1 — JQL: dai fondamenti ai filtri complessi (0:00 - 1:00)

#### 2.1 Introduzione a JQL (30 min)

- Cos'è JQL e perché è fondamentale
- Anatomia di una query JQL: `campo operatore valore`
- Campi principali: `space` (alias: `project`), `status`, `assignee`, `reporter`, `priority`, `type` (alias: `issuetype`), `created`, `updated`, `resolved`, `labels`, `component`
- Operatori di confronto: `=`, `!=`, `>`, `<`, `>=`, `<=`
- Operatori logici: `AND`, `OR`, `NOT`
- Operatore `IN` / `NOT IN`: `status IN ("To Do", "In Progress")`
- Operatore `IS EMPTY` / `IS NOT EMPTY`: `assignee IS EMPTY`
- Ordinamento: `ORDER BY created DESC`
- Esempi pratici contestualizzati Tyvak:
  - `space = "SERVICE-DESK-IT" AND status = "Open" ORDER BY priority DESC`
  - `assignee = currentUser() AND status != Done`
  - `labels = "onboarding" AND created >= -7d`

#### 2.2 Filtri multi-condizione e scenari per ruolo (20 min)

**Parte 1 — Building incrementale (5 min)**

Partire da una query semplice e aggiungere condizioni passo dopo passo:

1. `space = "SERVICE-DESK-IT"`
2. `space = "SERVICE-DESK-IT" AND status != Done`
3. `space = "SERVICE-DESK-IT" AND status != Done AND (priority = Highest OR priority = High)`
4. `space = "SERVICE-DESK-IT" AND status != Done AND (priority = Highest OR priority = High) AND assignee = currentUser() ORDER BY created ASC`

Concetto chiave: precedenza degli operatori (`AND` ha priorità su `OR`), perché servono le parentesi.

**Parte 2 — Condizioni annidate: gerarchia e cronologia (7 min)**

- Campo `parent`: `parent IS NOT EMPTY`, `parent IS EMPTY`
- Status storico: `status WAS "In Review"`, `status CHANGED FROM "To Do" TO "In Progress"`
- Date range: `created >= startOfMonth(-1) AND created <= endOfMonth(-1)`
- Combinazione gerarchia + cronologia + date

Demo incrementale:

1. `type = Task AND space = "SERVICE-DESK-IT"`
2. `type = Task AND space = "SERVICE-DESK-IT" AND parent IS NOT EMPTY`
3. `type = Task AND space = "SERVICE-DESK-IT" AND parent IS NOT EMPTY AND status WAS "In Review"`
4. `type = Task AND space = "SERVICE-DESK-IT" AND parent IS NOT EMPTY AND status WAS "In Review" AND created >= startOfMonth(-1) AND created <= endOfMonth(-1)`

> ℹ️ **Nota:** JQL standard non supporta `parent.status` (non è un campo valido). Workaround: creare un filtro salvato sui parent e incrociare i risultati su board o dashboard.

**Parte 3 — Uno scenario per ruolo (8 min)**

- **IT Manager** — Subtask aperti con storia "In Review", ultimo mese:
  `type = Task AND space = "SERVICE-DESK-IT" AND parent IS NOT EMPTY AND status WAS "In Review" AND status != Done AND created >= -30d`
- **Admin & Finance** — Ordini con cambio stato e scadenza imminente:
  `labels IN ("acquisti", "fatturazione") AND (status CHANGED FROM "In attesa approvazione" OR due <= 7d) AND status NOT IN ("Done", "Cancelled")`
- **HR Generalist** — Task onboarding figli, in ritardo o revisionati:
  `labels = "onboarding" AND parent IS NOT EMPTY AND (due < now() OR status WAS "In Review") AND status != Done ORDER BY due ASC`
- **Facility Manager** — Manutenzioni con passaggio di stato questo mese:
  `space = "FACILITY" AND labels = "manutenzione" AND status CHANGED FROM "Open" TO "In Progress" AFTER startOfMonth() ORDER BY priority DESC`

> ℹ️ **Nota:** `due <= 7d` include anche gli elementi scaduti (overdue). Per filtrare solo i prossimi 7 giorni usare: `due >= startOfDay() AND due <= 7d`.

**☕ Pausa (10 min)**

### Esercizi Blocco 1 (1:00 - 1:45)

- [Esercizio 1: JQL fondamentali](./esercizi/esercizio-0201-jql-fondamentali.md)

---

### Blocco 2 — JQL avanzato e gestione filtri (1:45 - 2:45)

#### 2.3 Funzioni JQL (25 min)

- Funzioni utente: `currentUser()`, `membersOf("team")`
- Funzioni temporali: `now()`, `startOfDay()`, `startOfWeek()`, `startOfMonth()`, `endOfDay()`
- Periodi relativi: `-7d`, `-1w`, `-30d` (⚠️ non esiste `-1M`: per i mesi usare `startOfMonth(-1)`)
- Funzioni di testo: `text ~ "keyword"` (ricerca full-text)
- Funzioni di spazio: `spacesLeadByUser()`, `spacesWhereUserHasRole()`
- Combinazioni avanzate:
  - `space = "FACILITY" AND created >= startOfMonth() AND priority IN (High, Highest)`
  - `assignee WAS currentUser() AND status CHANGED TO "Done" AFTER -7d`
  - `text ~ "satellite" AND space IN ("MISSIONI", "R&D")`

#### 2.4 Salvataggio e gestione filtri (15 min)

- Salvare un filtro: nome, descrizione
- Filtri personali vs filtri condivisi
- Condivisione: con utenti, gruppi, spazi (o progetti)
- Filtri come segnalibri: stella per accesso rapido
- Best practice per la denominazione dei filtri

#### 2.5 Sottoscrizioni ai filtri (10 min)

- Configurare notifiche email periodiche
- Frequenza: giornaliera, settimanale
- Casi d'uso Tyvak: report settimanale work item aperti, elementi di lavoro in scadenza
- Attenzione: non sovraccaricare la casella email

**☕ Pausa (10 min)**

### Esercizi Blocco 2 (2:45 - 3:30)

- [Esercizio 2: JQL avanzato e filtri condivisi](./esercizi/esercizio-0202-jql-avanzato.md)

### Recap e Q&A (3:30 - 4:00)

- Riepilogo: JQL è il fondamento per dashboard, automazioni e report
- Cheatsheet JQL: dove trovarlo e come usarlo
- Anteprima sessione 3: dashboard, grafici e analytics

---

## Materiali di riferimento

- [Slide sessione 2](./slides/)
- [JQL Cheatsheet](../cheatsheet/jql-cheatsheet.md)
- [Glossario Jira](../glossario.md)
