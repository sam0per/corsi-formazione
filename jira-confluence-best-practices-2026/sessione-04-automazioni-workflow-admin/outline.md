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

### Blocco 1 — Automazioni in Jira Cloud (0:00 - 1:15)

#### 4.1 Introduzione alle automazioni (15 min)

- Cos'è Jira Automation e perché usarla
- Dove trovare le automazioni: Space settings → Automation
- Concetto chiave: **Trigger → Condizioni → Azioni** (+ **Branch** per work item collegati)
- Automazioni di spazio (space) vs automazioni globali
- Limiti di esecuzione mensili per piano Cloud:
  - Free: ~100 esecuzioni globali/mese
  - Standard: ~1.700 totali/mese (500 globali)
  - Premium: 1.000 per utente/mese (pool condiviso)
  - Enterprise: illimitato

#### 4.2 Trigger principali (15 min)

- **Work item created**: quando viene creato un elemento di lavoro (work item)
- **Work item transitioned**: quando cambia lo status
- **Field value changed**: quando cambia un campo
- **Comment added**: quando viene aggiunto un commento con specifiche parole chiave
- **Scheduled**: esecuzione programmata (cron)
- **Manual trigger**: avviato dall'utente
- Esempi Tyvak:
  1. trigger su creazione work item IT → assegnazione automatica
  2. trigger su transizione a "In Orbita" → Creazione automatica del CSV con inventario prodotti in magazzino

#### 4.3 Condizioni e azioni (20 min)

- **Condizioni**: Work item fields condition, JQL condition, User condition, Related work items condition
- **Azioni principali**:
  - Transition work item (cambia status)
  - Modifica campo (assegna, cambia data di scadenza, aggiungi etichetta)
  - Invia email / notifica Slack / Microsoft Teams
  - Crea sotto-attività
  - Aggiungi commento
  - Link work items
- **Branch rule**: applicare azioni su work item collegati
- **Rule actor**: l'utente virtuale che esegue le azioni dell'automazione. Se il rule actor non ha i permessi necessari, la regola fallisce silenziosamente. Verificare sempre i permessi del rule actor.
- **Template di automazione**: Jira offre una libreria di regole predefinite (Automation templates). Punto di partenza consigliato prima di creare regole da zero.
- **Debug e audit log**: Space settings → Automation → Audit log. Ogni esecuzione mostra trigger, condizioni valutate e azioni eseguite. Strumento fondamentale per il troubleshooting.
- **Smart values**: `{{issue.key}}`, `{{issue.summary}}`, `{{now.plusDays(7)}}`, `{{issue.assignee.displayName}}`
  - > **Nota terminologia**: nonostante la UI mostri "work item", gli smart values usano ancora la sintassi `{{issue.*}}`. La forma `{{workItem.*}}` non è supportata e causerebbe errori.
- Esempi Tyvak pratici:
  - HR: alla creazione di un work item "Nuovo dipendente" → crea automaticamente 5 sotto-task di onboarding
  - Facility: quando un reclamo passa a "Risolto" → invia email di conferma al reporter
  - IT: se un work item Critical resta aperto > 24h → notifica automatica al manager

#### 4.4 Workflow personalizzati (25 min)

- Ripasso: stati e transizioni
- Editor visuale del workflow
- Aggiungere stati personalizzati
- **Categorie di status**: ogni stato deve appartenere a una delle tre categorie obbligatorie: *To Do*, *In Progress*, *Done*. Le categorie determinano il comportamento di board, report e sprint insights.
- Configurare transizioni nel nuovo editor — tre tipi di regole:
  - **Restrict transition**: chi può eseguire la transizione (es. solo l'assegnatario, un ruolo specifico)
  - **Validate details**: cosa deve essere vero prima della transizione (es. campo obbligatorio compilato)
  - **Perform action**: cosa succede dopo la transizione (es. assegnazione automatica, aggiornamento campo)
- Transizioni globali vs transizioni specifiche
- Best practice: semplicità, chiarezza, non più di 6-7 stati
- Domanda: quali stati e transizioni sono essenziali per il vostro team? Quali sono superflui?
- Workshop: progettare il workflow ideale per ciascun ruolo
  - IT: `Nuovo → Assegnato → In lavorazione → In attesa → Risolto → Chiuso`
  - HR: `Da fare → In corso → In revisione → Completato`
  - Facility: `Segnalato → Preso in carico → In intervento → Verifica → Chiuso`
  - Finance: `Richiesto → Approvato → In elaborazione → Completato`

**☕ Pausa (10 min)**

### Esercizi Blocco 1 (1:20 - 2:10)

- [Esercizio 1: Crea le tue regole di automazione](esercizi/esercizio-0401-regole-automazione.md)
- [Esercizio 2: Workflow personalizzato](esercizi/esercizio-0402-workflow-personalizzato.md)

---

### Blocco 2 — Workflow e Amministrazione (2:10 - 2:55)

#### 4.5 Amministrazione Jira — Focus IT Manager (30 min)

- Recap: differenze tra spazi Team-managed e Company-managed
- **Gestione utenti e gruppi**:
  - *Livello organizzazione* (admin.atlassian.com): invitare utenti, creare gruppi, gestire licenze
  - *Livello spazio* (Space settings → People): assegnare ruoli di spazio ai gruppi/utenti
  - Esempio concreto di come creare un gruppo "Data Analisi", invitare i membri e assegnare ruoli specifici.
- > **Nota**: i seguenti schemi (permission, notification, work type, screen) si applicano solo a spazi **Company-managed**. Gli spazi Team-managed usano configurazioni semplificate integrate.
- **Permission schemes**: chi può fare cosa nello spazio
  - Esempio concreto per il gruppo "Data Analisi" che può creare, modificare e assegnare dashboard a specifici ruoli. Gli utenti assegnati al ruolo possono solo visualizzare le loro dashboard. Il gruppo "Data Analisi" non può modificare i work item ma solo visualizzarli.
- **Notification schemes**: chi riceve quali notifiche
  - Esempio concreto per il gruppo "Data Analisi" che riceve notifiche quando nuove richieste di aggiornamento o creazione dashboard vengono assegnate a loro.
- **Work type schemes**: quali tipi di lavoro (work type) per quale spazio
  - Esempio concreto per il gruppo "Data Analisi" che utilizza un tipo di lavoro personalizzato "Richiesta Dashboard" con campi specifici come "Scopo", "Dati richiesti", "Deadline".
- **Screen schemes**: quali campi mostrare per quale operazione
  - Esempio concreto per il gruppo "Data Analisi" che ha uno screen scheme personalizzato per la creazione di richieste di dashboard, mostrando campi specifici come "Scopo", "Dati richiesti", "Deadline" e nascondendo campi non rilevanti.
- **Configurazione spazio**: impostazioni generali, categorie, componenti
  - Esempio concreto per il gruppo "Data Analisi" che configura lo spazio con categorie come "Dashboard", "Report", "Richieste di dati" e componenti come "Sales Data", "Customer Data", "Operational Data".
- **Issue security schemes**: controllano la *visibilità* dei singoli work item (chi può vedere cosa). Complementari ai permission schemes, che controllano le *azioni*. Particolarmente rilevanti per dati sensibili o riservati.
- Best practice: principio del minimo privilegio, documentare le configurazioni

#### 4.6 Best practice di governance Jira (15 min)

- Convenzioni di nomenclatura: spazi, ruoli, etichette, componenti
- Pulizia periodica manuale vs automatizzata: work item obsoleti, filtri inutilizzati, utenti inattivi
- Template di spazio per nuovi team
- Documentare le configurazioni (collegamento con Confluence — sessione 5)
- Controllo periodico permessi e accessi (manualmente o con automazione)

**☕ Pausa (10 min)**

### Esercizi Blocco 2 (2:55 - 3:45)

- [Esercizio 3: Amministrazione e permessi](esercizi/esercizio-0403-admin-permessi.md)
- [Esercizio 4: Tipi di spazio e workflow](esercizi/esercizio-0404-tipi-space-workflow.md)

### Recap e Q&A (3:45 - 4:00)

- Riepilogo: automazione + workflow + governance = Jira efficiente
- Checklist di configurazione per nuovi spazi e team
- Anteprima sessione 5: Confluence, integrazione e knowledge transfer
