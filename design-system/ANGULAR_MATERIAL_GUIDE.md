# Gorilla HIS — Angular 22 + Angular Material Design & Implementation Guide v1.0

## Purpose

Gorilla HIS Frontend target is **Angular 22** and the preferred UI foundation is **Angular Material**.

Core rule:

> **Angular Material is the primary UI implementation foundation; Gorilla HIS Design System remains the product/design authority.**

Angular Material must reduce custom code, improve consistency, accessibility and Dev handoff — but must not make Gorilla HIS look like a generic default Material application.

---

## 1. Authority

When designing or building Gorilla HIS UI:

`Application Blueprint / Business Truth`
→ `VISUAL_DNA`
→ `LEGACY_DNA`
→ `ADAPTIVE_CLINICAL_DENSITY`
→ `Gorilla Design Tokens / UX Rules`
→ `Angular Material / Angular CDK implementation primitives`
→ `Custom component only when needed`

Angular Material is **not** composition authority and must not override Patient Safety, clinical density, Gorilla HIS continuity or approved product craft.

---

## 2. Material-First Rule

Before creating a custom control, check whether Angular Material or Angular CDK already provides the required behavior.

Prefer Angular Material for common primitives such as:

- Button / Icon Button
- Form Field / Input / Textarea
- Select / Autocomplete
- Checkbox / Radio / Slide Toggle
- Tabs
- Menu
- Tooltip
- Dialog
- Bottom/side Drawer when appropriate
- Sidenav
- Table primitives when appropriate
- Sort / Paginator when appropriate
- Datepicker
- Stepper
- Snackbar / Toast behavior
- Progress / Spinner
- Chips when semantically appropriate
- Expansion Panel when appropriate

Prefer Angular CDK for:

- Overlay
- Portal
- Focus management
- Accessibility behaviors
- Drag/drop when genuinely required
- Virtual scrolling for large lists where appropriate
- Layout/interaction primitives that should not invent custom infrastructure

If Material/CDK can do the job safely and efficiently, do not build an unnecessary bespoke control.

---

## 3. Gorilla Theme over Default Material Look

Do **not** ship default Angular Material appearance unchanged.

Gorilla HIS must apply:

- Gorilla design tokens
- Gorilla typography hierarchy
- Gorilla spacing and density
- Gorilla semantic clinical colors
- Gorilla radius/surface/elevation language
- Gorilla focus/hover/selected states
- Gorilla Patient Context behavior
- Gorilla worklist/table density
- Gorilla Legacy continuity

Material gives the component foundation and interaction behavior; Gorilla gives the product identity.

A screen that looks like an Angular Material demo page = **Design FAIL**.

---

## 4. Clinical Density Rule

Default Material spacing may be too generous for hospital workstations.

For clinical workspaces:

- preserve `ADAPTIVE_CLINICAL_DENSITY.md` ranges;
- do not globally enlarge Material controls;
- do not accept default padding if it wastes important clinical working area;
- use compact density deliberately while preserving click target, readability and accessibility;
- worklist/table/form density must support 1366×768 hospital desktop usage;
- Patient Context must remain a distinct clinical anchor, not a generic Material card.

Material density must be tuned to Gorilla HIS, not the other way around.

---

## 5. Recommended Mapping

| Gorilla HIS Need | Preferred Angular Foundation | Gorilla Requirement |
|---|---|---|
| Primary/Secondary Action | MatButton / MatIconButton | Gorilla button hierarchy and finish |
| Form Field | MatFormField + MatInput | Gorilla density, validation, label hierarchy |
| Search/Lookup | MatInput + MatAutocomplete | keyboard-first workflow, fast selection |
| Tabs | MatTabs | Gorilla active surface/compact clinical tabs |
| Modal/Confirmation | MatDialog | safety language + deliberate confirmation |
| Side Inspector / Context | MatSidenav / CDK Overlay where appropriate | must not create unnecessary permanent nav layer |
| Menu | MatMenu | concise contextual actions |
| Date | MatDatepicker | hospital locale/date rules as project requires |
| Notification | MatSnackBar behavior | Gorilla semantic status rules |
| Loading | MatProgressSpinner / ProgressBar | only where workflow requires |
| Large list/worklist | Material/CDK table/list + virtual scroll when suitable | Gorilla high-density scanability |
| Sorting/Paging | MatSort / MatPaginator when suitable | workflow-driven, not automatic everywhere |
| Step Workflow | MatStepper only when process is truly sequential | do not force wizard layout |

---

## 6. Tables and Worklists

Do not assume `MatTable` is automatically the best answer for every HIS worklist.

Use Angular Material/CDK table primitives where they support the requirement, but prioritize:

- high information density;
- frozen/sticky context where needed;
- efficient keyboard/mouse scanning;
- large data volume performance;
- clear row state and clinical alerts;
- horizontal scroll where clinically necessary;
- selection persistence;
- sort/filter behavior justified by workflow.

A custom table implementation is acceptable only when Material/CDK cannot meet the functional/performance/clinical requirement cleanly. Document the reason.

---

## 7. Forms

Use Angular Material form primitives by default, but Gorilla HIS rules control layout.

Requirements:

- clear label/value hierarchy;
- compact but readable density;
- validation state visible and specific;
- required/disabled/read-only state unmistakable;
- keyboard navigation considered;
- avoid huge vertical form spacing;
- group by clinical task, not by Material component type.

---

## 8. Dialog / Confirmation / Destructive Action

Prefer MatDialog/CDK Overlay behavior for modal interaction.

Clinical/financial/destructive actions must follow Gorilla safety rules:

- clear subject/context;
- exact action being performed;
- consequence when material;
- primary/secondary action hierarchy;
- no generic `Are you sure?` when a safer specific message is possible;
- no dialog merely because Material provides one.

---

## 9. Icons

Angular Material component use does **not** replace the Gorilla icon authority.

Continue to follow `design-system/icon-rules.md`.

Current Gorilla rule remains:

- Font Awesome semantic mapping is the approved icon language;
- no Emoji UI;
- no unnecessary custom SVG when an approved icon exists;
- no CDN/Kit dependency in mockups.

Dev may integrate Font Awesome inside Angular Material controls as the implementation permits.

---

## 10. Accessibility and Interaction

Use Material/CDK accessibility capabilities rather than rebuilding them manually when possible.

Preserve:

- keyboard access;
- visible focus;
- correct disabled state;
- screen-reader semantics where applicable;
- focus trapping/restoration for dialogs/overlays;
- predictable menu/tab behavior;
- deliberate Loading/Empty/Error/Success states.

Accessibility does not justify oversized clinical UI; solve accessibility and density together.

---

## 11. Mockup Factory Rule

The UI Factory currently produces a portable single `index.html` Discovery Mockup.

Because the mockup is not a compiled Angular application, it must **design with Angular Material compatibility in mind**, not load Angular Material through CDN or pretend Material packages are actually running.

For each relevant control, Design Notes should indicate the intended Angular Material mapping, for example:

- Search → `MatFormField + MatInput + MatAutocomplete`
- Main Tabs → `MatTabs`
- Review dialog → `MatDialog`
- Notification → `MatSnackBar`

The mockup may implement equivalent local HTML/CSS/JS behavior for demonstration, while preserving a clear path to Angular 22 implementation.

---

## 12. Dev Handoff Rule

For implementation-oriented handoff, prefer:

**Angular 22 + Angular Material + Angular CDK + Gorilla Design Tokens**

Custom UI is justified when at least one applies:

1. Clinical workflow cannot be represented safely/efficiently with Material primitives.
2. Performance/data volume requires another approach.
3. Gorilla product continuity requires a specialized component.
4. Approved Design System component intentionally wraps/extends Material.
5. Material behavior conflicts with an explicit Blueprint/UX requirement.

The reason must be documented; custom UI must not be created merely for visual novelty.

---

## 13. Angular Material Verification — Post-Build

For every UI Factory candidate, verify:

1. Which Material/CDK primitive each major control maps to.
2. Whether any custom control duplicates an existing Material capability without reason.
3. Whether Material defaults were customized to Gorilla HIS tokens/density/product DNA.
4. Whether the design is feasible in Angular 22 without redesigning the screen.
5. Whether Material usage creates excessive whitespace or generic SaaS appearance.
6. Whether accessibility/focus/overlay behavior can use Material/CDK instead of custom infrastructure.

If a mockup cannot be reasonably implemented in Angular 22 + Angular Material without changing its interaction model, **Dev Handoff Readiness FAILS** until the mismatch is resolved.
