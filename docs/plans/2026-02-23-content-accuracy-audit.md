# Content Accuracy Audit — Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Audit all 23 markdown files in the Jira-Confluence course (Sessions 1-3, cheatsheets, glossary) for technical accuracy against Jira Cloud 2025-2026, producing a per-file issue list.

**Architecture:** Sequential file-by-file review. Each task reads file(s), verifies technical claims via web research, and appends findings to a single audit report. A final cross-consistency check catches inter-file contradictions.

**Tech Stack:** Markdown output, web search for Jira Cloud verification, git for commits.

---

### Task 1: Research current Jira Cloud 2025-2026 state

**Purpose:** Build a reference baseline of current Jira Cloud terminology, features, and known changes before reviewing any course files. This prevents repeated lookups later.

**Step 1: Research Jira Cloud UI and terminology changes (2024-2026)**

Use web search to find:
- Current Jira Cloud navigation terminology (sidebar, top bar, menus)
- "Team-managed" vs "Company-managed" project naming — any rebrand?
- Current issue types, workflow editor state
- Automation rule limits and features in Jira Cloud 2025-2026
- Dashboard gadget list and any deprecated gadgets
- JQL function list — any new or deprecated functions

Search queries:
- `Jira Cloud 2025 2026 UI changes navigation`
- `Jira Cloud team-managed company-managed renamed 2025`
- `Jira Cloud automation rules changes 2025 2026`
- `Jira Cloud dashboard gadgets list 2025`
- `Jira Cloud JQL functions list 2025 2026`
- `Confluence Cloud 2025 2026 changes`

**Step 2: Save reference notes**

Create `docs/audit/jira-cloud-2026-reference.md` with a summary of findings for use during review. This is a working document, not a deliverable.

**Step 3: Commit**

```bash
git add docs/audit/jira-cloud-2026-reference.md
git commit -m "docs: add Jira Cloud 2026 reference notes for audit"
```

---

### Task 2: Create audit report scaffold and review course README

**Files:**
- Read: `jira-confluence-best-practices-2026/README.md`
- Create: `docs/audit/2026-02-23-content-accuracy-audit.md`

**Step 1: Create the audit report file with header**

Create `docs/audit/2026-02-23-content-accuracy-audit.md` with:

```markdown
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
```

**Step 2: Read and audit the course README**

Read `jira-confluence-best-practices-2026/README.md`. Check:
- Course structure claims (number of sessions, hours) match actual file tree
- Platform references (Jira Cloud, Confluence Cloud) are accurate
- Any feature claims or prerequisites that may be outdated
- Terminology accuracy

**Step 3: Append findings to audit report**

Add a section for the README with the issue table (or "No issues found.").

**Step 4: Commit**

```bash
git add docs/audit/2026-02-23-content-accuracy-audit.md
git commit -m "docs: audit course README"
```

---

### Task 3: Audit Session 1 outline

**Files:**
- Read: `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/outline.md`
- Modify: `docs/audit/2026-02-23-content-accuracy-audit.md`

**Step 1: Read the Session 1 outline**

This covers Jira fundamentals: architecture, navigation, project types, issue types, basic workflows.

**Step 2: Verify against Jira Cloud 2025-2026**

Check:
- Navigation paths (e.g., "Projects > Board > Backlog") match current UI
- Project type names and descriptions are current
- Issue type list is accurate
- Workflow concepts described correctly
- Any feature descriptions that may be outdated
- Cross-reference with Task 1 research notes

**Step 3: Append findings to audit report**

**Step 4: Commit**

```bash
git add docs/audit/2026-02-23-content-accuracy-audit.md
git commit -m "docs: audit session 1 outline"
```

---

### Task 4: Audit Session 1 exercises (5 files)

**Files:**
- Read: `sessione-01-fondamenti-jira/esercizi/esercizio-01-navigazione-progetto.md`
- Read: `sessione-01-fondamenti-jira/esercizi/esercizio-01-dashboard-personale.md`
- Read: `sessione-01-fondamenti-jira/esercizi/esercizio-01-regole-automazione.md`
- Read: `sessione-01-fondamenti-jira/esercizi/esercizio-01-ricerca-base.md`
- Read: `sessione-01-fondamenti-jira/esercizi/esercizio-01-confluence-pagine.md`
- Modify: `docs/audit/2026-02-23-content-accuracy-audit.md`

**Step 1: Read all 5 exercise files**

**Step 2: For each exercise, verify:**

- UI navigation steps match current Jira Cloud interface
- Feature references are accurate (dashboard creation, automation rules, search, Confluence pages)
- Step-by-step instructions would actually work in current Jira Cloud
- Exercise objectives align with Session 1 outline topics
- **Topic placement check**: `esercizio-01-dashboard-personale.md` and `esercizio-01-regole-automazione.md` cover topics that appear in later sessions (dashboards = Session 3, automations = Session 4). Verify whether these exercises are intentionally introductory or misplaced.

**Step 3: Append findings for each exercise to audit report (one table per file)**

**Step 4: Commit**

```bash
git add docs/audit/2026-02-23-content-accuracy-audit.md
git commit -m "docs: audit session 1 exercises"
```

---

### Task 5: Audit Session 2 outline

**Files:**
- Read: `jira-confluence-best-practices-2026/sessione-02-filtri-ricerche-jql/outline.md`
- Modify: `docs/audit/2026-02-23-content-accuracy-audit.md`

**Step 1: Read the Session 2 outline**

This covers filters, searches, and JQL.

**Step 2: Verify against Jira Cloud 2025-2026**

Check:
- JQL syntax examples are correct
- JQL fields, operators, and functions referenced all exist in current Jira Cloud
- Filter management UI descriptions match current interface
- Subscription features described accurately
- Search UI (basic vs advanced) terminology is current

**Step 3: Append findings to audit report**

**Step 4: Commit**

```bash
git add docs/audit/2026-02-23-content-accuracy-audit.md
git commit -m "docs: audit session 2 outline"
```

---

### Task 6: Audit Session 2 exercises (5 files)

**Files:**
- Read: `sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-ricerca-base.md`
- Read: `sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-jql-fondamentali.md`
- Read: `sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-creazione-issue.md`
- Read: `sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-workflow-personalizzato.md`
- Read: `sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-integrazione-jira.md`
- Modify: `docs/audit/2026-02-23-content-accuracy-audit.md`

**Note:** The file `esercizio-02-gadget-grafici.md` also exists in Session 2 but covers a Session 3 topic (dashboard gadgets). This is flagged below.

Wait — let me recheck. The glob results show these Session 2 exercise files:
- `esercizio-02-gadget-grafici.md`
- `esercizio-02-workflow-personalizzato.md`
- `esercizio-02-creazione-issue.md`
- `esercizio-02-integrazione-jira.md`
- `esercizio-02-jql-fondamentali.md`

That's 5 files, but `esercizio-02-ricerca-base.md` is NOT in the list — `esercizio-02-gadget-grafici.md` is there instead.

**Corrected file list for Task 6:**
- Read: `sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-gadget-grafici.md`
- Read: `sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-jql-fondamentali.md`
- Read: `sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-creazione-issue.md`
- Read: `sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-workflow-personalizzato.md`
- Read: `sessione-02-filtri-ricerche-jql/esercizi/esercizio-02-integrazione-jira.md`
- Modify: `docs/audit/2026-02-23-content-accuracy-audit.md`

**Step 1: Read all 5 exercise files**

**Step 2: For each exercise, verify:**

- All JQL queries are syntactically valid
- JQL fields and functions used actually exist
- UI steps for creating/saving filters are current
- **Topic placement check**: `esercizio-02-gadget-grafici.md` covers dashboard gadgets/charts — this is a Session 3 topic ("Dashboard, Grafici e Analytics"). Flag as potentially misplaced.
- **Topic placement check**: `esercizio-02-workflow-personalizzato.md` covers custom workflows — this is a Session 4 topic ("Automazioni, Workflow e Amministrazione"). Flag as potentially misplaced.
- Issue creation and integration steps are accurate

**Step 3: Append findings for each exercise to audit report**

**Step 4: Commit**

```bash
git add docs/audit/2026-02-23-content-accuracy-audit.md
git commit -m "docs: audit session 2 exercises"
```

---

### Task 7: Audit Session 3 outline

**Files:**
- Read: `jira-confluence-best-practices-2026/sessione-03-dashboard-grafici-analytics/outline.md`
- Modify: `docs/audit/2026-02-23-content-accuracy-audit.md`

**Step 1: Read the Session 3 outline**

This covers dashboards, charts, and analytics.

**Step 2: Verify against Jira Cloud 2025-2026**

Check:
- Dashboard creation steps match current UI
- Gadget names are current (some gadgets have been renamed or deprecated)
- Report types listed are available in Jira Cloud (not just Jira Server/DC)
- Chart types and configuration options are accurate
- Sharing/permission model described correctly

**Step 3: Append findings to audit report**

**Step 4: Commit**

```bash
git add docs/audit/2026-02-23-content-accuracy-audit.md
git commit -m "docs: audit session 3 outline"
```

---

### Task 8: Audit Session 3 exercises (5 files)

**Files:**
- Read: `sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-admin-permessi.md`
- Read: `sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-report-analisi.md`
- Read: `sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-knowledge-sharing-plan.md`
- Read: `sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-tipi-progetto-workflow.md`
- Read: `sessione-03-dashboard-grafici-analytics/esercizi/esercizio-03-jql-avanzato.md`
- Modify: `docs/audit/2026-02-23-content-accuracy-audit.md`

**Step 1: Read all 5 exercise files**

**Step 2: For each exercise, verify:**

- Dashboard gadget references are current
- Report creation steps match current Jira Cloud
- **Topic placement check**: `esercizio-03-admin-permessi.md` covers admin/permissions — this is a Session 4 topic. Flag as potentially misplaced.
- **Topic placement check**: `esercizio-03-knowledge-sharing-plan.md` covers knowledge sharing — this is a Session 5 topic. Flag as potentially misplaced.
- **Topic placement check**: `esercizio-03-tipi-progetto-workflow.md` covers project types/workflows — overlaps Sessions 1 and 4. Flag.
- **Topic placement check**: `esercizio-03-jql-avanzato.md` covers advanced JQL — this is a Session 2 topic continuation. May be intentional (building on earlier JQL) or misplaced. Flag for review.
- Technical accuracy of all instructions

**Step 3: Append findings for each exercise to audit report**

**Step 4: Commit**

```bash
git add docs/audit/2026-02-23-content-accuracy-audit.md
git commit -m "docs: audit session 3 exercises"
```

---

### Task 9: Audit cheatsheets (3 files)

**Files:**
- Read: `jira-confluence-best-practices-2026/cheatsheet/jql-cheatsheet.md`
- Read: `jira-confluence-best-practices-2026/cheatsheet/dashboard-cheatsheet.md`
- Read: `jira-confluence-best-practices-2026/cheatsheet/automazioni-cheatsheet.md`
- Modify: `docs/audit/2026-02-23-content-accuracy-audit.md`

**Step 1: Read all 3 cheatsheet files**

**Step 2: JQL cheatsheet — verify:**

- All JQL field names exist in current Jira Cloud
- All operators listed are valid (`=`, `!=`, `>`, `<`, `IN`, `NOT IN`, `~`, `WAS`, `CHANGED`, etc.)
- All functions listed exist (`now()`, `currentUser()`, `startOfDay()`, `startOfMonth()`, etc.)
- Relative period syntax is correct (`-1d`, `-7d`, `-1w`, `-1M`)
- Role-specific example queries are syntactically valid
- No deprecated or removed JQL features referenced

**Step 3: Dashboard cheatsheet — verify:**

- Gadget names match current Jira Cloud gadget library
- Gadget configuration steps are accurate
- Layout recommendations are feasible in current UI
- Wallboard mode still exists and works as described
- Sharing/permission model is current

**Step 4: Automations cheatsheet — verify:**

- Trigger types listed all exist in current Jira Cloud automation
- Condition types are accurate
- Action types are accurate
- Smart value syntax (`{{issue.key}}`, `{{now.plusDays(7)}}`, etc.) is correct
- Automation limits mentioned are current
- Any Tyvak-specific recipes are technically feasible

**Step 5: Append findings for each cheatsheet to audit report**

**Step 6: Commit**

```bash
git add docs/audit/2026-02-23-content-accuracy-audit.md
git commit -m "docs: audit cheatsheets"
```

---

### Task 10: Audit glossary

**Files:**
- Read: `jira-confluence-best-practices-2026/glossario.md`
- Modify: `docs/audit/2026-02-23-content-accuracy-audit.md`

**Step 1: Read the glossary**

**Step 2: Verify each term definition:**

- Definitions are technically accurate for Jira Cloud 2025-2026
- No deprecated features defined without noting deprecation
- "Team-managed" vs "Company-managed" terminology is current
- Confluence-specific terms are accurate
- Definitions are consistent with how terms are used in session outlines and exercises (cross-reference earlier findings)

**Step 3: Append findings to audit report**

**Step 4: Commit**

```bash
git add docs/audit/2026-02-23-content-accuracy-audit.md
git commit -m "docs: audit glossary"
```

---

### Task 11: Cross-consistency check and final report

**Files:**
- Read: `docs/audit/2026-02-23-content-accuracy-audit.md` (accumulated so far)
- Modify: `docs/audit/2026-02-23-content-accuracy-audit.md`

**Step 1: Review all accumulated findings**

Scan the full audit report for:
- Terms defined differently in different files
- Contradictory instructions (e.g., outline says one navigation path, exercise says another)
- Exercise topics that don't match their session's theme (aggregate the topic placement flags from Tasks 4, 6, 8)
- Missing cross-references (e.g., exercise says "see cheatsheet" but cheatsheet doesn't cover that topic)

**Step 2: Add a "Cross-File Consistency" section at the end of the audit report**

```markdown
## Cross-File Consistency Issues

| # | Files Involved | Issue | Suggested Fix |
|---|---------------|-------|---------------|
```

**Step 3: Add a summary section at the very top (after the header)**

```markdown
## Summary

- **Files reviewed**: 23
- **Total issues found**: N
- **By category**: Terminology: X, JQL: Y, Feature: Z, Confluence: W, Consistency: V
- **Critical issues**: [list any showstoppers]
```

**Step 4: Final commit**

```bash
git add docs/audit/2026-02-23-content-accuracy-audit.md
git commit -m "docs: complete content accuracy audit report"
```

**Step 5: Clean up reference notes**

Remove the working reference file if no longer needed:

```bash
git rm docs/audit/jira-cloud-2026-reference.md
git commit -m "chore: remove audit working notes"
```

Or keep it if useful for future reference — implementer's judgment.
