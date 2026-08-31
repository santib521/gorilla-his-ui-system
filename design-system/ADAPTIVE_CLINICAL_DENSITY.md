# Gorilla HIS Adaptive Clinical Density Standard v1.0

This standard governs clinical workspaces where patient context, worklists and documentation compete for screen space. The goal is **high-density clarity**, not uniformly large UI and not tiny compressed UI.

## 1. Core Principle

`Density follows task phase and information priority.`

Do not solve readability by enlarging every element. Do not solve density by shrinking every element.

A premium clinical workspace should feel compact, calm and controlled: important content is immediately readable, supporting information is quieter, and temporary navigation/selection surfaces give space back to the main work when no longer needed.

## 2. Typography Hierarchy

Typography must use hierarchy, not a single global size.

Recommended working ranges at normal desktop zoom:
- Patient identity / page or task title: 16–18px when it is the primary anchor.
- Main clinical narrative / form value / primary workflow control: 13–14px.
- Worklist row primary label / main tab / important status: 13–14px.
- Secondary metadata / HN / encounter / timestamps / supporting labels: 11–12px.
- Technical micro-label: 11px only when low priority.

Rules:
- Never enlarge all regions merely to satisfy readability.
- Never use 9–10px for meaningful workflow content.
- Use weight, alignment, spacing, contrast and grouping before increasing font size.
- Thai text must remain comfortably readable without making the whole workspace visually oversized.
- At 1366×768 and 1920×1080, the first viewport must retain useful clinical working area.

## 3. Persistent Patient Context Anchor

When a screen is patient-specific, Patient Context is a **clinical anchor**, not another ordinary banner or row.

It must remain visually identifiable while the user works and should normally include, when relevant:
- patient identity;
- HN / encounter / location;
- attending / care context;
- high-value safety context such as allergy;
- compact clinical instruments such as vitals only when useful to the workflow.

The Patient Context Anchor must:
- be visually distinct from tabs, worklist rows and ordinary content;
- remain compact;
- use composition, alignment, surface and semantic zones to create prominence rather than excessive height;
- remain recognizable in grayscale;
- avoid looking like a marketing hero or decorative card.

A patient banner that visually blends into surrounding lists or tabs = FAIL.

## 4. Collapsible Context Panel

Patient/work/task selection panels must not permanently consume large width after selection when the workflow benefits from more working space.

Support relevant states:

### Expanded
Used for search, filtering, patient/task comparison and selection.

### Compact
A narrow persistent control retains orientation, count/status and a clear expand affordance while returning most width to the clinical workspace.

### Auto-collapse
When safe and useful, selection may collapse after a patient/task is chosen. Auto-collapse must never hide critical context because the Patient Context Anchor remains visible.

Rules:
- Collapse/expand control must be obvious and keyboard/focus accessible.
- State change must use a short causal transition, not decorative animation.
- User can reopen without losing search/filter/selection state.
- Do not auto-collapse when the user must continuously compare multiple patients/tasks.
- Do not create a second permanent navigation column merely to expose functions already available in the patient workspace.

## 5. Navigation Layer Budget

Clinical workspaces should avoid stacked navigation competing for attention.

Before adding another rail, tab row, worklist or secondary menu, classify it as one of:
1. Product / Module Navigation;
2. Patient or Task Selection;
3. Patient Workspace Navigation;
4. Contextual Action / Inspector.

If two layers serve the same purpose, consolidate them.

Main rule: **navigation is subordinate to clinical work**.

Three simultaneously dominant navigation layers = likely FAIL unless workflow evidence justifies them.

## 6. Adaptive Workspace Rule

The workspace should gain usable area as the user moves from selection to focused work.

Preferred clinical sequence when appropriate:
`Find / Select → Patient Context locks → Selection panel may compact/collapse → Main workspace expands → Contextual inspector appears only when needed`

This is a behavioral pattern, not a mandatory fixed layout.

## 7. Premium Density Test

PASS when:
- important text is readable without making the whole UI large;
- patient context is unmistakable but compact;
- temporary selection/navigation gives space back when appropriate;
- the main clinical task owns the largest useful area;
- the first viewport feels information-rich but not crowded;
- existing Gorilla HIS users retain orientation.

FAIL when:
- every font/control was enlarged globally;
- patient header blends into ordinary content;
- worklist permanently wastes width after selection without workflow reason;
- multiple navigation layers compete with the task;
- whitespace or large controls materially reduce clinical working area;
- density is achieved with unreadably small type.

## 8. Human Review Questions

Ask during rendered review:
1. Is the main clinical content comfortably readable at 100% zoom?
2. Is anything unnecessarily large?
3. Can the reviewer identify the current patient immediately?
4. Does patient/task selection consume space after its job is done?
5. Can the selection panel collapse and reopen without losing context?
6. Does the main task receive the most useful screen area?
7. Does the page feel calm and expensive because of proportion and control, not because everything is larger?
