# Gorilla HIS Visual DNA — Product Craft Standard v2.6

> Highest visual-design authority. Gorilla HIS is a precision clinical/operational instrument, not an admin template.

## 1. Human-Approved Visual Authority
The human-approved Social Work reference `index_10.html` supplied on 2026-09-04 is now the **primary UX/UI visual grammar reference** for Gorilla HIS operational modules unless a later Human-approved Gold Standard supersedes it.

The goal is not loose inspiration. New operational mockups should look and feel materially consistent with this reference in:
- shell proportion;
- typography;
- spacing and density;
- surface hierarchy;
- navigation treatment;
- buttons, badges, tabs and forms;
- worklist rhythm;
- patient/context anchors;
- modal/drawer behavior;
- status color discipline;
- numerical instrumentation.

**If a candidate is visibly unlike this reference without a workflow/safety reason, it is not a valid premium candidate.**

## 2. Design Ambition
Target: purpose-built, quiet confidence, high-density clarity, clinical gravity, crafted-not-assembled, desirable to use, refined at touchpoint level.

Mental model:
`Precision cockpit discipline × calm hospital density × authored workflow composition × Gorilla HIS continuity`.

## 3. Canonical Shell Grammar — HARD RULE
Default operational module shell:
- sticky **52px white topbar**;
- compact **64px dark command rail** on the left;
- soft cool-gray canvas;
- one dominant white work surface with subtle border and optical shadow;
- work surface owns most viewport width;
- module context visible in topbar;
- role/profile utilities live in topbar and do not compete with work;
- command rail uses icon-first navigation, tooltip labels, restrained count badges and a clear active state.

Command rail reference behavior:
- dark navy/charcoal gradient;
- minimum item height about 46px;
- transparent inactive items;
- active item becomes a light/white instrument surface with primary-action color;
- thin left active indicator;
- hover reveals label tooltip;
- counts appear only when operationally useful.

A wide dark sidebar with large text blocks is **not** the default premium shell.

## 4. Surface Architecture
Use four visual levels:
- **S0 Canvas** — cool low-contrast gray environment;
- **S1 Work Surface** — dominant white operational plane;
- **S2 Instrument Surface** — subtle gray/blue reading/control region;
- **S3 Elevated Surface** — drawer, modal, dropdown, contextual overlay.

Depth communicates hierarchy/interactivity, not decoration.

Preferred order of hierarchy tools:
1. typography/alignment;
2. spacing/proportion;
3. tonal shift;
4. subtle divider;
5. bounded container when the object truly behaves as one object;
6. shadow only for real elevation.

Repeated Card Everywhere = FAIL.

## 5. Typography — IBM PLEX SANS THAI AUTHORITY
The approved reference uses **IBM Plex Sans Thai** and this is now the primary product typography target.

Primary stack:
`"IBM Plex Sans Thai", "Noto Sans Thai", "Sarabun", "Segoe UI", Tahoma, sans-serif`

Numerical/technical stack may use:
`"IBM Plex Sans Thai", Consolas, "Noto Sans Mono", monospace`

Rules:
- IBM Plex Sans Thai is the visual target for production and rendered visual review;
- Thai body copy remains normal/medium weight, not bold everywhere;
- monospace treatment is for identifiers, dates, money, score, quota and aligned numeric instruments only;
- do not use monospace for Thai prose or patient names;
- production Angular should bundle/serve the approved font through application assets;
- self-contained mockups must not fetch external CDN fonts unless explicitly allowed by the active Factory contract; if the approved font is not actually rendered, Typography cannot be called fully verified.

Reference scale:
- root/body: 14px-class operational density (`0.875rem` baseline in the approved token system);
- technical metadata: 10–12px;
- worklist/table body: about 14px;
- patient name: 14px/600;
- HN/VN/subtext: 11–12px;
- table header: 10–11px uppercase technical style when appropriate;
- tabs/buttons/forms: 12–14px depending importance;
- page title: 22px-class (`1.375rem`) only where a true page context exists;
- patient context anchor name: 16px-class;
- KPI/instrument values may be 18–32px when they are genuine instruments.

Readability comes from font family, weight, contrast, grouping and rhythm before size inflation.

## 6. Color Grammar
Use the approved cool-neutral + indigo/blue action grammar:
- primary action: indigo/blue;
- normal/success: green;
- warning: orange/amber;
- critical: red;
- inactive/closed: gray;
- teal may support brand continuity but should not replace the action hierarchy.

Use semantic pale backgrounds with darker semantic text/borders. Color supports meaning; wording and position must still communicate state in grayscale.

Avoid rainbow UI and over-saturated work surfaces.

## 7. Shape / Border / Shadow Discipline
Reference-derived geometry:
- structural radius: 3–4px;
- controls: around 8px;
- work surfaces/contextual sections: around 12px;
- 16px only for rare floating objects;
- pill/full radius only for chips, badges, counts and compact filters.

Prefer subtle borders and optical shadows. Heavy soft shadows on every card are prohibited.

## 8. Spacing Rhythm
Use the approved 4/8/12/16/20/24/32/48/64 rhythm.

Operational density should feel compact but not cramped:
- topbar ≈ 52px;
- command rail ≈ 64px;
- workspace outer padding ≈ 12px;
- page/context horizontal padding ≈ 20px;
- primary content padding ≈ 20px;
- worklist rows around 10px vertical cell padding;
- compact controls 32–38px high.

Reduce decorative whitespace before shrinking important information.

## 9. Page Composition — HUMAN-APPROVED GRAMMAR
Preferred operational composition:
`Topbar + Command Rail → Work Surface → Page Context → optional Patient/Case Context Anchor → Tabs/Attention Strip → Command Bar → Operational Work → Drawer/Modal on demand`

The page must have a visual spine:
`Context → Situation → Evidence/Work → Exception → Next Action → Detail`.

Do not start from Dashboard + cards + sidebar merely because it is easy.

## 10. Patient / Case Context Anchor
When work is patient-centered, use a compact context anchor before deep work:
- patient name is primary;
- HN/VN/age/right/encounter are secondary metadata;
- prior-history indicator may appear as a small semantic cue;
- case actions stay on the right;
- avoid duplicating the same patient identity in multiple giant cards.

## 11. Buttons — HARD INTERACTION GRAMMAR
Button hierarchy:
- **Primary**: filled indigo/blue, strongest valid next action;
- **Secondary**: white surface + strong neutral border;
- **Quiet**: transparent, low visual weight;
- **Danger**: restrained red semantic treatment;
- **Small row action**: ~32px high, compact padding.

All enabled controls require hover/focus/pressed behavior. Disabled must be visibly disabled.

A status badge must never look like a button. A button must never look like passive status.

## 12. Badges / Status
Badges are small semantic instruments:
- short wording;
- pale semantic background;
- darker semantic text;
- thin semantic/neutral border;
- around 10–11px technical size when secondary.

Do not use large colorful pills as the dominant row structure.

## 13. Tabs
Tabs should use:
- flat horizontal row;
- subtle background only on selected/hovered state;
- active text in primary action color;
- thin 2px active underline;
- optional compact count badge.

Avoid large segmented-card tabs unless the job specifically needs them.

## 14. Forms
Reference form grammar:
- labels 12px-class, semibold, secondary neutral;
- controls around 38px high;
- white fill, strong neutral border, 8px radius;
- focus = primary border + soft primary focus ring;
- validation uses explicit message + semantic border/background;
- multi-column grids only when fields remain readable.

## 15. Worklist Grammar
For transaction-heavy hospital work:
- one dominant worklist surface;
- compact command/search/filter bar attached to it;
- stable aligned columns;
- technical header row in subtle gray;
- 14px-class row body;
- patient name stronger than HN/subtext;
- numbers/amounts/quotas use aligned/tabular instrumentation;
- restrained hover row;
- attention row may receive a subtle semantic wash;
- closed/off rows may reduce emphasis but remain inspectable;
- primary next action remains proportionate, not a wall of saturated buttons.

Follow `ENTERPRISE_WORKLIST_STANDARD.md` for detailed behavior.

## 16. Assessment / Professional Workspace Grammar
Deep professional work should look like an instrument, not a generic modal form:
- collapsible bounded sections;
- compact evidence blocks;
- tables for repeated economic inputs;
- score/result as an instrument with clear breakdown;
- prior assessment context shown before current reassessment;
- selected choices use primary border/soft primary surface;
- entitlement/progress uses compact quantitative tiles and bars;
- timeline uses a single vertical spine with semantic event markers.

## 17. Modal / Drawer
Use modal when a focused decision can be completed without losing list context. Use right drawer when the user needs contextual inspection while preserving the parent workspace.

Reference behavior:
- modal width around 480px for focused tasks;
- drawer around 560px for richer context;
- white surface;
- 12px radius;
- strong but controlled overlay shadow;
- fixed header/footer, scrollable body when needed.

## 18. Icons
Use consistent line icons at approximately 15–18px. Icons clarify semantics; they are not decoration.

No emoji UI. Avoid mixed icon families. Interactive icon-only controls must provide tooltip/accessible label.

## 19. Benchmark No-Regression — HARD GATE
When a Human-approved reference exists:
`EXTRACT → REUSE GRAMMAR → ADAPT TO WORKFLOW → RENDER → COMPARE`

Reviewer must compare:
- shell footprint;
- font and density;
- work-surface proportion;
- border/radius/shadow discipline;
- action hierarchy;
- badge vs button distinction;
- table rhythm;
- patient context treatment;
- modal/drawer polish;
- overall calmness and authored quality.

If visibly weaker than `index_10.html` without workflow/safety reason = `FAIL — VISUAL REGRESSION`.

## 20. Anti-Template Test
FAIL when:
1. screen could become CRM/fintech/logistics by changing labels;
2. page is mostly generic rounded cards;
3. wide sidebar visually dominates work;
4. UI uses local arbitrary colors/radii/shadows;
5. status and action look the same;
6. typography does not resemble the approved IBM Plex Sans Thai reference;
7. important patient/work context is fragmented;
8. candidate feels AI/template-generated rather than authored;
9. worklist density/rhythm is materially worse than the approved reference.

## 21. Responsive / Adaptive Density
At narrower widths:
- preserve command rail continuity;
- allow work surfaces/tables to adapt/scroll;
- keep patient/context anchors visible;
- do not solve width pressure by shrinking Thai operational text below readability;
- keep primary action discoverable.

## 22. Independent Premium Review
`Functional PASS + Visual Regression FAIL = Factory FAIL`.
`Functional PASS + Typography FAIL = Factory FAIL`.

Human Visual Review remains required before Gold/Signature promotion.

## 23. Gold Standard Rule
Human-approved reference strengths become reusable product grammar. Do not copy accidental content/business assumptions, but preserve approved visual behavior.

## 24. Final Rule
**The current Gorilla HIS operational visual baseline is the approved `index_10.html` grammar: compact command rail, white work surface, cool neutral canvas, IBM Plex Sans Thai, indigo action hierarchy, restrained semantic status, precise borders/radii, dense readable tables and instrument-like professional workspaces.**
