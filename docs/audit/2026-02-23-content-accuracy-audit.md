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
