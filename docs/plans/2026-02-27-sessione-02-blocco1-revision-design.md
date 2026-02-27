# Design: Sessione 02 — Revisione Blocco 1

> Data: 2026-02-27 | Sessione: sessione-02-filtri-ricerche-jql

## Motivazione

I 4 partecipanti Tyvak conoscono già la ricerca base di Jira (ricerca globale, filtri rapidi, filtri predefiniti). La sezione 2.1 originale (15 min) sulla panoramica delle ricerche è ridondante. Si libera tempo per contenuti più avanzati e utili.

## Cambiamenti rispetto alla versione attuale

### Rimosso

- **Sezione 2.1 "Ricerca in Jira: panoramica"** (15 min) — eliminata interamente

### Aggiunto

- **Nuova sezione 2.2 "Filtri multi-condizione e scenari per ruolo"** (20 min) con:
  - Query building incrementale (composizione progressiva di condizioni)
  - Condizioni annidate: campo `parent`, operatori `WAS`/`CHANGED`, date range
  - Uno scenario reale per ciascun ruolo

### Modificato

- **Sezione 2.1** rinumerata e ridotta da 35 a 30 min: `WAS`/`CHANGED` spostati nella nuova 2.2
- **Titolo Blocco 1**: da "Ricerca base e introduzione a JQL" a "JQL: dai fondamenti ai filtri complessi"
- **Obiettivi sessione**: rimosso riferimento alla ricerca base, aggiunto "comporre query multi-condizione"
- **Esercizio Blocco 1**: aggiunto Livello 4 con query annidate (parent, WAS/CHANGED, date range)

## Struttura Blocco 1 — Nuova

```
Blocco 1 — JQL: dai fondamenti ai filtri complessi (0:00 - 1:00)

  2.1 Introduzione a JQL (30 min)
    - Cos'è JQL e perché è fondamentale
    - Anatomia: campo operatore valore
    - Campi principali: space, status, assignee, reporter, priority, type,
      created, updated, resolved, labels, component
    - Operatori di confronto: =, !=, >, <, >=, <=
    - Operatori logici (intro): AND, OR, NOT
    - Operatore IN / NOT IN
    - IS EMPTY / IS NOT EMPTY
    - Ordinamento: ORDER BY
    - 2-3 esempi semplici contestualizzati Tyvak

  2.2 Filtri multi-condizione e scenari per ruolo (20 min)

    Part 1 — Building incrementale (5 min)
      Partire da una query semplice e aggiungere condizioni:
      1. space = "IT-HELPDESK"
      2. ... AND status != Done
      3. ... AND (priority = Critical OR priority = High)
      4. ... AND assignee = currentUser() ORDER BY created ASC
      Concetto chiave: precedenza operatori, perché servono le parentesi.

    Part 2 — Condizioni annidate: gerarchia e cronologia (7 min)
      Nuovi concetti:
      - Campo parent: parent IS NOT EMPTY, parent IS EMPTY
      - Status storico: status WAS "In Review",
        status CHANGED FROM "To Do" TO "In Progress"
      - Date range: created >= startOfMonth(-1) AND created <= endOfMonth(-1)
      - Combinazione gerarchia + cronologia + date

      Demo incrementale:
        type = Task AND space = "IT-HELPDESK"
        → ... AND parent IS NOT EMPTY
        → ... AND status WAS "In Review"
        → ... AND created >= startOfMonth(-1) AND created <= endOfMonth(-1)

      Nota: JQL standard non supporta parent.status.
      Workaround: filtro salvato sui parent + cross-reference su board/dashboard.

    Part 3 — Uno scenario per ruolo (8 min)

      IT Manager — Subtask aperti con storia "In Review", ultimo mese:
        type = Task AND space = "IT-HELPDESK"
        AND parent IS NOT EMPTY AND status WAS "In Review"
        AND status != Done AND created >= -30d

      Admin & Finance — Ordini con cambio stato e scadenza:
        labels IN ("acquisti", "fatturazione")
        AND (status CHANGED FROM "In attesa approvazione" OR due <= 7d)
        AND status NOT IN ("Done", "Cancelled")

      HR Generalist — Task onboarding figli, in ritardo o revisionati:
        labels = "onboarding" AND parent IS NOT EMPTY
        AND (due < now() OR status WAS "In Review")
        AND status != Done ORDER BY due ASC

      Facility Manager — Manutenzioni con passaggio di stato questo mese:
        space = "FACILITY" AND labels = "manutenzione"
        AND status CHANGED FROM "Open" TO "In Progress" AFTER startOfMonth()
        ORDER BY priority DESC

  ☕ Pausa (10 min)

  Esercizi Blocco 1 (1:00 - 1:45)
    esercizio-02-jql-fondamentali.md — aggiornato con Livello 4
```

## Blocco 2 — Invariato

Il Blocco 2 resta come da outline corrente:
- 2.3 Funzioni JQL (25 min) — funzioni utente, temporali, testo, spazio
- 2.4 Salvataggio e gestione filtri (15 min)
- 2.5 Sottoscrizioni ai filtri (10 min)
- Esercizi Blocco 2 (esercizio-02-jql-avanzato.md)

## File impattati

1. `sessione-02-filtri-ricerche-jql/outline.md` — riscrivere Blocco 1
2. `sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-jql-fondamentali.md` — aggiungere Livello 4
3. `sessione-02-filtri-ricerche-jql/slides/` — aggiornare slide PPTX (fuori scope: manuale)

## Note per il formatore

- La sezione 2.2 Part 2 include un avviso su `parent.status`: non è un campo JQL valido. Mostrare il workaround con filtri salvati.
- Le query negli scenari per ruolo usano spazi e label specifici Tyvak. Adattare se la configurazione dell'istanza è diversa.
