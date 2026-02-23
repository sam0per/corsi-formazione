# Automazioni Cheatsheet — Riferimento rapido

> Guida tascabile per le automazioni Jira Cloud

## Concetto base

```
TRIGGER (quando) → CONDIZIONE (se) → AZIONE (allora)
```

## Trigger principali

| Trigger | Si attiva quando... | Esempio d'uso |
|---------|---------------------|---------------|
| **Work item created** | Viene creato un nuovo **elemento di lavoro** (work item) | Auto-assegnazione, creazione sotto-task |
| **Work item transitioned** | Cambia lo status | Notifica al reporter, aggiorna campo |
| **Field value changed** | Cambia il valore di un campo | Priorità cambiata → notifica manager |
| **Comment added** | Viene aggiunto un commento | Notifica all'assegnatario |
| **Work item assigned** | Viene assegnato/riassegnato | Email di notifica al nuovo assegnatario |
| **Scheduled** | A intervalli programmati (cron) | Report giornaliero, pulizia settimanale |
| **Manual trigger** | Attivato manualmente dall'utente | Azioni su richiesta |
| **Work item deleted** | Viene eliminato un elemento di lavoro | Log/audit |

## Condizioni principali

| Condizione | Verifica se... | Esempio |
|-----------|----------------|---------|
| **Work item fields condition** | Un campo ha un certo valore | `Priority = Critical` |
| **JQL condition** | L'elemento di lavoro corrisponde a una query JQL | `labels = "urgente"` |
| **User condition** | L'utente ha un certo ruolo | Solo per admin |
| **Related work items condition** | Gli elementi di lavoro collegati soddisfano criteri | Tutte le sotto-task sono "Done" |
| **Advanced compare condition** | Confronto tra campi o valori | Due date < now |
| **If/else block** | Condizione con ramo alternativo | Se priorità alta → azione A, altrimenti → azione B |

## Azioni principali

| Azione | Cosa fa | Esempio |
|--------|---------|---------|
| **Transition work item** | Cambia lo status | Sposta a "In Progress" |
| **Edit work item** | Modifica un campo | Cambia priorità, aggiungi etichetta |
| **Assign work item** | Assegna l'elemento di lavoro | Assegna al team lead |
| **Add comment** | Aggiunge un commento | Messaggio automatico |
| **Send email** | Invia un'email | Notifica al reporter |
| **Create work item** | Crea un nuovo elemento di lavoro | Work item di follow-up |
| **Create sub-tasks** | Crea sotto-attività | Checklist onboarding |
| **Link work items** | Collega elementi di lavoro tra loro | Blocca/è bloccata da |
| **Send web request** | Chiama un webhook | Integrazione esterna |
| **Log action** | Registra nel log | Debug/audit |
| **Lookup work items** | Cerca elementi di lavoro con JQL | Per azioni batch |

## Smart values (variabili)

| Smart value | Restituisce | Esempio output |
|------------|-------------|----------------|
| `{{workItem.key}}` | Chiave elemento di lavoro (alias: `{{issue.key}}`) | `IT-123` |
| `{{workItem.summary}}` | Titolo elemento di lavoro (alias: `{{issue.summary}}`) | `Fix stampante` |
| `{{workItem.status.name}}` | Status attuale | `In Progress` |
| `{{workItem.priority.name}}` | Priorità | `High` |
| `{{workItem.assignee.displayName}}` | Nome assegnatario | `Marco Bianchi` |
| `{{workItem.reporter.displayName}}` | Nome reporter | `Laura Verdi` |
| `{{workItem.url}}` | URL dell'elemento di lavoro | `https://tyvak.atlassian.net/browse/IT-123` |
| `{{now}}` | Data/ora attuale | `2026-02-19T10:30:00` |
| `{{now.plusDays(7)}}` | Tra 7 giorni | `2026-02-26T10:30:00` |
| `{{now.minusDays(1)}}` | Ieri | `2026-02-18T10:30:00` |
| `{{trigger.user.displayName}}` | Chi ha attivato il trigger | `Admin Tyvak` |

> **Nota**: Gli smart value `{{issue.*}}` restano funzionanti come alias retrocompatibile. La forma canonica è `{{workItem.*}}`.

## Ricette per Tyvak

### Auto-assegnazione per componente
```
Trigger:  Work item created
Condizione: Component = "Hardware"
Azione:  Assign work item → IT Manager
```

### Checklist onboarding automatica
```
Trigger:  Work item created
Condizione: Labels contains "nuovo-dipendente"
Azione:  Create sub-tasks:
         - "Preparare postazione"
         - "Creare account email e Jira"
         - "Pianificare incontro team lead"
         - "Consegnare badge"
         - "Formazione strumenti"
```

### Escalation work item critici
```
Trigger:  Scheduled (ogni giorno ore 9:00)
Condizione: JQL → priority = Critical AND status != Done AND created <= -24h
Azione:  Add comment → "⚠️ Work item critico aperto da >24h"
Azione:  Send email → IT Manager
```

### Chiusura automatica dopo risoluzione
```
Trigger:  Scheduled (ogni settimana, lunedì ore 8:00)
Condizione: JQL → status = "Risolto" AND updated <= -7d
Azione:  Transition → "Chiuso"
Azione:  Add comment → "Chiuso automaticamente dopo 7 giorni in stato Risolto"
```

### Notifica scadenza imminente
```
Trigger:  Scheduled (ogni giorno ore 8:00)
Condizione: JQL → due <= 2d AND due >= now() AND status != Done
Azione:  Send email → Assignee
         Oggetto: "⏰ {{workItem.key}} scade tra meno di 2 giorni"
```

## Validazione regole e assistenza AI

- **Validazione regole** (aprile 2025): Jira verifica automaticamente la configurazione delle regole di automazione prima della pubblicazione, segnalando errori e potenziali conflitti.
- **Rovo AI**: l'assistente AI di Atlassian può suggerire regole di automazione basate sulle attività frequenti dello **spazio** (space) e aiutare nel debug di regole complesse.

## Debug delle automazioni

1. **Audit log**: Space settings → Automation → Audit log
2. Ogni esecuzione mostra: trigger, condizioni valutate, azioni eseguite
3. Status: ✅ Success, ⚠️ Some actions failed, ❌ Error
4. Clicca su un'esecuzione per vedere i dettagli step-by-step

## Limiti e best practice

- Verificare i **limiti mensili** del piano Cloud:
  - Free: 100 esecuzioni/mese
  - Standard: 1.700 esecuzioni/mese
  - Premium: 1.000 regole/utente/mese
  - Enterprise: illimitato
- **Testare sempre** su un singolo elemento di lavoro prima di attivare su tutto lo **spazio** (space)
- **Nominare le regole** in modo descrittivo: `[Trigger] - [Scopo] - [Target]`
- **Disabilitare** le regole non più necessarie (non eliminarle subito)
- **Evitare loop**: regola A modifica campo → trigger regola B → modifica campo → trigger regola A
- Usare **condizioni specifiche** per evitare esecuzioni involontarie
