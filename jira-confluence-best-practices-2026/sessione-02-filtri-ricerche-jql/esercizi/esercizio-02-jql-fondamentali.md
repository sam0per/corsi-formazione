# Esercizio 2 — JQL fondamentali

> ⏱ Tempo stimato: 25 minuti | 👥 Individuale, poi verifica in gruppo

## Obiettivo

Scrivere query JQL corrette usando campi, operatori e ordinamento.

## Istruzioni

Vai su **Filters → Advanced issue search** e passa alla modalità JQL. Scrivi le seguenti query, verifica i risultati e annotali.

### Query da completare

**Livello 1 — Base:**

1. Trova tutte le issue del progetto di training:
   ```
   project = "___" 
   ```

2. Trova tutte le issue assegnate a te:
   ```
   assignee = ___
   ```

3. Trova tutte le issue con priorità High o Critical:
   ```
   priority IN (___, ___)
   ```

**Livello 2 — Combinazioni:**

4. Trova le issue aperte (non "Done") assegnate a te, ordinate per priorità:
   ```
   assignee = currentUser() AND status ___ "Done" ORDER BY priority ___
   ```

5. Trova tutte le issue con etichetta "onboarding" create nell'ultima settimana:
   ```
   labels = "___" AND created >= ___
   ```

6. Trova le issue di tipo Task o Bug nel tuo progetto, create questo mese:
   ```
   project = "___" AND issuetype IN (___) AND created >= startOfMonth()
   ```

**Livello 3 — Sfida per ruolo:**

7. **IT Manager**: Trova tutti i ticket IT aperti con priorità Critical, ordinati per data di creazione (più vecchi prima)
8. **Admin & Finance**: Trova tutte le issue con etichetta "fatturazione" o "acquisti" non ancora completate
9. **HR Generalist**: Trova le issue di tipo Story relative all'onboarding, create negli ultimi 30 giorni
10. **Facility Manager**: Trova i ticket di manutenzione con priorità >= Medium, assegnati a te

## Risultato atteso

- 10 query JQL scritte e funzionanti
- Comprensione degli operatori `=`, `!=`, `IN`, `>=` e dell'ordinamento

## Soluzioni

Le soluzioni verranno discusse in gruppo dopo il completamento dell'esercizio.
