# Jira Cloud & Confluence Cloud - Stato Attuale (febbraio 2026)

Documento di riferimento per l'audit dei materiali formativi.
Ultimo aggiornamento: 2026-02-23.

---

## 1. Navigazione e interfaccia utente di Jira Cloud

### Cambiamento principale: dalla barra superiore alla sidebar laterale sinistra

Atlassian ha introdotto un nuovo sistema di navigazione a partire da **marzo 2025**, migrando
dalla barra di navigazione superiore (top bar) a una **sidebar verticale sul lato sinistro**.

| Aspetto | Prima (pre-2025) | Adesso (2025-2026) |
|---------|-------------------|---------------------|
| Navigazione principale | Barra superiore (top bar) | Sidebar sinistra verticale |
| Barra superiore | Menu, ricerca, notifiche, progetti | Solo impostazioni globali e notifiche |
| Configurazione progetto | Menu in alto | Sidebar sinistra nel contesto del progetto |
| Filtri e dashboard | Accessibili da menu superiore | Accessibili da qualsiasi punto tramite sidebar |

### Personalizzazione

- Gli utenti possono **trascinare, nascondere o mostrare** elementi nella sidebar.
- Le personalizzazioni sono **per singolo utente**, non impattano gli altri.
- Filtri e dashboard possono essere **contrassegnati con stella** (starred) per accesso rapido.

### Rollout timeline

| Data | Evento |
|------|--------|
| Marzo 2025 | Rollout iniziato per piani Standard |
| Luglio 2025 | Premium ed Enterprise |
| Post-attivazione | Utenti possono disattivare per 3-8 settimane, poi la nuova nav diventa obbligatoria |

### Impatto sull'audit

Se i materiali formativi mostrano screenshot con la barra superiore o descrivono la navigazione
come menu in alto, queste istruzioni sono **obsolete**. Tutti i riferimenti alla navigazione devono
essere aggiornati per descrivere la sidebar sinistra.

---

## 2. Terminologia: rinominazioni principali

### 2a. "Project" --> "Space" (Spazio)

| Aspetto | Dettagli |
|---------|----------|
| Vecchio termine | Project (Progetto) |
| Nuovo termine | **Space** (Spazio) |
| Inizio rollout | Settembre 2025 (Free/Standard), Ottobre 2025 (Premium/Enterprise) |
| Completamento | ~Dicembre 2025 per tutti i piani |
| Opt-out | **Non disponibile** - il cambiamento e' obbligatorio per tutti |

**Motivazione**: Atlassian ha introdotto "Atlassian Projects" come concetto separato (con timeline,
obiettivi, stakeholder), quindi "project" in Jira creava confusione. "Space" indica meglio un
contenitore di lavoro senza inizio/fine definiti.

**Nota importante su Confluence**: Confluence usa gia' il termine "space" (spazio) per i suoi
contenitori di pagine. Questa omonimia potrebbe creare confusione nei materiali formativi.

### 2b. "Issue" --> "Work Item" (Elemento di lavoro)

| Aspetto | Dettagli |
|---------|----------|
| Vecchio termine | Issue (Issue/Segnalazione) |
| Nuovo termine | **Work Item** (Elemento di lavoro) |
| Vecchio termine correlato | Issue Type (Tipo di issue) |
| Nuovo termine correlato | **Work Type** (Tipo di lavoro) |
| Inizio rollout | Free/Standard: inizio 2025; Premium/Enterprise: dopo aprile 2025 |
| Completamento | Bundled release track: luglio 2025 |

**Motivazione**: Jira nasce come bug tracker, dove "issue" aveva senso. Con l'espansione a team
non tecnici (marketing, HR, legale), "work item" risulta piu' inclusivo.

### 2c. "Team-managed" e "Company-managed" (invariati ma con contesto "space")

| Aspetto | Dettagli |
|---------|----------|
| Vecchi nomi (storici) | "Next-gen" e "Classic" |
| Nomi attuali | **Team-managed** e **Company-managed** |
| Cambiamento 2025 | Rimangono team-managed e company-managed, ma ora si riferiscono a **spaces** invece che a projects |

Questi due termini **non sono stati rinominati** nel ciclo 2025-2026.
Si dice ora "team-managed space" e "company-managed space".

### 2d. Riepilogo completo delle rinominazioni

| Vecchio termine | Nuovo termine (2025-2026) | Note |
|----------------|--------------------------|------|
| Project | **Space** | Rollout completato dic 2025 |
| Issue | **Work Item** | Rollout completato ~lug 2025 |
| Issue Type | **Work Type** | Rollout completato ~lug 2025 |
| Next-gen project | Team-managed space | Doppia rinominazione (next-gen -> team-managed gia' avvenuta in passato) |
| Classic project | Company-managed space | Idem |
| Top navigation bar | **Left sidebar** | Nuova navigazione mar-lug 2025 |

### Impatto sull'audit

Qualsiasi riferimento a "progetto" (in senso Jira), "issue", "tipo di issue" nei materiali
formativi deve essere verificato e aggiornato con la nuova terminologia. I riferimenti alla
navigazione tramite barra superiore devono essere aggiornati alla sidebar sinistra.

---

## 3. Automation Rules (Regole di automazione)

### Stato attuale

Jira Cloud Automation permette di creare regole basate su trigger, condizioni e azioni per
automatizzare i flussi di lavoro.

### Limiti per piano (aggiornati 2026)

| Piano | Esecuzioni mensili | Note |
|-------|-------------------|------|
| Free | 100/mese (totale sito) | Solo regole per singolo space |
| Standard | 1.700/mese (totale sito) | Regole globali sbloccate |
| Premium | 1.000/utente/mese (pooled) | Es: 200 utenti = 200.000 esecuzioni |
| Enterprise | **Illimitate** | Nessun limite |

### Novita' 2025-2026

| Data | Cambiamento |
|------|-------------|
| Aprile 2025 | **Validazione regole**: possibilita' di verificare errori prima di abilitare una regola |
| Aprile 2025 | **Integrazione Okta** in JSM: azioni "Create user in Okta" e "Retrieve user details from Okta" |
| Ottobre 2025 | **Smart value branch limits**: i branch smart value contano verso il limite di 5.000 associated items |
| 2025 | **Forge Automation Actions** in GA: estendere la piattaforma con azioni custom basate su Forge |
| 2025 | **Atlassian Teams** utilizzabili nativamente nelle regole di automazione |
| 2025 | **Trigger cross-prodotto Confluence->Jira**: regola che si attiva quando viene creato un work item in un dato space Jira |
| 2025 | **Rovo AI**: possibilita' di creare regole di automazione descrivendo trigger e azioni in linguaggio naturale |
| Giugno 2025 | **Deprecazione azione LaunchDarkly**: "Create feature flag in LaunchDarkly" rimossa |

### Workflow Editor

A partire dal **26 giugno 2026**, Atlassian rimuovera' il vecchio editor di workflow.
Tutti i workflow saranno modificabili solo nel nuovo workflow editor.

### Impatto sull'audit

- Verificare che i limiti di esecuzione menzionati nei materiali siano aggiornati.
- Verificare che eventuali screenshot dell'interfaccia di automazione siano attuali.
- Aggiungere menzione della validazione regole e dell'integrazione AI (Rovo) se pertinenti.

---

## 4. Dashboard Gadgets

### Lista completa dei gadget pre-installati (febbraio 2026)

Nota: la terminologia ufficiale usa ora "work item" e "space" al posto di "issue" e "project".

| # | Gadget | Descrizione |
|---|--------|-------------|
| 1 | Activity Stream | Riepilogo delle attivita' recenti |
| 2 | Assigned To Me | Work item aperti assegnati all'utente corrente |
| 3 | Average Age | Grafico a barre dell'eta' media dei work item non risolti |
| 4 | Average Time in Status | Tempo medio trascorso in ciascuno status |
| 5 | Average Number of Times in Status | Numero medio di volte in uno status |
| 6 | Bubble Chart | Visualizzazione a 4 dimensioni dei work item (*vedi nota deprecazione*) |
| 7 | Created vs Resolved | Confronto tra work item creati e risolti nel tempo |
| 8 | Days Remaining in Sprint | Giorni rimanenti nello sprint attivo |
| 9 | Filter Results | Risultati di un filtro salvato |
| 10 | Introduction | Messaggio introduttivo personalizzabile |
| 11 | Work Item Calendar | Calendario dei work item per data di scadenza |
| 12 | Work Item Statistics | Statistiche dei work item per campo specifico |
| 13 | Work Items in Progress | Work item in corso assegnati all'utente |
| 14 | Labels | Label associate a uno space (*vedi nota deprecazione*) |
| 15 | Pie Chart | Grafico a torta dei work item per statistica |
| 16 | Spaces (ex Projects) | Informazioni e filtri sugli space (*vedi nota deprecazione*) |
| 17 | Quick Links | Link ai work item dell'utente |
| 18 | Recently Created Work Items | Tasso di creazione e stato di risoluzione |
| 19 | Resolution Time | Tempo medio di risoluzione |
| 20 | Road Map | Versioni imminenti e completamento (*vedi nota deprecazione*) |
| 21 | Service Space Report | Report da service space (JSM) |
| 22 | Sprint Health | Snapshot dello stato dello sprint |
| 23 | Sprint Burndown | Lavoro rimanente nello sprint |
| 24 | Time Since Work Items | Work item per attivita' nel periodo |
| 25 | Time to First Response Chart | Ore per prima risposta (JSM) |
| 26 | Two Dimensional Filter Statistics | Tabella con due dimensioni di dati filtrati |
| 27 | Voted Work Items | Work item votati dall'utente |
| 28 | Wallboard Spacer | Spaziatura tra gadget |
| 29 | Watched Work Items | Work item sotto osservazione dell'utente |

### Gadget in fase di deprecazione (sospesi)

Cinque gadget erano previsti per la rimozione a maggio 2025, ma la rimozione e' stata **sospesa**
il 30 aprile 2025:

| Gadget | Stato | Alternativa |
|--------|-------|-------------|
| **Road Map** | Sospeso - ancora disponibile | Atlassian sta lavorando a nuove esperienze dashboard |
| **Bubble Chart** | Sospeso - ancora disponibile | **Nessuna alternativa nativa** |
| **Heat Map** | Sospeso - ancora disponibile | (non elencato nei gadget attuali, potrebbe essere gia' rimosso) |
| **Spaces (Projects)** | Sospeso - ancora disponibile | Dashboard cross-prodotto in sviluppo |
| **Labels** | Sospeso - ancora disponibile | Dashboard cross-prodotto in sviluppo |

### Impatto sull'audit

- Heat Map potrebbe non essere piu' disponibile; verificare nei materiali.
- I nomi dei gadget ora usano "Work Item" e "Space" al posto di "Issue" e "Project".
- Road Map, Bubble Chart, Spaces, Labels sono tecnicamente ancora disponibili ma a rischio.

---

## 5. JQL - Funzioni e campi

### Lista completa delle funzioni JQL built-in (febbraio 2026)

Nota: molte funzioni sono state rinominate da "issue" a "work item" e da "project" a "space".

#### Funzioni generali

| Funzione | Descrizione |
|----------|-------------|
| `currentUser()` | Utente corrente |
| `currentLogin()` | Timestamp del login corrente |
| `lastLogin()` | Timestamp dell'ultimo login |
| `membersOf("gruppo")` | Membri di un gruppo |
| `now()` | Data/ora corrente |
| `updatedBy(utente, da, a)` | Work item aggiornati da un utente |

#### Funzioni data/ora

| Funzione | Descrizione |
|----------|-------------|
| `startOfDay()` | Inizio del giorno corrente |
| `startOfWeek()` | Inizio della settimana corrente |
| `startOfMonth()` | Inizio del mese corrente |
| `startOfYear()` | Inizio dell'anno corrente |
| `endOfDay()` | Fine del giorno corrente |
| `endOfWeek()` | Fine della settimana corrente |
| `endOfMonth()` | Fine del mese corrente |
| `endOfYear()` | Fine dell'anno corrente |

Tutte accettano offset: `startOfDay("-1d")`, `startOfMonth("+2M")`, ecc.

#### Funzioni sprint

| Funzione | Descrizione |
|----------|-------------|
| `openSprints()` | Sprint attualmente aperti |
| `closedSprints()` | Sprint chiusi |
| `futureSprints()` | Sprint futuri (non ancora iniziati) |

#### Funzioni versioni

| Funzione | Descrizione |
|----------|-------------|
| `earliestUnreleasedVersion()` | Prima versione non rilasciata |
| `latestReleasedVersion()` | Ultima versione rilasciata |
| `releasedVersions()` | Tutte le versioni rilasciate |
| `unreleasedVersions()` | Tutte le versioni non rilasciate |

#### Funzioni space (ex project)

| Funzione | Descrizione | Vecchio nome |
|----------|-------------|--------------|
| `spacesLeadByUser()` | Space guidati da un utente | `projectsLeadByUser()` |
| `spacesWhereUserHasPermission()` | Space dove l'utente ha un permesso | `projectsWhereUserHasPermission()` |
| `spacesWhereUserHasRole()` | Space dove l'utente ha un ruolo | `projectsWhereUserHasRole()` |

#### Funzioni work item (ex issue)

| Funzione | Descrizione | Vecchio nome |
|----------|-------------|--------------|
| `workItemHistory()` | Cronologia del work item | `issueHistory()` |
| `workItemsWithRemoteLinksByGlobalId()` | Work item con remote link | `issuesWithRemoteLinksByGlobalId()` |
| `linkedWorkItem` | Work item collegato | `linkedIssue` |
| `linkedWorkItems()` | Work item collegati | `linkedIssues()` |
| `votedWorkItems()` | Work item votati | `votedIssues()` |
| `watchedWorkItems()` | Work item osservati | `watchedIssues()` |
| `standardWorkTypes()` | Tipi di lavoro standard | `standardIssueTypes()` |
| `subtaskWorkTypes()` | Tipi di lavoro subtask | `subtaskIssueTypes()` |

#### Funzioni specifiche per Jira Service Management

| Funzione | Descrizione |
|----------|-------------|
| `approved()` | Richieste approvate |
| `approver()` | Utente approvatore |
| `breached()` | SLA violati |
| `completed()` | SLA completati |
| `customerDetail()` | Dettagli del cliente |
| `entitlementDetail()` | Dettagli dell'entitlement |
| `entitlementProduct()` | Prodotto dell'entitlement |
| `everBreached()` | SLA mai violati storicamente |
| `myApproval()` | Approvazioni dell'utente corrente |
| `myPending()` | Approvazioni pendenti |
| `myPendingApproval()` | Approvazioni pendenti dell'utente |
| `organizationDetail()` | Dettagli organizzazione |
| `organizationMembers()` | Membri dell'organizzazione |
| `paused()` | SLA in pausa |
| `pending()` | Approvazioni pendenti |
| `pendingApprovalBy()` | Approvazioni pendenti per utente |
| `pendingBy()` | Pendenti per utente |
| `remaining()` | Tempo SLA rimanente |
| `running()` | SLA in esecuzione |
| `withinCalendarHours()` | Entro le ore di calendario |

#### Altre funzioni

| Funzione | Descrizione |
|----------|-------------|
| `cascadeOption()` | Opzione a cascata per campi select |
| `choiceOption()` | Opzione di un campo select |
| `componentsLeadByUser()` | Componenti guidati da un utente |
| `parentEpic` | Epic genitore |

### Campi JQL rinominati

| Vecchio campo | Nuovo campo | Note |
|--------------|-------------|------|
| `project` | `space` | Backward compatible: `project` funziona ancora |
| `issueKey` | `work item key` | Backward compatible |
| `issueLink` | `work item link` | Backward compatible |
| `issueLinkType` | `work item link type` | Backward compatible |
| `issueType` / `type` | `type` | Rimasto invariato nel JQL |
| `projectType` | `space type` | Backward compatible |

### Backward compatibility

**I vecchi termini JQL continuano a funzionare**. Atlassian ha confermato che non ci sono breaking
changes nelle query JQL esistenti. Le query con `project = ...` e `issue = ...` restano valide.
La documentazione ora mostra i nuovi termini, ma i vecchi sono supportati per compatibilita'.

### Impatto sull'audit

- Le funzioni JQL nei materiali formativi che usano i vecchi nomi (`issueHistory()`,
  `projectsLeadByUser()`, ecc.) funzionano ancora ma la documentazione ufficiale li ha rinominati.
- Valutare se aggiornare i materiali ai nuovi nomi o mantenere i vecchi con nota di compatibilita'.
- Nessuna nuova funzione JQL significativa aggiunta nel 2025-2026 per uso base (le novita' sono
  per JSM e Forge).

---

## 6. Confluence Cloud (2025-2026)

### Deprecazione Legacy Editor

| Fase | Periodo | Dettaglio |
|------|---------|-----------|
| Fase 2 | Gennaio - Marzo 2026 | Visualizzare/modificare una pagina legacy la converte automaticamente al cloud editor |
| Fase 3 | **Aprile 2026** | Legacy editor completamente deprecato; non e' possibile tornare indietro |

Tutte le modifiche avverranno nel **cloud editor**, che offre: Live Docs, AI, Smart Links,
automation.

### Novita' principali

| Feature | Descrizione |
|---------|-------------|
| **Live Docs** | Documenti collaborativi in tempo reale (simili a Google Docs) |
| **Whiteboards con AI** | Generazione idee, raggruppamento automatico, riassunti tramite Atlassian Intelligence |
| **Smart Create (beta)** | Brainstorming e diagrammi generati da prompt AI nelle whiteboard |
| **Create with Rovo** | Generazione contenuti (pagine, Live Docs, Whiteboards) basata su dati Jira/Confluence/Loom |
| **AI Page Catch Up** | Riepilogo AI delle modifiche a una pagina dall'ultima visita |
| **AI Work Creation** | Trasformare contenuti Confluence in work item Jira (singolo o in blocco) |
| **Miro Import** | Importazione bulk di board Miro (Premium/Enterprise) |
| **Confluence + Figma** | Widget per incorporare contenuti Confluence in Figma |

### Terminologia Confluence

I termini principali di Confluence Cloud **non sono cambiati** nel 2025-2026:

| Termine | Stato |
|---------|-------|
| Space (Spazio) | Invariato - ma ora in omonimia con Jira "Space" |
| Page (Pagina) | Invariato |
| Blog post | Invariato |
| Whiteboard | Relativamente nuovo (introdotto 2023-2024), ora potenziato con AI |
| Live Doc | Nuovo tipo di contenuto collaborativo in tempo reale |

### Cambiamenti API e sicurezza (per riferimento)

- **Rate limit basati su punti**: enforcement posticipato al 2 marzo 2026.
- **API v1 Content body**: deprecazione estesa al 5 agosto 2026.
- **SCIM API key expiration**: le chiavi esistenti (lifetime infinito) scadranno tra maggio 2026
  e maggio 2027.
- **OAuth 2.0** per Application Links come nuovo metodo di autenticazione standard.

### Impatto sull'audit

- Se i materiali formativi menzionano il "legacy editor" di Confluence, e' da aggiornare
  (sara' completamente rimosso ad aprile 2026).
- L'omonimia "Space" tra Jira e Confluence richiede attenzione nella redazione dei materiali.
- Live Docs e Whiteboards con AI sono novita' significative che potrebbero meritare menzione.

---

## 7. Riepilogo: cambiamenti ad alto impatto per l'audit

### Cambiamenti critici (richiedono aggiornamento dei materiali)

1. **Navigazione Jira**: da barra superiore a sidebar sinistra - tutti gli screenshot e le
   istruzioni di navigazione sono da aggiornare.
2. **"Project" -> "Space"**: ogni riferimento a "progetto Jira" va verificato e aggiornato.
3. **"Issue" -> "Work Item"**: ogni riferimento a "issue" va verificato e aggiornato.
4. **"Issue Type" -> "Work Type"**: terminologia correlata da aggiornare.

### Cambiamenti importanti (da valutare per l'aggiornamento)

5. **Funzioni JQL rinominate**: le vecchie funzionano ancora ma la documentazione ufficiale
   usa i nuovi nomi.
6. **Gadget dashboard a rischio**: Road Map, Bubble Chart, Heat Map, Spaces, Labels sono
   sospesi ma non ancora rimossi.
7. **Confluence Legacy Editor**: sara' rimosso ad aprile 2026.
8. **Rovo AI**: integrazione AI pervasiva in Jira e Confluence.
9. **Workflow editor vecchio**: sara' rimosso a giugno 2026.

### Cambiamenti a basso impatto (informativi)

10. **Limiti automazione**: verificare se i numeri nei materiali sono corretti.
11. **Nuove feature automation**: validazione regole, integrazione Okta, Forge actions.
12. **Confluence Live Docs e Whiteboards AI**: nuove funzionalita' da menzionare se pertinenti.

---

## Fonti

- [Jira's ever-evolving-UI (2025 Edition)](https://community.atlassian.com/forums/Jira-articles/Jira-s-ever-evolving-UI-2025-Edition/ba-p/2966105)
- [What is the new navigation in Jira?](https://support.atlassian.com/jira-software-cloud/docs/what-is-the-new-navigation-in-jira/)
- [Jira Spaces have landed!](https://community.atlassian.com/forums/Jira-articles/Jira-Spaces-have-landed/ba-p/3117620)
- [Evolving Jira terminology: Projects to Spaces](https://community.atlassian.com/forums/Jira-articles/Evolving-Jira-terminology-Projects-will-soon-be-Spaces/ba-p/3034977)
- [Work: the new collective term for items tracked in Jira](https://community.atlassian.com/forums/Jira-articles/Reimagining-work-in-Jira-to-better-represent-all-teams/ba-p/2854968)
- [It's here: Work is the new collective term](https://community.atlassian.com/forums/Jira-articles/It-s-here-Work-is-the-new-collective-term-for-all-items-you/ba-p/2954892)
- [What are team-managed and company-managed spaces?](https://support.atlassian.com/jira-software-cloud/docs/what-are-team-managed-and-company-managed-projects/)
- [Dashboard gadgets](https://support.atlassian.com/jira-cloud-administration/docs/use-dashboard-gadgets/)
- [Update: Ending support for five dashboard gadgets](https://community.atlassian.com/forums/Jira-articles/Update-We-re-ending-support-for-five-dashboard-gadgets-in-May/ba-p/2844556)
- [JQL functions (Jira Cloud)](https://support.atlassian.com/jira-software-cloud/docs/jql-functions/)
- [JQL fields (Jira Cloud)](https://support.atlassian.com/jira-software-cloud/docs/jql-fields/)
- [Automation service limits](https://support.atlassian.com/cloud-automation/docs/automation-service-limits/)
- [Create automation rules in Jira](https://support.atlassian.com/cloud-automation/docs/create-and-edit-jira-automation-rules/)
- [Is automation in Jira free? (2026 guide)](https://www.eesel.ai/blog/is-automation-in-jira-free)
- [Atlassian 2025: The Biggest Changes on Cloud](https://community.atlassian.com/forums/Jira-Cloud-Admins-articles/Atlassian-2025-The-Biggest-Changes-on-Cloud-How-Will-the-Future/ba-p/3167591)
- [Confluence Legacy Editor deprecation](https://community.atlassian.com/forums/Confluence-articles/The-Legacy-Editor-is-being-deprecated-in-Confluence-Cloud-Here-s/ba-p/3046832)
- [Confluence Cloud changelog](https://developer.atlassian.com/cloud/confluence/changelog/)
- [What's New in Confluence Cloud](https://www.atlassian.com/software/confluence/features/whats-new)
- [Atlassian Cloud changes (weekly notes)](https://confluence.atlassian.com/cloud/blog/2026/02/atlassian-cloud-changes-feb-2-to-feb-9-2026)
- [Aligning with Jira's new terminology](https://community.atlassian.com/forums/Atlassian-Analytics-articles/Aligning-with-Jira-s-new-terminology/ba-p/3048084)
