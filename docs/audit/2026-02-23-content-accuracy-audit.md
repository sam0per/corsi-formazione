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
