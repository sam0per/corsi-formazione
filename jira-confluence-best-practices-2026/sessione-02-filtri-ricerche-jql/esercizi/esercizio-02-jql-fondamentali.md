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

## Risultato atteso

- 10 query JQL scritte e funzionanti
- Comprensione degli operatori `=`, `!=`, `IN`, `>=` e dell'ordinamento

## Soluzioni

Le soluzioni verranno discusse in gruppo dopo il completamento dell'esercizio.
