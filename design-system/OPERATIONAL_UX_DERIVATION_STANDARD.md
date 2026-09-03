# Gorilla HIS — Operational UX Derivation Standard v1.2

Status: `UNIVERSAL UX FACTORY MASTER`

Applies to **EVERY Gorilla HIS module**.

## 1. Core Principle — PRODUCT FIRST, GATE AFTER
The Factory must behave like a strong Senior HIS BA + Product Designer, not like an auditor assembling UI from checklists.

Mandatory execution loop:

`DISCOVER → MODEL → DESIGN → BUILD → PLAY → CHALLENGE → FIX`

Expanded:
`Hospital Actual Workflow → Work Objects/State Machine → User Job/Decisions → Product Concept → Premium UI → Running Workflow → Independent Challenge → Fix/Retest`.

The Master is a **quality floor, not a layout generator**. It prevents unsafe invention and workflow omission; it must not slow early product synthesis with ceremonial matrices.

## 2. RAPID PRODUCT SYNTHESIS — MANDATORY
Before first build, create only the minimum internal model needed to design correctly:
1. Actual Main Flow(s)
2. Core Work Objects / Transactions
3. State Machine / Lifecycle
4. Key Actors / Handoffs
5. Repeated / quantity / longitudinal behavior when material
6. 2–5 user decisions/actions that dominate the module
7. Design Intent

If those seven items are sufficiently understood, **BUILD THE FIRST PRODUCT CANDIDATE EARLY**. Detailed traceability matrices, documentation and audit artifacts may be completed/refined after a coherent candidate exists, provided no Critical Hospital Truth is silently invented.

## 3. Designer / Reviewer Separation
During composition, the Product Designer optimizes the work experience and is not required to mentally execute every Factory checklist.

After the candidate exists, an Independent Reviewer challenges:
- workflow fidelity;
- missing states/capabilities;
- invented Hospital Policy;
- broken handoff/ownership;
- repeated-flow continuity;
- function/runtime execution;
- benchmark regression;
- visual/product quality.

**Designer freedom high during creation; Factory rigor high during review.**

## 4. BA/SA Derivation Boundary
A competent Factory derives obvious application capability without asking users to design screens.

May derive as `EXPERT APPLICATION DERIVATION`:
- incoming work → Worklist/Queue;
- new transaction → Entry surface;
- receive/accept/assign → Ownership action;
- assessment/scoring → Professional Assessment Workspace;
- material handoff → Review/Verify;
- approval → Approval Inbox/Decision Workspace;
- repeated work → Longitudinal/Follow-up Workspace;
- prior evidence affects current work → History/Version context;
- closure → Closure/Outstanding-work check;
- operational volume → Search/Filter/Sort;
- lifecycle-driven work → Status/Owner/Next Action.

Must not invent as Hospital Truth:
- authority/approval thresholds;
- SLA/escalation;
- formula/score cut-off;
- local/legal policy;
- exact permissions;
- unverified source-of-truth;
- financial posting/reversal;
- clinical decision rules.

Ask the hospital about **policy/authority/decision rules**, not obvious UI capability.

## 5. STATE MACHINE BEFORE SCREEN LIST
Do not translate `Requirement → Screen`.

Use:
`Workflow → Work Object → State → User Job → Capability → Workspace → Interaction`.

Every material state-changing action must define what changes, who owns the next state, and what the user sees next. Similar-looking flows with materially different lifecycle/authority/quantity must remain separate transactions.

## 6. Workspace Pattern Selection
Choose the pattern that makes the job easiest: Worklist/Queue, split view, inspector, full-page professional workspace, schedule, resource board, approval inbox, timeline, ledger, task workspace or hybrid.

Do not start from `Dashboard + Cards + Sidebar`.
Do not force every module into one content pattern.

The designer should be able to explain in one sentence why the chosen pattern fits the work.

## 7. Worklist / Queue
When work arrives and must be triaged, received, assigned, progressed or handed off, derive a work-management surface automatically.

Select only fields that improve scanning/action. Typical candidates:
`Type | Identity | Reason/Service | Source | Priority | Status | Owner | Aging/Due | Progress | Next Action`.

Exact columns are design decisions, not a mandatory database dump.

## 8. Professional Work Surfaces
Core work receives a proportionate workspace.
- Assessment/scoring: prior evidence + current inputs + resulting classification + validation.
- Review/verify: decision summary + exceptions + handoff.
- Follow-up: entitlement/planned work + prior event + current reassessment + used/remaining + next event.
- Approval: request + evidence + financial/quantity context + decision.

Do not bury a core task in a tiny generic modal merely to claim coverage.

## 9. Benchmark-Driven Product Rule — HARD GATE
When a user supplies a reference/mockup/product candidate, treat it as a **Minimum Product Quality Floor** for the qualities it demonstrates well.

Mandatory sequence:
`UNDERSTAND → EXTRACT STRENGTHS → IDENTIFY BUSINESS/UX DEFECTS → PRESERVE PROVEN STRENGTHS → CORRECT DEFECTS → EXCEED`.

Compare at least:
1. UX/UI — hierarchy, scanability, density, navigation, action clarity, polish;
2. Function — what can actually be done/interacted with;
3. Workflow — transaction/state/handoff/repeated-flow fidelity.

A new Gorilla candidate must **not regress below the supplied benchmark** in UX/UI or Function without a documented workflow/safety reason. It should exceed the benchmark in Workflow Fidelity whenever Gorilla has stronger Hospital Evidence.

A user-supplied candidate that communicates the job better than Factory output is evidence the Factory must improve; never defend the weaker output with Master rules.

## 10. UX Decision Architecture
For each primary workspace reason from:
`User Goal → Decision Question → Evidence Needed → Attention/Exception → Primary Action → Detail on Demand`.

Within ~5 seconds an experienced user should understand where they are, what needs attention, current state, and next action.

## 11. Premium Composition Direction
Target: **Premium, simple, calm, precise, professional, expensive without decorative luxury.**

Use hierarchy, Thai readability, deliberate density, restrained semantics, state-driven actions, progressive disclosure and crafted interaction states.

Avoid card sprawl, oversized KPI blocks, badge overload, tiny text, giant empty whitespace, generic SaaS/admin language and Master/checklist labels in the product.

## 12. Design Freedom Rule
The Master specifies outcomes/failure conditions, not pixel layout.

A designer may simplify, combine, hide, reorder or reinterpret UI elements when:
- workflow fidelity remains intact;
- decisions/actions remain discoverable;
- state/data/owner continuity remains clear;
- runtime scenario remains executable;
- no Hospital Truth is invented;
- benchmark strengths are not needlessly lost.

## 13. Operational UX Hard Failures
FAIL when:
- material work cannot be performed naturally;
- next action is unclear;
- queued work has no usable work-management surface;
- core assessment/review/follow-up is reduced to inadequate UI;
- repeated work loses history/progression;
- handoff/approval has no receiver state;
- generic template dominates domain context;
- candidate is materially worse than a credible supplied benchmark without workflow justification.

## 14. Final Rule
`Requirement is not a screen specification.`
`Master is not a screen specification.`

The Factory must **understand fast, model correctly, design freely, build early, execute real work, then challenge hard**.