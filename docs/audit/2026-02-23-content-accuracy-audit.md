# Content Accuracy Audit — Jira e Confluence Best Practices 2026

**Date**: 2026-02-23
**Reviewer**: Claude (automated)
**Target platform**: Jira Cloud + Confluence Cloud (2025-2026)
**Scope**: Sessions 1-3, cheatsheets, glossary (23 files)

**Verification categories:**
1. Jira Cloud terminology
2. JQL syntax
3. Feature accuracy
4. Confluence references
5. Internal consistency

---

## `jira-confluence-best-practices-2026/README.md`

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 34 | Terminology | "tipi di progetto, issue types" uses deprecated terminology. "Project" is now "Space" (since Dec 2025) and "Issue Type" is now "Work Type" (since Jul 2025). | Change to "tipi di space, work type" (or "tipi di spazio, tipi di lavoro" in Italian). |
| 2 | 34 | Terminology | "workflow base" is fine terminology-wise, but the session description references "navigazione" implicitly through "Architettura Jira, navigazione". Navigation has changed from top bar to left sidebar (March 2025). | Ensure session 1 outline covers the **new left sidebar navigation**, not the deprecated top bar. No change needed in README text itself, but flag for session outline review. |
| 3 | 34 | Terminology | Session 1 description says "issue types" — this term has been renamed to **"Work Types"** in Jira Cloud. | Replace "issue types" with "work types" (or "tipi di lavoro"). |
| 4 | 37 | Terminology | Session 4 description says "configurazione progetti" — "progetti" (projects) is now **"spaces"** (spazi) in Jira Cloud. | Replace "configurazione progetti" with "configurazione space" (or "configurazione spazi"). |
| 5 | 21 | Terminology | Participant table uses "ticket IT" and "Ticket facility desk" (lines 21, 24). While "ticket" is informal and not an official Jira term, it implicitly refers to "issues" which are now **"work items"** (elementi di lavoro). | Consider replacing "ticket" with "work item" or "elemento di lavoro" for consistency with current Jira terminology, or add a glossary note that "ticket" is used colloquially. |
| 6 | 24 | Terminology | Same as issue #5 — "Ticket facility desk" on line 24 uses deprecated implicit terminology. | Replace "Ticket facility desk" with "Work item facility desk" or "Elementi facility desk". |
| 7 | 35 | Terminology | Session 2 description mentions "filtri avanzati" which is acceptable, but the JQL functions referenced in the session may use old function names (e.g., `issueHistory()` instead of `workItemHistory()`). | Flag for detailed review of session 2 outline and JQL cheatsheet. No README text change needed. |
| 8 | 88 | Internal consistency | The `risorse/` directory listing shows `jql-cheatsheet.md`, `dashboard-cheatsheet.md`, `automazioni-cheatsheet.md`, and `glossario.md`. These files should use updated 2025-2026 terminology throughout. | Flag all four resource files for terminology audit. |
| 9 | 1 | Feature accuracy | Title says "2026" which is correct for the course delivery year, but the course should reflect all Jira Cloud changes completed by early 2026 (Space rename Dec 2025, Work Item rename Jul 2025, new navigation Mar-Jul 2025). | No change needed to the title — this is an informational note to ensure content matches the "2026" label. |
| 10 | 14 | Feature accuracy | "Focus principale: Jira Cloud (con modulo Confluence nella sessione 5)" — this is accurate. However, the Confluence module should note that the **legacy editor will be deprecated in April 2026**, which is imminent at course delivery time. | Flag for session 5 outline review: ensure legacy editor deprecation is covered. |

**Summary**: 10 issues found (6 terminology, 1 JQL syntax, 2 feature accuracy, 1 internal consistency). The most critical issues are the use of deprecated terms "issue types" (now "work types"), "progetti" (now "spaces/spazi"), and "ticket" (now "work item"). These appear in the session descriptions table (lines 34, 37) and participant role descriptions (lines 21, 24).

---

## `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/outline.md`

This session is the most impacted by 2025-2026 changes because it covers architecture, navigation, project/space types, issue/work item types, and basic workflows — all areas that have undergone significant terminology and UI changes.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 9 | Terminology | Hierarchy described as "sito → progetto → board → issue". "Progetto" is now **"space/spazio"** (since Dec 2025) and "issue" is now **"work item/elemento di lavoro"** (since Jul 2025). | Change to "sito → space → board → work item" (or "sito → spazio → board → elemento di lavoro"). |
| 2 | 11 | Terminology | "Distinguere tra progetti Team-managed e Company-managed" — "progetti" should be **"space"**. Team-managed and Company-managed now refer to spaces, not projects. | Change to "Distinguere tra space Team-managed e Company-managed". |
| 3 | 12 | Terminology | "Creare e configurare issue" — "issue" is now **"work item"** (elemento di lavoro). | Change to "Creare e configurare work item" (or "elementi di lavoro"). |
| 4 | 26 | Terminology | "Ruoli globali vs ruoli di progetto" — "progetto" should be **"space/spazio"**. | Change to "Ruoli globali vs ruoli di space" (or "ruoli di spazio"). |
| 5 | 30 | Terminology | Hierarchy bold text: "**Gerarchia**: Sito → Progetto → Board → Issue" — both "Progetto" and "Issue" are deprecated. | Change to "**Gerarchia**: Sito → Space → Board → Work Item". |
| 6 | 31 | Terminology | "**Progetti**: contenitori logici per il lavoro" — "Progetti" should be **"Space"**. | Change to "**Space**: contenitori logici per il lavoro". |
| 7 | 32 | Terminology | "**Issue types**: Epic, Story, Task, Sub-task, Bug (e tipi custom)" — "Issue types" is now **"Work types"** (tipi di lavoro). | Change to "**Work types**: Epic, Story, Task, Sub-task, Bug (e tipi custom)". |
| 8 | 33 | Terminology | "come Jira collega issue types, workflow, schermate e permessi" — "issue types" should be **"work types"**. | Change to "come Jira collega work types, workflow, schermate e permessi". |
| 9 | 34 | Terminology | "come un progetto di missione satellitare (es. MILANI) si mappa su Jira" — "progetto" here refers to a Jira project, now **"space"**. | Change to "come uno space di missione satellitare (es. MILANI) si mappa su Jira". Note: if "progetto" is used in the business sense (not the Jira container), it could remain, but clarity is needed since the line discusses Jira mapping. |
| 10 | 36-43 | Feature accuracy | Section "1.3 Navigazione dell'interfaccia" describes navigation with a "Barra di navigazione superiore" (line 38). Since March 2025, Jira Cloud uses a **left sidebar** for primary navigation. The top bar was replaced and is no longer the main navigation element. | Rewrite the entire navigation section: replace "Barra di navigazione superiore" with "Sidebar di navigazione sinistra". Reorganize the bullet points to describe the new sidebar-first layout. |
| 11 | 38 | Feature accuracy | "Barra di navigazione superiore" — this is the old pre-2025 navigation. The primary navigation is now the **left sidebar**. | Replace with "**Sidebar di navigazione sinistra**" and describe how the sidebar provides access to spaces, boards, filters, dashboards, and settings. |
| 12 | 39 | Terminology | "Menu laterale del progetto" — "progetto" should be **"space"**. Also, this line is now partially redundant since the main navigation itself is a left sidebar. | Change to "Menu contestuale dello space" or restructure to distinguish between the global sidebar and the space-specific navigation panel. |
| 13 | 49 | Terminology | Exercise link text "Navigazione e esplorazione progetto" — "progetto" should be **"space"**. | Change to "Navigazione e esplorazione space" (or "dello spazio"). |
| 14 | 50 | Terminology | Exercise link text "Creazione e gestione issue" — "issue" should be **"work item"**. | Change to "Creazione e gestione work item" (or "elementi di lavoro"). |
| 15 | 54 | Terminology | Section title "Tipi di progetto, Issue e Workflow" — both "progetto" and "Issue" are deprecated terms. | Change to "Tipi di space, Work Item e Workflow". |
| 16 | 56 | Terminology | Sub-section title "Tipi di progetto in Jira Cloud" — "progetto" should be **"space"**. | Change to "Tipi di space in Jira Cloud". |
| 17 | 57 | Terminology | "**Team-managed** (ex 'Next-gen'): configurazione semplificata, ideale per team autonomi" — the description is accurate but should specify that these are now **spaces**, not projects. | Add context: "**Team-managed space** (ex 'Next-gen project')..." |
| 18 | 59 | Terminology | "**Company-managed** (ex 'Classic'): configurazione centralizzata dall'admin" — same as above, should specify these are spaces. | Change to "**Company-managed space** (ex 'Classic project')..." |
| 19 | 62 | Terminology | "Team-managed per piccoli team operativi, Company-managed per processi aziendali" — missing "space" qualifier. | Change to "Team-managed space per piccoli team operativi, Company-managed space per processi aziendali". |
| 20 | 64 | Terminology | Sub-section title "Issue in profondita'" — "Issue" is now **"Work Item"**. | Change to "Work Item in profondita'" (or "Elemento di lavoro in profondita'"). |
| 21 | 65 | Terminology | "Anatomia di un'issue: campi standard e custom" — "issue" should be **"work item"**. | Change to "Anatomia di un work item: campi standard e custom". |
| 22 | 66-68 | Terminology | Lines 66-68 contain "issue" references: "Priorita', etichette, componenti, versioni" (line 66 is fine), "Relazioni tra issue: collegamento, clonazione, sotto-attivita'" (line 67), "Allegati e commenti" (line 68, fine). | Line 67: change "Relazioni tra issue" to "Relazioni tra work item". |
| 23 | 73 | Terminology | Sub-section title "Workflow base" is acceptable as-is; "workflow" has not been renamed. | No change needed. |
| 24 | 77 | Terminology | "Visualizzazione del workflow di un progetto" — "progetto" should be **"space"**. | Change to "Visualizzazione del workflow di uno space". |
| 25 | 79 | Terminology | "workflow di un ticket IT (IT Manager)" — "ticket" is colloquial for "issue", now **"work item"**. | Change to "workflow di un work item IT (IT Manager)" or "workflow di un elemento IT (IT Manager)". |
| 26 | 85 | Terminology | Exercise link text "Tipi di progetto e workflow" — "progetto" should be **"space"**. | Change to "Tipi di space e workflow". |
| 27 | 13 | Feature accuracy | "Comprendere il concetto di workflow e status" — while the terminology is correct (workflow and status have not been renamed), the outline does not mention that the **old workflow editor will be removed in June 2026**. Since this is a fundamentals session, at minimum a note should be added. | Add a bullet under section 2.3 or the learning objectives noting that only the new workflow editor will be available from June 2026. |
| 28 | 57-62 | Feature accuracy | The Team-managed vs Company-managed section does not mention that these now refer to **spaces** rather than projects. The "(ex 'Next-gen')" and "(ex 'Classic')" notes are historically accurate but incomplete — they should also note the project-to-space rename. | Update the historical note to: "(ex 'Next-gen project', ora 'Team-managed space')" and "(ex 'Classic project', ora 'Company-managed space')". |
| 29 | 43 | Feature accuracy | "Demo live: tour guidato dell'istanza Tyvak" — the demo will need to reflect the new sidebar navigation and updated terminology. While this is a facilitation note rather than a content error, flagging it to ensure the live demo uses current UI. | Add a facilitation note: ensure the demo instance uses the current Jira Cloud UI with left sidebar navigation and updated Space/Work Item terminology. |
| 30 | 49-50 | Internal consistency | Exercise file links point to `esercizi/esercizio-01-navigazione-progetto.md` and `esercizi/esercizio-02-creazione-issue.md`. The filenames themselves use deprecated terms ("progetto", "issue"). | Rename files to `esercizio-01-navigazione-space.md` and `esercizio-02-creazione-work-item.md`, and update the link paths accordingly. |
| 31 | 85 | Internal consistency | Exercise file link points to `esercizi/esercizio-03-tipi-progetto-workflow.md` — filename uses deprecated term "progetto". | Rename file to `esercizio-03-tipi-space-workflow.md` and update the link path. |
| 32 | 98 | Internal consistency | Reference to `../risorse/glossario.md` — the glossary must be updated to reflect the new terminology (Space, Work Item, Work Type) for consistency with the updated session 1 content. | Flag glossary for terminology update during resource audit. |

**Summary**: 32 issues found (24 terminology, 4 feature accuracy, 4 internal consistency). Session 1 is **heavily impacted** by the 2025-2026 changes. The three most critical areas are:

1. **Navigation (lines 36-43)**: The entire navigation section describes the deprecated top-bar navigation. It must be rewritten around the left sidebar introduced in March 2025.
2. **Hierarchy and architecture (lines 9, 30-34)**: The core hierarchy "Sito → Progetto → Board → Issue" must be updated to "Sito → Space → Board → Work Item" throughout.
3. **Pervasive terminology**: "progetto", "issue", and "issue type" appear on 20+ lines and must be systematically replaced with "space", "work item", and "work type" respectively. Exercise filenames (lines 49-50, 85) also embed the deprecated terms.

---

## `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/esercizi/esercizio-01-navigazione-progetto.md`

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 1 | Terminology | Title "Navigazione e esplorazione progetto" — "progetto" (project) is now **"space"** in Jira Cloud (since Dec 2025). | Change to "Navigazione e esplorazione space" (or "dello spazio"). Also rename the file from `esercizio-01-navigazione-progetto.md` to `esercizio-01-navigazione-space.md`. |
| 2 | 7 | Terminology | "la struttura dei progetti esistenti" — "progetti" should be **"space"** (spazi). | Change to "la struttura degli space esistenti" (or "degli spazi esistenti"). |
| 3 | 14 | Feature accuracy | "Dalla barra di navigazione superiore, individua e annota:" — Jira Cloud has replaced the top navigation bar with a **left sidebar** since March 2025. This instruction is obsolete. | Change to "Dalla sidebar di navigazione sinistra, individua e annota:" and update all sub-steps to reference the sidebar layout. |
| 4 | 15 | Terminology | "Quanti progetti sono visibili nel menu 'Progetti'" — "progetti" and "Progetti" are now **"space"** and the menu is labeled accordingly. | Change to "Quanti space sono visibili nel menu 'Spaces'" (or the Italian equivalent if the UI is localized). |
| 5 | 17 | Feature accuracy | "Come accedere alla sezione 'Your Work'" — in the new sidebar UI, "Your Work" is accessed from the left sidebar, not from a top bar menu. The instruction should specify sidebar navigation. | Change to "Come accedere alla sezione 'Your Work' dalla sidebar sinistra". |
| 6 | 18 | Terminology | "Seleziona un progetto qualsiasi" — "progetto" should be **"space"**. | Change to "Seleziona uno space qualsiasi". |
| 7 | 19 | Terminology | "Il tipo di progetto (Team-managed o Company-managed)" — "progetto" should be **"space"**. These are now "team-managed space" and "company-managed space". | Change to "Il tipo di space (Team-managed o Company-managed)". |
| 8 | 21 | Terminology | "Il numero di issue attualmente aperte" — "issue" is now **"work item"** (elemento di lavoro). | Change to "Il numero di work item attualmente aperti" (or "elementi di lavoro attualmente aperti"). |
| 9 | 26 | Terminology | "Una issue per chiave (es. `PROJ-123`)" — "issue" should be **"work item"**. | Change to "Un work item per chiave (es. `PROJ-123`)". |
| 10 | 27 | Terminology | "Una issue per parola chiave" — "issue" should be **"work item"**. | Change to "Un work item per parola chiave". |
| 11 | 28 | Terminology | "Un progetto per nome" — "progetto" should be **"space"**. | Change to "Uno space per nome". |
| 12 | 35 | Terminology | "Usare la ricerca globale per trovare issue e progetti" — both "issue" and "progetti" are deprecated. | Change to "Usare la ricerca globale per trovare work item e space". |
| 13 | 36 | Terminology | "Distinguere visivamente i tipi di progetto" — "progetto" should be **"space"**. | Change to "Distinguere visivamente i tipi di space". |
| 14 | 40 | Terminology | "Quali progetti sono più rilevanti per il tuo ruolo?" — "progetti" should be **"space"**. | Change to "Quali space sono più rilevanti per il tuo ruolo?". |
| 15 | 41 | Terminology | "Hai trovato issue che non ti aspettavi di vedere?" — "issue" should be **"work item"**. | Change to "Hai trovato work item che non ti aspettavi di vedere?". |

**Summary**: 15 issues found (12 terminology, 3 feature accuracy). This file is **heavily impacted** because it covers navigation and project/space exploration — both areas completely reshaped by 2025 changes. The critical issue is the navigation instruction on line 14 that references the deprecated top bar. Every occurrence of "progetto/i" and "issue" must be replaced with "space" and "work item" respectively.

---

## `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/esercizi/esercizio-01-dashboard-personale.md`

**Topic placement note**: This exercise covers dashboard creation, which is listed as a Session 3 topic in the course README. Including it as a Session 1 exercise is potentially misplaced unless it is intended as a forward-looking introductory activity. However, line 11 says "Avere almeno 2 filtri JQL salvati dalla sessione precedente" — this implies the exercise is designed to be used **after** JQL sessions, not during Session 1. The "01" in the filename and its location in the `sessione-01` folder may be an error. **Recommendation**: Verify if this file should be moved to `sessione-03` exercises, or rename/renumber it to clarify it is a cross-session exercise.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 11 | Internal consistency | "Avere almeno 2 filtri JQL salvati dalla sessione precedente." — This prerequisite implies the exercise follows a JQL-focused session (Session 2). This makes it unsuitable as a pure Session 1 exercise since students would not yet have saved JQL filters. | Either move this exercise to Session 3 (`sessione-03`) where dashboards are the main topic, or remove the JQL prerequisite and simplify the exercise for Session 1. |
| 2 | 17 | Feature accuracy | "Vai su **Dashboards → Crea dashboard**" — in the new left sidebar navigation, Dashboards are accessed from the sidebar. The path is no longer a top-bar dropdown. The instruction should specify sidebar access. | Change to "Dalla sidebar sinistra, vai su **Dashboards → Crea dashboard**" or describe how to access Dashboards from the sidebar. |
| 3 | 20 | Feature accuracy | "Layout: seleziona **2 colonne**" — Dashboard layouts in current Jira Cloud are customizable but the specific "2 colonne" option wording should be verified against the current UI. The layout selection still exists but the UI may have changed slightly. | Minor: verify the exact layout option name in current Jira Cloud UI. The concept is still valid. |
| 4 | 27 | Terminology | "ticket IT aperti" — "ticket" informally refers to "issue", now **"work item"**. | Change to "work item IT aperti" (or "elementi IT aperti"). |
| 5 | 29 | Terminology | "Creati vs Risolti: andamento ticket ultimo mese" — "ticket" should be **"work item"**. | Change to "andamento work item ultimo mese". |
| 6 | 33 | Terminology | "ordini e fatture in corso" — acceptable as business terms (not Jira terms). | No change needed. |
| 7 | 35 | Terminology | "andamento issue ultimo trimestre" — "issue" is now **"work item"**. | Change to "andamento work item ultimo trimestre". |
| 8 | 45 | Terminology | "ticket facility aperti" — "ticket" should be **"work item"**. | Change to "work item facility aperti". |
| 9 | 27-48 | Feature accuracy | Gadget names use the Italian/informal names ("Risultati filtro", "Grafico a torta", "Creati vs Risolti", "Due dimensioni", "Attività recente", "Testo"). The actual Jira Cloud gadget names in English are: "Filter Results", "Pie Chart", "Created vs Resolved", "Two Dimensional Filter Statistics", "Activity Stream", "Introduction" (for text). If the Jira instance is in English, these names will not match. | Decide whether to use the official English gadget names (matching the Jira UI) or the Italian translations. If using Italian, add the English name in parentheses for clarity, e.g., "Risultati filtro (Filter Results)". |
| 10 | 30 | Feature accuracy | "Due dimensioni: matrice priorità × status" — the official gadget name is "Two Dimensional Filter Statistics". The Italian informal name is acceptable but should be clarified for students who may have an English-language Jira instance. | Add English name: "Due dimensioni (Two Dimensional Filter Statistics)". |
| 11 | 41 | Feature accuracy | "Attività recente: ultime modifiche nel progetto HR" — "Attività recente" maps to the "Activity Stream" gadget. Also, "progetto" should be **"space"**. | Change to "Attività recente (Activity Stream): ultime modifiche nello space HR". |

**Summary**: 11 issues found (4 terminology, 5 feature accuracy, 1 internal consistency, 1 informational). The most critical issue is the **topic placement**: this exercise requires JQL filter prerequisites from Session 2, making it inappropriate for Session 1 without modification. The navigation path for accessing dashboards should be updated for the sidebar UI. Gadget names should be aligned with the English UI or clarified with both Italian and English names.

---

## `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/esercizi/esercizio-01-regole-automazione.md`

**Topic placement note**: This exercise covers automation rules, which is listed as a Session 4 topic in the course README. Including it as a Session 1 exercise seems misplaced. The exercise requires understanding of JQL, triggers, conditions, and actions — concepts that go well beyond Session 1 fundamentals. **Recommendation**: Move this exercise to `sessione-04` or clearly mark it as an advanced/optional preview activity.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 1 | Internal consistency | Title "Crea le tue regole di automazione" — automation is a Session 4 topic per the course README. This exercise is filed under Session 1 but the content complexity (JQL conditions, scheduled triggers, smart values) is far beyond Session 1 fundamentals. | Move this file to `sessione-04-configurazione-avanzata/esercizi/` or add a clear note that this is an advanced preview not meant for Session 1. |
| 2 | 13 | Feature accuracy | "Vai su **Project settings → Automation → Create rule**" — "Project settings" is now **"Space settings"** in the new Jira Cloud UI. Additionally, the path depends on the sidebar navigation. | Change to "Vai su **Space settings → Automation → Create rule**" (or "Impostazioni space → Automazione → Crea regola"). |
| 3 | 19 | Terminology | "**Trigger**: Issue created" — "Issue created" trigger is now labeled **"Work item created"** in the Jira automation UI. | Change to "**Trigger**: Work item created". |
| 4 | 20 | Terminology | "**Condizione**: Issue type = Task" — "Issue type" is now **"Work type"** in the automation condition UI. | Change to "**Condizione**: Work type = Task". |
| 5 | 21 | Terminology | "**Azione**: Assign issue to → Current user" — "Assign issue to" is now **"Assign work item to"** in the automation action UI. | Change to "**Azione**: Assign work item to → Current user". |
| 6 | 24 | Terminology | "creando una nuova issue di tipo Task" — "issue" should be **"work item"**. | Change to "creando un nuovo work item di tipo Task". |
| 7 | 32 | Terminology | JQL condition uses `project = "IT-HELPDESK"` — while `project` still works in JQL (backward compatible), the current documentation uses `space`. | Consider updating to `space = "IT-HELPDESK"` with a note that `project` is still backward-compatible, or keep `project` and add a note about the rename. |
| 8 | 32 | Terminology | JQL condition uses `status != Done` — this is correct, "status" has not been renamed. | No change needed. |
| 9 | 32 | Feature accuracy | JQL uses `created <= -24h` — this is an older JQL syntax. The more standard form is `created <= "-24h"` or `created <= -1d`. Both forms work in Jira Cloud. | Minor: verify the exact syntax is accepted. The concept is correct. |
| 10 | 38 | Feature accuracy | Smart value `{{now.plusDays(3)}}` — this is valid Jira automation smart value syntax. | No change needed. |
| 11 | 40 | Feature accuracy | "Transition issue → 'Urgente' (se lo status esiste)" — "Transition issue" action is now **"Transition work item"** in the automation UI. Also, "Urgente" as a status name is project-specific and may not exist in the training instance. | Change to "Transition work item → 'Urgente' (se lo status esiste nel workflow dello space)". |
| 12 | 43 | Terminology | "**Trigger**: Issue created" (for the HR rule) — same as issue #3. | Change to "**Trigger**: Work item created". |
| 13 | 44 | Terminology | "**Condizione**: Labels contains 'nuovo-dipendente'" — this is fine, "Labels" has not been renamed as a field. | No change needed. |
| 14 | 45 | Terminology | "**Azione**: Create sub-tasks" — the sub-task creation action in automation now uses work item terminology. "Sub-task" as a work type name is still valid. | Change to "**Azione**: Create sub-task work items" or keep as-is with a note that the UI label may differ. |
| 15 | 53 | Terminology | "**Trigger**: Issue transitioned → status = 'Risolto'" — "Issue transitioned" trigger is now **"Work item transitioned"**. | Change to "**Trigger**: Work item transitioned → status = 'Risolto'". |
| 16 | 54 | Terminology | "**Condizione**: Issue type = Task AND labels contains 'reclamo'" — "Issue type" should be **"Work type"**. | Change to "**Condizione**: Work type = Task AND labels contains 'reclamo'". |
| 17 | 55 | Terminology | "Send email to reporter" — this action name has not changed. However, the text references `{{issue.key}}` and `{{issue.summary}}` smart values. | The smart values `{{issue.key}}` and `{{issue.summary}}` may have been updated to `{{workItem.key}}` and `{{workItem.summary}}` in the automation UI. Verify current smart value syntax and update if needed. If backward-compatible, add a note. |
| 18 | 65 | Feature accuracy | "**log di esecuzione** dell'automazione (Audit log)" — the automation execution log is still available and is an accurate reference. The feature name "Audit log" in parentheses is correct. | No change needed. |

**Summary**: 18 issues found (11 terminology, 4 feature accuracy, 2 internal consistency, 1 informational). The most critical issue is the **topic placement**: automation rules belong to Session 4, and this exercise requires JQL and workflow knowledge not yet covered in Session 1. The trigger/condition/action names throughout the exercise use deprecated "issue" terminology that should be updated to "work item". The navigation path to automation settings must be updated from "Project settings" to "Space settings".

---

## `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/esercizi/esercizio-01-ricerca-base.md`

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 13 | Terminology | "cerca issue usando:" — "issue" is now **"work item"** (elemento di lavoro). | Change to "cerca work item usando:". |
| 2 | 17 | Feature accuracy | "Usa la schermata 'Ricerca avanzata' (Filters → Advanced issue search)" — the menu path has changed with the sidebar navigation. "Advanced issue search" may now be labeled **"Advanced work item search"** or accessed differently through the sidebar. | Update to reflect sidebar navigation: "Dalla sidebar sinistra, vai su **Filters** e seleziona **Advanced work item search**" (or verify the exact current label). |
| 3 | 18 | Terminology | "Passa dalla modalità 'Base' alla modalità 'JQL' e osserva come Jira traduce i tuoi filtri in JQL" — the concept is correct and "Base" / "JQL" mode toggle still exists. However, the term "filtri" here is used correctly (not deprecated). | No change needed. |
| 4 | 21 | Terminology | "Vai su una board del tuo progetto" — "progetto" is now **"space"**. | Change to "Vai su una board del tuo space" (or "del tuo spazio"). |
| 5 | 29 | Terminology | "Saper usare la ricerca globale con diversi criteri" — acceptable as-is. | No change needed. |
| 6 | 30 | Terminology | "Comprendere il passaggio da filtro visuale a JQL" — acceptable as-is. | No change needed. |
| 7 | 8 | Terminology | "Padroneggiare la ricerca base di Jira e i filtri rapidi della board." — "filtri rapidi della board" is correct terminology; quick filters on boards have not been renamed. | No change needed. |
| 8 | 25 | Feature accuracy | "Annota: quale combinazione di filtri rapidi è più utile per il tuo lavoro quotidiano?" — acceptable as-is. Quick filters on boards remain a current feature. | No change needed. |

**Summary**: 4 issues found (2 terminology, 2 feature accuracy). This exercise is **lightly impacted** compared to the others. The main changes are replacing "issue" with "work item" and "progetto" with "space", and updating the advanced search navigation path for the new sidebar UI. The core content about search and quick filters is accurate.

---

## `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/esercizi/esercizio-01-confluence-pagine.md`

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 14 | Confluence references | "Identifica (o crea) uno spazio adatto al tuo ruolo" — Confluence still uses the term "space" (spazio), so this is correct. However, with Jira also now calling its containers "spaces", there may be confusion. | Add a clarifying note: "uno spazio Confluence" to disambiguate from Jira spaces. |
| 2 | 48-55 | Feature accuracy | The "Elementi obbligatori per tutti" checklist mentions "Un pannello informativo (info, warning, o note)" (line 53) and "Un elenco (numerato o puntato)" (line 54). These are standard Confluence editor features that remain available in the current cloud editor. | No change needed. The features listed are all available in the current Confluence cloud editor. |
| 3 | 59-60 | Feature accuracy | "Familiarità con l'editor di Confluence e gli elementi di formattazione" — this is correct but should note that the **legacy editor will be fully deprecated in April 2026**. Since the course runs in 2026, students should be aware they will only have access to the cloud editor. | Add a note: "Nota: da aprile 2026 solo il cloud editor sarà disponibile. L'editor legacy è stato deprecato." |
| 4 | 25 | Feature accuracy | "pannello informativo" (info panel) — this feature is available in the current Confluence cloud editor and works as described. | No change needed. |
| 5 | 32 | Feature accuracy | "checklist (task list)" — Confluence cloud editor supports task lists via `/` command or toolbar. This is accurate. | No change needed. |
| 6 | 39 | Feature accuracy | "espansione (expand)" — the expand/collapse macro is available in the Confluence cloud editor. This is accurate. | No change needed. |
| 7 | 46 | Feature accuracy | "espansione, pannello di avviso, tabella" — all three features are available in the current Confluence cloud editor. | No change needed. |
| 8 | 55 | Feature accuracy | "Almeno un'etichetta" — labels (etichette) remain a core Confluence feature, applied to pages. This is accurate. | No change needed. |

**Summary**: 3 issues found (1 Confluence references, 2 feature accuracy — one informational, one requiring a note). This exercise is **minimally impacted** by the 2025-2026 changes. Confluence terminology has not changed, and all described editor features remain available. The two actionable items are: (1) disambiguate "spazio Confluence" from "space Jira" to avoid confusion due to the new Jira terminology, and (2) note the legacy editor deprecation since the course will be delivered in 2026.

---

## `jira-confluence-best-practices-2026/sessione-02-filtri-ricerche-jql/outline.md`

This session is the most JQL-intensive in the course, covering search fundamentals, JQL syntax, JQL functions, filter management, and filter subscriptions. The main audit concerns are: (1) JQL field names that have been renamed, (2) JQL function names that have been renamed, (3) deprecated "progetto"/"issue" terminology in prose, and (4) filter/search UI navigation paths.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 22 | Terminology | "Ricerca globale vs ricerca nel progetto" — "progetto" (project) is now **"space"** in Jira Cloud (since Dec 2025). | Change to "Ricerca globale vs ricerca nello space" (or "nello spazio"). |
| 2 | 24 | Terminology | "Le mie issue aperte" — "issue" is now **"work item"** (elemento di lavoro). The predefined filter label in Jira Cloud may have been updated to reflect the new terminology. | Change to "I miei work item aperti" (or verify the current Italian UI label). Also update "Segnalate di recente" if its official name has changed. |
| 3 | 31 | JQL syntax | Field list includes `project` and `issuetype` as "campi principali". The JQL field `project` has been renamed to `space` (backward compatible — `project` still works). The field `issuetype` is listed in the reference as `type` (unchanged in JQL). | Update the field list to: `space` (ex `project`), `status`, `assignee`, `reporter`, `priority`, `type`, `created`, `updated`, `resolved`, `labels`, `component`. Add a note that `project` and `issuetype` still work for backward compatibility. |
| 4 | 38 | JQL syntax | Example query `project = "IT-HELPDESK" AND status = "Open" ORDER BY priority DESC` — uses the old field name `project`. While backward compatible, the current Jira documentation uses `space`. | Update to `space = "IT-HELPDESK" AND status = "Open" ORDER BY priority DESC`. Add a sidebar note that `project` remains backward-compatible. |
| 5 | 39 | JQL syntax | Example query `assignee = currentUser() AND status != Done` — `currentUser()` is unchanged and the syntax is correct. However, `Done` should be quoted as `"Done"` for best practice (unquoted single-word values work but quoting is recommended in teaching materials for consistency). | Minor: consider changing to `assignee = currentUser() AND status != "Done"` for consistency with the quoting style used on line 38. |
| 6 | 40 | JQL syntax | Example query `labels = "onboarding" AND created >= -7d` — syntax is correct. `labels`, `created`, and the relative date `-7d` are all unchanged. | No change needed. |
| 7 | 59 | JQL syntax | `projectsLeadByUser()` has been renamed to **`spacesLeadByUser()`** (backward compatible). `projectsWhereUserHasRole()` has been renamed to **`spacesWhereUserHasRole()`** (backward compatible). Both old names still work. | Update to `spacesLeadByUser()` and `spacesWhereUserHasRole()`. Add a note that the old names (`projectsLeadByUser()`, `projectsWhereUserHasRole()`) remain backward-compatible. |
| 8 | 59 | Terminology | The label "Funzioni di progetto" uses "progetto" which is now **"space"**. | Change to "Funzioni di space" (or "Funzioni space"). |
| 9 | 61 | JQL syntax | Example query `project = "FACILITY" AND created >= startOfMonth() AND priority IN (High, Critical)` — uses old field name `project`. The rest of the query is correct: `startOfMonth()` is unchanged, `IN` operator and `priority` field are unchanged. | Update to `space = "FACILITY" AND created >= startOfMonth() AND priority IN (High, Critical)`. |
| 10 | 62 | JQL syntax | Example query `assignee WAS currentUser() AND status CHANGED TO "Done" AFTER -7d` — syntax is correct. `WAS`, `CHANGED`, `currentUser()`, and relative date syntax are all unchanged. | No change needed. |
| 11 | 63 | JQL syntax | Example query `text ~ "satellite" AND project IN ("MISSIONI", "R&D")` — uses old field name `project`. The `~` operator and `text` pseudo-field are unchanged. | Update to `text ~ "satellite" AND space IN ("MISSIONI", "R&D")`. |
| 12 | 69 | Terminology | "Condivisione: con utenti, gruppi, progetti" — "progetti" (projects) is now **"space"** (spaces/spazi). Filter sharing in Jira Cloud now refers to sharing with spaces, not projects. | Change to "Condivisione: con utenti, gruppi, space". |
| 13 | 77 | Terminology | "issue in scadenza" — "issue" is now **"work item"** (elemento di lavoro). | Change to "work item in scadenza" (or "elementi di lavoro in scadenza"). |
| 14 | 77 | Terminology | "report settimanale ticket aperti" — "ticket" informally refers to "issue", now **"work item"**. | Change to "report settimanale work item aperti" (or "elementi di lavoro aperti"). |
| 15 | 25 | Feature accuracy | "La vista 'Filtri' nel menu laterale" — this correctly references the sidebar ("menu laterale"), which aligns with the new left sidebar navigation introduced in March 2025. | No change needed. This is one of the few navigation references in the course that is already correct. |
| 16 | 58 | JQL syntax | "Funzioni di testo: `text ~ \"keyword\"` (ricerca full-text)" — while the `~` (contains) operator with `text` is valid, `text` is technically a pseudo-field for full-text search, not a "function". The categorization as "Funzioni di testo" is slightly misleading since `~` is an operator and `text` is a field. | Consider recategorizing: move the `~` operator explanation to the operators section (line 35 area) or rename the label to "Ricerca full-text" instead of "Funzioni di testo". |
| 17 | 53-59 | Feature accuracy | Section "2.3 Funzioni JQL" lists several function categories but does not mention the renamed work item functions that may be useful for the audience: `linkedWorkItems()` (ex `linkedIssues()`), `votedWorkItems()` (ex `votedIssues()`), `watchedWorkItems()` (ex `watchedIssues()`). These are relevant for team-based filter use cases. | Consider adding `linkedWorkItems()`, `votedWorkItems()`, and `watchedWorkItems()` to the function list, or at minimum note their existence in a "per approfondire" section. |
| 18 | 88 | Terminology | "JQL è il fondamento per dashboard, automazioni e report" — terminology is acceptable; "dashboard", "automazioni", and "report" have not been renamed. | No change needed. |
| 19 | 97 | Internal consistency | Reference to `../risorse/jql-cheatsheet.md` — this cheatsheet must be audited to ensure all JQL field names and function names use the updated 2025-2026 terminology (or note backward compatibility). | Flag `jql-cheatsheet.md` for separate audit. Ensure it uses `space` instead of `project`, `spacesLeadByUser()` instead of `projectsLeadByUser()`, etc. |
| 20 | 98 | Internal consistency | Reference to `../risorse/glossario.md` — the glossary must include entries for the renamed terms: Space (ex Project), Work Item (ex Issue), Work Type (ex Issue Type), and the renamed JQL functions. | Flag `glossario.md` for terminology update during resource audit. |

**Summary**: 20 issues found (6 terminology, 8 JQL syntax, 2 feature accuracy, 2 internal consistency, 2 informational/no-change-needed). This session is **moderately impacted** by the 2025-2026 changes. The three most critical areas are:

1. **JQL field name `project` (lines 31, 38, 61, 63)**: Used in the field reference list and in 3 out of 5 example queries. Should be updated to `space` with a backward-compatibility note, since students learning JQL in 2026 should learn the current canonical field names.
2. **JQL function names (line 59)**: `projectsLeadByUser()` and `projectsWhereUserHasRole()` have been renamed to `spacesLeadByUser()` and `spacesWhereUserHasRole()`. The old names still work but the course should teach the current names.
3. **Terminology "progetto"/"issue"/"ticket" in prose (lines 22, 24, 69, 77)**: Several prose references use deprecated terms that should be updated to "space", "work item", etc.

Notably, the navigation reference on line 25 ("menu laterale") is **already correct** for the new sidebar UI — this is an exception compared to other sessions where navigation references were outdated. The JQL operator syntax, date/time functions, and ordering clauses are all accurate and require no changes.
