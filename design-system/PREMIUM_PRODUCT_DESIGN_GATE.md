# Gorilla HIS — Premium Product Design Gate v1.0

Status: `MANDATORY UI FACTORY MASTER`

Purpose: prevent a functionally correct mockup from being released when it still looks/feels like a generic admin template. Quality benchmark: **BMW cockpit discipline × Apple interaction discipline × hospital-grade information density × Gorilla HIS continuity**. BMW/Apple are quality metaphors, not visual styles to copy.

## 1. Release Equation
`Functional PASS + Design FAIL = FACTORY FAIL`

`Premium` cannot be self-declared by Builder. It requires Independent Design Review and Human Visual Review for Gold/Signature promotion.

## 2. Independent Design Critic
After Builder and Agent Function Test, run a separate Design Critic pass acting as:
- Senior Product Design Director;
- Enterprise/Clinical UX specialist;
- Interaction Design specialist;
- Thai typography/readability reviewer;
- Gorilla HIS continuity reviewer.

The critic reviews rendered screens, not source code alone, and must not accept Builder explanation as evidence of visual quality.

Allowed results:
- `PASS — READY FOR HUMAN VISUAL REVIEW`
- `FAIL — GENERIC ADMIN / SAAS`
- `FAIL — TYPOGRAPHY`
- `FAIL — INFORMATION HIERARCHY`
- `FAIL — NAVIGATION FOOTPRINT`
- `FAIL — DENSITY / SPACE UTILIZATION`
- `FAIL — INTERACTION CRAFT`
- `FAIL — GORILLA CONTINUITY`
- `FAIL — VISUAL POLISH`
- `FAIL — RESPONSIVE / COLLAPSE BEHAVIOR`

Any FAIL → `REDESIGN → RENDER → INDEPENDENT REVIEW`.

## 3. Navigation Footprint Gate
Navigation is subordinate to clinical work.

Mandatory checks:
- primary navigation width must be justified by content, not template convention;
- persistent sidebar must not consume disproportionate first-viewport width;
- when work requires width, support compact/collapsed/rail/contextual navigation where appropriate;
- collapsing navigation must preserve orientation and easy reopen;
- avoid simultaneously dominant sidebar + topbar + tabs + secondary rail;
- selected state must remain unmistakable in compact mode.

If reviewer says “the bar is too big and the work area feels squeezed/empty” → FAIL.

## 4. Space Utilization & Composition Gate
First viewport must allocate the largest useful area to the real task/evidence.

FAIL when:
- large unused blank regions exist while important content is compressed elsewhere;
- content occupies only a narrow strip because of fixed template widths;
- equal cards/grids determine composition instead of workflow;
- actions float far away from the object they affect;
- every section is boxed into a card;
- page has no visual spine or authored focal path.

Required authored path:
`Context → Situation → Evidence/Work → Exception → Next Action → Detail`.

## 5. Thai Typography Craft Gate
Thai typography is a first-class product surface.

Mandatory:
- use a locally available, highly readable Thai-capable font stack; do not rely on poor browser fallback as the intended design;
- document the production font recommendation without distributing font files;
- tune Thai line-height, weight and optical spacing independently from Latin assumptions;
- main body/form/table/action normally 13–14px or larger;
- critical instructions/patient identity/status cannot use micro text;
- English/Thai mixed labels must share coherent baseline/weight;
- headings must be compact, confident and not oversized;
- avoid excessive bold Thai text that creates visual noise;
- tabular numerals for aligned IDs/times/numbers where supported.

If Thai text feels cheap, cramped, blurry, weakly weighted or like an OS fallback → `FAIL — TYPOGRAPHY`.

## 6. Hierarchy & Task Focus Gate
Within 5 seconds the reviewer must identify:
1. where am I / which patient/case/task?
2. what is the current state?
3. what needs attention?
4. what is the next action?
5. what information supports that action?

Do not give Role selector, decoration, KPI or secondary metadata more visual weight than the primary task.

## 7. Progressive Disclosure Gate
Do not show everything at once merely because the system has many functions.
- intake shows what is needed to classify/accept the request;
- case workspace reveals deeper tools after case creation;
- advanced/rare details may use drawer/accordion/contextual inspector;
- persistent context remains compact;
- selection/navigation gives space back after selection when appropriate.

## 8. Component Jewelry Gate
Review buttons, tabs, fields, selectors, badges, table headers, focus, hover, pressed, selected, disabled, validation, loading, empty and error states.

FAIL when controls look browser-default, Bootstrap-default, generic Material-default or inconsistently padded/aligned.

## 9. Anti-Generic Gate
Ask with labels/logo hidden:
- Could this be CRM/finance/logistics admin with text replaced?
- Is the page mainly a dark sidebar + white cards + generic KPI grid?
- Are repeated rounded rectangles the main grammar?
- Does the page feel AI-generated/template-generated?

Any yes → `FAIL — GENERIC ADMIN / SAAS`.

## 10. Gorilla HIS Continuity Gate
Compare relevant actual Gorilla HIS screenshots/approved Gold Standards.
Document:
`PRESERVE / IMPROVE / REPLACE` for shell, context anchor, tables/worklists, forms, tabs, actions, statuses and density.

Premium evolution must still be recognizably Gorilla HIS.

## 11. Responsive / Collapse Gate
At minimum inspect desktop first viewport and narrower desktop/tablet behavior when relevant.
- sidebar/rail behavior;
- table/workspace compression;
- action wrapping;
- patient/case context persistence;
- no hidden primary action;
- no horizontal layout break caused by decorative fixed widths.

## 12. Rendered Review Requirement
Source/CSS inspection cannot PASS this gate. Review rendered screenshots at representative viewport(s). If rendering is blocked, status = `NOT VERIFIED — HUMAN/RENDER REVIEW REQUIRED`.

## 13. Premium Scoring — Diagnostic, not substitute for hard gate
Score 0–5 each:
- Workflow-authored composition
- Navigation proportion
- Space utilization
- Information hierarchy
- Thai typography
- Density/readability
- Control craftsmanship
- Interaction states
- Gorilla continuity
- Visual desirability

Target for `READY FOR HUMAN VISUAL REVIEW`: no hard FAIL and average ≥4.0, no category <3.5.
Gold/Signature still requires Human Design Approval.

## 14. Required Artifact
Create `INDEPENDENT_DESIGN_REVIEW.md` containing:
- screenshots/viewports reviewed;
- scores;
- hard-gate results;
- top 5 visual defects;
- required redesign actions;
- final status.

## 15. Final Rule
`Clean ≠ Premium`
`Modern ≠ Premium`
`More cards ≠ Better design`
`Angular Material ≠ Design`
`Functionally complete ≠ Release-ready`

A Gorilla HIS Premium Candidate must feel precise, calm, dense where useful, effortless to navigate and intentionally designed at both page and control level.