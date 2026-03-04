# Sessione 3 Blocco 1 Esercizio 2 — Gadget e grafici

> ⏱ Tempo stimato: 25 minuti

## Obiettivo

Configurare gadget avanzati e imparare a leggere i grafici di Jira.

## Istruzioni

### Parte A: Gadget per il team e la direzione

Nell'esercizio precedente hai configurato gadget personali. Ora aggiungi alla stessa dashboard gadget pensati per la **visibilità di team e direzione**:

1. **Grafico "Creati vs Risolti"** (Created vs Resolved):
   - Collegalo a un filtro che copra il tuo **spazio** (space)
   - Imposta il periodo: ultimi 30 giorni
   - Granularità: giornaliera
   - Domanda: il trend è positivo (più risolti che creati) o negativo?

2. **Gadget "Due dimensioni"** (Two Dimensional Filter Statistics):
   - Riga: `Priority` o `Assignee` (o un altro campo rilevante per il tuo ruolo)
   - Colonna: `Status`
   - Filtro: tutti gli **elementi di lavoro** (work item) del tuo spazio
   - Domanda: ci sono work item ad alta priorità bloccate in uno status?

3. **Gadget "Introduzione"** (Introduction):
   - Aggiungi un gadget Introduction con:
     - Titolo del team/ruolo
     - KPI target (es. "Obiettivo: risolvere work item critici entro 24h")
     - Link utili

4. **Scegli uno** tra i seguenti gadget (in base al tuo spazio):
   - **Sprint Health** (se il tuo spazio usa Scrum): snapshot dello sprint corrente, scope changes e carico per membro del team
   - **Età media** (Average Age) (se il tuo spazio non usa Scrum): età media in giorni dei work item non risolti — utile per identificare work item "dimenticati"

### Parte B: Interpretazione grafici

In coppia, usate questa scheda per analizzare i grafici creati:

| Gadget | Cosa osservi? | Segnale positivo o negativo? | Azione suggerita |
|--------|---------------|------------------------------|------------------|
| **Creati vs Risolti** | La linea "Risolti" sta sopra o sotto "Creati"? | Sopra = positivo (il team smaltisce) / Sotto = negativo (accumulo) | _es. ridistribuire il carico, rivedere le priorità_ |
| **Due dimensioni** | Ci sono celle con numeri alti in rosso/arancione? Quale incrocio priorità×status è critico? | Celle alte in "Critical + To Do" = negativo | _es. escalation, sprint planning mirato_ |
| **Sprint Health / Età media** | Sprint Health: lo sprint è in linea con gli obiettivi? Età media: ci sono work item non risolti da troppi giorni? | Sprint Health: scope stabile = positivo / Età media: giorni bassi = positivo | _es. rivedere scope dello sprint, chiudere o riprioritizzare work item vecchi_ |
| **Il gadget più comunicativo** | Quale gadget scegliereste per una presentazione alla direzione? Perché? | — | _es. Pie Chart per immediatezza, Created vs Resolved per trend_ |

Riflettete sulle azioni suggerite.

### Parte C: Modifica le impostazioni di un gadget

1. Scegli un gadget esistente sulla tua dashboard (es. Pie Chart o Created vs Resolved)
2. Clicca sui tre puntini (**⋯**) del gadget e seleziona **"Modifica"**
3. Cambia una impostazione:
   - Per **Pie Chart**: cambia il campo di raggruppamento (es. da Status a Priority)
   - Per **Created vs Resolved**: cambia il periodo temporale (es. da 30 a 90 giorni)
4. Salva e osserva come cambia la visualizzazione
5. Domanda: come cambiano le informazioni mostrate? Quale configurazione è più utile per il tuo ruolo?

## Risultato atteso

- 4 nuovi gadget aggiunti alla dashboard
- 1 modifica alle impostazioni di un gadget esistente
- Capacità di interpretare i grafici con occhio critico
- Discussione in coppia completata

## Domande di riflessione

- Quali metriche sarebbero più utili da monitorare per il vostro ruolo?
- Come potreste usare questi grafici nelle riunioni di team?
