# Audit — Sessione 03: Dashboard, Grafici e Analytics

> Data audit: 2026-03-04
> Validato contro: documentazione ufficiale Atlassian (Jira Cloud, marzo 2026)
> Stato: **da correggere** — 6 errori di accuratezza, 13 gap di completezza, 5 problemi esercizi

---

## Riepilogo

Su ~30 affermazioni validate, 23 sono accurate, 5 parzialmente accurate, 1 fattualmente errata.
Il materiale è di buona qualità complessiva ma richiede correzioni puntuali.

---

## 1. ERRORI DI ACCURATEZZA (must-fix)

### 1.1 Average Age — descrizione ERRATA

- **File**: `outline.md`, riga 43
- **Testo attuale**: `Media tempo in status (Average Age): tempo medio di permanenza`
- **Problema**: Average Age misura l'**età media (in giorni) dei work item non risolti** dalla
  data di creazione, NON il tempo medio in uno status. Sono metriche completamente diverse.
- **Correzione**: Cambiare in `**Media dell'età** (Average Age): età media (in giorni) dei work item non risolti`
- **Fonte**: [How is the Average Age report calculated?](https://support.atlassian.com/jira/kb/how-is-the-jira-average-age-report-calculated/)

### 1.2 Heat Map — stato deprecazione IMPRECISO

- **File**: `outline.md`, riga 44
- **Testo attuale**: `⚠️ gadget in fase di rimozione, potrebbe non essere disponibile`
- **Problema**: Atlassian ha **sospeso la rimozione** il 30 aprile 2025. Il gadget è ancora
  disponibile ma non più mantenuto attivamente. La rimozione era prevista per 5 gadget
  (Heat Map, Road Map, Bubble Chart, Projects/Spaces, Labels).
- **Correzione**: Cambiare in `⚠️ Atlassian ha annunciato la rimozione di questo gadget, ma la
  rimozione è stata sospesa (aprile 2025). Attualmente ancora disponibile, ma non più mantenuto
  attivamente e potrebbe essere rimosso in futuro.`
- **Fonte**: [Update: Ending support for five dashboard gadgets](https://community.atlassian.com/forums/Jira-articles/Update-We-re-ending-support-for-five-dashboard-gadgets-in-May/ba-p/2844556)

### 1.3 Control Chart — descrizione INCOMPLETA

- **File**: `outline.md`, riga 65
- **Testo attuale**: `Control Chart: report a livello di board, tempo di ciclo dei work item`
- **Problema**: Il Control Chart misura sia il **cycle time** che il **lead time**, a seconda
  della configurazione degli status selezionati. Descrivere solo il cycle time è incompleto.
- **Correzione**: Cambiare in `**Control Chart**: report a livello di board, tempo di ciclo
  (cycle time) e lead time dei work item`
- **Fonte**: [View and understand the control chart](https://support.atlassian.com/jira-software-cloud/docs/view-and-understand-the-control-chart/)

### 1.4 Layout dashboard — sequenza IMPRECISA

- **File**: `outline.md`, righe 31-32
- **Testo attuale**: Implica che il layout (1/2/3 colonne) si seleziona durante la creazione
- **Problema**: Il layout si cambia **dopo** la creazione, tramite Edit → Change layout, non
  durante il dialog di creazione iniziale.
- **Correzione**: Chiarire nella sezione 3.2 che la creazione imposta nome e descrizione, poi
  il layout si configura in modalità editing (Edit → Change layout).
- **Fonte**: [Create and edit dashboards](https://support.atlassian.com/jira-software-cloud/docs/create-and-edit-dashboards/)

### 1.5 "Dashboard di sistema" — terminologia IMPRECISA

- **File**: `outline.md`, riga 23
- **Testo attuale**: `Dashboard di sistema vs dashboard personali`
- **Problema**: Il termine ufficiale Jira Cloud è **"default dashboard"**, non "system
  dashboard". Il concetto è corretto ma la terminologia no.
- **Correzione**: Usare `Dashboard predefinito (default dashboard) vs dashboard personali`
  oppure mantenere "di sistema" con nota che il termine ufficiale è "default dashboard".
- **Fonte**: [What is a Jira dashboard?](https://support.atlassian.com/jira-software-cloud/docs/what-is-a-jira-dashboard/)

### 1.6 Gadget Introduction — caveat importante MANCANTE

- **File**: `outline.md`, riga 45
- **Testo attuale**: `Introduzione (Introduction): note e istruzioni in formato wiki`
- **Problema**: Il testo del gadget Introduction è configurato **globalmente** nelle impostazioni
  di sistema Jira — tutte le istanze del gadget su tutte le dashboard mostrano lo stesso testo.
  Non è personalizzabile per singola dashboard senza app di terze parti.
- **Correzione**: Aggiungere nota: `⚠️ Il testo è configurato globalmente (Settings → General
  Configuration); per testo personalizzato per dashboard, servono app di terze parti.`
- **Fonte**: [How to configure Jira's Introduction Gadget](https://support.atlassian.com/jira/kb/how-to-configure-jiras-introduction-gadget/)

---

## 2. GAP DI COMPLETEZZA — Gadget mancanti (should-fix)

### 2.1 Gadget importanti non menzionati nella sezione 3.3

| Gadget mancante | Perché è importante | Rilevanza per il target |
|---|---|---|
| **Assigned to Me** | Il gadget più fondamentale per una dashboard personale — mostra i work item assegnati all'utente corrente | Tutti i ruoli |
| **Sprint Health** | Gadget nativo che mostra stato sprint, scope changes, carico per membro | IT teams; utile per dimostrare ai team non tecnici |
| **Sprint Burndown** (gadget) | Versione gadget dashboard del burndown, distinta dal report a livello di board | IT teams |
| **Quick Links** | Scorciatoie di navigazione per i link più usati | Tutti i ruoli, specialmente utenti non tecnici |
| **Watched Work Items** | Work item sotto osservazione — essenziale per stakeholder che monitorano senza essere assegnatari | Manager, HR, Finance |

### 2.2 Inconsistenza con cheatsheet

Il cheatsheet (`cheatsheet/dashboard-cheatsheet.md`) include "Assigned to Me" e "Recently Created
Work Items" nella sua tabella, ma questi NON compaiono nell'outline né nelle slide. Allineare i
due documenti.

---

## 3. GAP DI COMPLETEZZA — Concetti di condivisione (should-fix)

Sezione 3.6 manca di concetti critici:

| Concetto mancante | Perché è critico |
|---|---|
| **Requisito condivisione filtri** | Problema #1 di supporto: dashboard condivisa con filtri privati = gadget vuoti per gli altri utenti. Quando si condivide una dashboard, **anche i filtri JQL sottostanti devono essere condivisi**. |
| **Distinzione Viewers vs Editors** | Chi ha permessi di Editor può aggiungere gadget E cancellare la dashboard. Chi ha solo permessi di Viewer può solo visualizzare. |
| **Restrizione condivisione gruppi** | Su Jira Cloud si può condividere solo con gruppi di cui si è membri. |
| **Permessi globali necessari** | Servono i permessi globali "Share dashboards and filters" E "Browse users and groups" per condividere. Senza questi, l'utente vede solo "Private". |

**Fonti**:
- [Share Jira Dashboard or Filter](https://support.atlassian.com/jira/kb/how-to-share-a-dashboard-or-filter-ie-make-it-public-change-its-viewers-and-editor-permissions/)
- [Only private option available while sharing](https://support.atlassian.com/jira/kb/only-private-option-available-while-sharing-viewer-permission-for-dashboards-and-filters/)

---

## 4. GAP DI COMPLETEZZA — Funzionalità dashboard (should-fix)

| Funzionalità mancante | Sezione | Dettagli |
|---|---|---|
| **Starring/favoriting dashboard** | 3.2 | Senza stella, gli utenti perdono la dashboard nel menu. Critico per l'usabilità quotidiana. |
| **Copiare/duplicare dashboard** | 3.2 | Disponibile dal menu "…". Utile come template per utenti non tecnici. |
| **Cercare dashboard** | 3.2 | Ricerca con fuzzy matching e wildcards. Importante con molte dashboard. |
| **Wallboard slideshow** | 3.5 | Rotazione automatica tra più dashboard in wallboard mode con intervalli configurabili. Distinto dal wallboard singolo. |

**Fonte**: [Search for an existing or shared dashboard](https://support.atlassian.com/jira-software-cloud/docs/search-for-an-existing-or-shared-dashboard/)

---

## 5. GAP DI COMPLETEZZA — Report mancanti (should-fix)

Sezione 3.4 copre 4 report. Report importanti non menzionati:

| Report mancante | Tipo | Rilevanza |
|---|---|---|
| **Sprint Report** | Scrum board-level | Il report agile più usato — mostra completamento sprint e work item spostati nel backlog. Fondamentale per le sprint review. |
| **Burnup Chart** | Scrum/Kanban board-level | Complementare al burndown — mostra scope e completamento. Più facile da leggere per stakeholder non tecnici. |
| **Epic Report** | Scrum board-level | Traccia il progresso di un epic attraverso più sprint. Utile per iniziative grandi (es. trasloco ufficio, audit annuale). |

**Fonte**: [Track and analyze your team's work with reports](https://support.atlassian.com/jira-software-cloud/docs/track-and-analyze-your-teams-work-with-reports/)

---

## 6. PROBLEMI ESERCIZI

### 6.1 Esercizio 1 — "Crea la tua dashboard personale"

- **File**: `esercizi/esercizio-03-dashboard-personale.md`
- [ ] **Aggiungere gadget "Assigned to Me"** nelle raccomandazioni per TUTTI i ruoli — è il
  gadget personale più fondamentale
- [ ] **Aggiungere step "Contrassegna con stella"** — senza questo, i partecipanti non
  ritroveranno la dashboard dopo aver navigato altrove
- [ ] Valutare se 20 minuti bastano per 4 gadget con utenti non tecnici (considerare 25 min
  o ridurre a 3 gadget)

### 6.2 Esercizio 2 — "Gadget e grafici"

- **File**: `esercizi/esercizio-03-gadget-grafici.md`
- [ ] Nessun esercizio sulla **modifica delle impostazioni** di un gadget dopo la creazione
  (cambiare filtro, periodo temporale). Gli utenti devono sapere che i gadget sono editabili.
- [ ] La Parte B (interpretazione, 10 min) beneficerebbe di un framework di analisi strutturato
  anziché domande aperte per utenti non tecnici.

### 6.3 Esercizio 3 — "Report e dashboard condivisa"

- **File**: `esercizi/esercizio-03-report-analisi.md`
- [ ] **Gap critico**: Lo Step 1 dice "L'IT Manager crea la dashboard e la condivide con il
  gruppo" ma **non spiega la meccanica della condivisione** (Viewers/Editors, percorso menu,
  requisito condivisione filtri). Aggiungere Step 1b con istruzioni esplicite.
- [ ] **Manca esercizio wallboard**: Nonostante il wallboard mode sia coperto nella sezione 3.5,
  non c'è nessun "prova ora" negli esercizi. Aggiungere un mini-step.
- [ ] **Manca navigazione report**: La Parte B chiede di esplorare i report ma non chiarisce
  come navigare alla sezione Reports per space team-managed vs company-managed.

### 6.4 Copertura complessiva esercizi

| Argomento trattato nell'outline | Esercitato? | Note |
|---|---|---|
| Creare dashboard | Sì (Es 1) | OK |
| Aggiungere gadget | Sì (Es 1, 2) | OK |
| Configurare impostazioni gadget | Parziale (Es 2) | Solo creazione, non modifica |
| Interpretare grafici | Sì (Es 2) | OK |
| Condividere dashboard | Nominato ma non insegnato (Es 3) | **Gap critico** |
| Wallboard mode | No | Da aggiungere |
| Stella/preferiti dashboard | No | Da aggiungere |
| Copiare dashboard | No | Da aggiungere |
| Report a livello di board | Parziale (Es 3B) | Solo esplorazione, nessuna analisi strutturata |
| Viewer vs Editor | No | Da aggiungere |

---

## 7. NOTE SULLA TERMINOLOGIA

### 7.1 "Spazio" (Space) — USO CORRETTO

Il materiale usa correttamente "spazio" (space), allineato con la rinominazione Atlassian 2025.
Tuttavia, poiché Confluence usa anch'esso "space", una nota esplicita nella sessione per
distinguere i due contesti sarebbe utile pedagogicamente.

### 7.2 Accesso wallboard — potenzialmente datato

Il cheatsheet suggerisce di aggiungere `?wallboard` all'URL. L'approccio attuale documentato
da Atlassian è via menu: Dashboard → More actions (…) → "View as wallboard". Entrambi i metodi
funzionano, ma il menu è più user-friendly per utenti non tecnici.

**Fonte**: [Set up a wallboard](https://support.atlassian.com/jira-software-cloud/docs/set-up-a-wallboard/)

---

## 8. NICE-TO-HAVE (arricchimenti)

- [ ] Breve menzione di **Atlassian Analytics** (disponibile per piani Enterprise) nella
  sezione 3.5
- [ ] Breve menzione dei **gadget Marketplace** — app aggiuntive disponibili su Atlassian
  Marketplace
- [ ] Nota sull'accesso dashboard da **app mobile** Jira Cloud (Android/iOS)
- [ ] Nota forward-looking su **Home Dashboards** (beta) — nuova esperienza dashboard con
  riassunti AI

---

## 9. CHECKLIST CORREZIONI

### Priorità ALTA (errori di accuratezza)

- [ ] Correggere descrizione Average Age (`outline.md:43`)
- [ ] Aggiornare warning Heat Map (`outline.md:44`)
- [ ] Completare descrizione Control Chart con lead time (`outline.md:65`)
- [ ] Chiarire sequenza creazione layout (`outline.md:31-32`)
- [ ] Aggiornare terminologia "dashboard di sistema" (`outline.md:23`)
- [ ] Aggiungere caveat gadget Introduction (`outline.md:45`)

### Priorità MEDIA (completezza contenuti)

- [ ] Aggiungere gadget Assigned to Me, Sprint Health, Sprint Burndown, Quick Links, Watched
  Work Items alla sezione 3.3
- [ ] Aggiungere requisito condivisione filtri alla sezione 3.6
- [ ] Aggiungere distinzione Viewers vs Editors alla sezione 3.6
- [ ] Aggiungere restrizione condivisione gruppi alla sezione 3.6
- [ ] Aggiungere permessi globali necessari alla sezione 3.6
- [ ] Aggiungere starring, copiare, cercare dashboard alla sezione 3.2
- [ ] Aggiungere wallboard slideshow alla sezione 3.5
- [ ] Aggiungere Sprint Report, Burnup Chart, Epic Report alla sezione 3.4

### Priorità MEDIA (esercizi)

- [ ] Aggiungere "Assigned to Me" all'esercizio 1 per tutti i ruoli
- [ ] Aggiungere step "Contrassegna con stella" all'esercizio 1
- [ ] Aggiungere meccanica condivisione esplicita all'esercizio 3
- [ ] Aggiungere mini-step wallboard all'esercizio 3
- [ ] Aggiungere istruzioni navigazione report per space team/company-managed all'esercizio 3

### Priorità BASSA (arricchimenti)

- [ ] Menzione Atlassian Analytics
- [ ] Menzione gadget Marketplace
- [ ] Nota accesso mobile
- [ ] Nota Home Dashboards (beta)

---

## 10. AFFERMAZIONI VALIDATE COME ACCURATE

Per completezza, le seguenti affermazioni sono state confermate come **corrette** dalla
documentazione ufficiale Atlassian:

| Affermazione | Verdetto |
|---|---|
| Filter Results: tabella work item da filtro salvato | ACCURATO |
| Pie Chart: distribuzione per campo (status, priority, assignee) | ACCURATO |
| Created vs Resolved: andamento nel tempo | ACCURATO |
| Two Dimensional Filter Statistics: matrice campo × campo | ACCURATO |
| Activity Stream: feed delle attività | ACCURATO |
| Collegamento gadget ↔ filtro salvato (molti ma non tutti) | ACCURATO |
| Report nella sidebar dello spazio | ACCURATO |
| Burndown Chart: report Scrum a livello di board | ACCURATO |
| Velocity Chart: report a livello di board | ACCURATO |
| CFD: report a livello di board | ACCURATO |
| Distinzione report board-level vs gadget dashboard | ACCURATO |
| JQL dinamico con `currentUser()` e date relative | ACCURATO |
| Wallboard mode | ACCURATO |
| Auto-refresh dei gadget | ACCURATO |
| Layout dashboard: 1, 2, 3 colonne | ACCURATO |
| Condivisione con utenti specifici | ACCURATO |
| Condivisione con gruppi | ACCURATO |
| Condivisione con intera organizzazione ("Any logged-in user") | ACCURATO |
| Percorso sidebar Dashboards → Create dashboard | ACCURATO |
| Dashboard come strumento di reporting per la direzione | ACCURATO |

---

## Fonti principali

- [Dashboard gadgets | Atlassian Support](https://support.atlassian.com/jira-cloud-administration/docs/use-dashboard-gadgets/)
- [Create and edit dashboards | Jira Cloud](https://support.atlassian.com/jira-software-cloud/docs/create-and-edit-dashboards/)
- [Share Jira Dashboard or Filter](https://support.atlassian.com/jira/kb/how-to-share-a-dashboard-or-filter-ie-make-it-public-change-its-viewers-and-editor-permissions/)
- [View and understand the control chart](https://support.atlassian.com/jira-software-cloud/docs/view-and-understand-the-control-chart/)
- [How is the Average Age report calculated?](https://support.atlassian.com/jira/kb/how-is-the-jira-average-age-report-calculated/)
- [Update: Ending support for five dashboard gadgets](https://community.atlassian.com/forums/Jira-articles/Update-We-re-ending-support-for-five-dashboard-gadgets-in-May/ba-p/2844556)
- [Set up a wallboard | Jira Cloud](https://support.atlassian.com/jira-software-cloud/docs/set-up-a-wallboard/)
- [Track and analyze your team's work with reports](https://support.atlassian.com/jira-software-cloud/docs/track-and-analyze-your-teams-work-with-reports/)
- [Search for an existing or shared dashboard](https://support.atlassian.com/jira-software-cloud/docs/search-for-an-existing-or-shared-dashboard/)
- [How to configure Jira's Introduction Gadget](https://support.atlassian.com/jira/kb/how-to-configure-jiras-introduction-gadget/)
- [What is a Jira dashboard?](https://support.atlassian.com/jira-software-cloud/docs/what-is-a-jira-dashboard/)
- [Only private option available while sharing](https://support.atlassian.com/jira/kb/only-private-option-available-while-sharing-viewer-permission-for-dashboards-and-filters/)
- [Difference between Average Age Chart gadget in Server and Cloud](https://support.atlassian.com/jira/kb/difference-between-average-age-chart-gadget-in-jira-server-and-cloud/)
- [Generate a report | Jira Cloud](https://support.atlassian.com/jira-software-cloud/docs/generate-a-report/)
- [Configure custom dashboards | Jira Cloud](https://support.atlassian.com/jira-cloud-administration/docs/configure-custom-dashboards/)
