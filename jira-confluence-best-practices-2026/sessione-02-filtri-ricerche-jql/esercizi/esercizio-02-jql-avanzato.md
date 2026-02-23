# Esercizio 3 — JQL avanzato e filtri condivisi

> ⏱ Tempo stimato: 25 minuti | 👥 Individuale + condivisione

## Obiettivo

Utilizzare funzioni JQL avanzate, salvare filtri e configurare sottoscrizioni.

## Istruzioni

### Parte A — Query avanzate (10 min)

Scrivi le seguenti query usando funzioni JQL avanzate:

1. **Elementi di lavoro (work item) modificati oggi**:
   ```
   updated >= startOfDay()
   ```

2. **Elementi di lavoro il cui status è cambiato nell'ultima settimana**:
   ```
   status CHANGED AFTER -1w
   ```

3. **Ricerca full-text**: trova elementi di lavoro che contengono la parola "satellite" nella descrizione o nel titolo:
   ```
   text ~ "satellite"
   ```

4. **Elementi di lavoro creati da te ma assegnati ad altri**:
   ```
   reporter = currentUser() AND assignee != currentUser()
   ```

5. **Query personalizzata per il tuo ruolo**: scrivi una query utile per il tuo lavoro quotidiano (discussione di gruppo)

### Parte B — Salva e condividi filtri (10 min)

1. Prendi la query più utile che hai scritto e **salvala come filtro**:
   - Clicca "Save as" nella ricerca avanzata
   - Dai un nome descrittivo seguendo la convenzione: `[Ruolo] - Descrizione` (es. `[IT] - Work item critici aperti`)
   - Aggiungi una descrizione
2. **Condividi il filtro** con il gruppo di training:
   - Dettagli filtro → Modifica permessi → Aggiungi gruppo o spazio (space)
3. **Aggiungi il filtro ai preferiti** (stella)

### Parte C — Sottoscrizione (5 min)

1. Sul filtro appena creato, configura una **sottoscrizione email**:
   - Clicca su "Sottoscrizioni" nelle opzioni del filtro
   - Imposta frequenza: giornaliera o settimanale
   - Seleziona i destinatari

## Risultato atteso

- 5 query JQL avanzate funzionanti
- 1 filtro salvato, condiviso e con sottoscrizione attiva
- Comprensione del valore dei filtri condivisi per il team

## Domande di riflessione

- Quali filtri sarebbero utili da condividere con tutto il team?
- Con quale frequenza vorresti ricevere aggiornamenti via email?
