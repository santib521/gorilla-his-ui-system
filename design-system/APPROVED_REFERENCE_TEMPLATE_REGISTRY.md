# Approved Reference Template Registry — Gorilla HIS

**Status:** Human-approved reference sources supplied by the Product Owner  
**Purpose:** Reuse proven Gorilla HIS UI and interaction patterns instead of rebuilding them for every module.

This registry is the lookup table for the Mockup Factory. When a requirement asks for a familiar UI pattern, select the mapped source first. Do not invent a visually similar replacement.

## 1. Gold reference HTML

| Reference source | Authority | Reuse for | Do not copy |
|---|---|---|---|
| `reference-templates/Social_V2.html` | **Primary operational module reference** | Application shell, top bar, command rail, role selector, module navigation, worklist rhythm, dashboard/KPI arrangement, patient/context banner, search/filter, forms, request flow, drawers/modals, buttons, badges, toast/feedback, history/timeline, interaction/state patterns | Social-work business rules, Social Work role labels, social-work-specific fields, patient records or policy that do not apply to the target module |
| `reference-templates/Education_V2.html` | **Clinical EMR / Minimal Paper reference** | Patient/encounter context, visit context, clinical documentation layout, compact clinical sections, CC/HPI/PE/history, SOAP/progress-note patterns, clinical note history/timeline, relevant order-entry interaction patterns | Education module identity, MS4/MS5/student workflow, education grading/evaluation, student-only controls, education-specific navigation or roles |

### Authority rule

- If the user says “use this HTML as the template”, “copy this”, or supplies a human-approved HTML reference, activate `EXACT_REFERENCE_REPLICATION_STANDARD.md`.
- Start from the reference source itself and adapt it in place. Do not start from a different shell and try to imitate the reference with CSS overrides.
- The reference controls visual identity and interaction grammar. The target module requirements control business data, roles, states, labels, actions and workflow.
- Reuse only the relevant part of a source. A clinical EMR request may reuse Education V2's clinical documentation pattern without turning the target module into an Education system.
- Keep the reference HTML intact. Build a target module copy; do not overwrite the Gold reference with module-specific changes.
- Reference examples contain mock data and module-specific behavior. Never interpret their sample records, business rules or role names as target-module truth.

## 2. Component lookup — use before building

| User asks for | First source to inspect/reuse | Selection guidance |
|---|---|---|
| Dashboard KPI / summary card | `components/stat-card.html`, `components/enterprise-kpi-strip.html`, `patterns/dashboard-home.md` | Use stat cards for suitable Home/Executive summaries; prefer the compact enterprise KPI strip for dense operational dashboards. KPI values and click-through filters must be data-consistent and functional. |
| Patient Banner | `components/patient-banner.html` | Use for compact patient identity/context. |
| Detailed patient context panel | `components/patient-summary-panel.html` | Use when vitals, allergy, underlying conditions or other detailed context must remain visible. Do not show the same data twice without a reason. |
| Worklist / queue | `components/worklist.html`, `ux-rules.md`, `ENTERPRISE_WORKLIST_STANDARD.md` | A worklist is an actionable queue, not a display-only table. Row action, owner, status, search/filter and empty state must work. |
| Minimal Paper EMR / clinical note | `reference-templates/Education_V2.html` | Reuse the clinical documentation surface and note rhythm directly. Adapt only required sections and actions; do not rebuild a generic “SOAP card” that loses the reference's layout. |
| Module shell / navigation | `reference-templates/Social_V2.html` first when the user names it; otherwise `components/application-shell.html` | For an explicit Social V2 reference request, Social V2 takes precedence over generic shell defaults. |

## 3. Required source reuse map

Before implementation, record this compact map in the feature's design notes:

- `Reference file → exact regions/components reused`
- `Existing design-system component → target screen`
- `Target-specific changes → reason`
- `Source-only behavior intentionally excluded → reason`

Example:
- Social V2 → topbar, command rail, role picker, page context, worklist, request form and toast.
- Education V2 → patient/encounter context, Minimal Paper clinical note, SOAP/progress timeline.
- Existing components → dashboard summary, Patient Banner, Worklist, status badges.
- Target-specific changes → target roles, target clinical fields, target workflow and sample records.

If a requested component already exists in this registry or the component/pattern library, creating a replacement from scratch is a review defect unless a documented requirement proves the existing pattern is unsuitable.

## 4. Required visual and functional checks

1. Compare the candidate and selected reference at the same viewport.
2. Verify the topbar, rail/sidebar, page context, typography, density, spacing, table rhythm, buttons, badges and patient context have not drifted without an explicit reason.
3. Verify every visible enabled action changes state/data or navigates to a real destination.
4. Verify KPI counts, worklist rows, filters and status transitions use the same data source.
5. Verify Role switching changes the actual workspaces and available actions, not just the role label.
6. Run end-to-end scenarios across roles; do not approve isolated screens alone.
7. Report what was tested and what remains untested. Syntax checking alone is not visual or functional QA.

## 5. Source files

- [Social_V2.html](./reference-templates/Social_V2.html)
- [Education_V2.html](./reference-templates/Education_V2.html)

These are reference assets, not production-ready shared clinical components. New mockups should copy/adapt them into a feature workspace and keep module-specific edits out of these canonical files.
