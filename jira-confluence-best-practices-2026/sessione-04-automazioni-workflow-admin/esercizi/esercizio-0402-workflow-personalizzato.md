# # Sessione 4 Blocco 1 Esercizio 2 — Workflow personalizzato

> ⏱ Tempo stimato: 25 minuti

> ⚠️ Il vecchio editor di workflow sarà rimosso a giugno 2026. Questo esercizio usa il nuovo editor.

## Obiettivo

Progettare e implementare un workflow personalizzato per un caso d'uso reale.

## Istruzioni

### Parte A — Progettazione su carta o digitale (12 min)

Prima di toccare Jira, disegnate il workflow su carta o digitale (Es. Miro, Lucidchart, draw.io):

1. Scegliete uno dei seguenti scenari (o create il vostro):
   - **Elemento di lavoro IT Helpdesk**: dalla segnalazione alla risoluzione
   - **Ordine forniture**: dalla richiesta all'approvazione e consegna
   - **Processo onboarding**: dal primo giorno al completamento
   - **Reclamo facility**: dalla segnalazione alla verifica

2. Definite:
   - Quali **stati** servono? (massimo 6-7)
   - Quali **transizioni** sono permesse? (non tutte le combinazioni hanno senso)
   - Ci sono **regole** (rules) nelle transizioni? (es. solo il manager può approvare, assegnazione automatica)

Formato suggerito:
```
[Stato A] --transizione--> [Stato B] --transizione--> [Stato C]
                                  |
                                  +--rifiuto--> [Stato A]
```

### Parte B — Implementazione in Jira (13 min)

> ⚠️ Questo esercizio richiede permessi di amministratore di **spazio** (space). Raccomandazione: usate l'istanza training in cui avete pieno accesso.

1. Andate su **Space settings → Workflows**
2. Copiate un workflow esistente (non modificare l'originale). Se non c'è un workflow adatto, create un nuovo workflow da zero.
3. Nell'editor visuale:
   - Aggiungete gli stati progettati durante la Parte A
   - Create le transizioni
   - Per almeno una transizione, aggiungete una **regola** (rule) (es. "Only assignee")
4. Pubblicate il workflow (se in ambiente di test)

## Risultato atteso

- 1 diagramma workflow su carta con stati e transizioni chiari
- 1 workflow implementato (o in bozza) nell'editor di Jira
- Comprensione delle implicazioni di ogni scelta di design

## Domande di riflessione

- Il workflow è abbastanza semplice da essere compreso da un nuovo utente?
- Ci sono colli di bottiglia prevedibili (stati dove gli **elementi di lavoro** si accumulano)?
- Come potreste monitorare l'efficacia del workflow con una dashboard?
