# JQL Cheatsheet — Riferimento rapido

> Jira Query Language — Guida tascabile per Tyvak International

## Struttura base

```
campo OPERATORE valore [AND/OR campo OPERATORE valore] [ORDER BY campo ASC/DESC]
```

## Campi principali

| Campo | Descrizione | Esempio |
|-------|-------------|---------|
| `project` | Progetto | `project = "IT-HELPDESK"` |
| `issuetype` | Tipo issue | `issuetype = Bug` |
| `status` | Status attuale | `status = "In Progress"` |
| `assignee` | Assegnatario | `assignee = currentUser()` |
| `reporter` | Creatore | `reporter = "mario.rossi"` |
| `priority` | Priorità | `priority = Critical` |
| `labels` | Etichette | `labels = "onboarding"` |
| `component` | Componente | `component = "Hardware"` |
| `created` | Data creazione | `created >= -7d` |
| `updated` | Data ultimo aggiornamento | `updated >= startOfDay()` |
| `resolved` | Data risoluzione | `resolved >= startOfMonth()` |
| `due` | Data scadenza | `due <= endOfWeek()` |
| `text` | Ricerca full-text | `text ~ "satellite"` |
| `summary` | Solo nel titolo | `summary ~ "manutenzione"` |
| `description` | Solo nella descrizione | `description ~ "urgente"` |

## Operatori

| Operatore | Significato | Esempio |
|-----------|-------------|---------|
| `=` | Uguale a | `status = "Done"` |
| `!=` | Diverso da | `status != "Done"` |
| `>` `<` `>=` `<=` | Confronto | `priority >= High` |
| `IN` | In una lista | `status IN ("To Do", "In Progress")` |
| `NOT IN` | Non in una lista | `priority NOT IN (Low, Lowest)` |
| `~` | Contiene (testo) | `summary ~ "ordine"` |
| `!~` | Non contiene | `summary !~ "test"` |
| `IS` | È vuoto | `assignee IS EMPTY` |
| `IS NOT` | Non è vuoto | `due IS NOT EMPTY` |
| `WAS` | Era (storico) | `status WAS "In Progress"` |
| `CHANGED` | È cambiato | `status CHANGED TO "Done"` |

## Operatori logici

| Operatore | Uso |
|-----------|-----|
| `AND` | Entrambe le condizioni vere |
| `OR` | Almeno una condizione vera |
| `NOT` | Negazione |
| `( )` | Raggruppamento |

Esempio: `project = "IT" AND (priority = Critical OR priority = High)`

## Funzioni temporali

| Funzione | Significato |
|----------|-------------|
| `now()` | Adesso |
| `currentUser()` | Utente corrente |
| `startOfDay()` | Inizio di oggi |
| `endOfDay()` | Fine di oggi |
| `startOfWeek()` | Inizio settimana corrente |
| `endOfWeek()` | Fine settimana corrente |
| `startOfMonth()` | Inizio mese corrente |
| `endOfMonth()` | Fine mese corrente |
| `startOfYear()` | Inizio anno corrente |

## Periodi relativi

| Periodo | Significato |
|---------|-------------|
| `-1d` | 1 giorno fa |
| `-7d` | 7 giorni fa |
| `-1w` | 1 settimana fa |
| `-30d` | 30 giorni fa |
| `-1M` | 1 mese fa |
| `-3M` | 3 mesi fa |

## Ordinamento

```
ORDER BY created DESC          -- più recenti prima
ORDER BY priority ASC          -- priorità crescente
ORDER BY updated DESC, priority ASC   -- combinato
```

## Query utili per Tyvak

### Per tutti
```sql
-- Le mie issue aperte
assignee = currentUser() AND status != Done ORDER BY priority DESC

-- Issue create questa settimana
project = "PROGETTO" AND created >= startOfWeek()

-- Issue in scadenza entro 3 giorni
due <= 3d AND due >= now() AND status != Done

-- Issue aggiornate oggi
updated >= startOfDay() AND project = "PROGETTO"
```

### IT Manager
```sql
-- Ticket critici aperti da più di 24h
project = "IT-HELPDESK" AND priority = Critical AND status != Done AND created <= -24h

-- Ticket per tipo di problema
project = "IT-HELPDESK" AND component = "Hardware" AND status != Done

-- Volume ticket ultima settimana
project = "IT-HELPDESK" AND created >= -7d
```

### Administration & Finance
```sql
-- Ordini in attesa di approvazione
labels = "acquisti" AND status = "In attesa approvazione"

-- Fatture in scadenza
labels = "fatturazione" AND due <= 7d AND status != Done

-- Issue completate questo mese
labels IN ("acquisti", "fatturazione") AND resolved >= startOfMonth()
```

### HR Generalist
```sql
-- Onboarding attivi
labels = "onboarding" AND status != Done ORDER BY created ASC

-- Task onboarding in ritardo
labels = "onboarding" AND due < now() AND status != Done

-- Nuovi dipendenti ultimo trimestre
labels = "nuovo-dipendente" AND created >= -90d
```

### Facility Manager
```sql
-- Reclami aperti per priorità
labels = "reclami" AND status != Done ORDER BY priority DESC

-- Manutenzioni programmate questo mese
labels = "manutenzione" AND due >= startOfMonth() AND due <= endOfMonth()

-- Ticket facility risolti ultima settimana
project = "FACILITY" AND resolved >= -7d
```

## Suggerimenti

- Usa l'autocompletamento nell'editor JQL (Jira suggerisce campi e valori)
- I nomi dei campi con spazi vanno tra virgolette: `"Custom Field Name"`
- I valori con spazi vanno tra virgolette: `status = "In Progress"`
- `currentUser()` è tuo amico: rende le query dinamiche e riutilizzabili
- Salva le query utili come filtri per riutilizzarle in dashboard e sottoscrizioni
