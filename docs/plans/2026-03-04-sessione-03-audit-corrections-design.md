# Design — Correzioni Audit Sessione 03

> Data: 2026-03-04
> Audit di riferimento: `docs/audit/sessione-03-audit.md`
> Approccio scelto: B — Ristrutturazione con nuova tempistica

---

## Obiettivo

Risolvere tutti i finding must-fix (6 errori di accuratezza) e should-fix (13 gap di
completezza + 5 problemi esercizi) identificati nell'audit della sessione 03, ristrutturando
la tempistica e la suddivisione dei contenuti per accogliere il materiale aggiuntivo.

---

## File coinvolti

| File | Tipo di modifica |
|---|---|
| `sessione-03-dashboard-grafici-analytics/outline.md` | Ristrutturazione completa |
| `sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-dashboard-personale.md` | Aggiunte |
| `sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-gadget-grafici.md` | Aggiunte |
| `sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-report-analisi.md` | Aggiunte |
| `cheatsheet/dashboard-cheatsheet.md` | Correzioni puntuali |

---

## Nuova struttura temporale

### Blocco 1 — Dashboard fondamentali (0:00 – 1:10)

| Sezione | Durata | Contenuto |
|---|---|---|
| 3.1 Panoramica delle dashboard | 15 min | Cos'e' una dashboard, dashboard predefinito vs personali, starring/favoriting, cercare e copiare dashboard, best practice |
| 3.2 Creare e configurare una dashboard | 15 min | Creazione (nome, descrizione), layout post-creazione (Edit -> Change layout), aggiungere gadget, posizionamento, demo live con starring |
| 3.3 Gadget per la dashboard personale | 20 min | Assigned to Me (NEW), Filter Results, Pie Chart, Activity Stream, Quick Links (NEW), Introduction (con caveat globale), collegamento gadget-filtro |
| 3.4 Gadget per il team e la direzione | 20 min | Created vs Resolved, Two Dimensional Filter Statistics, Average Age (CORRETTO), Sprint Health (NEW), Sprint Burndown gadget (NEW), Watched Work Items (NEW), Heat Map (deprecazione AGGIORNATA) |

**Pausa** (10 min)

### Esercizi Blocco 1 (1:10 – 2:00)

| Esercizio | Durata | Modifiche |
|---|---|---|
| Es. 1: Dashboard personale | 25 min (era 20) | Aggiunto Assigned to Me per tutti i ruoli, aggiunto step starring |
| Es. 2: Gadget e grafici | 25 min | Aggiunta Parte C: modifica impostazioni gadget |

### Blocco 2 — Report, condivisione e analytics (2:00 – 3:00)

| Sezione | Durata | Contenuto |
|---|---|---|
| 3.5 Report integrati di Jira | 20 min | Board reports (Burndown, Velocity, CFD, Control Chart con lead time CORRETTO), Sprint Report (NEW), Burnup Chart (NEW), Epic Report (NEW) |
| 3.6 Dashboard avanzate e trucchi | 15 min | JQL dinamico, dashboard manager/operativa, wallboard mode + slideshow (NEW), refresh automatico |
| 3.7 Condivisione e permessi dashboard | 25 min (era 15) | Livelli condivisione, Viewers vs Editors (NEW), requisito condivisione filtri (NEW), restrizione gruppi (NEW), permessi globali (NEW), best practice, esempio Tyvak |

**Pausa** (10 min)

### Esercizi Blocco 2 (3:10 – 3:45)

| Esercizio | Durata | Modifiche |
|---|---|---|
| Es. 3: Report e dashboard condivisa | 35 min (era 25) | Aggiunto Step 1b (meccanica condivisione), navigazione report, mini-step wallboard |

### Recap e Q&A (3:45 – 4:00) — 15 min (era 30)

---

## Modifiche dettagliate per file

### 1. outline.md — Ristrutturazione

#### Sezione 3.1 (Panoramica)

- Cambiare "Dashboard di sistema vs dashboard personali" in "Dashboard predefinito (default
  dashboard) vs dashboard personali"
- Aggiungere: "Contrassegnare con stella (star) le dashboard per accesso rapido"
- Aggiungere: "Cercare dashboard esistenti e copiare dashboard come template"

#### Sezione 3.2 (Creare e configurare)

- Chiarire la sequenza: creazione imposta nome e descrizione; il layout si configura dopo con
  Edit -> Change layout (1/2/3 colonne)
- Aggiungere alla demo: "Contrassegnare la dashboard con stella dopo la creazione"

#### Sezione 3.3 (NEW: Gadget per la dashboard personale)

Gadget da includere in questo ordine:
1. **Assigned to Me** (NEW): i tuoi work item assegnati — il gadget personale fondamentale
2. **Risultati filtro** (Filter Results): tabella work item da un filtro JQL
3. **Grafico a torta** (Pie Chart): distribuzione per campo
4. **Attivita' recente** (Activity Stream): feed delle attivita'
5. **Quick Links** (NEW): scorciatoie di navigazione
6. **Introduzione** (Introduction): note e istruzioni in formato wiki — aggiungere caveat:
   "il testo e' configurato globalmente nelle impostazioni di sistema; per testo personalizzato
   per dashboard servono app di terze parti"
7. Nota: collegamento gadget <-> filtro salvato

#### Sezione 3.4 (NEW: Gadget per il team e la direzione)

Gadget da includere:
1. **Creati vs Risolti** (Created vs Resolved): andamento nel tempo
2. **Grafico a due dimensioni** (Two Dimensional Filter Statistics): matrice campo x campo
3. **Eta' media** (Average Age): eta' media (in giorni) dei work item non risolti —
   CORREZIONE: non e' "media tempo in status"
4. **Sprint Health** (NEW): snapshot dello stato dello sprint, scope changes, carico per membro
5. **Sprint Burndown** gadget (NEW): lavoro rimanente nello sprint — distinto dal report
   a livello di board
6. **Work item sotto osservazione** (Watched Work Items) (NEW): per stakeholder che monitorano
   senza essere assegnatari
7. **Mappa di calore** (Heat Map): AGGIORNARE nota deprecazione — "Atlassian ha annunciato
   la rimozione di questo gadget (insieme a Road Map, Bubble Chart, Spaces, Labels), ma la
   rimozione e' stata sospesa ad aprile 2025. Attualmente ancora disponibile, ma non piu'
   mantenuto attivamente."
8. Collegamento gadget <-> filtro salvato: ribadire che molti gadget si basano su un filtro JQL

#### Sezione 3.5 (Report integrati — era 3.4)

Report da includere:
1. **Burndown Chart** (board Scrum) — invariato
2. **Velocity Chart** — invariato
3. **Cumulative Flow Diagram** — invariato
4. **Control Chart** — CORREZIONE: "tempo di ciclo (cycle time) e lead time dei work item"
5. **Sprint Report** (NEW): completamento sprint, work item spostati nel backlog
6. **Burnup Chart** (NEW): complementare al burndown, mostra scope e completamento —
   piu' leggibile per stakeholder non tecnici
7. **Epic Report** (NEW): progresso di un epic attraverso piu' sprint

#### Sezione 3.6 (Dashboard avanzate — era 3.5)

- Aggiungere: "Wallboard slideshow: rotazione automatica tra piu' dashboard con intervalli
  configurabili"
- Resto invariato

#### Sezione 3.7 (Condivisione e permessi — era 3.6)

Contenuto da includere:
1. Condividere con utenti specifici (esistente)
2. Condividere con gruppi (esistente) + NEW: "su Jira Cloud si puo' condividere solo con
   gruppi di cui si e' membri"
3. Condividere con l'intera organizzazione (esistente)
4. NEW: "Distinzione Viewers vs Editors: chi ha permessi di Editor puo' aggiungere/modificare
   gadget e cancellare la dashboard; i Viewer possono solo visualizzare"
5. NEW: "Condividere anche i filtri JQL sottostanti ai gadget — senza condivisione dei filtri,
   gli altri utenti vedranno gadget vuoti. Questo e' il problema di supporto piu' comune."
6. NEW: "Permessi globali necessari: 'Share dashboards and filters' e 'Browse users and groups'.
   Senza questi permessi, l'utente vedra' solo l'opzione 'Private'."
7. Dashboard come strumento di reporting per la direzione (esistente)
8. Best practice: chi dovrebbe vedere cosa? (esistente)
9. Esempio Tyvak (esistente)

### 2. esercizio-03-dashboard-personale.md

#### Aggiungere Assigned to Me per tutti i ruoli

Nella sezione "Step 2 — Aggiungi i gadget", aggiungere come gadget #1 per ogni ruolo:
- IT Manager: `1. **Assigned to Me**: i tuoi work item IT assegnati`
- Admin & Finance: `1. **Assigned to Me**: i tuoi elementi di lavoro assegnati`
- HR Generalist: `1. **Assigned to Me**: i tuoi task HR assegnati`
- Facility Manager: `1. **Assigned to Me**: i tuoi work item facility assegnati`

Cambiare "almeno 4 gadget" in "almeno 5 gadget" (oppure mantenere 4 se si preferisce
non aumentare il carico, rendendo Assigned to Me obbligatorio + 3 a scelta).

#### Aggiungere Step 3 — Stella

Dopo Step 2, aggiungere:
```
### Step 3 — Contrassegna con stella (2 min)

1. Dalla dashboard appena creata, clicca sull'icona stella accanto al nome
2. Verifica che la dashboard appaia nel menu **Dashboards** nella sidebar
```

#### Aggiornare risultato atteso

Aggiungere: "La dashboard e' contrassegnata con stella per accesso rapido"

### 3. esercizio-03-gadget-grafici.md

#### Aggiungere Parte C — Modifica impostazioni gadget (5 min)

Dopo Parte B, aggiungere:
```
### Parte C — Modifica le impostazioni di un gadget (5 min)

1. Scegli un gadget esistente sulla tua dashboard (es. Pie Chart)
2. Clicca sui tre puntini (...) del gadget e seleziona "Edit"
3. Cambia una impostazione:
   - Per Pie Chart: cambia il campo di raggruppamento (es. da Status a Priority)
   - Per Created vs Resolved: cambia il periodo temporale (es. da 30 a 90 giorni)
4. Salva e osserva come cambia la visualizzazione

Domanda: come cambiano le informazioni mostrate? Quale configurazione e' piu' utile?
```

#### Aggiornare risultato atteso

Cambiare "3 nuovi gadget" in "3 nuovi gadget + 1 modifica di impostazioni gadget"

### 4. esercizio-03-report-analisi.md

#### Aggiungere Step 1b — Meccanica condivisione

Dopo Step 1 ("L'IT Manager crea la dashboard"), aggiungere:
```
   **Step 1b — Condividi la dashboard** (IT Manager):
   1. Dalla dashboard, clicca **⋯** (More actions) → **Share dashboard**
   2. Nella sezione **Editors**, aggiungi i partecipanti del gruppo (per nome o email)
   3. **Importante**: condividi anche i filtri JQL usati dai gadget — altrimenti gli altri
      vedranno gadget vuoti. Per ogni filtro: Filters → trova il filtro → ⋯ → Share
```

#### Aggiungere nota navigazione report in Parte B

All'inizio della Parte B, aggiungere:
```
> Per trovare i report: dalla sidebar, seleziona il tuo spazio → **Reports**.
> Nota: per gli spazi company-managed con piu' board, assicurati di visualizzare la
> board corretta prima di aprire i report.
```

#### Aggiungere Parte C — Wallboard

Dopo Parte B, aggiungere:
```
### Parte C — Wallboard mode (5 min)

1. Dalla dashboard condivisa, clicca **⋯** (More actions) → **View as wallboard**
2. Osservate come la dashboard appare a schermo intero
3. Premete **Esc** per tornare alla vista normale
4. Discutete: in quale contesto usereste il wallboard mode? (riunioni, monitor condiviso?)
```

#### Aggiornare risultato atteso

Aggiungere: "Esperienza pratica con wallboard mode"

### 5. dashboard-cheatsheet.md

#### Riga 9 — Sequenza creazione

Cambiare:
```
3. Scegliere il layout (1, 2, o 3 colonne)
```
In:
```
3. Dopo la creazione: **Edit** → **Change layout** (1, 2, o 3 colonne)
```

#### Righe 26-27 — Lista deprecazione ERRATA

Cambiare:
```
> Heat Map, Resolution Time, Time Since Chart, Time to First Response, Workload Pie Chart
```
In:
```
> Heat Map, Road Map, Bubble Chart, Spaces (ex Projects), Labels
> (rimozione annunciata per maggio 2025, poi sospesa ad aprile 2025 — attualmente ancora disponibili)
```

#### Righe 90-98 — Tabella condivisione

Aggiungere riga per la distinzione Viewers/Editors:
```
> **Viewers vs Editors**: i Viewer possono solo visualizzare; gli Editor possono modificare
> gadget e cancellare la dashboard. Condividi anche i filtri JQL sottostanti!
```

#### Righe 103-106 — Wallboard mode

Aggiungere accesso via menu come metodo primario:
```
- **Via menu**: Dashboard → ⋯ → **View as wallboard**
- **Via URL** (alternativa): aggiungi `?wallboard` all'URL della dashboard
```

---

## Cosa NON cambiare

- La struttura generale del corso (5 sessioni) rimane invariata
- Gli obiettivi della sessione rimangono invariati (gia' corretti)
- I nomi dei file e le directory rimangono invariati
- Le slide (.pptx) non sono in scope — dovranno essere aggiornate separatamente
- I nice-to-have (Atlassian Analytics, Marketplace, mobile, Home Dashboards) sono esclusi

---

## Validazione

Dopo le modifiche:
1. Verificare che la somma dei tempi sia esattamente 4 ore (240 min)
2. Verificare che tutti i link interni (outline -> esercizi, outline -> cheatsheet) funzionino
3. Verificare che la terminologia sia coerente (spazio, work item, elemento di lavoro)
4. Cross-check con `docs/audit/sessione-03-audit.md` — tutte le checkbox must-fix e should-fix
   devono avere una modifica corrispondente
