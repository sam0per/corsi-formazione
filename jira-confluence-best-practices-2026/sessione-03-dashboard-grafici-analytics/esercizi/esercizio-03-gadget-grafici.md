# Esercizio 2 — Gadget e grafici

> ⏱ Tempo stimato: 25 minuti | 👥 In coppia

## Obiettivo

Configurare gadget avanzati e imparare a leggere i grafici di Jira.

## Istruzioni

### Parte A — Gadget avanzati (15 min)

Sulla dashboard creata nell'esercizio precedente, aggiungi:

1. **Grafico "Creati vs Risolti"** (Created vs Resolved):
   - Collegalo a un filtro che copra il tuo **spazio** (space)
   - Imposta il periodo: ultimi 30 giorni
   - Granularità: giornaliera
   - Domanda: il trend è positivo (più risolti che creati) o negativo?

2. **Gadget "Due dimensioni"** (Two Dimensional Filter Statistics):
   - Riga: `Priority`
   - Colonna: `Status`
   - Filtro: tutti gli **elementi di lavoro** (work item) del tuo spazio
   - Domanda: ci sono work item ad alta priorità bloccate in uno status?

3. **Gadget "Introduzione"** (Introduction):
   - Aggiungi un gadget Introduction con:
     - Titolo del team/ruolo
     - KPI target (es. "Obiettivo: risolvere work item critici entro 24h")
     - Link utili

### Parte B — Interpretazione grafici (10 min)

In coppia, usate questa scheda per analizzare i grafici creati:

| Gadget | Cosa osservi? | Segnale positivo o negativo? | Azione suggerita |
|--------|---------------|------------------------------|------------------|
| **Creati vs Risolti** | La linea "Risolti" sta sopra o sotto "Creati"? | Sopra = positivo (il team smaltisce) / Sotto = negativo (accumulo) | _es. ridistribuire il carico, rivedere le priorità_ |
| **Due dimensioni** | Ci sono celle con numeri alti in rosso/arancione? Quale incrocio priorità×status è critico? | Celle alte in "Critical + To Do" = negativo | _es. escalation, sprint planning mirato_ |
| **Il gadget più comunicativo** | Quale gadget scegliereste per una presentazione alla direzione? Perché? | — | _es. Pie Chart per immediatezza, Created vs Resolved per trend_ |

Compilate la tabella insieme e discutete le azioni suggerite (2 minuti per gadget).

### Parte C — Modifica le impostazioni di un gadget (5 min)

1. Scegli un gadget esistente sulla tua dashboard (es. Pie Chart o Created vs Resolved)
2. Clicca sui tre puntini (**⋯**) del gadget e seleziona **"Edit"**
3. Cambia una impostazione:
   - Per **Pie Chart**: cambia il campo di raggruppamento (es. da Status a Priority)
   - Per **Created vs Resolved**: cambia il periodo temporale (es. da 30 a 90 giorni)
4. Salva e osserva come cambia la visualizzazione
5. Domanda: come cambiano le informazioni mostrate? Quale configurazione è più utile per il tuo ruolo?

## Risultato atteso

- 3 nuovi gadget aggiunti alla dashboard
- 1 modifica alle impostazioni di un gadget esistente
- Capacità di interpretare i grafici con occhio critico
- Discussione in coppia completata

## Domande di riflessione

- Quali metriche sarebbero più utili da monitorare per il vostro ruolo?
- Come potreste usare questi grafici nelle riunioni di team?
