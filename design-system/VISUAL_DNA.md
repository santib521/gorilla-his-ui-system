# Gorilla HIS Visual DNA — Product Craft Standard v2.1

> This document defines the visual character that makes Gorilla HIS recognizable without its logo. It is the highest visual-design authority for mockups. It is not a styling checklist; it defines product taste, craft and desirability.

## 1. Design Ambition

Gorilla HIS is a **precision clinical and operational instrument**. It must not feel like an admin template with hospital data inserted into it.

Target quality:
- **Purpose-built** — composition follows the clinical/operational decision, not a generic dashboard grid.
- **Quiet confidence** — premium comes from proportion, optical balance, typography, surface control and detail.
- **High-density clarity** — more useful information with less cognitive noise.
- **Clinical gravity** — safety signals are unmistakable; everything else remains calm.
- **Crafted, not assembled** — a page feels authored as one product surface, not built from interchangeable cards.
- **Desirable to use** — professional does not mean dry. The interface should feel considered, responsive and satisfying without becoming decorative.
- **Refined at touchpoint level** — buttons, tabs, banners, icon treatment, fields, selectors and status indicators must look and feel like parts of one expensive precision product, not default browser controls with color applied.

A successful page should still feel like Gorilla HIS if logo, module name and brand color are temporarily hidden.

## 2. Premium Mental Model — BMW / iPhone Test

BMW and iPhone are **quality benchmarks, not visual references to copy**. The lesson is that products with the same functions can feel radically different because of proportion, material, control feel, typography, motion and fit-and-finish.

Translate that into Gorilla HIS:

| Product craft principle | Gorilla HIS equivalent |
|---|---|
| Proportion | Information hierarchy and page composition |
| Material | Surface hierarchy and controlled depth |
| Cockpit / instrument cluster | Clinical or operational workspace |
| Control feel | Button, filter, selector and task interaction |
| Typography | Reading priority and numerical instrumentation |
| Ambient light / state change | Contextual emphasis and semantic state |
| Motion / haptics | Micro-interaction and causal state transition |
| Brand DNA | Gorilla visual signature across modules |
| Fit & finish | Pixel-level alignment, rhythm, icon weight and optical balance |

### BMW Test — Mandatory design question
If two systems provide the same function, what in this page makes Gorilla HIS feel deliberately designed rather than merely functional?

If the answer is only `brand color`, `more whitespace`, `rounded corners`, `shadow`, or `better icons` → **FAIL**.

### iPhone Test — Mandatory design question
Can the interface remain refined when decoration is reduced? Can controlled depth and motion improve comprehension without becoming ornament?

If the page is only attractive because of gradients, large cards, glass effects or saturated color → **FAIL**.

## 3. Gorilla Signature

### 3.1 Authored work surface
The primary workspace is composed as one coherent field. Do not turn every information group into an isolated card.

Hierarchy tools, in preferred order:
1. typography and alignment;
2. spacing rhythm and proportion;
3. tonal surface shift;
4. subtle divider / optical border;
5. bounded container when the object genuinely behaves as one object;
6. shadow only when depth/elevation is meaningful.

### 3.2 Precision navigation
Navigation is visually subordinate to the work but must still feel crafted.
- Product identity is controlled, not oversized.
- Active navigation uses a precise indicator, tonal surface and clear icon treatment.
- Module navigation can use rail + contextual lens/secondary navigation.
- Do not use a large dark sidebar merely because enterprise templates do.
- Navigation must feel like a product control, not a prototype index.

### 3.3 Information has a spine
Every page needs a deliberate alignment spine. Key labels, numbers, tables, timelines, visualizations and actions share baselines/columns. Random independent boxes are prohibited.

### 3.4 Numbers are instruments
Operational/clinical numbers behave like instrument readings:
- tabular numerals where alignment matters;
- unit subordinate but optically attached to value;
- threshold, target, delta and time context near the value;
- micro-trend when it helps decision-making;
- never giant marketing numbers;
- color only when semantic meaning exists.

### 3.5 Intelligence is integrated
AI is not a visual theme. Prediction/recommendation should appear as an intelligence layer attached to real evidence.

Preferred pattern:
`Current state → trajectory → time-to-threshold → expected impact → recommended intervention`

Avoid generic `AI Brain`, sparkle, neon, futuristic panel or separate AI showroom.

## 4. Surface Architecture — Premium without decoration

Gorilla HIS uses controlled layers. A whole screen should not be pure white and flat, but it also must not become a pile of floating cards.

### S0 Canvas
Low-contrast cool/warm neutral environment behind the work surface.

### S1 Work Surface
Primary reading/working plane. Usually near-white; high legibility; owns most of the screen.

### S2 Instrument Surface
Compact bounded object for readings, controls or a meaningful instrument cluster. Uses subtle tonal contrast and optical border; not default for every section.

### S3 Elevated Surface
Menus, command selectors, drawers, contextual inspectors, floating controls. Uses real elevation/shadow.

### S4 Semantic Surface
Critical/warning/normal/info state. Semantic color is restrained and local; never repaint the whole application for decoration.

Depth must communicate **hierarchy or interactivity**, not luxury decoration.

## 5. Typography Craft

Typography is the primary hierarchy system.

A metric should normally contain multiple levels, for example:
- technical label;
- value;
- smaller unit;
- threshold or delta;
- optional trend / forecast.

### Readability floor — mandatory
- Normal body / form / worklist / tab text should normally use `--font-size-sm` (14px) or larger.
- `--font-size-xs` (12px) is for secondary metadata, compact labels and dense supporting information only.
- `--font-size-2xs` (11px) is reserved for technical micro-labels and low-priority metadata; it must never carry an instruction, primary action, clinical narrative, patient identity or important status.
- Do not invent 9px/10px local text merely to make more content fit.
- At 1366×768 the user must not need browser zoom to comfortably read the main workflow.

Rules:
- Avoid one weight/size everywhere.
- Avoid uppercase except micro-labels/technical labels.
- Headings remain compact but confident.
- Numerical typography must be optically aligned and easy to compare.
- Metadata is quieter but remains accessible.
- Important narrative may use slightly larger body text rather than a new card.
- Thai body text needs enough line-height and visual breathing room; density must not become cramped typography.

## 6. Shape Language

Use shape to communicate object type.

### Structural regions
Low radius or square; stable and architectural.

### Interactive controls
Moderate radius; clear hover/pressed/selected/focus states.

### Floating contextual objects
Largest radius and elevation because they physically sit above the workspace.

Do not apply the same medium radius to every panel, button, table and section. Repeated rounded rectangles are a generic SaaS signature.

## 7. Color and Light

### Product palette
- **Gorilla Ink** — deep neutral structure/text.
- **Precision Indigo** — selection, primary interaction and intelligence accent.
- **Clinical Teal** — controlled brand accent, not a substitute for semantic state.
- **Refined Neutrals** — canvas/work surfaces with enough tonal difference to create depth.
- **Clinical semantics** — critical/warning/normal/info retain strict meaning.

Premium color is not “more color”; it is disciplined saturation, contrast and relationship.

### Controlled light
Use subtle optical borders, tonal surfaces and ambient shadow only where depth is real. Avoid both extremes:
- flat white + hairlines everywhere = dry/unfinished;
- shadow/gradient everywhere = ornamental/template-like.

## 8. Motion & Micro-interaction

Professional HIS may and should have **controlled delight**.

Motion must explain causality:
- scenario changes → values transition → affected flow changes → exception emerges → decision state updates;
- task completion → capacity/status visibly resolves;
- drawer/modal/selector has clear spatial transition.

Recommended timing family:
- micro state: 120–180 ms;
- control/surface transition: 180–260 ms;
- causal dashboard/visual transition: 240–360 ms.

Respect reduced-motion preferences. No decorative perpetual animation.

Premium interaction means the user feels that every response was designed, not that the interface is animated.

## 9. Data Visualization Language

Data visualization is a product component, not decoration.

Preferred families:
- **Micro sparkline** — trend context beside KPI.
- **Threshold rail / capacity gauge** — current vs safe operating range.
- **Operational flow spine** — flow, pressure, velocity and bottleneck across stages.
- **Forecast band** — current trajectory + uncertainty + time horizon.
- **Time-to-threshold** — when operationally more useful than percentage alone.
- **Matrix / bed field / queue field** — operational state where spatial scanning matters.

A visualization must answer a decision question. Do not add charts because dashboards are expected to have charts.

## 10. Composition before Components

Before choosing components, define:
- **Decision Question** — what must the user know/decide in the first 5 seconds?
- **Primary Evidence** — what proves that situation?
- **Exception** — what requires attention now?
- **Primary Action** — what is the next safe action?
- **Secondary Evidence** — what supports deeper investigation?

Then create an authored visual path:
`Situation → Evidence → Exception → Action → Detail`

Component availability must not dictate composition.

## 11. Premium Fit & Finish — Component Jewelry Standard

A premium Gorilla HIS page can still fail if the small touchpoints look cheap. Evaluate controls as if they are the switches, knobs and trim pieces of a premium cockpit.

### Buttons
- Primary button must have clear silhouette, optical balance, icon/text spacing when an icon is used, and distinct hover/pressed/focus feedback.
- Avoid tiny short buttons, browser-default select styling, weak border-only buttons and arbitrary radii.
- Important actions should normally use at least `--font-size-sm` and a comfortable 36–44px control height depending on density.
- Secondary controls must look intentionally subordinate, not disabled or unfinished.

### Tabs
- Tabs must feel integrated into the work surface, not like underlined text links.
- Active state requires at least two cues chosen from: tonal surface, precise indicator, type weight, icon treatment, spatial attachment to active content.
- Tabs need enough vertical hit area and readable type. Tiny 10–11px tabs are prohibited for main workflow navigation.

### Banners / context strips
- A banner representing a mode, safety boundary or workflow constraint must be visually unmistakable within the first viewport.
- Use strong hierarchy: icon/mark + title + concise explanation + optional action/status.
- A critical context banner must not look like a pale decorative strip that can be ignored.
- The banner must remain distinguishable in grayscale through shape, border, weight and placement — not color alone.

### Icons
- Icons must have consistent optical size, weight and container relationship.
- Main navigation and important actions must not fall back to raw abbreviations such as `EDU`, `CASE`, `EMR` when a standard semantic icon is available.
- Text label may accompany the icon, but icon treatment should feel intentional rather than placeholder-like.
- If Font Awesome cannot render because local assets are unavailable, the mockup must use an approved non-deceptive fallback strategy documented in Design Notes; do not silently hide icon space or replace it with cheap placeholder text.

### Fields / selectors
- Form controls need refined focus, hover and selected states, aligned heights and consistent internal padding.
- Native-looking browser selects/inputs without crafted states are not Premium Candidate quality.

### Fit & Finish FAIL examples
- readable content is mostly 9–11px;
- mode/safety banner is visually weaker than ordinary content;
- tabs read like plain links;
- buttons look like default Bootstrap/browser controls;
- icons are missing, hidden or replaced with abbreviations;
- spacing inside controls is inconsistent;
- repeated thin borders make the page look low-cost or unfinished.

## 12. Anti-Template Test — Mandatory

Before PASS, ask:
1. Could this plausibly be CRM, fintech, logistics SaaS or generic admin after changing labels? **If yes → FAIL.**
2. Is the page mainly a collection of repeated rounded rectangles? **If yes → FAIL.**
3. Are major regions equal-sized because a grid was easy? **If yes → FAIL.**
4. Does removing color destroy hierarchy? **If yes → FAIL.**
5. Does the operational story remain obvious in grayscale? **If no → FAIL.**
6. Is there a clear authored focal path? **If no → FAIL.**
7. Is AI visually themed differently from the HIS? **If yes → FAIL.**
8. Does it feel merely tidy/functional but visually lifeless? **If yes → FAIL Premium Craft.**

## 13. Desirability Test — Mandatory for Premium Candidate

A Premium Candidate must create the reaction:
**“This feels precise, expensive, calm and intentionally designed — I want to use it.”**

It must not depend on superficial luxury effects.

Evaluate:
- visual balance and proportion;
- surface richness without clutter;
- typography craftsmanship;
- instrument quality of data;
- meaningful depth;
- micro-interaction quality;
- custom operational visualization where the workflow deserves it;
- coherent identity across the full page;
- component jewelry quality: buttons, tabs, banners, icons, selectors and field details.

If Human Visual Review returns only “clean”, “neat”, “usable” or “professional” but not “crafted/desirable” → keep status **Candidate**, not Premium.

## 14. Archetype — Command / Operational Intelligence

The Command Center is a **live decision instrument**, not a dashboard gallery.

First viewport communicates:
1. current hospital operating state;
2. trajectory / what is likely to happen;
3. bottleneck or exception;
4. evidence and time-to-threshold;
5. the next coordinated intervention and projected impact.

Preferred visual grammar:
- crafted situation/header layer;
- integrated Hospital Instrument Band, not spreadsheet KPI cells;
- dominant Operational Flow / Capacity Field;
- exception integrated at the affected point;
- Intelligence Intervention layer with rationale and projected impact;
- contextual tactical/frontline drill-down;
- subtle scenario transition that visibly changes the system state.

Do **not** lock this archetype to a fixed 2/3 + 1/3 template. Proportion follows the decision and evidence.

## 15. Gold Standard Rule

No component, layout master or pattern may call itself **Premium**, **World-class**, **Gold**, or **Signature** solely because it passes Factory Gate.

Promotion requires:
- rendered visual review;
- Human Design Approval;
- Anti-Template Test PASS;
- Desirability Test PASS;
- comparison with relevant Gorilla HIS continuity reference when available;
- evidence that composition was designed around workflow/decision;
- evidence of craft beyond default component assembly.

Until Human Design Approval exists, label artifact **Candidate**.

## 16. Extraction Rule

`Human-approved reference page → extract recurring Visual Grammar → extract components/patterns → Factory enforcement`

Never reverse this into:
`generic components → assemble page → declare premium`.
