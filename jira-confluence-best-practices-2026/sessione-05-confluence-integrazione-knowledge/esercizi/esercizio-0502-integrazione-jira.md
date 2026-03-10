# Sessione 5 Blocco 2 Esercizio 2 — Integrazione Jira-Confluence

> ⏱ Tempo stimato: 25 minuti

## Obiettivo

Integrare contenuti Jira nelle pagine Confluence e viceversa.

## Istruzioni

### Parte A — Da Jira a Confluence

Nella pagina creata nell'esercizio precedente:

1. **Inserisci una macro Jira Work Items**:
   - Nell'editor Confluence, digita `/jira` per inserire la macro
   - Inserisci una query JQL rilevante per il tuo ruolo (riusa i filtri della sessione 2)
   - Configura le colonne visibili: Key, Summary, Status, Priority, Assignee
   - Verifica che la tabella si aggiorni in tempo reale

2. **Inserisci un link smart a un elemento di lavoro (work item) Jira**:
   - Copia l'URL di un elemento di lavoro Jira
   - Incollalo nella pagina Confluence
   - Osserva come Confluence crea automaticamente una preview con status e dettagli

3. **(Opzionale) Inserisci un Jira Chart**:
   - Usa la macro Jira Chart per incorporare un grafico a torta o "creati vs risolti"
   - Collegalo a un filtro salvato

### Parte B — Da Confluence a Jira

1. Vai su un elemento di lavoro Jira creato durante il corso
2. Nella sezione **"Confluence pages"** (pannello laterale del work item):
   - Collega la pagina Confluence che hai appena creato
   - Verifica che il link appaia sia nell'elemento di lavoro che nella pagina Confluence

3. Nella **descrizione** di un elemento di lavoro Jira:
   - Aggiungi un link alla tua pagina Confluence come documentazione di riferimento
   - Formato: "📖 Documentazione: [link alla pagina Confluence]"

### Parte C — Runbook e best practice

1. **Crea una pagina runbook** nel tuo spazio Confluence, per un processo ricorrente del tuo ruolo:
   - Titolo: "Runbook — [nome processo]" (es. "Runbook — Reset password utente", "Runbook — Richiesta ferie")
   - Contenuto minimo: 3-5 step operativi numerati
   - Inserisci un link al workflow o al progetto Jira corrispondente
   - Aggiungi l'etichetta `runbook`

2. **Discussione** (5 min): chi dovrebbe essere responsabile di mantenere aggiornate le pagine Confluence collegate a Jira?

## Risultato atteso

- 1 pagina Confluence con almeno una macro Jira Work Items funzionante
- 1 elemento di lavoro Jira collegato a una pagina Confluence
- 1 pagina runbook con link al workflow Jira
- Comprensione del flusso bidirezionale Jira ↔ Confluence
