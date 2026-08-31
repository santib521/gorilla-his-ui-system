# Gorilla HIS UI Factory Gate — Premium Craft v3.0

Factory Gate is mandatory for every Gorilla HIS mockup. Its purpose is not only consistency. It must protect business truth, clinical safety, product continuity and premium craft.

If this file conflicts with `AI_INSTRUCTIONS.md`, `AI_INSTRUCTIONS.md` wins.

## 1. Authority

### Business Authority
1. Application Blueprint
2. Workflow / Requirement / Function List / Business Rules explicitly derived from the Blueprint

Missing Blueprint information = `N/A — not present in Blueprint`. Do not invent business rules to satisfy a checklist.

### Design Authority
1. `design-system/VISUAL_DNA.md`
2. `AI_INSTRUCTIONS.md`
3. `design-system/design-rules.md`, `ux-rules.md`, `tokens.css`, `icon-rules.md`
4. Human-approved Gold Standard relevant to the archetype
5. Approved Components / Patterns
6. Relevant actual Gorilla HIS screenshots for continuity
7. Candidate references
8. AI design judgment

**Important:** component reuse does not override Visual DNA. A component is a primitive, not a composition master.

## 2. Gate Flow

`Blueprint → Pre-Build → Decision Architecture → Product Feeling Intent → Reuse Contract → Craft Plan → Build → Self-QA → Post-Build → Independent QA → Human Visual Review → Approved → Gold Standard when explicitly promoted`

- Pre-Build FAIL = STOP
- Self-QA FAIL = FIX before Post-Build
- Post-Build FAIL = RETURN TO BUILDER
- Visual/Craft FAIL = RETURN TO BUILDER
- Human Approved ≠ Gold Standard until explicitly promoted

## 3. Binding Reuse Contract

Before coding, Builder declares relevant approved sources and planned use.

Minimum roles:

| Role | Source | Requirement |
|---|---|---|
| Visual DNA | `design-system/VISUAL_DNA.md` | composition/craft authority |
| Design Tokens | `design-system/tokens.css` | approved palette, surfaces, depth, type, motion |
| Icons | `design-system/icon-rules.md` | approved semantic Font Awesome mapping |
| Shell continuity | `design-system/components/application-shell.html` | reuse product identity/navigation behavior where relevant |
| Controls / Modal / Forms | relevant approved components | reuse interaction behavior and states |
| Pattern | relevant approved pattern(s) | reuse when workflow genuinely fits |
| Gold Standard | relevant Human-approved artifact | use only when archetype is close |

`Read/Reference ≠ Reuse` — implementation evidence must exist in `index.html`.

However, **reuse must not force weak composition**. If an existing candidate/master creates generic or barren output, Visual DNA has higher authority. Declare the divergence and preserve behavior/continuity rather than mechanically copying layout.

## 4. Decision Architecture Gate

Before coding Builder must state:
- Decision Question
- Primary Evidence
- Exception
- Primary Action
- Secondary Evidence

PASS only when these are grounded in the Blueprint.

## 5. Product Feeling Gate

Builder must state:
- 3–5 intended qualities, e.g. `precision / calm / responsive / crafted / confident`;
- 2–4 prohibited feelings, e.g. `admin template / barren spreadsheet / AI showcase / consumer toy`.

The rendered result is later evaluated against this intent.

## 6. Premium Craft Plan

Before Build declare how the page will achieve:
- authored proportion and focal path;
- Surface Architecture (Canvas / Work / Instrument / Elevated / Semantic);
- typography hierarchy;
- instrument-quality numbers;
- meaningful data visualization where needed;
- controlled depth;
- restrained color;
- micro-interaction / causal motion;
- product-specific detail beyond default component assembly.

A plan that only says `use cards / grid / colors / shadow / icons` = FAIL.

## 7. Hard Reject

Reject immediately when any applies:
- Blueprint not read;
- mandatory authority source not read;
- external CDN/font/JS/CSS or Font Awesome CDN/Kit;
- real patient data;
- missing Main Workflow / Critical Requirement;
- dead Main Workflow action;
- workflow-breaking JS error;
- hidden chain-of-thought in deliverables;
- local palette/design-token aliases used to bypass `tokens.css`;
- patient-safety semantic colors used decoratively;
- Emoji used as UI icon;
- custom icon/SVG used when approved Font Awesome semantic icon exists without approved exception;
- generic AI/futuristic theme;
- repeated rounded-card grammar used as the page architecture;
- visual hierarchy collapses when color is removed;
- composition is explained by an easy grid rather than workflow importance;
- page is merely a flat white spreadsheet/table with hairlines and no crafted surface hierarchy;
- page calls itself Premium/Gold/World-class without Human Visual Approval.

## 8. Premium HIS Visual Gate

Rendered UI must be reviewed whenever rendering is possible. If the tool cannot render, record `VISUAL REVIEW LIMITATION`; code inspection cannot self-certify Premium.

| Gate | Question | PASS condition |
|---|---|---|
| VG-01 Product Character | Purpose-built HIS or generic software? | Clinical / Operational / Trustworthy / Crafted / Desirable |
| VG-02 Decision Hierarchy | Can user grasp situation in ~5 seconds? | Situation → evidence → exception → action is visually obvious |
| VG-03 Icon System | Approved icon language? | Font Awesome semantic mapping; no Emoji/CDN/unapproved replacement |
| VG-04 Composition | Authored or grid-generated? | Proportion follows importance; no mechanical equal-card composition |
| VG-05 Surface Architecture | Too flat or too decorative? | Deliberate Canvas/Work/Instrument/Elevated layers; depth has meaning |
| VG-06 Typography Craft | Does typography carry hierarchy? | Values, units, labels, metadata and narrative have intentional rhythm |
| VG-07 Instrument Quality | Do key measures feel like readings or spreadsheet cells? | Threshold/delta/trend/forecast/context used when decision-relevant |
| VG-08 Color Discipline | Controlled and semantic? | Neutral-led; Indigo/Teal restrained; clinical semantics remain strict |
| VG-09 Data Visualization | Does visualization answer a decision question? | Flow/trend/forecast/capacity visualization used where it improves comprehension |
| VG-10 Interaction Craft | Does state change feel deliberate? | Hover/selected/pressed and relevant causal transitions are clear and restrained |
| VG-11 AI Integration | AI showroom or integrated intelligence? | Prediction/recommendation is attached to evidence and operational impact |
| VG-12 Density | Real HIS information density without noise? | First viewport carries meaningful work and remains scannable |
| VG-13 Anti-Template | Could labels be swapped for CRM/fintech? | No — composition and visualization are purpose-built |
| VG-14 Dryness / Barren Test | Does it feel sterile, unfinished or bureaucratic? | No — surface, type, instrument and interaction craft create a refined product feel |
| VG-15 Desirability | Would a user describe it as crafted and desirable, not merely tidy? | Candidate is visually compelling without luxury decoration |

### Severity

Automatic P0 Design FAIL:
- VG-01, VG-02, VG-08, VG-11, VG-13
- clear clinical-safety misuse
- external asset violation
- workflow failure

Premium Candidate cannot pass Human Visual Review when:
- VG-05, VG-06, VG-07, VG-10, VG-14 or VG-15 materially fail.

## 9. BMW Test — Product Quality Benchmark

This is a quality metaphor, not a visual-copy instruction.

Question:
**If another HIS has the same features, what in this screen makes Gorilla HIS feel materially more designed?**

Evidence may include:
- better proportion;
- richer but controlled surface hierarchy;
- superior instrument readability;
- clearer decision path;
- refined control feel;
- better causal motion;
- precise micro-detail;
- distinctive operational visualization.

If the only answer is color/logo/shadow/radius/icons → FAIL Premium Craft.

## 10. iPhone Test — Restraint + Refinement Benchmark

Questions:
- When decoration is reduced, does the interface remain refined?
- When depth is added, does it improve hierarchy instead of adding ornament?
- Does every interaction feel deliberate?
- Is visual complexity reduced without removing useful information?

A page cannot pass by being either flashy **or** barren.

## 11. Operational / Command Center Rule

Command Center is a live decision instrument, not a fixed layout template.

The previous `premium-operational-layout.html` is **Candidate Reference only** and is not mandatory composition authority.

The first viewport should communicate:
1. operating state;
2. trajectory / time-to-threshold;
3. bottleneck;
4. evidence;
5. intervention + projected impact.

Prefer, when appropriate:
- Hospital Instrument Band;
- Operational Flow Spine;
- Forecast / time-to-threshold;
- embedded exception at the affected point;
- Intelligence Intervention layer;
- scenario transitions that propagate through the system.

Do not force a 2/3 + 1/3 arrangement. Proportion follows information importance.

## 12. Post-Build Required Evidence

Post-Build must include:
- Blueprint Traceability Table
- Binding Reuse Verification Table
- Decision Architecture Verification
- Product Feeling Verification
- Anti-Template Test
- Dryness / Barren Test
- BMW Test
- iPhone Test
- Premium HIS Visual Gate VG-01..VG-15
- Human Visual Review limitation/status

## 13. Gold Standard Rule

Factory PASS = technically/design-governed Candidate only.

Promotion sequence:
`Candidate → Independent QA Passed → Human Approved → explicit Gold Standard promotion`

Human visual judgment is required for Premium/Gold status.
