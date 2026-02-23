# Dashboard Cheatsheet — Riferimento rapido

> Guida tascabile per creare dashboard efficaci in Jira Cloud

## Creare una dashboard

1. **Dashboards** → **Create dashboard**
2. Nome descrittivo: `[Team/Ruolo] — [Scopo]`
3. Scegliere il layout (1, 2, o 3 colonne)
4. Aggiungere gadget con **"Add gadget"**

## Gadget principali

| Gadget | Cosa mostra | Ideale per |
|--------|-------------|-----------|
| **Filter Results** | Tabella issue da un filtro JQL | Lista operativa delle attività |
| **Pie Chart** | Grafico a torta per campo | Distribuzione per status/priorità/assegnatario |
| **Created vs Resolved** | Andamento creazione/risoluzione | Monitorare il carico di lavoro nel tempo |
| **Two Dimensional Filter Statistics** | Matrice campo × campo | Panoramica priorità × status |
| **Activity Stream** | Feed attività recenti | Monitorare l'attività del team |
| **Average Age Chart** | Età media delle issue | Identificare issue stagnanti |
| **Heat Map** | Mappa di calore per campo | Visualizzare concentrazioni |
| **Recently Created Chart** | Issue create di recente | Monitorare il volume di nuovo lavoro |
| **Resolution Time** | Tempo di risoluzione | Misurare l'efficienza |
| **Text** | Testo libero (wiki) | Note, link, istruzioni |
| **Assigned to Me** | Le tue issue | Dashboard personale |

## Configurazione gadget — Impostazioni chiave

Ogni gadget che usa dati richiede:
- **Filtro salvato** (Saved Filter) o **Project/Filter**
- **Refresh interval**: quanto spesso aggiornare (15 min consigliato)
- **Numero risultati**: quante righe mostrare (10-25 per tabelle)

### Filter Results — Colonne consigliate

| Colonna | Quando includerla |
|---------|------------------|
| Key | Sempre |
| Summary | Sempre |
| Status | Sempre |
| Priority | Sempre |
| Assignee | Per dashboard di team |
| Created | Per monitorare il volume |
| Updated | Per identificare issue ferme |
| Due Date | Per issue con scadenza |
| Labels | Per categorizzazione |

### Pie Chart — Campi consigliati

- `Status` → distribuzione del lavoro
- `Priority` → distribuzione per urgenza
- `Assignee` → carico per persona
- `Component` → distribuzione per area
- `Labels` → distribuzione per categoria

## Layout consigliati

### Dashboard operativa personale (2 colonne)

```
┌─────────────────────┬─────────────────────┐
│  Filter Results     │  Pie Chart          │
│  (le mie issue)     │  (per status)       │
├─────────────────────┼─────────────────────┤
│  Created vs         │  Two Dimensional    │
│  Resolved           │  (priorità×status)  │
├─────────────────────┼─────────────────────┤
│  Text               │  Activity Stream    │
│  (note/obiettivi)   │  (attività recente) │
└─────────────────────┴─────────────────────┘
```

### Dashboard manager (2 colonne)

```
┌─────────────────────┬─────────────────────┐
│  Pie Chart          │  Pie Chart          │
│  (per assegnatario) │  (per priorità)     │
├─────────────────────┼─────────────────────┤
│  Created vs         │  Two Dimensional    │
│  Resolved           │  (progetto×status)  │
├─────────────────────┼─────────────────────┤
│  Filter Results     │  Filter Results     │
│  (critical/high)    │  (in scadenza)      │
└─────────────────────┴─────────────────────┘
```

## Condivisione e permessi

| Livello | Chi può vedere | Quando usare |
|---------|---------------|-------------|
| Privata | Solo tu | Dashboard personale |
| Gruppo | Membri del gruppo | Dashboard di team |
| Progetto | Ruolo nel progetto | Dashboard di progetto |
| Pubblica | Tutti gli utenti del sito | Dashboard aziendale |

**Come condividere**: Dashboard → ⋯ → Edit → Share → Aggiungi utenti/gruppi

## Wallboard mode

Per visualizzare la dashboard su uno schermo condiviso:
- Aggiungi `?wallboard` all'URL della dashboard
- Esempio: `https://tyvak.atlassian.net/jira/dashboards/10001?wallboard`
- I gadget si aggiornano automaticamente

## Best practice

- Ogni dashboard deve avere uno **scopo chiaro** (operativa, reporting, monitoring)
- Non sovraccaricare: **6-8 gadget massimo** per dashboard
- Usare nomi descrittivi per le dashboard
- Collegare gadget a **filtri salvati** (non a query JQL dirette) per manutenibilità
- Impostare il **refresh interval** appropriato (15 min per operativa, 1h per reporting)
- Revisionare le dashboard **trimestralmente** per rimuovere gadget obsoleti
