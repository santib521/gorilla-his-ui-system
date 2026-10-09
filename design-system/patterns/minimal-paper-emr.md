# Minimal Paper EMR Pattern — Clinical Documentation

**Status:** Approved reference-derived pattern  
**Canonical visual source:** `../reference-templates/Education_V2.html`  
**Scope:** Clinical note workspace and longitudinal progress documentation, not the Education module.

## Intent

Reuse the compact, paper-like clinical documentation presentation from Education V2 when a module needs Initial Assessment, Progress Note, SOAP or review of prior clinical notes. The pattern should feel like a clinical record within Gorilla HIS, not a new card-based mini-app.

## Source-first implementation

1. Open `reference-templates/Education_V2.html` and inspect its actual clinical EMR DOM, CSS classes, visit/context strip, clinical section structure and note feed.
2. Copy the relevant region and its required CSS/JavaScript dependencies into the target feature. Do not redraw it from memory.
3. Preserve the source's typography, spacing, field rhythm, section headings, timeline/log style and compact documentation density.
4. Reuse the Patient Banner / patient context pattern from the selected module shell when it already supplies the same context. Do not duplicate identity data unnecessarily.
5. Adapt only the sections required by the target workflow (for example CC/HPI, PE, Assessment, Plan, SOAP, allied-health discipline, author, timestamp and follow-up). Keep field names and clinical content governed by the target requirement.
6. Preserve source note history and visit context where the workflow needs longitudinal review. New notes must append to the relevant patient/case history rather than visually pretending to save without changing data.
7. Do not copy Education-specific roles, student evaluation, grading, academic workflow, menus or student-only controls into clinical modules.
8. Keep the canonical Education V2 file unchanged; edit a copy in the feature folder.

## Functional contract

- Form values remain populated when a saved note is reopened in the same mockup session.
- Save/submit actions mutate the mock data and append a note/history event.
- The note feed displays author, role/discipline, timestamp, note type and the saved clinical content that is relevant to the view.
- SOAP labels remain unambiguous: S = Subjective, O = Objective, A = Assessment, P = Plan.
- Empty, validation-error and saved states are represented honestly.
- Any Order/Referral UI must distinguish a mock order from an actual HIS order; do not imply external persistence or execution.
- Cross-role handoff must show the same patient/case context and the data already entered by the previous role.

## QA checklist

- [ ] The feature uses Education V2 clinical-note regions as the source, not a newly invented substitute.
- [ ] Patient and encounter context match the selected case.
- [ ] The same note content is visible after saving and navigating away/back in the active mock session.
- [ ] Note history appends rather than silently overwrites prior notes.
- [ ] Role/discipline and timestamp are visible.
- [ ] Core sections and typography remain visually consistent with Education V2.
- [ ] No Education-only navigation, roles or academic fields remain unless explicitly required.
- [ ] Save, validation, and cross-role workflow were tested in a browser.
