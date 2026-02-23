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

---

## `jira-confluence-best-practices-2026/sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-gadget-grafici.md`

**Topic placement note**: This exercise covers dashboard gadget configuration and chart interpretation. According to the course README, dashboards, gadgets, and charts are **Session 3** topics ("Dashboard, Grafici e Analytics"). Placing this exercise in Session 2 (Filters & JQL) is **potentially misplaced**. Students have not yet been introduced to dashboard creation or gadget concepts in Session 2. **Recommendation**: Move this file to `sessione-03-dashboard-grafici-analytics/esercizi/` and renumber it accordingly.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 1 | Internal consistency | Exercise title "Gadget e grafici" covers a Session 3 topic (Dashboard, Grafici e Analytics), not Session 2 (Filtri, Ricerche e JQL). The exercise assumes a dashboard was already created "nell'esercizio precedente" (line 13), which is not part of Session 2 outline. | Move this exercise to `sessione-03-dashboard-grafici-analytics/esercizi/` and renumber. Alternatively, if kept in Session 2, add a prerequisite note explaining it bridges to Session 3 content. |
| 2 | 15 | Terminology | "Grafico 'Creati vs Risolti'" — the official gadget name in Jira Cloud 2026 is **"Created vs Resolved"**. The gadget now tracks "work items created vs resolved", not "issues". | Change to "Grafico **Created vs Resolved** (Creati vs Risolti)" to match the official gadget name. |
| 3 | 16 | Terminology | "Collegalo a un filtro che copra il tuo progetto" — "progetto" (project) is now **"space"** (spazio) in Jira Cloud since Dec 2025. | Change to "Collegalo a un filtro che copra il tuo space" (or "il tuo spazio"). |
| 4 | 21 | Terminology | "Gadget 'Due dimensioni'" — the official gadget name is **"Two Dimensional Filter Statistics"**. | Change to "Gadget **Two Dimensional Filter Statistics** (Due dimensioni)" to match the official name. |
| 5 | 24 | Terminology | "tutte le issue del tuo progetto" — both "issue" and "progetto" are deprecated. "Issue" is now **"work item"** (since Jul 2025) and "progetto" is now **"space"** (since Dec 2025). | Change to "tutti i work item del tuo space". |
| 6 | 25 | Terminology | "ci sono issue ad alta priorità bloccate in uno status?" — "issue" should be **"work item"**. | Change to "ci sono work item ad alta priorità bloccati in uno status?". |
| 7 | 37 | Terminology | "il team riesce a gestire il carico di lavoro?" — acceptable as-is, no deprecated terms. | No change needed. |
| 8 | 38 | Terminology | "ci sono pattern problematici? (es. molte issue Critical in 'To Do')" — "issue" should be **"work item"**. | Change to "molti work item Critical in 'To Do'". |
| 9 | 30 | Terminology | "KPI target (es. 'Obiettivo: risolvere ticket critici entro 24h')" — "ticket" informally refers to "issue", now **"work item"**. | Change to "risolvere work item critici entro 24h" (or "elementi critici entro 24h"). |
| 10 | 27-31 | Feature accuracy | The "Gadget 'Testo'" described here maps to the **"Introduction"** gadget in Jira Cloud (not a generic "Text" gadget). The Introduction gadget allows HTML content, titles, and links. | Clarify: "Gadget **Introduction** (Testo introduttivo)" to match the official name. |
| 11 | 43 | Terminology | "3 nuovi gadget aggiunti alla dashboard" — acceptable; "gadget" and "dashboard" are not deprecated. | No change needed. |

**Summary**: 11 issues found (7 terminology, 2 feature accuracy, 1 internal consistency, 1 informational). The **most critical issue** is the topic placement: this exercise belongs in Session 3, not Session 2. The gadget names should use the official English names (with Italian in parentheses for clarity). All references to "issue" must be updated to "work item" and "progetto" to "space".

---

## `jira-confluence-best-practices-2026/sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-jql-fondamentali.md`

This exercise is **correctly placed** in Session 2 (Filtri, Ricerche e JQL). It covers JQL query writing, which is the core topic of this session.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 11 | Feature accuracy | "Vai su **Filters → Advanced issue search**" — the menu item may now be labeled **"Advanced work item search"** in the Jira Cloud UI. Additionally, the navigation should specify sidebar access. | Change to "Dalla sidebar sinistra, vai su **Filters** e seleziona **Advanced work item search**" (or verify the exact current label). |
| 2 | 11 | Terminology | "passa alla modalità JQL" — correct; the JQL toggle mode has not been renamed. | No change needed. |
| 3 | 17 | Terminology | "Trova tutte le issue del progetto di training" — "issue" is now **"work item"** and "progetto" is now **"space"**. | Change to "Trova tutti i work item dello space di training". |
| 4 | 19 | JQL syntax | `project = "___"` — the JQL field `project` has been renamed to `space` (backward compatible). Students learning JQL in 2026 should use the current canonical field name. | Change to `space = "___"`. Add a note that `project` still works for backward compatibility. |
| 5 | 22 | Terminology | "Trova tutte le issue assegnate a te" — "issue" should be **"work item"**. | Change to "Trova tutti i work item assegnati a te". |
| 6 | 27 | Terminology | "Trova tutte le issue con priorità High o Critical" — "issue" should be **"work item"**. | Change to "Trova tutti i work item con priorità High o Critical". |
| 7 | 34 | Terminology | "Trova le issue aperte (non 'Done') assegnate a te" — "issue" should be **"work item"**. | Change to "Trova i work item aperti (non 'Done') assegnati a te". |
| 8 | 39 | Terminology | "Trova tutte le issue con etichetta 'onboarding'" — "issue" should be **"work item"**. | Change to "Trova tutti i work item con etichetta 'onboarding'". |
| 9 | 44 | Terminology | "Trova le issue di tipo Task o Bug nel tuo progetto" — "issue" should be **"work item"** and "progetto" should be **"space"**. | Change to "Trova i work item di tipo Task o Bug nel tuo space". |
| 10 | 46 | JQL syntax | `project = "___" AND issuetype IN (___) AND created >= startOfMonth()` — uses old field names `project` and `issuetype`. The field `project` is now `space`; `issuetype` is documented as `type` (unchanged but the alias `issuetype` is deprecated in documentation). | Change to `space = "___" AND type IN (___) AND created >= startOfMonth()`. |
| 11 | 51 | Terminology | "Trova tutti i ticket IT aperti" — "ticket" informally refers to "issue", now **"work item"**. | Change to "Trova tutti i work item IT aperti". |
| 12 | 52 | Terminology | "Trova tutte le issue con etichetta 'fatturazione' o 'acquisti' non ancora completate" — "issue" should be **"work item"**. | Change to "Trova tutti i work item con etichetta 'fatturazione' o 'acquisti' non ancora completati". |
| 13 | 53 | Terminology | "Trova le issue di tipo Story relative all'onboarding" — "issue" should be **"work item"**. | Change to "Trova i work item di tipo Story relativi all'onboarding". |
| 14 | 54 | Terminology | "Trova i ticket di manutenzione con priorità >= Medium, assegnati a te" — "ticket" should be **"work item"**. | Change to "Trova i work item di manutenzione con priorità >= Medium, assegnati a te". |
| 15 | 58 | Terminology | "10 query JQL scritte e funzionanti" — acceptable; "query JQL" is correct terminology. | No change needed. |

**Summary**: 15 issues found (11 terminology, 2 JQL syntax, 2 feature accuracy). This exercise is **correctly placed** in Session 2. The core JQL syntax taught (operators `=`, `!=`, `IN`, `>=`, `ORDER BY`, `currentUser()`, `startOfMonth()`, relative dates) is all accurate and unchanged. The main issues are: (1) pervasive use of "issue" (11 occurrences) which should be "work item", (2) the JQL field `project` should be updated to `space`, and (3) `issuetype` should be updated to `type`. The exercise structure and pedagogical approach are sound.

---

## `jira-confluence-best-practices-2026/sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-creazione-issue.md`

**Topic placement note**: This exercise covers creating and managing work items (issues), including setting fields, creating sub-tasks, linking items, and adding comments. Work item creation is a **Session 1** topic ("Fondamenti di Jira Cloud" — which covers architecture, work types, and basic workflow). Placing it in Session 2 (Filters & JQL) seems **misplaced** unless it is intended as a warmup to generate data for JQL exercises. **Recommendation**: Move this to `sessione-01-fondamenti-jira/esercizi/` or add a clear note explaining that this exercise generates data that the subsequent JQL exercises will query.

**Terminology note**: The filename itself uses deprecated terminology: `esercizio-02-creazione-issue.md`. The term "issue" is now "work item". Consider renaming to `esercizio-02-creazione-work-item.md`.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 1 | Terminology | Title "Creazione e gestione issue" — "issue" is now **"work item"** (elemento di lavoro) since Jul 2025. | Change to "Creazione e gestione work item" (or "elementi di lavoro"). Also rename file to `esercizio-02-creazione-work-item.md`. |
| 2 | 7 | Terminology | "Creare issue complete con tutti i campi rilevanti e comprendere le relazioni tra issue." — two occurrences of "issue" should be **"work item"**. | Change to "Creare work item completi con tutti i campi rilevanti e comprendere le relazioni tra work item." |
| 3 | 11 | Terminology | "Stai lavorando al progetto di supporto interno" — "progetto" (project) is now **"space"** in Jira Cloud. | Change to "Stai lavorando allo space di supporto interno". |
| 4 | 15 | Terminology | "Creazione issue per ruolo" — "issue" should be **"work item"**. | Change to "Creazione work item per ruolo". |
| 5 | 17 | Terminology | "Crea **2 issue** nel progetto di training" — "issue" should be **"work item"** and "progetto" should be **"space"**. | Change to "Crea **2 work item** nello space di training". |
| 6 | 38 | Terminology | "Tipo di issue (Task, Bug, Story)" — "Tipo di issue" is now **"Work type"** (tipo di lavoro). | Change to "Work type (Task, Bug, Story)" or "Tipo di lavoro (Task, Bug, Story)". |
| 7 | 43 | Terminology | "Relazioni tra issue" — "issue" should be **"work item"**. | Change to "Relazioni tra work item". |
| 8 | 45 | Terminology | "Crea una **sotto-attività** per una delle tue issue" — "issue" should be **"work item"**. The term "sotto-attività" (sub-task) is still valid as a work type. | Change to "Crea una **sotto-attività** per uno dei tuoi work item". |
| 9 | 46 | Terminology | "**Collega** le due issue tra loro con 'is related to'" — "issue" should be **"work item"**. | Change to "**Collega** i due work item tra loro con 'is related to'". |
| 10 | 51 | Terminology | "2 issue create correttamente" — "issue" should be **"work item"**. | Change to "2 work item creati correttamente". |
| 11 | 52 | Terminology | "1 sotto-attività collegata" — acceptable; "sotto-attività" (sub-task) is still a valid work type name. | No change needed. |
| 12 | 53 | Terminology | "1 relazione tra issue" — "issue" should be **"work item"**. | Change to "1 relazione tra work item". |
| 13 | 1 | Internal consistency | Exercise is placed in `sessione-02-filtri-ricerche-jql/` but covers work item creation, which is a Session 1 (Fondamenti) topic, not a Session 2 (Filtri & JQL) topic. | Move to `sessione-01-fondamenti-jira/esercizi/` or add a note explaining this is a data-generation warmup for subsequent JQL exercises. |

**Summary**: 13 issues found (11 terminology, 1 internal consistency, 1 informational). The exercise content itself is **technically accurate** — all described fields (Summary, Description, Priority, Labels, Components, Assignee), relationships (sub-tasks, linking with "is related to"), and interactions (comments with @mentions) are current Jira Cloud features. The sole problem domains are: (1) **pervasive "issue" terminology** appearing 12 times across the file, all of which should be "work item"; (2) **"progetto" → "space"** on lines 11 and 17; and (3) **topic placement** — the exercise fits better in Session 1 or needs a rationale for being in Session 2.

---

## `jira-confluence-best-practices-2026/sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-workflow-personalizzato.md`

**Topic placement note**: This exercise covers designing and implementing a custom workflow, including states, transitions, conditions, and publishing. According to the course README, custom workflows are a **Session 4** topic ("Automazioni, Workflow e Amministrazione"). Placing this in Session 2 (Filters & JQL) is **clearly misplaced** — students have not yet been introduced to workflow configuration concepts. **Recommendation**: Move this file to `sessione-04-automazioni-workflow-admin/esercizi/` and renumber.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 1 | Internal consistency | Exercise "Workflow personalizzato" covers a Session 4 topic (Automazioni, Workflow e Amministrazione). It is misplaced in Session 2 (Filtri, Ricerche e JQL). | Move to `sessione-04-automazioni-workflow-admin/esercizi/` and renumber the exercise. |
| 2 | 38 | Feature accuracy | "Andate su **Project settings → Workflows**" — "Project settings" is now **"Space settings"** in Jira Cloud since the Project-to-Space rename (Dec 2025). Navigation is via the left sidebar, not a top-bar menu. | Change to "Dalla sidebar sinistra dello space, andate su **Space settings → Workflows**" (or "Impostazioni space → Workflow"). |
| 3 | 39 | Feature accuracy | "Copiate un workflow esistente (non modificare l'originale)" — this instruction is valid. The new workflow editor supports duplicating workflows. However, the old workflow editor will be **removed in June 2026**. The exercise should note that only the new visual editor is available. | Add a note: "Nota: da giugno 2026 è disponibile solo il nuovo editor visuale dei workflow." |
| 4 | 40 | Feature accuracy | "Nell'editor visuale" — this correctly references the visual editor. However, the new workflow editor in Jira Cloud has specific UI differences from the old one (e.g., drag-and-drop states, rule-based transitions). The instruction should clarify that this is the **new** workflow editor. | Clarify: "Nel **nuovo editor visuale** dei workflow (l'unico disponibile dal 2026):" |
| 5 | 43 | Feature accuracy | "aggiungete una **condizione** (es. 'Only assignee')" — In the new workflow editor, conditions on transitions work differently. The new editor uses **rules** (not the old "conditions/validators/post-functions" model). "Only assignee" translates to a **restrict transition** rule. | Update to: "aggiungete una **regola** di restrizione (es. 'Restrict to assignee')" to match the new workflow editor terminology. |
| 6 | 44 | Feature accuracy | "Pubblicate il workflow (se in ambiente di test)" — in the new workflow editor, workflows are published by clicking "Update workflow" and the changes go live. The verb "publish" may be slightly misleading. | Change to "Salvate e aggiornate il workflow (Update workflow)" to match the current UI action. |
| 7 | 55 | Terminology | "stati dove le issue si accumulano" — "issue" is now **"work item"**. | Change to "stati dove i work item si accumulano". |
| 8 | 24 | Terminology | "es. solo il manager può approvare" — acceptable; this is a business concept, not a Jira-specific term. | No change needed. |
| 9 | 49 | Terminology | "1 workflow implementato (o in bozza) nell'editor di Jira" — acceptable; "workflow" and "editor" are not deprecated terms. | No change needed. |

**Summary**: 9 issues found (1 terminology, 5 feature accuracy, 1 internal consistency, 2 informational). The **most critical issue** is the topic placement: this exercise belongs in Session 4, not Session 2. The second most critical area is the **workflow editor references**: the exercise should be updated to reflect the new workflow editor (which is the only editor available since the old one is being removed June 2026). Specifically, the "conditions" terminology (line 43) must be updated to "rules" to match the new editor's model, and the navigation path must change from "Project settings" to "Space settings".

---

## `jira-confluence-best-practices-2026/sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-integrazione-jira.md`

**Topic placement note**: This exercise covers Jira-Confluence integration (embedding Jira macros in Confluence, linking Confluence pages to Jira work items). According to the course README, Jira-Confluence integration is a **Session 5** topic ("Confluence + Integrazione + Knowledge Transfer"). Placing this in Session 2 (Filters & JQL) is **clearly misplaced** — students have not yet been introduced to Confluence in the course. **Recommendation**: Move this file to `sessione-05-confluence-integrazione-knowledge/esercizi/` and renumber.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 1 | Internal consistency | Exercise "Integrazione Jira-Confluence" covers a Session 5 topic (Confluence + Integrazione + Knowledge Transfer). It is misplaced in Session 2 (Filtri, Ricerche e JQL). | Move to `sessione-05-confluence-integrazione-knowledge/esercizi/` and renumber the exercise. |
| 2 | 12 | Internal consistency | "Nella pagina creata nell'esercizio precedente" — this assumes students have already created a Confluence page, which is not part of Session 2. This prerequisite belongs to Session 5 flow. | If moved to Session 5, this reference becomes valid. If kept in Session 2, this prerequisite is unmet. |
| 3 | 17 | Terminology | "Inserisci una query JQL rilevante per il tuo ruolo (riusa i filtri della sessione 2)" — self-referential: this exercise is in Session 2 but references "filtri della sessione 2" as if it is external. | If moved to Session 5, change to "riusa i filtri salvati dalla sessione 2". If kept in Session 2, change to "riusa i filtri appena creati". |
| 4 | 21 | Terminology | "Copia l'URL di un'issue Jira" — "issue" is now **"work item"** (elemento di lavoro). | Change to "Copia l'URL di un work item Jira". |
| 5 | 22 | Terminology | "Incollalo nella pagina Confluence" — acceptable; "pagina Confluence" is correct terminology. | No change needed. |
| 6 | 23 | Terminology | "Osserva come Confluence crea automaticamente una preview con status e dettagli" — this describes Confluence Smart Links, which is a current feature. Terminology is acceptable. | No change needed. |
| 7 | 26-28 | Feature accuracy | "Usa la macro Jira Chart per incorporare un grafico a torta o 'creati vs risolti'" — the Jira Chart macro is still available in Confluence Cloud. However, it should be noted that this is labeled as **optional** (line 26: "Opzionale"), which is appropriate given that the macro may require specific permissions. | No change needed. The optional label is appropriate. |
| 8 | 32 | Terminology | "Vai su un'issue Jira creata durante il corso" — "issue" should be **"work item"**. | Change to "Vai su un work item Jira creato durante il corso". |
| 9 | 33 | Terminology | "Nella sezione **'Confluence pages'** (pannello laterale dell'issue)" — "issue" should be **"work item"**. The section label "Confluence pages" in the work item detail panel is still accurate. | Change to "pannello laterale del work item". |
| 10 | 35 | Terminology | "Verifica che il link appaia sia nell'issue che nella pagina Confluence" — "issue" should be **"work item"**. | Change to "sia nel work item che nella pagina Confluence". |
| 11 | 37 | Terminology | "Nella **descrizione** di un'issue Jira" — "issue" should be **"work item"**. | Change to "Nella **descrizione** di un work item Jira". |
| 12 | 44 | Terminology | "Quali pagine Confluence sarebbero più utili da collegare ai vostri progetti Jira?" — "progetti" (projects) is now **"space"** in Jira. | Change to "ai vostri space Jira" (or "ai vostri spazi Jira"). |
| 13 | 50 | Terminology | "1 pagina Confluence con almeno una macro Jira Issues funzionante" — "Jira Issues" in the macro name may have been updated to reflect "work item" terminology. | Verify the current macro name in Confluence. If still "Jira Issues", keep as-is but add a note. If renamed, update accordingly. |
| 14 | 51 | Terminology | "1 issue Jira collegata a una pagina Confluence" — "issue" should be **"work item"**. | Change to "1 work item Jira collegato a una pagina Confluence". |
| 15 | 52 | Terminology | "flusso bidirezionale Jira ↔ Confluence" — acceptable; this is a conceptual description, not deprecated terminology. | No change needed. |
| 16 | 15 | Confluence references | "Nell'editor Confluence, digita `/jira` per inserire la macro" — this slash-command shortcut is valid in the current Confluence cloud editor. However, note that the legacy editor will be fully deprecated in April 2026. | Add a note that this uses the Confluence cloud editor (not the legacy editor). |

**Summary**: 16 issues found (9 terminology, 1 feature accuracy, 2 internal consistency, 1 Confluence references, 3 informational). The **most critical issue** is the topic placement: this exercise belongs in Session 5, not Session 2. Students in Session 2 have not yet been introduced to Confluence. The remaining issues are the standard "issue" → "work item" and "progetto" → "space" terminology updates, which affect 8 lines in the file. The Jira-Confluence integration features described (Smart Links, Jira Issues macro, Confluence pages panel in work items) are all current and technically accurate.

---

## `jira-confluence-best-practices-2026/sessione-03-dashboard-grafici-analytics/outline.md`

This session is the **dashboard and analytics** session, making it the most sensitive to dashboard gadget changes, report availability, and the deprecated-gadget situation in Jira Cloud 2025-2026. The audit focuses on: (1) gadget names vs current official names, (2) deprecated gadgets mentioned without caveat, (3) gadgets that do not exist, (4) report types and their availability in Cloud vs Server, (5) terminology, and (6) sharing/permissions model.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 38 | Terminology | "tabella issue da un filtro JQL" — "issue" is now **"work item"** (elemento di lavoro) since Jul 2025. | Change to "tabella work item da un filtro JQL". |
| 2 | 38 | Feature accuracy | "**Risultati filtro** (Filter Results)" — the official gadget name is **"Filter Results"**. The Italian informal name with the English in parentheses is acceptable, but should be consistent with the format used for other gadgets. | No change strictly needed; the English name is correctly given in parentheses. |
| 3 | 39 | Feature accuracy | "**Grafico a torta** (Pie Chart)" — the official gadget name is **"Pie Chart"**. The Italian translation with English in parentheses is correct. | No change needed. |
| 4 | 40 | Feature accuracy | "**Creati vs Risolti** (Created vs Resolved)" — the official gadget name is **"Created vs Resolved"**. Correct. | No change needed. |
| 5 | 41 | Feature accuracy | "**Grafico a due dimensioni** (Two Dimensional Filter Statistics)" — the official gadget name is **"Two Dimensional Filter Statistics"**. Correct. | No change needed. |
| 6 | 42 | Feature accuracy | "**Attività recente** (Activity Stream)" — the official gadget name is **"Activity Stream"**. Correct. | No change needed. |
| 7 | 43 | Feature accuracy | "**Media tempo in status** (Average Age Chart): tempo medio di permanenza" — **Two errors**: (a) The official gadget name is **"Average Age"**, not "Average Age Chart". (b) The description "tempo medio di permanenza" (average time in status) is inaccurate for this gadget. Average Age measures the **average age of unresolved work items** (time since creation), not time spent in a specific status. The gadget that measures time in status is **"Average Time in Status"**, which is a separate gadget. | Fix the gadget name to "**Average Age**" and correct the description to "età media dei work item non risolti" (average age of unresolved work items). Consider also adding **"Average Time in Status"** as a separate entry if you want to cover time-in-status analytics — it is a distinct gadget. |
| 8 | 44 | Feature accuracy | "**Mappa di calore** (Heat Map): visualizzazione intensità" — Heat Map is one of the **5 gadgets in deprecation limbo** (removal paused April 30, 2025). Per the reference document, Heat Map is **not listed in the current 29-gadget inventory** and may already have been removed. Presenting it as a standard available gadget is misleading. | Either (a) remove Heat Map from the main gadget list and add a note in a "Gadget deprecati" sidebar, or (b) add a prominent caveat: "**Attenzione**: Heat Map è in fase di deprecazione e potrebbe non essere più disponibile nella vostra istanza (rimozione sospesa da aprile 2025)." |
| 9 | 45 | Feature accuracy | "**Testo** (Text): note e istruzioni in formato wiki" — there is **no gadget called "Text"** in the current Jira Cloud gadget list. The closest equivalent is the **"Introduction"** gadget, which allows a customizable introductory message with a title and HTML content. The description "formato wiki" is also inaccurate — the Introduction gadget uses HTML, not wiki markup. | Change to "**Introduzione** (Introduction): messaggio introduttivo personalizzabile con titolo e contenuto HTML". Remove the "formato wiki" reference. |
| 10 | 46 | Terminology | "ogni gadget usa un filtro JQL" — this is an oversimplification. Not every gadget requires a saved JQL filter. For example, Activity Stream, Assigned To Me, Days Remaining in Sprint, Introduction, Quick Links, Sprint Health, Sprint Burndown, and Wallboard Spacer do not use JQL filters. Only filter-based gadgets (Filter Results, Pie Chart, Created vs Resolved, Two Dimensional Filter Statistics, etc.) require a saved filter. | Clarify: "molti gadget si basano su un filtro JQL salvato" (many gadgets are based on a saved JQL filter) instead of stating all gadgets use one. |
| 11 | 43-44 | Feature accuracy | The gadget list (lines 38-45) presents 8 gadgets but omits several widely-used gadgets from the 29 available. Notable omissions relevant to a training course: **Assigned To Me** (essential for personal dashboards), **Sprint Burndown** and **Sprint Health** (critical for Scrum teams — mentioned later in reports section but not in the gadget section), **Days Remaining in Sprint**, **Work Item Statistics** (ex Issue Statistics), **Recently Created Work Items**, **Quick Links**. | Consider expanding the gadget list or explicitly noting that only a selection is shown, with a reference to the full list. Add at minimum **Assigned To Me** and **Work Item Statistics** as these are among the most commonly used gadgets. |
| 12 | 61 | Terminology | "Report del progetto: dove trovarli" — "progetto" (project) is now **"space"** (spazio) in Jira Cloud since Dec 2025. | Change to "Report dello space: dove trovarli" (or "Report dello spazio"). |
| 13 | 62 | Feature accuracy | "**Burndown Chart** (progetti Scrum): monitorare lo sprint" — the term "progetti" should be **"space"**. Also, in Jira Cloud the sprint burndown is available both as a **board-level report** (in the board's Reports section) and as a **dashboard gadget** ("Sprint Burndown"). The outline should clarify which context is being discussed. | Change to "**Burndown Chart** (space Scrum)" and clarify: "disponibile come report della board e come gadget dashboard (Sprint Burndown)". |
| 14 | 63 | Feature accuracy | "**Velocity Chart**: capacità del team nel tempo" — Velocity Chart is available as a **board-level report** in Jira Cloud for Scrum boards. It is **not** a dashboard gadget. The outline should clarify it is accessed from the board's Reports section, not from a dashboard. | Add context: "disponibile nella sezione Reports della board Scrum (non come gadget dashboard)". |
| 15 | 64 | Feature accuracy | "**Cumulative Flow Diagram**: visualizzare i colli di bottiglia" — Cumulative Flow Diagram is available as a **board-level report** in Jira Cloud for both Scrum and Kanban boards. It is **not** a dashboard gadget. | Add context: "disponibile nella sezione Reports della board (non come gadget dashboard)". |
| 16 | 65 | Feature accuracy | "**Control Chart**: tempo di ciclo delle issue" — Control Chart is available as a **board-level report** in Jira Cloud. It is **not** a dashboard gadget. Also, "issue" should be **"work item"**. | Change to "**Control Chart**: tempo di ciclo dei work item" and add: "disponibile nella sezione Reports della board (non come gadget dashboard)". |
| 17 | 65 | Terminology | "tempo di ciclo delle issue" — "issue" is now **"work item"**. | Change to "tempo di ciclo dei work item". |
| 18 | 59-66 | Feature accuracy | Section "3.4 Report integrati di Jira" mixes board-level reports (Burndown, Velocity, Cumulative Flow, Control Chart) without clarifying that these are **not dashboard gadgets** but board reports accessed from the board's sidebar. Students may confuse board reports with dashboard gadgets after Blocco 1. The section should explicitly distinguish between the two report types: (a) dashboard gadgets configured on dashboards, and (b) board reports accessible from the board's Reports section. | Add an introductory note at line 60: "Jira Cloud offre due tipi di report: (1) **gadget dashboard** configurabili sulle dashboard (visti nel Blocco 1), e (2) **report della board** accessibili dalla sezione Reports della board Scrum o Kanban." |
| 19 | 62 | Terminology | "progetti Scrum" — "progetti" should be **"space"**. | Change to "space Scrum". |
| 20 | 70 | Terminology | "JQL dinamico" — acceptable; JQL has not been renamed. | No change needed. |
| 21 | 71 | Terminology | "Dashboard 'manager': panoramica cross-progetto" — "progetto" (project) is now **"space"**. | Change to "panoramica cross-space". |
| 22 | 73 | Feature accuracy | "Wallboard mode: dashboard su schermo condiviso" — Wallboard mode is still available in Jira Cloud. The "Wallboard Spacer" gadget exists in the current gadget list, confirming wallboard functionality remains. | No change needed. Wallboard mode is accurately described. |
| 23 | 74 | Feature accuracy | "Refresh automatico dei gadget" — dashboard gadgets in Jira Cloud do support automatic refresh. The refresh interval is configurable per gadget (typically 15 minutes by default). | No change needed. This is accurate. |
| 24 | 77 | Feature accuracy | "Condividere con utenti specifici" — dashboard sharing in Jira Cloud supports sharing with individual users. This is accurate. | No change needed. |
| 25 | 78 | Feature accuracy | "Condividere con gruppi" — dashboard sharing supports groups. This is accurate. | No change needed. |
| 26 | 79 | Feature accuracy | "Condividere con l'intera organizzazione" — dashboards can be shared with "All users" or "Public". This is accurate. | No change needed. |
| 27 | 9 | Terminology | "Scegliere e configurare i gadget più utili per il proprio ruolo" — acceptable; "gadget" is not a deprecated term. | No change needed. |
| 28 | 11 | Terminology | "Leggere e interpretare grafici e report di Jira" — acceptable; no deprecated terms. | No change needed. |
| 29 | 12 | Terminology | "Condividere dashboard con il team e la direzione" — acceptable; "dashboard" and "team" are not deprecated terms. | No change needed. |
| 30 | 93 | Terminology | "filtri JQL → gadget → dashboard → reporting" — acceptable; all terms are current. | No change needed. |

**Summary**: 30 items audited, **21 issues found** (4 terminology, 15 feature accuracy, 2 informational/no-change-needed). The most critical issues for this session are:

1. **Gadget accuracy (lines 43-45)**: Three gadgets are problematic: (a) "Average Age Chart" is named incorrectly (should be "Average Age") and its description confuses it with the separate "Average Time in Status" gadget; (b) **Heat Map** is in deprecation limbo and may already be removed — it should not be presented as a standard gadget; (c) **"Text" gadget does not exist** — the correct gadget is "Introduction".
2. **Board reports vs dashboard gadgets (lines 59-66)**: The four reports listed (Burndown, Velocity, Cumulative Flow, Control Chart) are **board-level reports**, not dashboard gadgets. The outline does not distinguish between these two categories, which will confuse students who just learned about dashboard gadgets in Blocco 1. A clear distinction is needed.
3. **Terminology (lines 38, 61, 62, 65, 71)**: Standard "issue" → "work item" and "progetto" → "space" replacements needed on 5 lines. Less pervasive than Sessions 1-2 because much of this session uses gadget-specific vocabulary.
4. **Gadget coverage (line 46)**: The claim "ogni gadget usa un filtro JQL" is inaccurate — many gadgets (Activity Stream, Assigned To Me, Sprint Health, etc.) do not require a saved filter. This should be softened.
5. **Sharing/permissions model (lines 77-80)**: Accurately described. No changes needed.
6. **Wallboard mode (line 73)**: Still exists and is accurately described. No changes needed.

---

## `jira-confluence-best-practices-2026/sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-admin-permessi.md`

**Topic placement note**: This exercise covers administration and permissions (permission schemes, notification schemes, project configuration, governance conventions). According to the course README, administration and permissions are a **Session 4** topic ("Automazioni, Workflow e Amministrazione" — which includes "permessi, configurazione progetti"). Placing this in Session 3 (Dashboard, Grafici e Analytics) is **misplaced**. **Recommendation**: Move this file to `sessione-04-automazioni-workflow-admin/esercizi/` and renumber.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 1 | Internal consistency | Exercise title "Amministrazione e permessi" covers a Session 4 topic (Automazioni, Workflow e Amministrazione). It is misplaced in Session 3 (Dashboard, Grafici e Analytics). | Move to `sessione-04-automazioni-workflow-admin/esercizi/` and renumber the exercise. |
| 2 | 7 | Terminology | "la gestione dei permessi, degli schemi e delle configurazioni di progetto" — "progetto" (project) is now **"space"** (spazio) in Jira Cloud since Dec 2025. | Change to "configurazioni di space" (or "configurazioni dello spazio"). |
| 3 | 15 | Feature accuracy | "Andate su **Project settings → Permissions** di un progetto" — "Project settings" is now **"Space settings"** in Jira Cloud. Additionally, "un progetto" should be "uno space". Navigation is via the left sidebar. | Change to "Dalla sidebar sinistra dello space, andate su **Space settings → Permissions**". |
| 4 | 16 | Terminology | "Analizzate il **Permission scheme** associato" — "Permission scheme" is still the correct term; permission schemes have not been renamed. However, they now apply to **spaces**, not projects. | Minor: add context that permission schemes apply to spaces. |
| 5 | 17 | Terminology | "Chi può creare issue?" — "issue" is now **"work item"** (elemento di lavoro) since Jul 2025. | Change to "Chi può creare work item?". |
| 6 | 18 | Terminology | "Chi può assegnare issue?" — "issue" should be **"work item"**. | Change to "Chi può assegnare work item?". |
| 7 | 20 | Terminology | "Chi può eliminare issue?" — "issue" should be **"work item"**. | Change to "Chi può eliminare work item?". |
| 8 | 22 | Terminology | "Confrontate con un secondo progetto: usano lo stesso scheme o uno diverso?" — "progetto" should be **"space"**. | Change to "Confrontate con un secondo space". |
| 9 | 28 | Terminology | "quali issue types sono disponibili nel progetto" — "issue types" is now **"work types"** (tipi di lavoro) and "progetto" should be **"space"**. | Change to "quali work types sono disponibili nello space". |
| 10 | 30 | Terminology | "come organizzare le issue per area" — "issue" should be **"work item"**. | Change to "come organizzare i work item per area". |
| 11 | 31 | Terminology | "come raggruppare i progetti a livello di sito" — "progetti" should be **"space"**. Note: "Categorie" for grouping spaces at site level may have been updated in the UI. | Change to "come raggruppare gli space a livello di sito". |
| 12 | 34 | Terminology | "Quali componenti sarebbero utili per il proprio progetto?" — "progetto" should be **"space"**. | Change to "per il proprio space". |
| 13 | 41 | Terminology | "Nomenclatura progetti" — "progetti" should be **"space"**. The example codes (IT-HELPDESK, HR-ONBOARDING, FAC-TICKETS) are space keys and remain valid. | Change to "Nomenclatura space" (or "Nomenclatura degli spazi"). |
| 14 | 48 | Terminology | "Comprensione dei permission scheme e notification scheme" — acceptable; these terms have not been renamed. | No change needed. |
| 15 | 49 | Terminology | "Lista di componenti ed etichette proposti per ciascun progetto" — "progetto" should be **"space"**. | Change to "per ciascuno space". |
| 16 | 55 | Terminology | "Revisione permission scheme per ogni progetto" — "progetto" should be **"space"**. | Change to "per ogni space". |
| 17 | 57 | Terminology | "Creazione di un template di progetto per nuovi team" — "progetto" should be **"space"**. Space templates exist in Jira Cloud. | Change to "Creazione di un template di space per nuovi team". |
| 18 | 19 | Feature accuracy | "Chi può modificare il workflow?" — This permission exists in Jira Cloud but is now managed through the **new workflow editor** (the old editor is being removed June 2026). The permission itself is still valid. | Minor: no immediate change needed, but the exercise could note that workflow editing now uses the new visual editor. |

**Summary**: 18 issues found (14 terminology, 2 feature accuracy, 1 internal consistency, 1 informational). The **most critical issue** is the topic placement: administration and permissions belong to Session 4, not Session 3. Beyond that, the file has extensive use of "progetto" (appearing 9 times, all needing replacement with "space") and "issue"/"issue types" (appearing 5 times, needing replacement with "work item"/"work types"). The permission and notification scheme concepts themselves are accurate. The navigation path "Project settings → Permissions" must be updated to "Space settings → Permissions".

---

## `jira-confluence-best-practices-2026/sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-report-analisi.md`

**Topic placement note**: This exercise covers dashboard creation and report analysis. Dashboards, gadgets, and reports are the **core Session 3** topics ("Dashboard, Grafici e Analytics"). This exercise is **correctly placed**.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 21 | Feature accuracy | "Aggiungete un gadget comune: **'Creati vs Risolti'** su tutti i progetti" — the official gadget name is **"Created vs Resolved"**. Also, "progetti" (projects) is now **"space"** (spaces). | Change to "**Created vs Resolved** (Creati vs Risolti) su tutti gli space". |
| 2 | 17 | Terminology | "gadget con conteggio ticket aperti per priorità" — "ticket" informally refers to "issue", now **"work item"** (elemento di lavoro). | Change to "gadget con conteggio work item aperti per priorità". |
| 3 | 18 | Terminology | "gadget con issue in corso su ordini/fatture" — "issue" should be **"work item"**. | Change to "gadget con work item in corso su ordini/fatture". |
| 4 | 21 | Terminology | "su tutti i progetti" — "progetti" should be **"space"**. | Change to "su tutti gli space". |
| 5 | 27 | Feature accuracy | "navigate su **Report** (menu laterale del progetto)" — "progetto" should be **"space"**. The reference to "menu laterale" is correct for the new sidebar navigation. However, reports in Jira Cloud are accessed from the **board's sidebar**, not the space's general sidebar. | Change to "navigate su **Reports** dalla sidebar della board" (or "dalla sezione Reports della board nello space"). |
| 6 | 29 | Feature accuracy | "Burndown Chart (se il progetto usa Scrum)" — "progetto" should be **"space"**. Burndown Chart is a board-level report, not a dashboard gadget. | Change to "Burndown Chart (se lo space usa Scrum)". |
| 7 | 38 | Terminology | "1 dashboard condivisa con 5+ gadget, visibile a tutto il gruppo" — acceptable; "dashboard" and "gadget" are current terms. | No change needed. |
| 8 | 39 | Feature accuracy | "Comprensione di almeno 2 report nativi di Jira" — acceptable; these are board-level reports that are indeed native to Jira Cloud. | No change needed. |
| 9 | 44 | Terminology | "la dashboard alla direzione Tyvak" — acceptable; "dashboard" is current. | No change needed. |

**Summary**: 9 items audited, **6 issues found** (3 terminology, 3 feature accuracy). This exercise is **correctly placed** and is the least impacted among the Session 3 exercises. The main issues are: (1) standard "issue"/"ticket" → "work item" and "progetto/i" → "space" terminology replacements on 4 lines, (2) the gadget name "Creati vs Risolti" should include the official English name "Created vs Resolved", and (3) the report navigation path should clarify that reports are accessed from the board's sidebar, not the space's general sidebar.

---

## `jira-confluence-best-practices-2026/sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-knowledge-sharing-plan.md`

**Topic placement note**: This exercise covers knowledge sharing planning, Confluence space creation, and training material organization. According to the course README, knowledge sharing is a **Session 5** topic ("Confluence + Integrazione + **Knowledge Transfer**"). Placing this in Session 3 (Dashboard, Grafici e Analytics) is **clearly misplaced**. **Recommendation**: Move this file to `sessione-05-confluence-integrazione-knowledge/esercizi/` and renumber.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 1 | Internal consistency | Exercise title "Piano di Knowledge Sharing" covers a Session 5 topic (Confluence + Integrazione + Knowledge Transfer). It is misplaced in Session 3 (Dashboard, Grafici e Analytics). | Move to `sessione-05-confluence-integrazione-knowledge/esercizi/` and renumber the exercise. |
| 2 | 27 | Terminology | "Navigazione base di Jira" — acceptable as a concept reference; "navigazione" is not deprecated. However, the navigation referred to here is the **new left sidebar** navigation (since March 2025). | No immediate text change, but ensure any linked navigation material reflects the sidebar UI. |
| 3 | 28 | Terminology | "Creare e gestire issue correttamente" — "issue" is now **"work item"** (elemento di lavoro) since Jul 2025. | Change to "Creare e gestire work item correttamente". |
| 4 | 31 | Terminology | "Leggere e usare le dashboard" — acceptable; "dashboard" is current terminology. | No change needed. |
| 5 | 32 | Terminology | "Aprire ticket IT / facility / HR correttamente" — "ticket" informally refers to "issue", now **"work item"**. | Change to "Aprire work item IT / facility / HR correttamente" (or "Creare work item..."). |
| 6 | 59 | Confluence references | "Create (o strutturate) uno spazio Confluence **'Formazione Jira — Tyvak'**" — Confluence still uses the term "spazio" (space), so this is correct. However, with Jira also now calling its containers "spaces" (since Dec 2025), the instruction could benefit from explicit disambiguation. | Consider adding "uno spazio **Confluence**" to disambiguate from Jira spaces, or note the shared terminology. |
| 7 | 61 | Confluence references | "Create la struttura delle pagine" — "pagine" (pages) is correct Confluence terminology, unchanged. | No change needed. |
| 8 | 80 | Confluence references | "Creare almeno 1 pagina Confluence di documentazione per i colleghi" — correct Confluence terminology. | No change needed. |
| 9 | 81 | Terminology | "Condurre almeno 1 sessione di knowledge transfer nelle prossime 4 settimane" — acceptable; "knowledge transfer" is a general training term, not Jira-specific. | No change needed. |
| 10 | 34 | Terminology | "Best practice: etichette, componenti, commenti" — acceptable; "etichette" (labels), "componenti" (components), and "commenti" (comments) are current Jira terms. | No change needed. |

**Summary**: 10 items audited, **4 issues found** (2 terminology, 1 internal consistency, 1 Confluence references). The **most critical issue** is the topic placement: knowledge sharing planning is a Session 5 topic and has no relation to Session 3's dashboard/analytics theme. The content itself is largely terminology-neutral since it focuses on training planning rather than Jira features. The two terminology fixes are the standard "issue" → "work item" and "ticket" → "work item" replacements. The Confluence references are accurate.

---

## `jira-confluence-best-practices-2026/sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-tipi-progetto-workflow.md`

**Topic placement note**: This exercise covers project types (Team-managed vs Company-managed) and workflow analysis. According to the course README, project/space types are a **Session 1** topic ("Fondamenti di Jira Cloud" — "tipi di progetto") and custom workflows are a **Session 4** topic ("Automazioni, Workflow e Amministrazione" — "workflow personalizzati"). This exercise overlaps both sessions but fits **neither** Session 3 (Dashboard, Grafici e Analytics). **Recommendation**: Split the exercise — move Parte A (project/space types) to Session 1 and Parte B (workflow analysis) to Session 4, or move the entire exercise to Session 4 as it leans more toward configuration.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 1 | Internal consistency | Exercise title "Tipi di progetto e workflow" covers Session 1 (space types) and Session 4 (workflow) topics. It is misplaced in Session 3 (Dashboard, Grafici e Analytics). | Move to `sessione-04-automazioni-workflow-admin/esercizi/` or split between Sessions 1 and 4. |
| 2 | 1 | Terminology | Title "Tipi di progetto e workflow" — "progetto" (project) is now **"space"** (spazio) in Jira Cloud since Dec 2025. | Change to "Tipi di space e workflow". Also rename file from `esercizio-03-tipi-progetto-workflow.md` to `esercizio-03-tipi-space-workflow.md` (or renumber per new session). |
| 3 | 7 | Terminology | "Comprendere le differenze tra progetti Team-managed e Company-managed" — "progetti" should be **"space"**. Since Dec 2025, Jira uses "Team-managed space" and "Company-managed space". | Change to "Comprendere le differenze tra space Team-managed e Company-managed". |
| 4 | 12 | Terminology | "Apri un progetto **Team-managed** (se disponibile) e uno **Company-managed**" — "progetto" should be **"space"**. | Change to "Apri uno space **Team-managed** (se disponibile) e uno **Company-managed**". |
| 5 | 15 | Terminology | "Dove si trovano le impostazioni del progetto" — "progetto" should be **"space"**. "Impostazioni del progetto" (Project settings) is now **"Space settings"**. | Change to "Dove si trovano le impostazioni dello space" (Space settings). |
| 6 | 17 | Terminology | "Se puoi aggiungere nuovi issue types" — "issue types" is now **"work types"** (tipi di lavoro) since Jul 2025. | Change to "Se puoi aggiungere nuovi work types". |
| 7 | 18 | Terminology | "Se puoi modificare i campi delle issue" — "issue" should be **"work item"**. | Change to "Se puoi modificare i campi dei work item". |
| 8 | 23 | Terminology | "Si possono aggiungere issue types?" — "issue types" should be **"work types"**. | Change to "Si possono aggiungere work types?". |
| 9 | 24 | Terminology | "I campi sono condivisi con altri progetti?" — "progetti" should be **"space"**. | Change to "I campi sono condivisi con altri space?". |
| 10 | 30 | Terminology | "Vai nelle impostazioni di un progetto Company-managed" — "progetto" should be **"space"**. Navigation is now via the left sidebar. | Change to "Vai nelle impostazioni di uno space Company-managed (Space settings dalla sidebar sinistra)". |
| 11 | 31 | Feature accuracy | "Visualizza il workflow associato (Board settings → Workflow)" — the path to view workflows in the new UI is **"Space settings → Workflows"**, not "Board settings → Workflow". Board settings control column mapping, not workflow definition. | Change to "Visualizza il workflow associato (**Space settings → Workflows**)". |
| 12 | 36 | Terminology | "Confronta con il workflow di un progetto Team-managed" — "progetto" should be **"space"**. | Change to "di uno space Team-managed". |
| 13 | 40 | Feature accuracy | "Bozza uno schema con gli stati: `Nuovo → In analisi → In lavorazione → In attesa di feedback → Risolto → Chiuso`" — these are valid workflow states. However, the exercise should note that workflow creation/editing will use the **new workflow editor** exclusively from June 2026 (the old editor is being removed). | Add a note: "Nota: dal giugno 2026 i workflow si modificano esclusivamente nel nuovo editor visuale." |
| 14 | 46 | Terminology | "(IT Manager) Bozza del workflow ideale per helpdesk IT" — acceptable; "workflow" and "helpdesk" are current terms. | No change needed. |
| 15 | 50 | Terminology | "Per il vostro team, quale tipo di progetto sarebbe più appropriato?" — "progetto" should be **"space"**. | Change to "quale tipo di space sarebbe più appropriato?". |

**Summary**: 15 items audited, **14 issues found** (11 terminology, 2 feature accuracy, 1 internal consistency). The **most critical issue** is the topic placement: project/space types and workflow analysis are Session 1 and Session 4 topics, not Session 3. This exercise has **no connection** to the Session 3 theme of dashboards and analytics. The second most critical issue is the workflow navigation path (line 31): "Board settings → Workflow" is incorrect and should be "Space settings → Workflows". The file has extensive "progetto" usage (10 occurrences needing "space") and "issue"/"issue types" (3 occurrences needing "work item"/"work types"). The new workflow editor deprecation timeline (June 2026) should also be noted.

---

## `jira-confluence-best-practices-2026/sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-jql-avanzato.md`

**Topic placement note**: This exercise covers advanced JQL functions, saving/sharing filters, and filter subscriptions. Advanced JQL is primarily a **Session 2** topic ("Filtri, Ricerche e JQL" — "JQL sintassi, operatori, funzioni, filtri avanzati, sottoscrizioni"). Including it in Session 3 may be intentional as a continuation/reinforcement of Session 2 JQL skills, using them in the context of dashboard creation (since dashboard gadgets rely on saved filters). If that is the intent, the exercise is **acceptable in Session 3** but should explicitly connect JQL filter skills to the dashboard/analytics theme. As-is, the exercise makes no reference to dashboards, making the connection unclear.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 1 | Internal consistency | Exercise "JQL avanzato e filtri condivisi" is a Session 2 continuation topic (Filtri, Ricerche e JQL). Placing it in Session 3 may be intentional as a bridge to dashboard gadgets (which use saved filters), but the exercise makes **no explicit connection** to the Session 3 dashboard theme. | Either (a) add an introductory note connecting this exercise to dashboards: "I filtri salvati in questo esercizio saranno usati come base per i gadget della dashboard nella prossima attività", or (b) move to `sessione-02-filtri-ricerche-jql/esercizi/` if no dashboard connection is intended. |
| 2 | 16-17 | JQL syntax | Query `updated >= startOfDay()` — syntax is correct. `updated` field and `startOfDay()` function are unchanged in Jira Cloud 2026. | No change needed. |
| 3 | 21-22 | JQL syntax | Query `status CHANGED AFTER -1w` — syntax is correct. The `CHANGED` operator and relative date syntax `-1w` are unchanged. | No change needed. |
| 4 | 26-27 | JQL syntax | Query `text ~ "satellite"` — syntax is correct. The `text` pseudo-field and `~` (contains) operator are unchanged. | No change needed. |
| 5 | 31-32 | JQL syntax | Query `reporter = currentUser() AND assignee != currentUser()` — syntax is correct. `reporter`, `assignee`, `currentUser()` are all unchanged. | No change needed. |
| 6 | 25 | Terminology | "trova issue che contengono la parola 'satellite' nella descrizione o nel titolo" — "issue" is now **"work item"** (elemento di lavoro). | Change to "trova work item che contengono...". |
| 7 | 30 | Terminology | "Issue create da te ma assegnate ad altri" — "Issue" should be **"work item"**. | Change to "Work item creati da te ma assegnati ad altri". |
| 8 | 15 | Terminology | "Issue modificate oggi" — "Issue" should be **"work item"**. | Change to "Work item modificati oggi". |
| 9 | 20 | Terminology | "Issue il cui status è cambiato nell'ultima settimana" — "Issue" should be **"work item"**. | Change to "Work item il cui status è cambiato nell'ultima settimana". |
| 10 | 40 | Feature accuracy | "Clicca 'Save as' nella ricerca avanzata" — the "Save as" button is still present in Jira Cloud's advanced search. However, the navigation to advanced search may now be labeled "Advanced work item search" (instead of "Advanced issue search") and is accessed via the left sidebar. | Minor: verify the current label. If the exercise does not describe how to reach the advanced search, no change is needed for this line specifically. |
| 11 | 44 | Feature accuracy | "Dettagli filtro → Modifica permessi → Aggiungi gruppo o progetto" — "progetto" here refers to sharing a filter with a project, now **"space"**. The filter sharing UI now references "space" where it previously said "project". | Change to "Aggiungi gruppo o space". |
| 12 | 56 | Terminology | "5 query JQL avanzate funzionanti" — acceptable; "query JQL" is current terminology. | No change needed. |
| 13 | 57 | Terminology | "1 filtro salvato, condiviso e con sottoscrizione attiva" — acceptable; "filtro" (filter) and "sottoscrizione" (subscription) are current terms. | No change needed. |

**Summary**: 13 items audited, **7 issues found** (4 terminology, 2 feature accuracy, 1 internal consistency). This exercise is **lightly impacted** by the 2025-2026 changes. The JQL syntax in all four example queries is **completely accurate** — no functions or operators have changed. The main issues are: (1) the exercise's connection to the Session 3 dashboard theme is implicit at best and should be made explicit; (2) four occurrences of "issue" in query labels should be changed to "work item"; (3) the filter sharing reference to "progetto" on line 44 should be updated to "space". The exercise is well-structured and the JQL concepts taught (date functions, CHANGED operator, full-text search, currentUser()) are all current and useful.

---

## `jira-confluence-best-practices-2026/cheatsheet/jql-cheatsheet.md`

This cheatsheet provides a compact JQL reference covering fields, operators, functions, relative dates, and role-specific query examples for Tyvak. It is well-structured and most JQL syntax is correct, but the terminology reflects pre-2025 naming (project, issue, issuetype) and the cheatsheet omits any mention of the renamed JQL functions introduced in 2025-2026.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 3 | Terminology | Subtitle says "Guida tascabile per Tyvak International" — acceptable as-is, no terminology issue. | No change needed. |
| 2 | 15 | Terminology | Field `project` described as "Progetto". Since Dec 2025, the Jira concept formerly called "Project" is now **"Space"** (Spazio). The JQL field `project` still works (backward compatible), but the new canonical field name is `space`. | Change description to "Space (ex Progetto)" and add a note that `project` is a backward-compatible alias for `space`. |
| 3 | 16 | Terminology | Field `issuetype` described as "Tipo issue". "Issue Type" is now **"Work Type"** (Tipo di lavoro) since Jul 2025. The JQL field `issuetype` still works (backward compatible), and `type` is also accepted. | Change description to "Work type (ex Tipo issue)" and note that `issuetype` remains a valid alias. |
| 4 | 15 | JQL syntax | Example `project = "IT-HELPDESK"` — syntactically correct and still functional due to backward compatibility. However, the canonical modern equivalent is `space = "IT-HELPDESK"`. | Consider showing both forms: `space = "IT-HELPDESK"` (or `project = "IT-HELPDESK"`). |
| 5 | 16 | JQL syntax | Example `issuetype = Bug` — syntactically correct. The field `issuetype` is backward compatible. `type = Bug` is also valid and unchanged. | Optionally update to `type = Bug` which has always been the shorter alias and is now preferred in documentation. |
| 6 | 27 | Terminology | Field `text` described as "Ricerca full-text" — acceptable, `text` is a pseudo-field that has not been renamed. | No change needed. |
| 7 | 44 | JQL syntax | Operator `WAS` example `status WAS "In Progress"` — correct syntax, `WAS` operator is unchanged in 2026. | No change needed. |
| 8 | 45 | JQL syntax | Operator `CHANGED` example `status CHANGED TO "Done"` — correct syntax. The `CHANGED` operator with `TO`/`FROM`/`AFTER`/`BEFORE` modifiers is unchanged. | No change needed. |
| 9 | 58-70 | Feature accuracy | The "Funzioni temporali" section lists `now()`, `currentUser()`, `startOfDay()` through `startOfYear()`, `endOfDay()` through `endOfMonth()`. All are correct and unchanged in Jira Cloud 2026. | No change needed. |
| 10 | 70 | Feature accuracy | `endOfYear()` is missing from the temporal functions table. The reference lists `endOfYear()` as a valid function. The cheatsheet lists `startOfYear()` but not `endOfYear()`. | Add `endOfYear()` with description "Fine anno corrente" to complete the set. |
| 11 | 72-81 | JQL syntax | Relative periods (`-1d`, `-7d`, `-1w`, `-30d`, `-1M`, `-3M`) — all are correct and unchanged. | No change needed. |
| 12 | 83-89 | JQL syntax | `ORDER BY` examples — syntactically correct. `ORDER BY created DESC`, `ORDER BY priority ASC`, and combined ordering are all valid. The comment syntax `--` is not valid JQL but is used here as annotation outside the query; acceptable for a cheatsheet. | No change needed (the `--` comments are presentational, not meant to be executed). |
| 13 | 94-106 | Terminology | Section "Query utili per Tyvak" — comments use "Le mie issue aperte" (line 96), "Issue create questa settimana" (line 99), "Issue in scadenza entro 3 giorni" (line 101), "Issue aggiornate oggi" (line 104). All occurrences of "issue" should be **"work item"**. | Replace all "issue" with "work item" in comments: "I miei work item aperti", "Work item creati questa settimana", "Work item in scadenza entro 3 giorni", "Work item aggiornati oggi". |
| 14 | 96 | JQL syntax | Query `assignee = currentUser() AND status != Done ORDER BY priority DESC` — correct syntax. | No change needed. |
| 15 | 99 | JQL syntax | Query `project = "PROGETTO" AND created >= startOfWeek()` — syntactically correct. `project` is backward compatible. | Optionally update to `space = "PROGETTO"`. |
| 16 | 101 | JQL syntax | Query `due <= 3d AND due >= now() AND status != Done` — **potential issue**: `due <= 3d` is a relative future expression. In standard JQL, relative offsets like `3d` without a sign are interpreted as relative to now in the future (`+3d`). This is correct for "due within 3 days". | No change needed — the syntax is valid. Jira interprets unsigned relative dates as future offsets for `<=` comparisons. |
| 17 | 104 | JQL syntax | Query `updated >= startOfDay() AND project = "PROGETTO"` — correct syntax. | Optionally update `project` to `space`. |
| 18 | 110-118 | Terminology | IT Manager section — comments use "Ticket critici" (line 111), "Ticket per tipo di problema" (line 114), "Volume ticket ultima settimana" (line 117). "Ticket" is colloquial for "issue", now **"work item"**. | Replace "Ticket" with "Work item" in comments: "Work item critici aperti da più di 24h", etc. |
| 19 | 111 | JQL syntax | Query `project = "IT-HELPDESK" AND priority = Critical AND status != Done AND created <= -24h` — syntactically correct. `created <= -24h` means "created more than 24 hours ago". | Optionally update `project` to `space`. |
| 20 | 123-130 | Terminology | Administration & Finance section — comments use "Ordini in attesa" (fine), "Fatture in scadenza" (fine), "Issue completate questo mese" (line 129). | Line 129: change "Issue completate" to "Work item completati". |
| 21 | 133-142 | Terminology | HR Generalist section — comments use "Onboarding attivi" (fine), "Task onboarding in ritardo" (fine), "Nuovi dipendenti ultimo trimestre" (fine). No "issue" references in comments. | No change needed. |
| 22 | 145-154 | Terminology | Facility Manager section — comments use "Reclami aperti" (fine), "Manutenzioni programmate" (fine), "Ticket facility risolti" (line 153). | Line 153: change "Ticket facility risolti" to "Work item facility risolti". |
| 23 | 153 | JQL syntax | Query `project = "FACILITY" AND resolved >= -7d` — syntactically correct. | Optionally update `project` to `space`. |
| 24 | 156-163 | Feature accuracy | "Suggerimenti" section — all tips are accurate. Autocomplete in JQL editor (line 158), quoting rules for field and value names (lines 159-160), `currentUser()` recommendation (line 161), saving queries as filters (line 162) are all current best practices. | No change needed. |
| 25 | — | Feature accuracy | **Missing content**: The cheatsheet does not mention any of the **renamed JQL functions** introduced in 2025-2026. While these are advanced, a cheatsheet should at minimum note the existence of function renames: `issueHistory()` → `workItemHistory()`, `linkedIssues()` → `linkedWorkItems()`, `votedIssues()` → `votedWorkItems()`, `watchedIssues()` → `watchedWorkItems()`, `projectsLeadByUser()` → `spacesLeadByUser()`, `standardIssueTypes()` → `standardWorkTypes()`, `subtaskIssueTypes()` → `subtaskWorkTypes()`. All old names remain backward compatible. | Add a new section "Funzioni rinominate (2025)" with a table of old → new function names, noting that old names remain valid for backward compatibility. |
| 26 | — | Feature accuracy | **Missing content**: No mention of `membersOf("group")` function, which is useful for team-based queries (e.g., `assignee IN membersOf("IT-team")`). | Consider adding `membersOf()` to the functions table as it is commonly used in role-based filtering. |
| 27 | — | Feature accuracy | **Missing content**: No mention of sprint-related JQL functions: `openSprints()`, `closedSprints()`, `futureSprints()`. While Tyvak may not use Scrum, these are fundamental JQL functions. | If Scrum/sprint workflows are relevant for any Tyvak teams, add sprint functions. Otherwise, omission is acceptable for a Kanban-focused organization. |

**Summary**: 27 items audited, **13 issues found** (8 terminology, 2 JQL syntax suggestions, 3 feature accuracy gaps). The JQL syntax throughout the cheatsheet is **fully correct** — all operators, functions, and query examples are valid Jira Cloud 2026 JQL. The main issues are: (1) **terminology**: the `project` field description should note the `space` alias, `issuetype` should note `type`/Work Type, and ~10 occurrences of "issue"/"ticket" in comments should be updated to "work item"; (2) **missing content**: the cheatsheet omits the 2025-2026 renamed JQL functions entirely — a new section listing the old→new function names (all backward compatible) should be added; (3) `endOfYear()` is missing from the temporal functions table. The role-specific queries for Tyvak are well-crafted and syntactically sound.

---

## `jira-confluence-best-practices-2026/cheatsheet/dashboard-cheatsheet.md`

This cheatsheet covers dashboard creation, gadget selection, configuration, layout recommendations, sharing, wallboard mode, and best practices. It is concise and well-organized, but the gadget list has terminology issues and includes a gadget that may no longer be available.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 7 | Feature accuracy | Step 1 says "**Dashboards** → **Create dashboard**". With the new left sidebar navigation (since March 2025), dashboards are accessed from the sidebar, not a top bar menu. The exact path is sidebar → Dashboards → Create dashboard. | Update to "**Sidebar sinistra** → **Dashboards** → **Create dashboard**" to reflect the new navigation. |
| 2 | 16 | Terminology | "Filter Results" gadget described as "Tabella issue da un filtro JQL" — "issue" is now **"work item"**. | Change to "Tabella work item da un filtro JQL". |
| 3 | 17 | Terminology | "Pie Chart" gadget described with "Distribuzione per status/priorità/assegnatario" — acceptable, no deprecated terms. | No change needed. |
| 4 | 18 | Terminology | "Created vs Resolved" gadget described as "Andamento creazione/risoluzione" — acceptable. The gadget name itself is unchanged in Jira Cloud 2026. | No change needed. |
| 5 | 19 | Terminology | "Two Dimensional Filter Statistics" — name is correct and unchanged. | No change needed. |
| 6 | 20 | Terminology | "Activity Stream" — name is correct and unchanged. | No change needed. |
| 7 | 21 | Terminology | "Average Age Chart" — the **actual gadget name** in Jira Cloud 2026 is **"Average Age"** (without "Chart"). | Change gadget name from "Average Age Chart" to "Average Age". Update description from "Età media delle issue" to "Età media dei work item non risolti". |
| 8 | 22 | Feature accuracy | **"Heat Map"** is listed as a recommended gadget. Heat Map is one of 5 gadgets in **deprecation limbo** — it was scheduled for removal in May 2025, the removal was suspended on April 30, 2025, but it may already have been removed from some instances. The reference document notes it is "not listed in current gadgets" and "may already be removed". | **Remove Heat Map** from the recommended gadget list. Add a note in a separate "Gadget deprecati" section that Heat Map, along with Road Map, Bubble Chart, Spaces, and Labels, are at risk of removal. If Heat Map is still needed, note its uncertain status. |
| 9 | 23 | Terminology | "Recently Created Chart" — the **actual gadget name** in Jira Cloud 2026 is **"Recently Created Work Items"** (not "Chart"). | Change gadget name from "Recently Created Chart" to "Recently Created Work Items". Update description from "Issue create di recente" to "Work item creati di recente". |
| 10 | 24 | Terminology | "Resolution Time" — name is correct and unchanged. Description "Tempo di risoluzione" is accurate. | No change needed. |
| 11 | 25 | Feature accuracy | **"Text"** gadget — the actual gadget name in Jira Cloud 2026 is **"Introduction"** (NOT "Text"). The "Introduction" gadget allows adding a customizable introductory message to a dashboard. | Change gadget name from "Text" to **"Introduction"**. Update description from "Testo libero (wiki)" to "Messaggio introduttivo personalizzabile" or similar. |
| 12 | 26 | Terminology | "Assigned to Me" — name is correct and unchanged. Description "Le tue issue" uses deprecated term. | Change "Le tue issue" to "I tuoi work item". |
| 13 | 16 | Terminology | Column header "Cosa mostra" uses "issue" in multiple gadget descriptions. The overall header row is fine, but individual descriptions need updating. | Ensure all gadget descriptions replace "issue" with "work item" where applicable. |
| 14 | 37-47 | Terminology | "Filter Results — Colonne consigliate" section references columns. "Key", "Summary", "Status", "Priority", "Assignee", "Created", "Updated", "Due Date", "Labels" — all column names are current and unchanged. | No change needed. |
| 15 | 44 | Terminology | "Per identificare issue ferme" — "issue" should be **"work item"**. | Change to "Per identificare work item fermi". |
| 16 | 69-71 | Feature accuracy | Layout uses "Text" gadget — should reference "Introduction" gadget per finding #11. | Change "Text" to "Introduction" in the layout diagram. |
| 17 | 93-96 | Terminology | Sharing levels table: "Progetto" level described as "Ruolo nel progetto". "Progetto" (Project) is now **"Space"** in Jira Cloud. | Change "Progetto" to "Space" and "Ruolo nel progetto" to "Ruolo nello space". Change "Dashboard di progetto" to "Dashboard di space". |
| 18 | 98 | Feature accuracy | "Dashboard → ⋯ → Edit → Share → Aggiungi utenti/gruppi" — the sharing path may differ slightly with the new sidebar navigation, but the general pattern (edit dashboard, then share) remains correct. | Minor: verify exact path. The instruction is functionally accurate. |
| 19 | 100-105 | Feature accuracy | Wallboard mode section — `?wallboard` URL parameter is still valid in Jira Cloud 2026. The instructions are accurate. | No change needed. |
| 20 | 110 | Feature accuracy | "6-8 gadget massimo per dashboard" — this is consistent with current Atlassian best practice recommendations. | No change needed. |
| 21 | — | Feature accuracy | **Missing gadgets**: The cheatsheet lists 11 gadgets but Jira Cloud 2026 has **29 pre-installed gadgets**. While a cheatsheet does not need to list all, several commonly useful gadgets are omitted: **Assigned To Me** (listed), **Days Remaining in Sprint**, **Sprint Burndown**, **Sprint Health**, **Work Item Statistics**, **Work Items in Progress**, **Quick Links**, **Watched Work Items**, **Voted Work Items**. | Consider adding at minimum **Work Item Statistics** (very commonly used, shows issue counts by field), **Sprint Burndown** (essential for Scrum teams), and **Work Items in Progress** (useful for personal dashboards). |
| 22 | — | Feature accuracy | **Missing content**: No mention of gadgets in **deprecation limbo**. Five gadgets (Road Map, Bubble Chart, Heat Map, Spaces, Labels) were scheduled for removal in May 2025 but removal was suspended. These gadgets may be removed at any time. Users should be warned not to build critical dashboards around them. | Add a "Gadget a rischio deprecazione" section listing the 5 affected gadgets with a note that they could be removed in future updates. |
| 23 | — | Feature accuracy | **Missing content**: No mention of the **Spaces (ex Projects)** gadget, which shows space-level information. While it is in deprecation limbo, it exists and users may encounter it. | If not adding it to the main list, at minimum mention it in the deprecation warning section. |
| 24 | 109-114 | Feature accuracy | Best practices section — all recommendations are current and accurate: clear purpose, 6-8 gadget limit, descriptive names, saved filters over direct JQL, refresh intervals, quarterly review. | No change needed. |

**Summary**: 24 items audited, **14 issues found** (6 terminology, 8 feature accuracy). The most critical issues are: (1) **"Text" gadget name is wrong** — the actual gadget is called "Introduction" (line 25); this is a factual error that will confuse users looking for the gadget. (2) **"Heat Map" is listed as a recommended gadget** but it is in deprecation limbo and may already be removed (line 22). (3) **"Average Age Chart" and "Recently Created Chart" have incorrect names** — they are called "Average Age" and "Recently Created Work Items" respectively. (4) Multiple "issue" references need updating to "work item". (5) Missing content: no mention of deprecated gadgets or the broader 29-gadget catalog. The layout recommendations and best practices sections are solid and current.

---

## `jira-confluence-best-practices-2026/cheatsheet/automazioni-cheatsheet.md`

This cheatsheet covers the automation rule model (trigger → condition → action), common triggers/conditions/actions, smart values, Tyvak-specific recipes, debugging, and limits. It is well-structured and the recipes are technically feasible, but trigger and action names use deprecated "Issue" terminology, the automation limits are incomplete, and several 2025-2026 features are missing.

| # | Line(s) | Category | Issue | Suggested Fix |
|---|---------|----------|-------|---------------|
| 1 | 15 | Terminology | Trigger **"Issue created"** — in Jira Cloud 2026, automation triggers now use "Work item" terminology: **"Work item created"**. | Change to "**Work item created**". Update description from "Viene creata una nuova issue" to "Viene creato un nuovo work item". |
| 2 | 16 | Terminology | Trigger **"Issue transitioned"** — now **"Work item transitioned"**. | Change to "**Work item transitioned**". Update description to "Cambia lo status di un work item". |
| 3 | 17 | Terminology | Trigger **"Field value changed"** — this trigger name is still correct; it is generic and does not reference "issue". | No change needed. |
| 4 | 18 | Terminology | Trigger **"Comment added"** — this trigger name is still correct. | No change needed. |
| 5 | 19 | Terminology | Trigger **"Issue assigned"** — now **"Work item assigned"**. Description "Viene assegnata/riassegnata" uses feminine pronoun referencing "issue". | Change to "**Work item assigned**". Update description to "Viene assegnato/riassegnato un work item". |
| 6 | 20 | Terminology | Trigger **"Scheduled"** — correct, unchanged. | No change needed. |
| 7 | 21 | Terminology | Trigger **"Manual trigger"** — correct, unchanged. | No change needed. |
| 8 | 22 | Terminology | Trigger **"Issue deleted"** — now **"Work item deleted"**. | Change to "**Work item deleted**". Update description from "Viene eliminata un'issue" to "Viene eliminato un work item". |
| 9 | 28 | Terminology | Condition **"Issue fields condition"** — now **"Work item fields condition"**. | Change to "**Work item fields condition**". |
| 10 | 30 | Terminology | Condition **"User condition"** — correct, unchanged. | No change needed. |
| 11 | 31 | Terminology | Condition **"Related issues condition"** — now **"Related work items condition"**. Description says "Le issue collegate soddisfano criteri". | Change to "**Related work items condition**". Update description to "I work item collegati soddisfano criteri". |
| 12 | 39 | Terminology | Action **"Transition issue"** — now **"Transition work item"**. | Change to "**Transition work item**". |
| 13 | 40 | Terminology | Action **"Edit issue"** — now **"Edit work item"**. | Change to "**Edit work item**". |
| 14 | 41 | Terminology | Action **"Assign issue"** — now **"Assign work item"**. Description "Assegna l'issue" uses old term. | Change to "**Assign work item**". Update description to "Assegna il work item". |
| 15 | 42 | Terminology | Action **"Add comment"** — correct, unchanged. | No change needed. |
| 16 | 43 | Terminology | Action **"Send email"** — correct, unchanged. | No change needed. |
| 17 | 44 | Terminology | Action **"Create issue"** — now **"Create work item"**. Description "Crea una nuova issue". | Change to "**Create work item**". Update description to "Crea un nuovo work item". Update example to "Work item di follow-up". |
| 18 | 45 | Terminology | Action **"Create sub-tasks"** — the action name should be verified. Sub-tasks as a concept still exist. The description is acceptable. | Minor: verify current action name. "Create sub-tasks" or "Create sub-work items" — Jira Cloud 2026 documentation may still use "sub-tasks" as a work type name. Likely no change needed as "Sub-task" remains a standard work type name. |
| 19 | 46 | Terminology | Action **"Link issues"** — now **"Link work items"**. Description "Collega issue tra loro". | Change to "**Link work items**". Update description to "Collega work item tra loro". |
| 20 | 49 | Terminology | Action **"Lookup issues"** — now **"Lookup work items"**. Description "Cerca issue con JQL". | Change to "**Lookup work items**". Update description to "Cerca work item con JQL". |
| 21 | 55 | Feature accuracy | Smart value `{{issue.key}}` — Jira Cloud 2026 automation still supports `{{issue.key}}` as a valid smart value (backward compatible). However, the newer canonical form may be `{{workItem.key}}`. The old `{{issue.*}}` smart values continue to work. | Add a note that `{{issue.key}}` remains valid but `{{workItem.key}}` is the newer form. If only one form can be shown, keep `{{issue.*}}` for now as it is confirmed working and widely documented. |
| 22 | 55-65 | Terminology | All smart value descriptions use "issue" terminology: "Chiave issue" (line 55), "Titolo issue" (line 56), "URL dell'issue" (line 61). | Update descriptions: "Chiave work item", "Titolo work item", "URL del work item", etc. |
| 23 | 71-74 | Terminology | Recipe "Auto-assegnazione per componente" uses "Issue created" trigger and "Assign issue" action. | Update to "Work item created" trigger and "Assign work item" action. |
| 24 | 78-86 | Terminology | Recipe "Checklist onboarding automatica" uses "Issue created" trigger. Description says "Labels contains" which is correct syntax for automation conditions. | Update trigger to "Work item created". The recipe is **technically feasible** and well-designed. |
| 25 | 90-94 | Terminology | Recipe "Escalation ticket critici" uses "Scheduled" trigger (correct). JQL condition `priority = Critical AND status != Done AND created <= -24h` is valid. Actions "Add comment" and "Send email" are correct. | Update comment text: "Ticket critico" → "Work item critico". The recipe is **technically feasible**. |
| 26 | 98-102 | Terminology | Recipe "Chiusura automatica dopo risoluzione" — "Scheduled" trigger (correct), JQL condition (correct), "Transition" action (correct). | The recipe is **technically feasible**. No terminology issue in the JQL or actions themselves, but the section context uses "issue" implicitly. |
| 27 | 106-110 | Feature accuracy | Recipe "Notifica scadenza imminente" uses smart value `{{issue.key}}` in the email subject. As noted in #21, this works but newer form is `{{workItem.key}}`. | Optionally update to `{{workItem.key}}`, or keep `{{issue.key}}` with a backward-compatibility note. The recipe is **technically feasible**. |
| 28 | 114 | Terminology | "**Audit log**: Project settings → Automation → Audit log" — "Project settings" is now **"Space settings"** in Jira Cloud 2026 (since the Project→Space rename). | Change to "**Audit log**: Space settings → Automation → Audit log". |
| 29 | 121 | Feature accuracy | Automation limits listed as "Free: 100/mese, Standard: 1700/mese" — these are correct but **incomplete**. The cheatsheet omits **Premium** (1.000/utente/mese, pooled) and **Enterprise** (illimitate). | Add the full plan breakdown: "Free: 100/mese, Standard: 1.700/mese, Premium: 1.000/utente/mese (pooled), Enterprise: illimitate". |
| 30 | — | Feature accuracy | **Missing content**: No mention of **Rule validation** (April 2025) — the ability to check a rule for errors before enabling it. This is a significant workflow improvement for automation authors. | Add to a "Novità 2025" section: "Validazione regole: verifica errori nella regola prima di attivarla (aprile 2025)". |
| 31 | — | Feature accuracy | **Missing content**: No mention of **Rovo AI rule creation** — the ability to describe automation rules in natural language and have AI generate the trigger/condition/action configuration. | Add to a "Novità 2025" section: "Rovo AI: crea regole di automazione descrivendo trigger e azioni in linguaggio naturale". |
| 32 | — | Feature accuracy | **Missing content**: No mention of the **LaunchDarkly action deprecation** (June 2025). The "Create feature flag in LaunchDarkly" action has been removed. | If LaunchDarkly was mentioned or could be assumed relevant for Tyvak, add a deprecation note. If not relevant, omission is acceptable. Low priority for Tyvak context. |
| 33 | — | Feature accuracy | **Missing content**: No mention that the **old workflow editor will be removed June 2026**. While this is more of a workflow topic than automation, automation rules that transition work items depend on workflow configuration. A brief cross-reference is useful. | Consider adding a note: "Dal giugno 2026, solo il nuovo editor di workflow sarà disponibile per configurare le transizioni usate dalle regole di automazione". |
| 34 | 114-117 | Feature accuracy | Debug section describes audit log access and execution statuses (Success, Some actions failed, Error). This is still accurate — the audit log interface has not materially changed. | No change needed. |
| 35 | 125 | Feature accuracy | Anti-loop advice "Evitare loop" — this is current and important best practice. Jira Cloud does have built-in loop detection, but the manual precaution is still valid. | No change needed. |

**Summary**: 35 items audited, **22 issues found** (17 terminology, 5 feature accuracy). The cheatsheet is **heavily impacted** by terminology changes. The three most critical areas are: (1) **Trigger names**: 4 of 8 triggers use the deprecated "Issue" prefix (created, transitioned, assigned, deleted) and must be updated to "Work item". (2) **Action names**: 5 of 10 actions use the deprecated "issue" term (Transition, Edit, Assign, Create, Link, Lookup) and must be updated to "work item". (3) **Automation limits are incomplete**: only Free and Standard are listed; Premium (1.000/user/mo) and Enterprise (unlimited) are missing. Additionally, new 2025 features (rule validation, Rovo AI) are absent, smart value descriptions use "issue" terminology, and the audit log path says "Project settings" instead of "Space settings". The Tyvak-specific recipes are all **technically feasible** and well-designed — the JQL syntax, trigger-condition-action patterns, and smart value usage are all correct.
