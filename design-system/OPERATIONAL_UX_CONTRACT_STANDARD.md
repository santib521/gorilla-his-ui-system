# Gorilla HIS — Operational UX Contract Standard v1.0

Status: `MANDATORY DESIGN MASTER`

## Purpose
Bridge the gap between a correct Application Blueprint and a non-generic operational UI.

Blueprint answers: **what the application must do**.
Operational UX Contract answers: **how the user performs the job, what they must decide, what evidence they need, and what workspace composition must support that decision**.

Core:
`Blueprint → Work Obligation → User Job → Decision Architecture → Evidence Architecture → Workspace Contract → Interaction Contract → Screen Composition`

## 1. Mandatory Artifact
Before building `index.html`, create:
`Operational_UX_Contract_<Module>.md`

One contract is required for every material Work Obligation/Worklist and every material professional workspace.

## 2. Contract Schema
For each `WL-*` / primary workspace define:
- UX ID: `UXC-*`
- Work Obligation / Worklist
- Primary Role
- User Job
- Trigger / Entry
- Core Work Object
- Current state/owner/waiting context
- Primary Decision Question(s)
- Primary Evidence required to decide
- Attention / Exception evidence
- Primary Action
- Secondary Action(s)
- Observable mutation after action
- Handoff / receiving queue
- Repeated/longitudinal evidence when applicable
- Detail-on-demand content
- First-viewport mandatory content
- Dominant Work Surface
- Supporting surfaces
- Validation/error/recovery states
- KD/BM constraints that apply
- Blueprint `FN/SCN/AC` trace

## 3. First-Viewport Contract
The first viewport must allocate the largest useful area to the real work/evidence of the selected obligation.

It must answer within ~5 seconds:
1. What job am I doing?
2. Which patient/case/work object needs attention?
3. What is its current state/owner/waiting condition?
4. What evidence matters now?
5. What do I do next?

If a header, KPI/cards, navigation or whitespace displaces the real work without operational benefit:
`FAIL — FIRST VIEWPORT COMPOSITION`.

## 4. Material Workspace Depth Gate
A material professional activity must receive a workspace proportionate to its operational importance.

Examples:
- assessment/examination;
- medication/order review;
- authorization/approval;
- evidence/custody;
- report authoring/review;
- utilization/entitlement;
- appointment/reassessment;
- discharge/release.

A generic `table → generic drawer → two-column form → Save/Next` pattern is insufficient when the work contains multiple evidence domains, decisions, versions, handoffs or safety/legal controls.

Failure:
`FAIL — PROFESSIONAL WORKSPACE DEPTH`.

## 5. Composition Derivation
Screen composition must be explainable from:
`User Job → Decision Question → Evidence Priority → Action Priority → Interaction Pattern`.

The Builder must be able to state why each major region exists and why it occupies its proportion.

If composition is explained mainly by component availability, cards, grid convenience, template reuse or styling preference:
`FAIL — TEMPLATE-LED COMPOSITION`.

## 6. Worklist vs Workspace
Worklist answers:
`What work must I do?`

Workspace answers:
`How do I complete this specific work safely and efficiently?`

Do not force every job into one universal table/drawer shell.

Different material obligations may share product grammar while requiring different dominant work surfaces.

## 7. Decision/Evidence Proximity
Evidence needed for a decision should be visually and interactively close to the action it informs.

Avoid:
- critical evidence hidden several clicks away;
- detached actions in global headers when the action is row/object specific;
- status badges without next action;
- actions requiring the user to remember data from another screen;
- toast-only confirmation of meaningful state change.

## 8. Longitudinal / Version / Custody / Ledger Work
When applicable the workspace must expose the relevant continuity object directly:
- prior/current assessment;
- version/amendment history;
- custody chain/events;
- approved/used/remaining ledger;
- repeated visits/cycles;
- waiting result/history;
- next scheduled event.

Do not hide longitudinal truth in a generic audit drawer when it is central to the user decision.

## 9. Validation Before Build
The UX Contract must be reviewed against:
- Blueprint truth;
- Worklist/Queue architecture;
- compiled KD/BM constraints;
- Human-approved benchmark strengths when applicable.

No UX Contract = no full candidate build.

## 10. Final Rule
A functionally complete Blueprint does not automatically produce a good UI.

**Every material work obligation requires an explicit operational UX contract before implementation.**