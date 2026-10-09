# Components — Index

Read this file before creating a new component.

Components are reusable implementation/interaction primitives. They are **not composition authority**. Page composition is governed first by `../VISUAL_DNA.md` and the Decision Architecture.

Every HTML file is a preview/reference for single-file mockups using `tokens.css` with no external dependency.

| File | Purpose | Status / Notes |
|---|---|---|
| `application-shell.html` | Precision product-continuity shell: top identity + command rail + crafted work surface | **Candidate v3** — preserve continuity, do not mechanically force composition |
| `enterprise-kpi-strip.html` | Hospital Instrument Band: integrated operational readings with threshold/delta context | **Candidate** — preferred over spreadsheet KPI cells / marketing stat cards when suitable |
| `operational-panel.html` | Dense operational panel/table primitive | Approved primitive; do not use as Card Everywhere |
| `buttons.html` | Primary / secondary / danger / icon-button states | Approved primitive |
| `form-controls.html` | Input/select/date/checkbox/radio/textarea states | Approved primitive |
| `status-badges.html` | Semantic status badges | Approved primitive |
| `alert-banner.html` | Clinical/operational attention | Approved primitive |
| `patient-banner.html` | Patient context header | Approved primitive |
| `patient-search-bar.html` | Patient search + autocomplete | Approved primitive |
| `vitals-form.html` | Vitals form + validation | Approved primitive |
| `lab-result-table.html` | Lab result table + clinical flags | Approved primitive |
| `modal-dialog.html` | Confirmation/form modal | Approved primitive |
| `drawer.html` | Contextual short-task drawer | Approved primitive |
| `worklist.html` | Operational work queue | Approved primitive |
| `tabs.html` | In-page category navigation | Approved primitive |
| `notification-toast.html` | Temporary feedback | Approved primitive |
| `stat-card.html` | Home/Executive summary card | Use only when the archetype genuinely fits; not default operational grammar |
| `patient-summary-panel.html` | Detailed patient context panel | Approved primitive |
| `premium-operational-layout.html` | Historical rigid operational layout | **DEPRECATED Candidate — never use as Mandatory Master** |

## Human-Approved Gold Reference Mapping

Before creating a screen or component, consult `../APPROVED_REFERENCE_TEMPLATE_REGISTRY.md`.

- Dashboard summary card → `stat-card.html` or `enterprise-kpi-strip.html` according to use case.
- Patient Banner → `patient-banner.html`; rich clinical context → `patient-summary-panel.html`.
- Worklist → `worklist.html` and the Worklist UX standards.
- Minimal Paper clinical note / SOAP progress note → `../reference-templates/Education_V2.html` as the approved source reference; copy the relevant clinical documentation region into the target feature and adapt only required fields/actions.
- Explicit Social V2 visual reference → `../reference-templates/Social_V2.html` is the shell/operational UI authority for that feature.

Do not rebuild these from scratch. The two Gold HTML files are canonical source assets; do not edit them for a module-specific implementation.

## Selection Rule

1. Start from the **Decision Question**, not from a component.
2. Read `VISUAL_DNA.md` before choosing primitives.
3. Reuse behavior and product continuity where a component fits.
4. Do not let reuse force generic or visually barren composition.
5. Operational metrics should feel like instruments: value + unit + target/threshold + delta/trend/forecast when decision-relevant.
6. Dense information may use tables/worklists, but the full page must still pass Surface, Typography, Dryness and Desirability gates.
7. Emoji is prohibited as UI icon; use `icon-rules.md`.

## New Component Rule

1. A new reusable component begins as **Candidate**.
2. Use central `tokens.css`; no local palette escape.
3. Document Decision Question / use case / limits.
4. Render and visually review it.
5. Only Human Design Approval can promote it to shared premium/Gold status.
6. Use `kebab-case.html` and register it here.
