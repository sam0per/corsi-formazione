# Esercizio 1 — Crea la tua dashboard personale

> ⏱ Tempo stimato: 20 minuti | 👥 Individuale

## Obiettivo

Creare una dashboard personale con almeno 4 gadget utili per il proprio ruolo.

## Prerequisiti

Avere almeno 2 filtri JQL salvati dalla sessione 2.

## Istruzioni

### Step 1 — Crea la dashboard (5 min)

1. Dalla sidebar, vai su **Dashboards → Create dashboard**
2. Nome: `[Tuo ruolo] — Dashboard operativa` (es. `IT Manager — Dashboard operativa`)
3. Descrizione: breve spiegazione dello scopo
4. Layout: seleziona **2 colonne**

### Step 2 — Aggiungi i gadget (15 min)

Aggiungi almeno **4 gadget** scegliendo tra quelli indicati per il tuo ruolo:

**🔧 IT Manager:**
1. **Risultati filtro** (Filter Results): **elementi di lavoro** (work item) IT aperti (usa filtro JQL dalla sessione 2)
2. **Grafico a torta** (Pie Chart): distribuzione work item per priorità
3. **Creati vs Risolti** (Created vs Resolved): andamento work item ultimo mese
4. **Due dimensioni** (Two Dimensional Filter Statistics): matrice priorità × status

**💼 Administration & Finance:**
1. **Risultati filtro** (Filter Results): ordini e fatture in corso
2. **Grafico a torta** (Pie Chart): distribuzione per etichetta (acquisti/fatturazione)
3. **Creati vs Risolti** (Created vs Resolved): andamento elementi di lavoro ultimo trimestre
4. **Introduzione** (Introduction): note con scadenze importanti

**👥 HR Generalist:**
1. **Risultati filtro** (Filter Results): task onboarding attivi
2. **Grafico a torta** (Pie Chart): distribuzione per status
3. **Attività recente** (Activity Stream): ultime modifiche nello **spazio** (space) HR
4. **Creati vs Risolti** (Created vs Resolved): andamento task ultimo mese

**🏢 Facility Manager:**
1. **Risultati filtro** (Filter Results): work item facility aperti
2. **Grafico a torta** (Pie Chart): distribuzione per componente (manutenzione/reclami/sicurezza)
3. **Creati vs Risolti** (Created vs Resolved): andamento reclami e manutenzioni
4. **Due dimensioni** (Two Dimensional Filter Statistics): matrice priorità × componente

## Risultato atteso

- 1 dashboard personale funzionante con almeno 4 gadget
- I gadget devono essere collegati a filtri JQL reali
- Il layout deve essere ordinato e leggibile

## Consiglio

Se un gadget non mostra dati, verifica che il filtro JQL collegato restituisca risultati.
