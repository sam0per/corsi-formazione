# Sessione 4 — Automazioni, Workflow e Amministrazione

> ⏱ Durata: 4 ore | 📅 Sessione 4 di 5

## Obiettivi della sessione

Al termine di questa sessione i partecipanti saranno in grado di:

- Creare regole di automazione in Jira Cloud
- Progettare e implementare workflow personalizzati
- Gestire permessi, schemi e configurazioni dello **spazio** (space) (focus IT Manager)
- Applicare best practice di amministrazione Jira

---

## Programma dettagliato

### Blocco 1 — Automazioni in Jira Cloud (0:00 - 1:00)

#### 4.1 Introduzione alle automazioni (15 min)

- Cos'è Jira Automation e perché usarla
- Concetto chiave: **Trigger → Condizioni → Azioni**
- Automazioni di spazio (space) vs automazioni globali
- Limiti del piano Cloud (numero di esecuzioni mensili)
- Dove trovare le automazioni: Space settings → Automation

#### 4.2 Trigger principali (15 min)

- **Work item created**: quando viene creato un elemento di lavoro (work item)
- **Work item transitioned**: quando cambia lo status
- **Field value changed**: quando cambia un campo
- **Comment added**: quando viene aggiunto un commento
- **Scheduled**: esecuzione programmata (cron)
- **Manual trigger**: avviato dall'utente
- Esempio Tyvak: trigger su creazione work item IT → assegnazione automatica

#### 4.3 Condizioni e azioni (20 min)

- **Condizioni**: Work item fields condition, JQL condition, User condition, Related work items condition
- **Azioni principali**:
  - Transition work item (cambia status)
  - Modifica campo (assegna, cambia priorità, aggiungi etichetta)
  - Invia email / notifica Slack
  - Crea sotto-attività
  - Aggiungi commento
  - Link work items
- **Branch rule**: applicare azioni su work item collegati
- **Smart values**: `{{workItem.key}}`, `{{workItem.summary}}`, `{{now.plusDays(7)}}`, `{{workItem.assignee.displayName}}`
- Esempi Tyvak pratici:
  - HR: alla creazione di un work item "Nuovo dipendente" → crea automaticamente 5 sotto-task di onboarding
  - Facility: quando un reclamo passa a "Risolto" → invia email di conferma al reporter
  - IT: se un work item Critical resta aperto > 24h → notifica automatica al manager

**☕ Pausa (10 min)**

### Esercizi Blocco 1 (1:00 - 1:45)

- [Esercizio 1: Crea le tue regole di automazione](esercizi/esercizio-04-regole-automazione.md)
- [Esercizio 2: Workflow personalizzato](esercizi/esercizio-04-workflow-personalizzato.md)

---

### Blocco 2 — Workflow e Amministrazione (1:45 - 2:45)

#### 4.4 Workflow personalizzati (25 min)

- Ripasso: stati e transizioni
- Editor visuale del workflow
- Aggiungere stati personalizzati
- Configurare transizioni: regole (rules) nel nuovo editor
- Transizioni globali vs transizioni specifiche
- Best practice: semplicità, chiarezza, non più di 6-7 stati
- Workshop: progettare il workflow ideale per ciascun ruolo
  - IT: `Nuovo → Assegnato → In lavorazione → In attesa → Risolto → Chiuso`
  - HR: `Da fare → In corso → In revisione → Completato`
  - Facility: `Segnalato → Preso in carico → In intervento → Verifica → Chiuso`
  - Finance: `Richiesto → Approvato → In elaborazione → Completato`

#### 4.5 Amministrazione Jira — Focus IT Manager (20 min)

- **Gestione utenti e gruppi**: invitare utenti, creare gruppi, assegnare ruoli
- **Permission schemes**: chi può fare cosa nello spazio
- **Notification schemes**: chi riceve quali notifiche
- **Work type schemes**: quali tipi di lavoro (work type) per quale spazio
- **Screen schemes**: quali campi mostrare per quale operazione
- **Configurazione spazio**: impostazioni generali, categorie, componenti
- Best practice: principio del minimo privilegio, documentare le configurazioni

#### 4.6 Best practice di governance Jira (15 min)

- Convenzioni di nomenclatura: spazi, etichette, componenti
- Pulizia periodica: work item obsoleti, filtri inutilizzati, utenti inattivi
- Template di spazio per nuovi team
- Documentare le configurazioni (collegamento con Confluence — sessione 5)
- Controllo periodico permessi e accessi

**☕ Pausa (10 min)**

### Esercizi Blocco 2 (2:45 - 3:30)

- [Esercizio 3: Amministrazione e permessi](esercizi/esercizio-04-admin-permessi.md)
- [Esercizio 4: Tipi di spazio e workflow](esercizi/esercizio-04-tipi-space-workflow.md)

### Recap e Q&A (3:30 - 4:00)

- Riepilogo: automazione + workflow + governance = Jira efficiente
- Checklist di configurazione per nuovi spazi
- Anteprima sessione 5: Confluence, integrazione e knowledge transfer

---

## Materiali di riferimento

- [Slide sessione 4](slides/)
- [Automazioni Cheatsheet](../cheatsheet/automazioni-cheatsheet.md)
- [JQL Cheatsheet](../cheatsheet/jql-cheatsheet.md)
