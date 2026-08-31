# Gorilla HIS UI Factory Gate — Evolution Craft v3.1

Factory Gate is mandatory for every Gorilla HIS mockup. It protects business truth, clinical safety, recognizable product continuity, speed of prototyping and premium craft.

If this file conflicts with `AI_INSTRUCTIONS.md`, `AI_INSTRUCTIONS.md` wins.

## 1. Authority

### Business Authority
1. Application Blueprint
2. Workflow / Requirement / Function List / Business Rules explicitly derived from the Blueprint

Missing Blueprint information = `N/A — not present in Blueprint`. Do not invent business rules.

### Design Authority
1. `design-system/VISUAL_DNA.md`
2. `design-system/LEGACY_DNA.md`
3. `AI_INSTRUCTIONS.md`
4. `design-system/design-rules.md`, `ux-rules.md`, `tokens.css`, `icon-rules.md`
5. Human-approved Gold Standard relevant to the archetype
6. Approved Components / Patterns
7. Relevant actual Gorilla HIS screenshots for continuity
8. Candidate references
9. AI design judgment

Components are primitives, not composition masters.

## 2. Factory Flow

For `PROTOTYPE READY`:

`Blueprint → Legacy DNA Scan → FAST PRE-BUILD → Visual Concept → Build index.html → START_HERE → Self-QA → Post-Build → Independent QA → Human Prototype Review → Hospital Confirmation`

For confirmed/product UI:

`Confirmed Blueprint → Legacy DNA Scan → Full Pre-Build → Visual Concept → Build → Self-QA → Post-Build → Independent QA → Human Visual Review → Approved → Gold when explicitly promoted`

Rules:
- Pre-Build FAIL = STOP
- Visual Concept FAIL = STOP
- Self-QA FAIL = FIX before Post-Build
- Post-Build FAIL = RETURN TO BUILDER
- Legacy Continuity FAIL = RETURN TO BUILDER
- Visual/Craft FAIL = RETURN TO BUILDER

## 3. FAST PRE-BUILD Gate — PROTOTYPE READY

The purpose is to reach a useful first `index.html` quickly without weakening safety.

Before coding, Builder must state only:
1. Blueprint status + critical safety boundary;
2. Legacy Preserve / Improve / Replace summary;
3. Decision Question / Primary Evidence / Exception / Primary Action;
4. Visual Concept Signature;
5. Binding Reuse Contract;
6. top Anti-Template / Legacy Continuity risks;
7. PASS / FAIL.

Do not generate long traceability or compliance prose before the first working screen. Detailed evidence moves to Post-Build.

## 4. Legacy Continuity Gate

Review relevant real Gorilla HIS screenshots and classify important product grammar as:
- PRESERVE
- IMPROVE
- REPLACE

PASS when:
- the mockup remains recognizable as Gorilla HIS;
- familiar clinical/operational navigation and context are retained where useful;
- modernization improves hierarchy/control feel without inventing a different product family.

FAIL when:
- the page looks like another vendor, generic SaaS, LMS, CRM or fashionable clean-sheet redesign;
- legacy density/navigation/context is discarded without workflow rationale;
- continuity is claimed only through logo or brand color.

## 5. Visual Concept Gate

Before coding answer:

**What makes this screen unmistakably Gorilla HIS and materially better to operate than the current generation?**

PASS requires:
- recognizable legacy continuity;
- workflow-specific composition or interaction idea;
- concrete operational/clinical improvement;
- craft beyond color/radius/shadow/icons.

If the concept is only `clean / modern / premium / blue / spacious` = FAIL.

## 6. Binding Reuse Contract

Before coding declare relevant approved sources and planned use.

Minimum roles to evaluate:
| Role | Source | Requirement |
|---|---|---|
| Visual DNA | `design-system/VISUAL_DNA.md` | composition/craft authority |
| Legacy DNA | `design-system/LEGACY_DNA.md` + screenshots | continuity/evolution |
| Tokens | `design-system/tokens.css` | approved values |
| Icons | `design-system/icon-rules.md` | semantic Font Awesome |
| Shell continuity | approved shell / relevant real screenshot | preserve product family where suitable |
| Controls / Forms / Modal | relevant approved components | behavior/states |
| Pattern | relevant approved pattern(s) | reuse when workflow fits |
| Gold Standard | relevant Human-approved artifact / N/A | archetype continuity |

`Read/Reference ≠ Reuse`.

Do not require KPI/Operational components when irrelevant.

## 7. Decision Architecture Gate

State:
- Decision Question
- Primary Evidence
- Exception
- Primary Action
- Secondary Evidence

PASS only when grounded in Blueprint.

## 8. Hard Reject

Reject immediately when any applies:
- Blueprint not read;
- mandatory authority source not read;
- external CDN/font/JS/CSS or Font Awesome CDN/Kit;
- real patient data;
- missing Main Workflow / Critical Requirement;
- dead Main Workflow action;
- workflow-breaking JS error;
- hidden chain-of-thought in deliverables;
- local palette used to bypass tokens;
- patient-safety semantic colors used decoratively;
- Emoji UI;
- unapproved custom icon when approved FA semantic icon exists;
- generic AI/futuristic theme;
- repeated rounded-card grammar as architecture;
- hierarchy collapses without color;
- easy-grid composition without workflow reason;
- flat white spreadsheet with no authored hierarchy;
- clean-sheet visual redesign that breaks Gorilla HIS continuity without approved reason;
- missing `START_HERE.md`;
- reviewer cannot discover Main Demo Flow without guessing;
- page self-labels Premium/Gold/World-class without Human Approval.

## 9. Premium HIS Visual Gate

Rendered UI must be reviewed whenever rendering is possible.

| Gate | Question | PASS condition |
|---|---|---|
| VG-01 Product Character | Purpose-built HIS or generic software? | Clinical / Operational / Trustworthy / Crafted / Desirable |
| VG-02 Decision Hierarchy | Can user grasp situation in ~5 seconds? | Situation → evidence → exception → action is obvious |
| VG-03 Icon System | Approved icon language? | FA semantic mapping; no Emoji/CDN |
| VG-04 Composition | Authored or grid-generated? | Proportion follows importance |
| VG-05 Surface Architecture | Too flat/decorative? | deliberate meaningful layers |
| VG-06 Typography Craft | Does type carry hierarchy? | intentional rhythm |
| VG-07 Instrument Quality | Reading or spreadsheet cell? | contextual instrument treatment when relevant |
| VG-08 Color Discipline | Controlled and semantic? | neutral-led, clinical semantics strict |
| VG-09 Data Visualization | Answers a decision? | only meaningful visualization |
| VG-10 Interaction Craft | State change deliberate? | hover/selected/pressed/causal feedback |
| VG-11 AI Integration | AI showroom? | intelligence attached to evidence |
| VG-12 Density | Real HIS density without noise? | meaningful first viewport |
| VG-13 Anti-Template | Could labels become CRM/fintech? | No |
| VG-14 Dryness / Barren | Sterile/unfinished? | No |
| VG-15 Desirability | Crafted, not merely tidy? | visually compelling without decoration |
| VG-16 Legacy Continuity | Same Gorilla HIS product family? | recognizable continuity + justified evolution |
| VG-17 Demo Usability | Can a non-dev reviewer play it? | START_HERE + discoverable demo journey |

Automatic P0 Design FAIL:
- VG-01, VG-02, VG-08, VG-13, VG-16;
- clinical-safety misuse;
- external asset violation;
- workflow failure.

## 10. BMW Evolution Test

BMW is a quality benchmark, not a visual-copy instruction.

Ask:
1. What Gorilla HIS DNA is preserved?
2. What legacy friction is materially improved?
3. What specific control/information detail feels more precise and considered?
4. Would an existing Gorilla user know where they are and how to work?

If only color/logo/shadow/radius/icons changed → FAIL.
If the result feels like another product → FAIL.

## 11. iPhone Test

- refined when decoration is reduced;
- depth improves hierarchy, not ornament;
- controls feel deliberate;
- visual complexity is reduced without removing useful information.

A page cannot pass by being flashy or barren.

## 12. Operational / Command Center Rule

Command Center is a live decision instrument, not a fixed layout template.

`premium-operational-layout.html` is Candidate Reference only and is not mandatory composition authority.

First viewport should communicate operating state, trajectory/time-to-threshold, bottleneck, evidence and intervention/projected impact.

## 13. Demo Guide Gate

Every mockup must ship `START_HERE.md` containing:
- purpose;
- roles;
- first click;
- 4–8 step Main Demo Flow;
- expected result for critical actions;
- clickable controls;
- prototype assumptions/TBDs;
- confirmation questions when relevant.

When practical add an unobtrusive in-product `Demo Guide` control.

No README/demo guide = FAIL.

## 14. Post-Build Evidence

Post-Build must include:
- Blueprint Traceability;
- Binding Reuse Verification;
- Legacy Continuity Verification;
- Visual Concept Verification;
- Decision Architecture Verification;
- Anti-Template Test;
- Dryness Test;
- BMW Evolution Test;
- iPhone Test;
- Premium HIS Visual Gate VG-01..VG-17;
- Demo Usability Test;
- Human Visual Review limitation/status.

## 15. Gold Standard Rule

Factory PASS = governed Candidate only.

`Candidate → Independent QA Passed → Human Approved → explicit Gold promotion`
