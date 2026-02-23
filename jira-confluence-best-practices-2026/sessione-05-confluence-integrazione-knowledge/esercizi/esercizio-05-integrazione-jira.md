# Esercizio 2 — Integrazione Jira-Confluence

> ⏱ Tempo stimato: 25 minuti | 👥 Individuale, poi confronto

## Obiettivo

Integrare contenuti Jira nelle pagine Confluence e viceversa.

## Istruzioni

### Parte A — Da Jira a Confluence (12 min)

Nella pagina creata nell'esercizio precedente:

1. **Inserisci una macro Jira Issues**:
   - Nell'editor Confluence, digita `/jira` per inserire la macro
   - Inserisci una query JQL rilevante per il tuo ruolo (riusa i filtri della sessione 2)
   - Configura le colonne visibili: Key, Summary, Status, Priority, Assignee
   - Verifica che la tabella si aggiorni in tempo reale

2. **Inserisci un link smart a un'issue Jira**:
   - Copia l'URL di un'issue Jira
   - Incollalo nella pagina Confluence
   - Osserva come Confluence crea automaticamente una preview con status e dettagli

3. **(Opzionale) Inserisci un Jira Chart**:
   - Usa la macro Jira Chart per incorporare un grafico a torta o "creati vs risolti"
   - Collegalo a un filtro salvato

### Parte B — Da Confluence a Jira (8 min)

1. Vai su un'issue Jira creata durante il corso
2. Nella sezione **"Confluence pages"** (pannello laterale dell'issue):
   - Collega la pagina Confluence che hai appena creato
   - Verifica che il link appaia sia nell'issue che nella pagina Confluence

3. Nella **descrizione** di un'issue Jira:
   - Aggiungi un link alla tua pagina Confluence come documentazione di riferimento
   - Formato: "📖 Documentazione: [link alla pagina Confluence]"

### Parte C — Discussione (5 min)

In gruppo, discutete:
- Quali pagine Confluence sarebbero più utili da collegare ai vostri progetti Jira?
- Come potreste usare le macro Jira per creare report automatici su Confluence?
- Chi dovrebbe essere responsabile di mantenere aggiornate le pagine?

## Risultato atteso

- 1 pagina Confluence con almeno una macro Jira Issues funzionante
- 1 issue Jira collegata a una pagina Confluence
- Comprensione del flusso bidirezionale Jira ↔ Confluence
