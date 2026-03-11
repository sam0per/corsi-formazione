# Confluence Cheatsheet — Riferimento rapido

> Guida tascabile per Confluence Cloud

## Struttura di Confluence

```
Sito Atlassian (tyvak.atlassian.net)
  └── Spazio (Space) → contenitore per documentazione e collaborazione
       ├── Pagina (Page) → documento con workflow di pubblicazione
       ├── Live Doc → documento collaborativo in tempo reale (senza pubblicazione)
       ├── Blog Post → aggiornamenti cronologici
       ├── Whiteboard → lavagna collaborativa
       ├── Database → dati strutturati in tabelle collaborative
       ├── Cartella (Folder) → organizzazione dei contenuti
       └── Sotto-pagina → gerarchia ad albero
```

## Tipi di spazio

| Tipo | Quando usare |
|------|-------------|
| **Collaboration** | Lavoro di team, progetti, documentazione condivisa |
| **Knowledge base** | FAQ, guide, procedure — include template how-to e troubleshooting |
| **Custom** | Struttura personalizzata |

## Editor cloud — Comandi rapidi

| Comando | Azione |
|---------|--------|
| `/` | Apre il menu comandi (macro, formattazione, elementi) |
| `/tabella` | Inserisce una tabella |
| `/espansione` | Inserisce una sezione espandibile (expand) |
| `/pannello` | Inserisce un pannello (info, note, warning, error, success) |
| `/jira` | Mostra le macro Jira (Work Items, Chart, Create) |
| `/template` | Inserisce un template nella pagina |
| `/immagine` | Inserisce un'immagine |
| `/azione` | Inserisce un'azione (task con checkbox) |
| `/menzione` o `@nome` | Menziona un utente |
| `/data` | Inserisce un selettore di data |
| `---` | Inserisce una linea separatrice |

> **Nota**: i comandi sopra funzionano con l'interfaccia Confluence in italiano. Con UI in inglese usare: `/table`, `/expand`, `/panel`, `/action`, `/image`. Il comando `/jira` è uguale in entrambe le lingue.

## Pannelli (panel element)

| Tipo | Colore | Quando usare |
|------|--------|-------------|
| **Info** | Blu | Informazioni generali, contesto |
| **Note** | Viola | Note importanti, promemoria |
| **Success** | Verde | Conferme, risultati positivi |
| **Warning** | Giallo | Avvisi, attenzione richiesta |
| **Error** | Rosso | Errori, blocchi, azioni critiche |

## Template predefiniti utili

| Template | Scopo | Ideale per |
|----------|-------|-----------|
| **Meeting notes** | Verbale di riunione con partecipanti, agenda, azioni | Tutte le riunioni |
| **Decision** | Documentare una decisione con status, stakeholder, pro/contro | Scelte importanti |
| **How-to article** | Guida passo-passo | Procedure operative |
| **Retrospettiva** | Start/Stop/Keep o 4Ls | Fine progetto o sprint |
| **DevOps Runbook** | Procedure operative con prerequisiti e step | IT, Facility |
| **ITSM Runbook** | Gestione alert e troubleshooting | IT, Service Management |

## Organizzazione dei contenuti

### Gerarchia pagine
- Ogni spazio ha una **Home page**
- Le pagine si annidano come **sotto-pagine** (drag & drop nel content tree)
- Usare **cartelle (folder)** per raggruppare contenuti correlati

### Etichette (label)
- Aggiungi etichette a pagine e allegati per categorizzare
- Clicca su un'etichetta per trovare tutte le pagine con la stessa etichetta
- Convenzioni consigliate: `runbook`, `procedura`, `onboarding`, `faq`, `[nome-team]`

## Ricerca

| Metodo | Come |
|--------|------|
| **Ricerca globale** | Barra di ricerca in alto — cerca in tutti gli spazi |
| **Per etichetta** | Clicca su un'etichetta o filtra i risultati di ricerca per label |
| **Pagine recenti** | Sidebar sinistra → **Recent** |
| **Starred (preferiti)** | Sidebar sinistra → **Starred** (icona stella sulla pagina per aggiungerla) |
| **Content tree** | Sidebar dello spazio → vista ad albero, visite recenti, ultimo aggiornamento, A-Z |

## Permessi

| Livello | Cosa controlla | Chi lo gestisce |
|---------|---------------|-----------------|
| **Permessi globali** | Accesso a tutta l'istanza Confluence, creazione spazi | Site admin |
| **Permessi di spazio** | Chi può vedere, aggiungere, eliminare contenuti nello spazio | Space admin |
| **Restrizioni di pagina** | Limita chi può vedere o modificare una singola pagina | Autore / space admin |

> **Gruppi**: meccanismo per assegnare permessi a insiemi di utenti. Utilizzabili a tutti e tre i livelli (globale, spazio, pagina). Gestiti dal site admin.

> **Space shortcuts** (link rapidi nella sidebar): solo gli **space admin** possono aggiungerli. Nota: Atlassian sta progressivamente sostituendo gli shortcuts con Smart Links nel content tree.

## Notifiche e watching

- **Watch** (seguire): clicca "Watch" su una pagina per ricevere notifiche sulle modifiche
- **Watch uno spazio**: segui tutte le pagine di uno spazio contemporaneamente
- **Gestione notifiche**: profilo → **Settings** → **Email** per le preferenze di notifica email. L'icona campana mostra le notifiche recenti ricevute

## Integrazione Jira ↔ Confluence

### Da Confluence a Jira

| Macro/Funzione | Comando | Cosa fa |
|---------------|---------|---------|
| **Jira Work Items** | `/jira` → Jira work items | Tabella di work item da query JQL o filtro |
| **Jira Chart** | `/jira` → Jira chart | Grafico (torta, creati vs risolti, 2D) da filtro |
| **Crea work item** | `/jira` → Create Jira work item | Crea un work item direttamente dall'editor |
| **Smart Link** | Incolla URL di un work item Jira | Preview automatica con titolo e status |

### Da Jira a Confluence

- **Link page**: nel work item Jira, usa "+" o "Link" → "Existing Confluence page"
- **Nella descrizione**: incolla URL Confluence → smart link automatico
- **Mentioned in**: quando un work item è referenziato in Confluence, appare automaticamente nel work item

> La tabella Jira Work Items si aggiorna **ad ogni caricamento della pagina** (non in tempo reale via push).

## Page ownership

- Ogni pagina ha un **proprietario** (owner) — di default il creatore
- Il proprietario può essere trasferito da: owner, space admin, site admin
- **Best practice**: includere il trasferimento di ownership nelle checklist di offboarding

## Ciclo di vita dei contenuti

1. **Crea** → pubblica la pagina
2. **Mantieni** → aggiorna quando il processo cambia
3. **Archivia** → quando il contenuto non è più attuale (Space settings → Content → Archive)
4. **Revisiona** → pianifica revisioni periodiche (es. trimestrali)

## Best practice

- Ogni pagina deve avere uno **scopo chiaro** e un **proprietario**
- Usare **etichette coerenti** tra spazi Jira e Confluence
- Usare **template** per documenti ricorrenti (runbook, meeting notes, decision)
- Collegare **bidirezionalmente** pagine Confluence e work item Jira
- **Archiviare** pagine obsolete invece di eliminarle
- Revisionare i contenuti **trimestralmente**
