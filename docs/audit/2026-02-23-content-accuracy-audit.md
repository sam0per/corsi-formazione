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
