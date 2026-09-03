# Gorilla HIS — Premium Product Design Gate v1.3

Status: `MANDATORY UI FACTORY MASTER`

Purpose: stop visually weak, generic or operationally poor candidates before they consume deep implementation effort.

## 1. Release Principle
**Correct workflow is mandatory. Strong product design is mandatory. Neither compensates for the other.**

`Workflow Fidelity PASS + Functional PASS + Operational UX PASS + Benchmark No-Regression PASS + Independent Design PASS`.

## 2. Visual Preflight Veto — BEFORE DEEP FUNCTION BUILD
When a user benchmark exists, Builder must render the primary workspace early and compare it side-by-side before implementing the full interaction set.

If the primary screen visibly loses on first impression, hierarchy, density, typography, spacing, row/control craft, status clarity, next-action clarity, navigation proportion or product coherence → STOP and REDESIGN.

**Do not spend time making a visually rejected shell more functional.**

## 3. Screenshot Is Primary Visual Evidence
Rendered screenshot outranks CSS inspection, design notes, checklists and numeric scores.
Reviewer must be able to answer Yes to:
1. Would I choose Gorilla over the supplied benchmark at first glance?
2. Does the workspace look deliberately authored for this hospital job?
3. Is information density appropriate and visually controlled?
4. Is the main work faster to scan than the benchmark?
5. Are Thai typography, spacing, row height and controls finished-product quality?

Any clear No = FAIL.

## 4. Benchmark No-Regression
Benchmark is the minimum visible quality floor for strengths it demonstrates.
Required comparison dimensions:
`first impression | visual spine | information hierarchy | density | scan speed | navigation proportion | whitespace efficiency | typography | row craft | control craft | status clarity | next action | interaction confidence | product coherence | domain specificity`.

Each: `BETTER / EQUAL / WORSE / NOT COMPARABLE`.
Any material WORSE without workflow/safety justification = `FAIL — BENCHMARK REGRESSION`.

Target:
**Preserve proven benchmark strengths → correct its workflow/business defects → exceed it.**

## 5. Gorilla Shell Continuity
Preserve established Gorilla HIS **left-side application menu** unless Product Owner explicitly changes it.
The menu must be compact, refined and subordinate. It may not dominate the screen or reduce the module into a narrow admin content column.

## 6. Worklist Product Test
When work arrives in a queue, first viewport must make these obvious within ~5 seconds:
`what work exists | what needs attention | patient/transaction | state/owner | progress when material | next action`.

Reject:
- dashboard/KPI blocks displacing work;
- excessive blank space;
- tall rows with little decision value;
- passive rows;
- repetitive heavy buttons;
- generic status pills with weak hierarchy;
- card-per-row galleries;
- generic admin table styling;
- actions detached from work object.

## 7. Professional Workspace Adequacy
Core work gets a real workspace, not a tiny modal/textarea. Assessment, approval, repeated utilization and longitudinal review must surface the evidence needed for that decision and preserve context.

## 8. Density & Typography
Premium density = more decision value per viewport without clutter.
Thai operational text is first-class. Use intentional weight/line-height; avoid weak fallback appearance, oversized whitespace and micro-text.

`Dense ≠ cramped. Premium ≠ empty.`

## 9. Product Craft
Hierarchy should primarily come from typography, alignment, spacing and tonal structure—not boxes everywhere.
Controls require coherent hover/focus/pressed/disabled/validation states. Avoid browser-default/Bootstrap/default-Material feel.

## 10. Anti-Generic Veto
Hide branding and ask whether this could be CRM/finance/logistics after changing labels. If yes, redesign.
A dark sidebar + white rounded container + generic KPI/table composition is not sufficient product authorship.

## 11. Independent Product Design Critic
Critic is separate from Builder and reviews rendered screens at realistic viewport(s). Allowed hard failures:
`BENCHMARK REGRESSION | HUMAN VISUAL VETO | GENERIC ADMIN/SAAS | INFORMATION HIERARCHY | DENSITY/SPACE | TYPOGRAPHY | WORKLIST UX | NAVIGATION FOOTPRINT | INTERACTION CRAFT | PROFESSIONAL WORKSPACE | GORILLA CONTINUITY | VISUAL POLISH`.

Any hard FAIL → redesign → render → retest.

## 12. Human Visual Veto
If Product Owner/Human Reviewer says candidate is visibly inferior, any previous Design PASS is invalid immediately. Reopen as `FAIL — HUMAN VISUAL VETO`.
Internal scores cannot overrule the human-visible result.

## 13. Required Review Artifact
`INDEPENDENT_DESIGN_REVIEW.md` must include:
- rendered screenshots/viewports;
- side-by-side benchmark comparison when supplied;
- BETTER/EQUAL/WORSE table;
- 5-second work test;
- hard failures;
- redesign actions;
- final status.

## 14. Final Rule
**If the screenshot visibly loses to the supplied benchmark, Design PASS is impossible and the candidate must not be delivered as Premium Candidate.**