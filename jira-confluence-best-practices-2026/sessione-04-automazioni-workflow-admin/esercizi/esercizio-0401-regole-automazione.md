# Sessione 4 Blocco 1 Esercizio 1 — Crea le tue regole di automazione

> ⏱ Tempo stimato: 25 minuti

## Obiettivo

Creare almeno 2 regole di automazione utili per il proprio ruolo.

## Istruzioni

### Preparazione

Vai su **Space settings → Automation → Create rule** nello **spazio** (space) di training (oppure in un progetto dell'istanza Tyvak in cui è sicuro sperimentare).

### Regola 1

Crea una regola di **auto-assegnazione**:

- **Trigger**: Work item created
- **Condizione**: Work type = Task (o un altro tipo rilevante per il tuo ruolo)
- **Azione**: Assign work item to → Current user (o un utente specifico)
- **Nome regola**: `Auto-assegnazione [TIPO]` dove [TIPO] è il tipo di work item (es. Auto-assegnazione Bug)

Testa la regola creando un nuovo **elemento di lavoro** (work item) del tipo scelto.

### Regola 2

Crea una regola personalizzata per il tuo ruolo. Ecco alcuni esempi come ispirazione:

**🔧 IT — Escalation automatica:**
- **Trigger**: Scheduled (ogni giorno alle 9:00)
- **Condizione**: JQL `project = "IT-HELPDESK" AND priority = Critical AND status != Done AND created <= -24h`
- **Azione**: Add comment "⚠️ Attenzione: questo elemento di lavoro critico è aperto da più di 24h. Richiesta escalation."
- **Azione aggiuntiva**: Send email to IT Manager

**💼 Admin & Finance — Notifica scadenza:**
- **Trigger**: Field value changed (Due date)
- **Condizione**: Due date <= `{{now.plusDays(3)}}`
- **Azione**: Notifica (email o chat) al responsabile del work item → "Il work item {{workItem.key}} - {{workItem.summary}} scade tra 3 giorni. Verifica lo stato."
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

## Extra - Regola Branch (opionale)
Per chi vuole sperimentare di più, provate a creare una regola con un **branch**. È necessario avere una struttura di work item collegati per testarla. Ecco un esempio:
- **Trigger**: Work item transitioned → status = "In Review"
- **Branch**: For work items linked (type: "is blocked by")
- **Azione nel branch**: Aggiungi commento con il nome del reporter del work item bloccante → "@{{linkedIssue.reporter.displayName}} Il work item {{issue.key}} è in review ma è bloccato da {{linkedIssue.key}}. Verifica lo stato del blocco."
