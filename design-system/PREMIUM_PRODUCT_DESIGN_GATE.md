# Gorilla HIS — Premium Product Design Gate v1.1

Status: `MANDATORY UI FACTORY MASTER`

Purpose: prevent a functionally correct mockup from being released when it is operationally weak, generic, cognitively expensive or visually unrefined.

Quality benchmark: **precision cockpit discipline × excellent interaction discipline × hospital-grade information density × Gorilla HIS continuity**. Quality metaphors/references are not layouts to copy.

## 1. Release Equation
`Workflow Fidelity PASS + Operational UX PASS + Functional PASS + Independent Design PASS` are all required.

**Beautiful + wrong work = FAIL. Functional + unusable work surface = FAIL. Modern-looking + generic template = FAIL.**

## 2. Independent Design Critic
Reviewer is separate from Builder and acts as Senior Product Design Director + Enterprise/Clinical UX specialist + Interaction Designer + Thai typography/readability reviewer + Gorilla continuity reviewer.

Review rendered screens, not source code or Builder explanation.

Allowed failures include:
`GENERIC ADMIN/SAAS | TYPOGRAPHY | INFORMATION HIERARCHY | NAVIGATION FOOTPRINT | DENSITY/SPACE | INTERACTION CRAFT | WORKLIST UX | WRONG UI PATTERN | COGNITIVE LOAD | NEXT ACTION UNCLEAR | PROFESSIONAL WORKSPACE INADEQUATE | GORILLA CONTINUITY | VISUAL POLISH | RESPONSIVE`.

Any FAIL → redesign → render → independent retest.

## 3. Operational UX Authority
`design-system/OPERATIONAL_UX_DERIVATION_STANDARD.md` is mandatory.

The critic must verify that UI was derived through:
`Workflow → User Work → Operational Capability → Workspace → Decision Architecture → Interaction Pattern → Composition`.

A screen set that merely covers requirements/functions but does not provide the work surfaces implied by workflow = FAIL.

## 4. Worklist / Queue Gate
When workflow creates queued work, `design-system/ENTERPRISE_WORKLIST_STANDARD.md` is mandatory.

Within 5 seconds first viewport should answer:
1. What workload exists?
2. What needs attention first?
3. What transaction/patient/task is this?
4. What is its state and owner?
5. What should I do next?

Worklist FAIL when:
- dashboard/KPI cards push work below fold;
- rows are passive information with no lifecycle action;
- user infers next action from status code;
- card-per-row wastes density;
- oversized sidebar/navigation steals operational width;
- row opens generic Overview instead of relevant lifecycle stage;
- owner/progress/aging/priority is missing when workflow needs it.

Optional Attention/My Work zone must remain compact and support—not replace—the full operational list.

## 5. Navigation Footprint
Navigation is subordinate to work. Persistent width must be justified. Prefer compact/collapsible/contextual navigation when work needs width. Avoid simultaneously dominant sidebar + topbar + tabs + secondary rail.

If reviewer notices navigation before the task → likely FAIL.

## 6. Space Utilization & Composition
First viewport gives largest useful area to actual work/evidence.

FAIL for large unused blank regions, narrow template content strips, equal-card grids despite unequal importance, detached actions, card-sprawl or no authored focal path.

Required path:
`Context → Situation/Attention → Evidence/Work → Exception → Next Action → Detail`.

## 7. Decision Architecture
Every primary workspace must make visible:
`User Goal → Decision Question → Primary Evidence → Exception/Attention → Primary Action → Secondary Action → Detail on Demand`.

Do not give role selectors, decoration, KPI or secondary metadata more weight than the task.

## 8. Cognitive UX Gate
Apply interaction principles operationally:
- Familiarity/Jakob: respect established HIS/domain mental models;
- Hick: reduce simultaneous choices; stage by lifecycle;
- Fitts: frequent/important actions are easy to acquire and near affected object;
- Cognitive load/Miller: chunk and progressively disclose; do not make user remember prior state;
- Proximity: related evidence/actions stay together;
- Similarity: same semantics look/behave consistently; different semantics remain distinguishable;
- Aesthetic-usability: visual polish improves trust/readability, never masks weak workflow;
- Peak-End: critical handoff/closure provides clear confidence and end-state feedback;
- Recognition over Recall: prior values/status/owner/progress/last assessment are surfaced when needed.

## 9. Professional Workspace Adequacy
Core professional tasks deserve adequate work surfaces.

FAIL examples:
- assessment reduced to a small textarea in generic detail page;
- verify/approval has no decision evidence summary;
- repeated follow-up has no prior/current comparison;
- clinical/operational review requires bouncing across unrelated screens to reconstruct context;
- important task is squeezed into modal/card because component was convenient.

## 10. Density Gate
Premium density = more decision value per viewport without clutter.

- Thai main operational text normally ≥13–14px;
- secondary metadata may be smaller but readable;
- compact rows/forms where volume demands it;
- use alignment/typography/dividers before boxes/shadows;
- do not achieve density by micro-text;
- do not achieve premium by excessive whitespace.

**Dense ≠ cramped. Premium ≠ empty.**

## 11. Thai Typography Craft
Thai is first-class. Use readable Thai-capable stack available in target environment; document production font recommendation without distributing font files. Tune line-height/weight; keep headings compact; avoid excessive bold; align mixed Thai/English and tabular numbers carefully.

Poor Thai fallback/cramped text = TYPOGRAPHY FAIL.

## 12. Progressive Disclosure
Show what is needed for current lifecycle decision. Deeper/rare detail goes to drawer/accordion/inspector where appropriate. Persistent patient/case/task context stays compact and visible.

## 13. Component Craft
Buttons, tabs, fields, selectors, chips, tables, row hover/selection, focus, pressed, disabled, validation, loading, empty and error states must feel one product. Browser/Bootstrap/default-Material appearance = FAIL.

## 14. Anti-Generic Gate
Hide logo/labels and ask:
- Could this be CRM/finance/logistics with text replaced?
- Is it mainly dark sidebar + white rounded cards + KPI grid?
- Are repeated rounded rectangles the visual grammar?
- Was pattern selected because it was easy to generate?
- Does it feel AI/template assembled?

Any yes = FAIL.

## 15. Reference Use Rule
User-supplied references and approved products are used to extract **quality/pattern lessons** such as density, scan hierarchy, attention zone, command bar, row craft, master-detail behavior and control refinement.

Do not copy layouts blindly. Derive the pattern from Gorilla workflow and domain needs.

## 16. Gorilla HIS Continuity
Compare actual Gorilla/Gold references and document `PRESERVE / IMPROVE / REPLACE` for shell, context, worklists, forms, actions, status language, density and interaction.

Premium evolution must remain recognizably Gorilla HIS.

## 17. Responsive / Adaptive
Inspect representative desktop and narrower workspace. Preserve identity/status/next action first; collapse low-value detail; do not hide primary action; navigation compacts when needed; worklists retain scanability.

## 18. Rendered Review Requirement
Source/CSS inspection cannot PASS. Review rendered screenshots at representative viewports. Rendering blocked = `NOT VERIFIED — HUMAN/RENDER REVIEW REQUIRED`.

## 19. Premium Scoring
Score 0–5:
- Workflow-authored composition
- Operational capability fit
- Worklist/queue quality when applicable
- Decision architecture
- Navigation proportion
- Space utilization
- Information hierarchy
- Cognitive efficiency
- Thai typography
- Density/readability
- Control craftsmanship
- Interaction states
- Gorilla continuity
- Visual desirability

Target: no hard FAIL, average ≥4.0, no category <3.5. Human approval still required for Gold/Signature.

## 20. Required Artifact
`INDEPENDENT_DESIGN_REVIEW.md` must include screenshots/viewports, scores, hard-gate results, 5-second test, top defects, redesign actions and final status.

## 21. Final Rules
`Requirement coverage ≠ UX`
`Dashboard ≠ Worklist`
`Modern ≠ cards`
`Clean ≠ Premium`
`Dense ≠ cramped`
`Premium ≠ empty`
`Angular Material ≠ Design`

A Gorilla HIS Premium Candidate must feel like a precise professional instrument: real work is immediately visible, the next action is obvious, evidence is close to the decision, interaction reduces cognitive effort, and visual craft reinforces trust.