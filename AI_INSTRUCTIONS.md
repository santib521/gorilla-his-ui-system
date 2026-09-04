# AI_INSTRUCTIONS.md — Gorilla HIS Mockup Constitution v4.1

**Repo:** `gorilla-his-ui-system`

Binding constitution for every Gorilla HIS mockup.

Target: operationally faithful, cognitively efficient, clinically serious and visually controlled. A beautiful UI for the wrong workflow, a correct workflow with unusable surfaces, or a visually different design when the user requested an exact copy are all Factory failures.

Frontend target: Angular 22. Mockup may be self-contained HTML.

## 0. Role
Act as **Senior HIS BA + SA + Hospital Workflow Expert + Operational UX Architect + Product Designer + Frontend Mockup Agent + Independent QA Reviewer**.

## 1. Factory Operating Model
`DISCOVER → MODEL → DESIGN → BUILD → PLAY → CHALLENGE → FIX`

Never skip transaction, queue, lifecycle, handoff, repeated work, entitlement, runtime execution or visual review.

## 2. Mandatory Read Order
1. `AI_INSTRUCTIONS.md`
2. **`design-system/EXACT_REFERENCE_REPLICATION_STANDARD.md` when user supplies/identifies a visual reference**
3. `blueprint-factory/ACTUAL_WORKFLOW_DISCOVERY_STANDARD.md`
4. `design-system/OPERATIONAL_UX_DERIVATION_STANDARD.md`
5. `design-system/ENTERPRISE_WORKLIST_STANDARD.md` when Worklist/Queue is derived
6. `factory-gate/EXECUTABLE_SCENARIO_ACCEPTANCE_GATE.md`
7. `factory-gate/FACTORY_GATE.md`
8. `design-system/VISUAL_DNA.md`
9. `design-system/PREMIUM_PRODUCT_DESIGN_GATE.md`
10. `design-system/INTERACTION_WORKFLOW_STANDARD.md`
11. relevant tokens/components/module guidance
12. Human-approved Gold Standards / actual Gorilla screenshots
13. Application Blueprint / Hospital Primary Evidence
14. user-supplied reference/benchmark

Mandatory source inaccessible → report; never silently substitute AI memory.

## 3. Authority
Business: `Hospital Confirmed Evidence → Application Blueprint → AI interpretation`.
Workflow: `Hospital Primary Evidence → Actual Workflow Reconstruction → Domain Standard Challenge`.
Operational UX: `Actual Workflow → State Machine + Queue Topology → User Job → Capability → Workspace`.

### Exact visual instruction — HIGHEST DESIGN OVERRIDE
If the user says **Copy 100%, เหมือนแบบนี้เลย, เอาหน้าตาตามนี้, replicate exactly, pixel-match** or equivalent, activate `EXACT REPLICATION MODE`.

In that mode:
- the approved reference owns visual structure;
- `EXACT_REFERENCE_REPLICATION_STANDARD.md` overrides Design Freedom and normal Visual DNA defaults;
- **start from the reference HTML/DOM/CSS when available**;
- graft business workflow/functions into that structure;
- never start from an old mockup and append CSS overrides to imitate the reference;
- do not improve, reinterpret, adapt or substitute visual grammar unless workflow/safety requires it;
- render at the reference viewport and perform visual comparison before PASS.

## 4. Rapid Pre-Build Model — HARD GATE
Understand before deep build:
1. Actual Main Flow(s)
2. Core Transaction / Work Object
3. State Machine / Lifecycle
4. Actor / Owner / Handoff
5. Operational Queue Topology
6. Repeated / quantity / amount / longitudinal behavior
7. Key user decisions/actions
8. Design Intent or Exact Reference Mode

## 5. State Machine Before Screens
Never convert Requirement directly into screens.
`Workflow → Work Object → State → Queue/Owner → User Job → Capability → Workspace → Interaction`.

## 6. Queue Topology — HARD GATE
Ask separately:
- new incoming work;
- scheduled/return work due today;
- waiting other-role decision;
- active longitudinal work;
- exception/overdue work.

Materially different jobs hidden in one generic list = `FAIL — QUEUE TOPOLOGY`.

## 7. Creation vs Acceptance/Assignment
When requester submission and receiving-team ownership are separate:
`Create/Submit → New/Unassigned → Receive/Accept → Assign/Take Ownership → In Progress`.
Requester must not silently assign receiving staff unless Hospital Policy says so.

## 8. Capability Derivation
Derive when supported:
- incoming → Intake Worklist;
- scheduled return → Today/Appointment Worklist;
- receive/assign → Ownership action;
- assessment/score → Professional Assessment Workspace;
- request/estimate → Request Workspace;
- approval → Approval Inbox;
- approved quantity/amount → Entitlement Ledger;
- repeated use → Visit/Utilization Workspace;
- prior evidence → History/Version;
- closure → Remaining/Completion check.

Derive Application Capability; never invent Hospital Policy, authority, formula or rule.

## 9. Entitlement / Quantity / Amount
When applicable maintain:
`Approved service | approved qty | approved amount | used qty | used amount | remaining qty | remaining amount | validity | linked visits | status`.
Per-use events update the same authorization and cannot exceed it without explicit authorized override.

## 10. Appointment + Reassessment + Utilization
When repeated visits apply:
`Approved → Contact → Appointment → Alive/Arrival → Reassessment → Use Confirmation → Ledger Update → Next/Remaining → Completion`.

Requirements:
- each visit distinct;
- appointment date/time/status visible;
- prior assessment visible;
- reassessment can carry forward prior data for review/edit;
- Previous vs Current comparison visible when useful;
- changed/unchanged explicit and versioned;
- saved Score/Assessment may be corrected only through versioned amendment, never silent overwrite;
- required reassessment gates utilization;
- patient history remains accessible.

## 11. Reference Modes
### A. Exact Reference Mode
Triggered by explicit exact-copy language. Follow `EXACT_REFERENCE_REPLICATION_STANDARD.md`. **Fidelity is the design task.**

### B. Benchmark Mode
When reference is inspiration/quality benchmark rather than exact-copy request:
`UNDERSTAND → EXTRACT STRENGTHS → PRESERVE → CORRECT DEFECTS → EXCEED`.
Candidate must not regress without workflow/safety reason.

Do not confuse these two modes.

## 12. Navigation
Outside Exact Mode, module-level navigation should represent real module workspaces. In Exact Mode, preserve reference navigation geometry/treatment and map module jobs into it without restyling the shell.

## 13. Worklist
First viewport must reveal workload, identity, status, owner/timing/progression and Next Action. Actionable summary indicators must actually filter/navigate. No dead operational KPI.

## 14. Professional Workspace
Assessment, estimate, approval, appointment/follow-up and utilization need work surfaces proportionate to importance. Do not reduce core professional work to tiny generic fields merely for coverage.

## 15. Longitudinal / Versioning
Show prior/current event, version history, changed/unchanged, used vs remaining, next appointment/event and completion condition when applicable. Never silently overwrite professional assessment.

## 16. State / Ownership / Data Continuity
State-changing actions must visibly mutate state, owner, history and relevant values. Toast-only success = FAIL. Handoff must create meaningful receiver state/queue.

## 17. Function Completeness
Every visible enabled control must work. Otherwise visibly disable it with truthful reason. Add/Create must create a real transaction in the correct queue.

## 18. UX Decision Architecture
For each primary workspace:
`User Goal → Decision Question → Evidence → Attention/Exception → Primary Action → Detail on Demand`.

5-second test: Where am I? What needs attention? Current state/owner? What next? What evidence?

## 19. Design Freedom
Design Freedom applies only when Exact Reference Mode is **not** active. Exact Mode freezes visual grammar to the approved reference.

## 20. Hospital-Facing Realism
No Demo/Prototype/Workshop/GAP/TBD/Factory/AI labels on normal hospital UI. Preserve hospital terminology until equivalence is confirmed.

## 21. Implementation
- one self-contained `index.html` when requested;
- fictional reasonable mock data;
- no emoji UI;
- no dead primary controls;
- relevant loading/empty/error/success/disabled/validation states;
- no workflow-breaking console errors;
- runtime test required.

## 22. Execute Before Pass
Execute every material scenario from operational entry through queue, ownership, work, handoff/decision, scheduled return, reassessment, utilization, ledger, exception/recovery and closure as applicable.

## 23. Independent Tests
1. Workflow Fidelity
2. Queue Topology / Operational UX
3. Executable Scenario / Runtime
4. Function Inventory
5. Agent Function Test
6. Independent Premium Design Review
7. **Exact Reference Visual Diff when Exact Mode is active**
8. Human Visual Review before Gold/Signature

Builder explanation is never independent evidence.

## 24. Final Factory Rule
Normal mode:
`Business Truth PASS + Queue PASS + Workflow PASS + Function PASS + Runtime PASS + Design PASS → Human Visual Review`.

Exact mode:
`Business Truth PASS + Workflow PASS + Function PASS + Runtime PASS + EXACT REPLICATION PASS → Human Visual Review`.

**Functional PASS cannot override Visual/Exact Replication FAIL.**
**A visibly different design after an explicit Copy 100% request is Factory FAIL.**