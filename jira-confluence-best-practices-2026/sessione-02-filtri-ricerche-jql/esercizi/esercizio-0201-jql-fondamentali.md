# Sessione 2 Blocco 1 Esercizio — JQL fondamentali

> ⏱ Tempo stimato: 30 minuti | 👥 Individuale, poi verifica in gruppo

## Obiettivo

Scrivere query JQL corrette usando campi, operatori e ordinamento.

## Istruzioni

Vai su **Filters → Advanced issue search** e passa alla modalità JQL. Scrivi le seguenti query, verifica i risultati e annotali.

> ℹ️ In Jira Cloud 2025 la UI usa "Space" al posto di "Project" e "Work Type" al posto di "Issue Type". In JQL entrambe le forme sono valide: `space` e `project` sono alias, così come `type` e `issuetype`.

### Query da completare

**Livello 1 — Base:**

1. Trova tutti gli elementi di lavoro (work item) dello spazio di training o del tuo spazio di lavoro:
   <details>
   <summary>Suggerimento</summary>

   ```
   space ? "___"
   ```
   
   </details>

2. Trova tutti gli elementi di lavoro assegnati a te:
   <details>
   <summary>Suggerimento</summary>

   ```
   assignee ? ___
   ```
   
   </details>

3. Trova tutti gli elementi di lavoro con priorità High o un'altra priorità a tua scelta:
   <details>
   <summary>Suggerimento</summary>

   ```
   priority ? (___, ___)
   ```

   </details>

**Livello 2 — Combinazioni:**

4. Trova gli elementi di lavoro aperti (non "Done") assegnati a te, ordinati per priorità:
   <details>
   <summary>Suggerimento</summary>

   ```
   assignee = currentUser() AND ___ ? "Done" ORDER BY ___ ___
   ```

   </details>

5. Trova tutti gli elementi di lavoro con un'etichetta a tua scelta creati nell'ultima settimana:
   <details>
   <summary>Suggerimento</summary>

   ```
   labels ? "___" AND created ? ___
   ```

   </details>

6. Trova gli elementi di lavoro di due tipi a tua scelta, ad esempio Task o Bug, nel tuo spazio, creati questo mese:
   <details>
   <summary>Suggerimento</summary>

   ```
   space ? "___" AND type ? (___) AND created ? startOfMonth()
   ```

   </details>

**Livello 3 — Sfida per ruolo:**

7. Chiedi ad uno/a dei partecipanti di suggerirti un criterio di ricerca rilevante per il tuo ruolo e scrivi la query.

**Livello 4 — Condizioni annidate e cronologia:**

8. Trova tutti i subtask (elementi di lavoro con un parent) del tuo spazio che non sono completati:
   <details>
   <summary>Suggerimento</summary>

    ```
    space ? "___" AND parent ? ___ ? status ? "Done"
    ```

   </details>

9. Trova gli elementi di lavoro il cui status è passato per "In Review" nell'ultimo mese:
   <details>
   <summary>Suggerimento</summary>

    ```
    status ___ "In Review" AND created >= ___
    ```
   </details>

10. Trova gli elementi di lavoro con priorità Highest OPPURE con scadenza entro 7 giorni, in uno spazio a tua scelta, ordinati per scadenza:
      <details>
      <summary>Suggerimento</summary>

    ```
    space ? "___" AND (___ ? Highest ___ due ? ___) AND status ? Done ORDER BY ___ ASC
    ```

      </details>

11. **Sfida finale**: Modifica la query richiesta dal tuo/a collega in modo che ci siano almeno 4 condizioni, includa parentesi di raggruppamento e utilizzi `WAS` o `CHANGED`. Discuti la query con il collega che ti ha fornito i criteri.

## Risultato atteso

- 11 query JQL scritte e funzionanti
- Comprensione degli operatori `=`, `!=`, `IN`, `>=`, `IS EMPTY`, `WAS` e dell'ordinamento
- Capacità di comporre query multi-condizione con raggruppamento tramite parentesi

## Soluzioni

Le soluzioni verranno discusse in gruppo dopo il completamento dell'esercizio.
