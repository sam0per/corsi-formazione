# Esercizio 1 — Crea le tue regole di automazione

> ⏱ Tempo stimato: 25 minuti | 👥 Individuale, poi condivisione

## Obiettivo

Creare almeno 2 regole di automazione utili per il proprio ruolo.

## Istruzioni

### Preparazione (2 min)

Vai su **Space settings → Automation → Create rule** nello **spazio** (space) di training.

### Regola 1 — Comune a tutti (10 min)

Crea una regola di **auto-assegnazione**:

- **Trigger**: Work item created
- **Condizione**: Work type = Task
- **Azione**: Assign work item to → Current user (o un utente specifico)
- **Nome regola**: `Auto-assegnazione task`

Testa la regola creando un nuovo **elemento di lavoro** (work item) di tipo Task.

### Regola 2 — Specifica per ruolo (13 min)

Crea una regola personalizzata per il tuo ruolo:

**🔧 IT Manager — Escalation automatica:**
- **Trigger**: Scheduled (ogni giorno alle 9:00)
- **Condizione**: JQL → `space = "IT-HELPDESK" AND priority = Critical AND status != Done AND created <= -24h`
- **Azione**: Add comment → "⚠️ Attenzione: questo elemento di lavoro critico è aperto da più di 24h. Richiesta escalation."
- **Azione aggiuntiva**: Send email → IT Manager

**💼 Admin & Finance — Notifica scadenza:**
- **Trigger**: Field value changed (Due date)
- **Condizione**: Due date <= `{{now.plusDays(3)}}`
- **Azione**: Add comment → "📅 Questa attività scade tra 3 giorni o meno."
- **Azione**: Transition work item → "Urgente" (se lo status esiste)

**👥 HR — Creazione checklist onboarding:**
- **Trigger**: Work item created
- **Condizione**: Labels contains "nuovo-dipendente"
- **Azione**: Create sub-tasks:
  1. "Preparare postazione di lavoro"
  2. "Creare account email e Jira"
  3. "Pianificare incontro con team lead"
  4. "Consegnare badge e materiale"
  5. "Sessione formativa strumenti aziendali"

**🏢 Facility — Conferma risoluzione:**
- **Trigger**: Work item transitioned → status = "Risolto"
- **Condizione**: Work type = Task AND labels contains "reclamo"
- **Azione**: Send email to reporter → "Il tuo reclamo {{workItem.key}} - {{workItem.summary}} è stato risolto. Ti preghiamo di verificare e confermare."

> ℹ️ Lo smart value `{{issue.key}}` funziona ancora come alias, ma `{{workItem.key}}` è il nome canonico.

## Risultato atteso

- 2 regole di automazione attive e funzionanti
- Comprensione del pattern Trigger → Condizione → Azione
- Test eseguito con successo

## Consiglio

Usa il **log di esecuzione** dell'automazione (Audit log) per verificare che la regola funzioni correttamente e per debuggare eventuali errori.
