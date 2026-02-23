# Content Accuracy Audit — Sessione 01: Fondamenti di Jira Cloud

> Date: 2026-02-23 | Scope: `jira-confluence-best-practices-2026/sessione-01-fondamenti-jira/`

## Files Audited

| File | Type |
|------|------|
| `outline.md` | Session program |
| `esercizi/esercizio-01-navigazione-space.md` | Exercise |
| `esercizi/esercizio-01-ricerca-base.md` | Exercise |
| `esercizi/esercizio-01-creazione-work-item.md` | Exercise |
| `slides/sessione-01-fondamenti-jira.pdf` | Slide deck (16 slides) |

## Verification Sources

- [Evolving Jira terminology: Projects → Spaces](https://community.atlassian.com/forums/Jira-articles/Evolving-Jira-terminology-Projects-will-soon-be-Spaces/ba-p/3034977) (Atlassian Community, Aug 2025)
- [Jira Spaces have landed](https://community.atlassian.com/forums/Jira-articles/Jira-Spaces-have-landed/ba-p/3117620) (Atlassian Community, Oct 2025)
- [Work is the new collective term for items tracked in Jira](https://community.developer.atlassian.com/t/work-is-the-new-collective-term-for-items-tracked-in-jira/88552) (Atlassian DevCom)
- [Out with the old workflow editor](https://community.atlassian.com/forums/Jira-articles/Out-with-the-old-workflow-editor-and-in-with-the-new-workflow/ba-p/3073415) (Atlassian Community)
- [JRACLOUD-83818](https://jira.atlassian.com/browse/JRACLOUD-83818) — Old workflow editor removal from June 2026

---

## CRITICAL Findings

### C1. Slides use entirely outdated terminology (11 of 16 slides)

The slides use the pre-September 2025 Jira terminology throughout. The markdown files have been correctly updated. This creates a direct contradiction between what the slides show and what the outline/exercises say.

| Concept | Slides (OLD) | Markdown (NEW) | Atlassian current (Feb 2026) |
|---------|-------------|----------------|-------------------------------|
| Container for work | progetto | spazio (space) | **space** — rolled out Sep-Oct 2025 |
| Unit of work | issue | elemento di lavoro (work item) | **work / work item** — rolling out |
| Category of work | issue type | tipo di lavoro (work type) | **work type** — rolling out |
| Hierarchy | sito → progetto → board → issue | Sito → Spazio → Board → Elemento di lavoro | Sito → Space → Board → Work item |

**Affected slides:** 1, 2, 4, 5, 6, 8, 9, 10, 11, 12, 14.

Specific instances:

- **Slide 1**: subtitle "issue types e workflow base"
- **Slide 2**: hierarchy "sito → progetto → board → issue"
- **Slide 4**: "gestione progetti, ticket"
- **Slide 5**: "Progetto → contenitore logico", "Issue → unita di lavoro"
- **Slide 6**: "Issue types principali", "sotto-attivita di un'issue padre"
- **Slide 8**: "Progetti, Filtri, Dashboard", "le tue issue", "Menu laterale del progetto", "crea issue"
- **Slide 9**: "Tipi di progetto"
- **Slide 10**: "progetti Team-managed", "progetto" used throughout
- **Slide 11**: "Issue in profondita"
- **Slide 12**: "Anatomia di un'issue", "issue" used throughout
- **Slide 14**: "ciclo di vita di un'issue", "Ogni issue", "Ogni progetto"

**Action required:** Rebuild the slide deck using the new terminology consistently. The markdown files serve as the correct reference.

### C2. Slides describe old top-bar navigation

Slide 8 describes navigation that no longer exists in Jira Cloud:

- **"Barra superiore: Progetti, Filtri, Dashboard, Persone, App"** — the top navigation bar was replaced by a **left sidebar** in the 2024-2025 navigation redesign. The outline.md correctly references "Sidebar di navigazione sinistra."
- **"campanella in alto a destra"** — notification bell location has moved in the new navigation.
- **"g poi d (vai a dashboard)"** — the old `g then ...` keyboard shortcut pattern is tied to the old navigation. May still partially work but is no longer the documented approach.
- **"/" for search and "c" for create** — these remain valid.

**Action required:** Redesign slide 8 to show the current left sidebar navigation, with correct element locations.

---

## WARNING Findings

### W1. Broken glossary reference

`outline.md` line 100 links to `[Glossario Jira](../glossario.md)`. The `risorse/` directory is empty — no `glossario.md`, no cheatsheets exist.

**Action required:** Either create the glossary file or remove the broken link.

### W2. Exercise/theory block misalignment

All 3 exercises are placed under "Esercizi Blocco 1" (1:00-1:45):

- Esercizio 1: Navigazione (fits Blocco 1 topics)
- Esercizio 2: Ricerca base (fits Blocco 1 topics)
- Esercizio 3: Creazione work item (covers Blocco 2 topic — section 2.2 "Elementi di lavoro in profondita")

Blocco 2 says "Nessun esercizio assegnato — sessione di discussione guidata e Q&A", leaving the most hands-on topic without practice after theory. Students would be creating work items with priorities, labels, and components **before** learning about them.

**Action required:** Move Esercizio 3 to Blocco 2 exercises, or restructure the outline to teach work item basics in Blocco 1.

### W3. Exercise uses English navigation labels

`esercizio-01-ricerca-base.md` line 17: "Filters → Advanced issue search" uses:
- English labels (the Italian UI would show different text)
- Old navigation path (not accessible the same way in the sidebar)
- Old terminology ("issue search")

**Action required:** Update to reflect the current Italian UI labels and sidebar-based navigation path.

### W4. Workflow deprecation note misplaced

`outline.md` line 14 places "il vecchio editor di workflow sara rimosso a giugno 2026" under "Obiettivi della sessione." This is a factual note about a future platform change, not a learning objective.

**Action required:** Move this note to section 2.3 (Workflow base) where it contextually belongs. The June 2026 date is factually correct per JRACLOUD-83818.

---

## INFO Findings

### I1. Priority values may not match Jira defaults

Slide 12 lists priorities as "Lowest → Low → Medium → High → Critical." Jira Cloud's **default** priority scheme uses: Lowest, Low, Medium, High, **Highest** (not "Critical").

`esercizio-01-creazione-work-item.md` line 33 also uses "Priorita: Critical" for a Facility Manager task.

This may be correct if Tyvak's instance has a custom priority scheme, but it deviates from Jira defaults. If students follow along on a fresh or default instance, they won't find "Critical."

**Action required:** Verify against Tyvak's actual Jira configuration. If using defaults, replace "Critical" with "Highest."

### I2. Informal "ticket" term in slides

Slide 4 uses "ticket" ("tracciamento del lavoro, gestione progetti, ticket, workflow"). Not incorrect as informal language, but inconsistent with the effort to teach official Jira terminology.

**Action required:** Consider replacing with the official term or noting "ticket" as informal.

### I3. Slide 1 subtitle mixes languages and uses old terms

Subtitle: "Architettura, navigazione, issue types e workflow base" — mixes Italian and English, and uses the old "issue types" term.

**Action required:** Align with new terminology: "Architettura, navigazione, tipi di lavoro (work type) e workflow base."

### I4. Cloud vs Data Center topic gap between outline and slides

Outline section 1.1 includes "Jira Cloud vs Data Center: differenze chiave" but no corresponding slide exists. May be intentional (covered verbally) but creates a coverage gap for students reviewing materials.

**Action required:** Either add a slide or note in the outline that this is covered verbally.

### I5. JQL backward compatibility not mentioned

The outline and exercises introduce JQL previews (esercizio-01-ricerca-base.md). JQL still uses `project` (not `space`) and `issuetype` (not `worktype`) for backward compatibility. Automation smart values also still use `{{project}}`.

This is relevant because students will see the new terminology in the UI but the old terminology in JQL/automation. Worth noting in session 1 as a heads-up, or deferring explicitly to session 2.

**Action required:** Add a brief note about JQL/automation backward compatibility in the outline or defer explicitly to session 2 outline.

---

## Findings Summary

| Severity | # | Key issue |
|----------|---|-----------|
| **CRITICAL** | 2 | Slides terminology (11/16 slides); slides navigation layout |
| **WARNING** | 4 | Broken glossary link; exercise/theory misalignment; English UI labels; misplaced note |
| **INFO** | 5 | Priority values; "ticket" term; subtitle language; Cloud vs DC gap; JQL compat |

## Recommended Fix Priority

1. **Rebuild slides** with new terminology and new navigation (addresses C1, C2, I3)
2. **Restructure exercise placement** (addresses W2)
3. **Fix broken references and labels** (addresses W1, W3)
4. **Move workflow note** (addresses W4)
5. **Verify Tyvak-specific configuration** (addresses I1)
6. **Add JQL compatibility note** (addresses I5)
