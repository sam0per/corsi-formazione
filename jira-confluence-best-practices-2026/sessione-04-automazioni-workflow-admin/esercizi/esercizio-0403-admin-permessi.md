# Sessione 4 Blocco 2 Esercizio 3 — Amministrazione e permessi

> ⏱ Tempo stimato: 25 minuti

## Obiettivo

Comprendere la gestione dei permessi, degli schemi e delle configurazioni di **spazio** (space).

## Istruzioni

### Parte A — Esplorazione permessi

> ℹ️ I permission scheme sono disponibili solo per spazi **Company-managed**. Per spazi Team-managed, i permessi si gestiscono da Space settings → Access.

1. Andate su **Space settings → Access → Space permissions** di uno spazio Company-managed a cui avete accesso.
2. Analizzate il **Permission scheme** associato:
   - Chi può creare **elementi di lavoro** (work item)?
   - Chi può assegnare elementi di lavoro?
   - Chi può modificare il workflow?
   - Chi può eliminare elementi di lavoro?
3. Verificate: i permessi attuali corrispondono a quello che vi aspettavate?
4. Viene applicato il principio del minimo privilegio? Cioè, gli utenti hanno solo i permessi di cui hanno bisogno per svolgere il loro lavoro, e non di più?
5. Confrontate con un secondo spazio: usano lo stesso scheme o uno diverso?
   > Se avete accesso a un solo spazio, annotate le configurazioni e confrontatele con un collega.

### Parte B — Configurazione spazio

Esplorare le seguenti configurazioni:

> ℹ️ Alcune configurazioni (work item types scheme, notification scheme) sono gestite a livello di **Jira admin** (Settings → Work items), non dallo spazio. Dallo spazio si vede quale schema è associato ma per modificarlo serve accesso admin Jira. Nota: admin.atlassian.com è per la gestione utenti/gruppi a livello organizzazione, non per gli schemi di prodotto.

1. **Work item types scheme**: quali work types sono disponibili nello spazio
2. **Notification scheme**: chi riceve notifiche per quali eventi
3. **Componenti**: come organizzare gli elementi di lavoro per area (es. "Hardware", "Software", "Rete" per IT)
4. **Fields o campi**: quali campi sono obbligatori, quali opzionali, e quanti/quali screens sono configurati

Ogni partecipante annota:
- Quali componenti sarebbero utili per il proprio spazio?
- Quali notifiche vorreste ricevere (o non ricevere)?

### Parte C — Piano di governance

Identificare le **convenzioni di base** per gli spazi a cui fate parte nell'istanza Tyvak:

1. **Nomenclatura spazi**: come sono stati chiamati i progetti, es. `DEPT-NOME` (IT-HELPDESK, HR-ONBOARDING, FAC-TICKETS)
2. **Etichette comuni**: quali sono le 5-10 etichette standard condivise, sono chiare e coerenti?
3. **Componenti standard**: per spazio, quali componenti hanno senso?
4. **Revisione periodica**: ogni quanto fare pulizia? (suggerimento: trimestrale)

## Risultato atteso

- Comprensione dei permission scheme e notification scheme
- Lista di componenti ed etichette proposti per ciascuno spazio
- Bozza di convenzioni di governance per l'istanza Tyvak

## Extra IT — Checklist IT admin (opzionale)

Dopo il corso/esercizio, valuta di implementare una checklist di configurazione e governance per i progetti IT. Se esiste già, rivedila provando a capire come migliorarla. Esempio di voci da includere:
- [ ] Revisione permission scheme per ogni spazio
- [ ] Standardizzazione etichette e componenti
- [ ] Creazione di un template di spazio per nuovi team
- [ ] Documentazione delle configurazioni su Confluence
- [ ] Calendario di revisione trimestrale

> Per la terminologia, consulta il [glossario](../../glossario.md).
