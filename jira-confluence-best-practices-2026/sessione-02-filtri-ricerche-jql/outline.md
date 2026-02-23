# Sessione 2 — Filtri, Ricerche e JQL

> ⏱ Durata: 4 ore | 📅 Sessione 2 di 5

## Obiettivi della sessione

Al termine di questa sessione i partecipanti saranno in grado di:

- Utilizzare la ricerca base e i filtri rapidi di Jira
- Scrivere query JQL (Jira Query Language) per ricerche avanzate
- Salvare, condividere e gestire filtri personali e di team
- Configurare sottoscrizioni email sui filtri

---

## Programma dettagliato

### Blocco 1 — Ricerca base e introduzione a JQL (0:00 - 1:00)

#### 2.1 Ricerca in Jira: panoramica (15 min)

- Ricerca globale vs ricerca nel progetto
- Filtri rapidi sulla board (Quick Filters)
- Filtri predefiniti: "Le mie issue aperte", "Segnalate di recente"
- La vista "Filtri" nel menu laterale

#### 2.2 Introduzione a JQL (35 min)

- Cos'è JQL e perché è fondamentale
- Anatomia di una query JQL: `campo operatore valore`
- Campi principali: `project`, `status`, `assignee`, `reporter`, `priority`, `issuetype`, `created`, `updated`, `resolved`, `labels`, `component`
- Operatori di confronto: `=`, `!=`, `>`, `<`, `>=`, `<=`
- Operatori logici: `AND`, `OR`, `NOT`
- Operatore `IN`: `status IN ("To Do", "In Progress")`
- Operatore `WAS` / `CHANGED`: per la cronologia degli stati
- Ordinamento: `ORDER BY created DESC`
- Esempi pratici contestualizzati Tyvak:
  - `project = "IT-HELPDESK" AND status = "Open" ORDER BY priority DESC`
  - `assignee = currentUser() AND status != Done`
  - `labels = "onboarding" AND created >= -7d`

**☕ Pausa (10 min)**

### Esercizi Blocco 1 (1:00 - 1:45)

- [Esercizio 1: JQL fondamentali](esercizi/esercizio-02-jql-fondamentali.md)

---

### Blocco 2 — JQL avanzato e gestione filtri (1:45 - 2:45)

#### 2.3 Funzioni JQL (25 min)

- Funzioni utente: `currentUser()`, `membersOf("team")`
- Funzioni temporali: `now()`, `startOfDay()`, `startOfWeek()`, `startOfMonth()`, `endOfDay()`
- Periodi relativi: `-7d`, `-1w`, `-30d`, `-1M`
- Funzioni di testo: `text ~ "keyword"` (ricerca full-text)
- Funzioni di progetto: `projectsLeadByUser()`, `projectsWhereUserHasRole()`
- Combinazioni avanzate:
  - `project = "FACILITY" AND created >= startOfMonth() AND priority IN (High, Critical)`
  - `assignee WAS currentUser() AND status CHANGED TO "Done" AFTER -7d`
  - `text ~ "satellite" AND project IN ("MISSIONI", "R&D")`

#### 2.4 Salvataggio e gestione filtri (15 min)

- Salvare un filtro: nome, descrizione
- Filtri personali vs filtri condivisi
- Condivisione: con utenti, gruppi, progetti
- Filtri come segnalibri: stella per accesso rapido
- Best practice per la denominazione dei filtri

#### 2.5 Sottoscrizioni ai filtri (10 min)

- Configurare notifiche email periodiche
- Frequenza: giornaliera, settimanale
- Casi d'uso Tyvak: report settimanale ticket aperti, issue in scadenza
- Attenzione: non sovraccaricare la casella email

**☕ Pausa (10 min)**

### Esercizi Blocco 2 (2:45 - 3:30)

- [Esercizio 2: JQL avanzato e filtri condivisi](esercizi/esercizio-02-jql-avanzato.md)

### Recap e Q&A (3:30 - 4:00)

- Riepilogo: JQL è il fondamento per dashboard, automazioni e report
- Cheatsheet JQL: dove trovarlo e come usarlo
- Anteprima sessione 3: dashboard, grafici e analytics

---

## Materiali di riferimento

- [Slide sessione 2](slides/)
- [JQL Cheatsheet](../risorse/jql-cheatsheet.md)
- [Glossario Jira](../risorse/glossario.md)
