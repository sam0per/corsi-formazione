# Glossario Jira e Confluence

> Termini principali in ordine alfabetico — Italiano / Inglese

## A

**Assegnatario (Assignee)**: La persona responsabile di un elemento di lavoro (work item).

**Automazione (Automation)**: Sistema di regole per eseguire azioni automatiche basate su trigger e condizioni.

**Azione (Action)**: L'operazione eseguita da una regola di automazione (es. inviare email, cambiare status).

## B

**Backlog**: Lista di elementi di lavoro (work item) da completare, non ancora pianificati in uno sprint.

**Board (Bacheca)**: Visualizzazione degli elementi di lavoro (work item) in colonne per status. Può essere Scrum o Kanban.

**Burndown Chart**: Grafico che mostra il lavoro rimanente in uno sprint nel tempo.

## C

**Campo (Field)**: Un attributo di un elemento di lavoro (work item) (es. Summary, Priority, Assignee, Labels).

**Campo personalizzato (Custom Field)**: Campo creato dall'amministratore per esigenze specifiche.

**Commento (Comment)**: Nota aggiunta a un work item per comunicare con il team.

**Company-managed space**: Spazio (space) con configurazione centralizzata dall'amministratore Jira. Più opzioni di personalizzazione, condivisione degli schemi tra spazi.

**Componente (Component)**: Sotto-sezione di uno spazio (space) per categorizzare gli elementi di lavoro (es. "Hardware", "Software").

**Condizione (Condition)**: Criterio che deve essere soddisfatto perché un'automazione esegua le sue azioni.

**Confluence**: Piattaforma wiki di Atlassian per la documentazione e la collaborazione.

**Content tree (Albero di navigazione)**: La sidebar di navigazione di uno spazio Confluence che mostra la gerarchia di pagine, live doc e cartelle. Supporta diverse viste: albero, visite recenti, ultimo aggiornamento, ordine alfabetico.

**Cartella (Folder)**: Tipo di contenuto Confluence per organizzare pagine e documenti all'interno di uno spazio. Funziona come una directory per raggruppare contenuti correlati.

## D

**Dashboard**: Pagina personalizzabile con gadget che visualizzano dati da Jira.

**Due Date (Scadenza)**: Data entro cui un work item deve essere completato.

## E

**Epic**: Work item di alto livello che raggruppa altri work item correlati. Rappresenta una funzionalità o un obiettivo grande.

**Espansione (Expand macro)**: Elemento dell'editor Confluence che crea una sezione espandibile/richiudibile. Utile per contenuti opzionali o FAQ. Nota: nel cloud editor non è possibile annidare macro con corpo (bodied macro) all'interno di un'espansione.

**Etichetta (Label)**: Tag testuale libero per categorizzare. In Jira: applicata ai work item (es. "urgente", "onboarding"). In Confluence: applicata a pagine e allegati per organizzare e facilitare la ricerca.

## F

**Filtro (Filter)**: Query JQL salvata che può essere riutilizzata in dashboard, sottoscrizioni e report.

**Filtro rapido (Quick Filter)**: Filtro predefinito visibile sulla board per filtrare rapidamente i work item.

## G

**Gadget**: Componente visuale aggiunto a una dashboard (es. grafico a torta, tabella filtro).

## I

**Issue**: vedi → Work Item

**Issue type**: vedi → Work Type

**Issue type scheme**: Schema che definisce quali tipi di lavoro (work type) sono disponibili in uno spazio (space).

## J

**JQL (Jira Query Language)**: Linguaggio di query per cercare work item in Jira con criteri specifici.

## K

**Kanban**: Metodologia di gestione del lavoro basata sul flusso continuo, visualizzata in una board con colonne.

## L

**Link (Collegamento)**: Relazione tra due work item (es. "blocks", "is blocked by", "relates to").

**Live doc**: Tipo di contenuto Confluence per la collaborazione in tempo reale. A differenza delle pagine, i live doc non hanno un workflow di pubblicazione — le modifiche sono visibili istantaneamente a tutti. Supporta fino a 30 editor simultanei.

## M

**Macro (Confluence)**: Componente inseribile in una pagina Confluence per mostrare contenuti dinamici (es. Jira Work Items macro).

**Menzione (@mention)**: Notifica a un utente tramite `@nome` in un commento o descrizione.

## N

**Notifica (Notification)**: Avviso inviato a un utente quando accade qualcosa di rilevante per un work item.

**Notification scheme**: Schema che definisce chi riceve notifiche per quali eventi in uno spazio (space).

## P

**Pagina (Page)**: Unità di contenuto in Confluence, equivalente a un documento wiki.

**Page ownership (Proprietario di pagina)**: Funzionalità Confluence che assegna un proprietario a ogni pagina. Di default è il creatore. Il proprietario può essere trasferito da owner, space admin o site admin.

**Pannello (Panel element)**: Elemento dell'editor Confluence per evidenziare contenuti con un riquadro colorato. Tipi predefiniti: info (blu), note (viola), success (verde), warning (giallo), error (rosso).

**Permission scheme**: Schema che definisce chi può fare cosa all'interno di uno spazio (space).

**Post-function**: Azione automatica eseguita dopo che una transizione di workflow viene completata. ⚠️ Il vecchio editor di workflow sarà rimosso a giugno 2026: verificare che le post-function siano migrate al nuovo editor.

**Priorità (Priority)**: Livello di urgenza di un work item (Lowest, Low, Medium, High, Critical/Highest).

**Progetto (Project)**: vedi → Spazio (Space)

## R

**Reporter**: La persona che ha creato un work item.

**Risoluzione (Resolution)**: Indica come un work item è stato risolto (Done, Won't Do, Duplicate, etc.).

## S

**Schema (Scheme)**: Configurazione riutilizzabile che collega impostazioni agli spazi (permission, notification, workflow, work type, screen).

**Scrum**: Metodologia agile basata su sprint (iterazioni a tempo fisso).

**Sidebar di navigazione**: La barra di navigazione laterale sinistra di Jira Cloud, introdotta nel 2025. Sostituisce la precedente barra di navigazione superiore. Consente l'accesso rapido a spazi recenti, board, backlog, e impostazioni.

**Smart values**: Variabili dinamiche usate nelle automazioni (es. `{{issue.key}}`, `{{issue.summary}}`, `{{now}}`). Nota: nonostante la UI dica "work item", la sintassi degli smart values usa `{{issue.*}}`. La forma `{{workItem.*}}` non è attualmente supportata.

**Sotto-attività (Sub-task)**: Work item figlio che dipende da un work item padre.

**Sottoscrizione (Subscription)**: Notifica email periodica basata sui risultati di un filtro JQL.

**Smart Link**: Funzionalità Atlassian che genera automaticamente un'anteprima visuale (titolo, stato, icona) quando si incolla un URL di Jira o Confluence in una pagina. Disponibile anche come tipo di contenuto nel content tree di Confluence.

**Spazio (Space)**: In Jira Cloud: **contenitore organizzativo per il lavoro** (in precedenza chiamato "progetto/project"). In Confluence: contenitore per pagine e documentazione. Non confondere i due contesti.

**Space (Spazio Jira)**: Contenitore organizzativo in Jira Cloud (in precedenza "progetto/project"). Non confondere con gli spazi Confluence.

**Sprint**: Iterazione di lavoro a tempo fisso (tipicamente 1-4 settimane) nella metodologia Scrum.

**Status**: Lo stato attuale di un work item nel suo workflow (es. "To Do", "In Progress", "Done").

## T

**Team-managed space**: Spazio (space) con configurazione semplificata gestita dal team. Ogni spazio ha i propri workflow e campi indipendenti.

**Template**: Modello predefinito per creare pagine Confluence o configurazioni di spazio (space).

**Transizione (Transition)**: Passaggio di un work item da uno status a un altro all'interno di un workflow.

**Trigger**: Evento che avvia l'esecuzione di una regola di automazione.

## V

**Validatore (Validator)**: Controllo eseguito durante una transizione di workflow per verificare che certe condizioni siano soddisfatte prima di procedere.

**Versione (Version/Release)**: Marcatore per raggruppare work item associati a un rilascio o milestone.

## W

**Wallboard**: Modalità di visualizzazione a schermo intero di una dashboard.

**Watching (Seguire)**: Funzionalità Confluence per ricevere notifiche quando una pagina o uno spazio viene modificato. Clicca "Watch" sulla pagina per attivarla.

**Whiteboard (Lavagna)**: Tipo di contenuto Confluence per la collaborazione visuale. Permette di creare diagrammi, mappe mentali e schemi utilizzando forme, connettori, note adesive e testo libero. Supporta la collaborazione simultanea.

**Work Item (Elemento di lavoro)**: Unità di lavoro in Jira Cloud (in precedenza chiamata "issue"). Include Epic, Story, Task, Sub-task, Bug e tipi personalizzati.

**Work Type (Tipo di lavoro)**: Classificazione dei work item in Jira Cloud (in precedenza "issue type"). Esempi: Epic, Story, Task, Bug.

**Workflow**: Sequenza di stati e transizioni che definisce il ciclo di vita di un work item. ⚠️ Il vecchio editor di workflow sarà rimosso a giugno 2026.
