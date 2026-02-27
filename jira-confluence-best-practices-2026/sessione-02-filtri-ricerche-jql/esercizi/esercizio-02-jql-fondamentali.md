# Esercizio 2 — JQL fondamentali

> ⏱ Tempo stimato: 25 minuti | 👥 Individuale, poi verifica in gruppo

## Obiettivo

Scrivere query JQL corrette usando campi, operatori e ordinamento.

## Istruzioni

Vai su **Filters → Advanced issue search** e passa alla modalità JQL. Scrivi le seguenti query, verifica i risultati e annotali.

> ℹ️ Il campo `project` è stato rinominato `space` in Jira Cloud 2025. `project` funziona ancora come alias. Analogamente, `issuetype` è stato rinominato `type` (`issuetype` resta valido come alias).

### Query da completare

**Livello 1 — Base:**

1. Trova tutti gli elementi di lavoro (work item) dello spazio di training:
   ```
   space = "___"
   ```

2. Trova tutti gli elementi di lavoro assegnati a te:
   ```
   assignee = ___
   ```

3. Trova tutti gli elementi di lavoro con priorità High o Critical:
   ```
   priority IN (___, ___)
   ```

**Livello 2 — Combinazioni:**

4. Trova gli elementi di lavoro aperti (non "Done") assegnati a te, ordinati per priorità:
   ```
   assignee = currentUser() AND status ___ "Done" ORDER BY priority ___
   ```

5. Trova tutti gli elementi di lavoro con etichetta "onboarding" creati nell'ultima settimana:
   ```
   labels = "___" AND created >= ___
   ```

6. Trova gli elementi di lavoro di tipo Task o Bug nel tuo spazio, creati questo mese:
   ```
   space = "___" AND type IN (___) AND created >= startOfMonth()
   ```

**Livello 3 — Sfida per ruolo:**

7. **IT Manager**: Trova tutti gli elementi di lavoro IT aperti con priorità Critical, ordinati per data di creazione (più vecchi prima)
8. **Admin & Finance**: Trova tutti gli elementi di lavoro con etichetta "fatturazione" o "acquisti" non ancora completati
9. **HR Generalist**: Trova gli elementi di lavoro di tipo Story relativi all'onboarding, creati negli ultimi 30 giorni
10. **Facility Manager**: Trova gli elementi di lavoro di manutenzione con priorità >= Medium, assegnati a te

**Livello 4 — Condizioni annidate e cronologia:**

11. Trova tutti i subtask (elementi di lavoro con un parent) del tuo spazio che non sono completati:
    ```
    space = "___" AND parent IS ___ AND status != "Done"
    ```

12. Trova gli elementi di lavoro il cui status è passato per "In Review" nell'ultimo mese:
    ```
    status ___ "In Review" AND created >= ___
    ```

13. Trova gli elementi di lavoro con priorità Critical OPPURE con scadenza entro 7 giorni, nello spazio IT, ordinati per scadenza:
    ```
    space = "IT-HELPDESK" AND (___ = Critical ___ due <= ___) AND status != Done ORDER BY ___ ASC
    ```

14. **Sfida finale**: Scrivi una query per il tuo ruolo che combini almeno 4 condizioni, includa parentesi di raggruppamento e utilizzi `WAS` o `CHANGED`. Discuti la query con il gruppo.

## Risultato atteso

- 14 query JQL scritte e funzionanti
- Comprensione degli operatori `=`, `!=`, `IN`, `>=`, `IS EMPTY`, `WAS` e dell'ordinamento
- Capacità di comporre query multi-condizione con raggruppamento tramite parentesi

## Soluzioni

Le soluzioni verranno discusse in gruppo dopo il completamento dell'esercizio.
