# Gorilla HIS — Operational UX Derivation Standard v1.3

Status: `UNIVERSAL UX FACTORY MASTER`

Applies to **EVERY Gorilla HIS module**.

## 1. Core Principle — PRODUCT FIRST, GATE AFTER
The Factory must behave like a strong Senior HIS BA + Product Designer, not like an auditor assembling UI from checklists.

Mandatory execution loop:
`DISCOVER → MODEL → DESIGN → BUILD → PLAY → CHALLENGE → FIX`.

Expanded:
`Hospital Actual Workflow → Work Objects/State Machine/Queue Topology → User Job/Decisions → Product Concept → Premium UI → Running Workflow → Independent Challenge → Fix/Retest`.

The Master is a quality floor, not a layout generator.

## 2. Rapid Product Synthesis
Before first build create only the minimum internal model needed:
1. Actual Main Flow(s)
2. Core Work Objects / Transactions
3. State Machine / Lifecycle
4. Key Actors / Handoffs
5. Operational Queue Topology
6. Repeated / quantity / amount / longitudinal behavior
7. 2–5 dominant user decisions/actions
8. Design Intent

Then build early. Do not use speed as a reason to collapse distinct queues, ownership boundaries or repeated-utilization logic.

## 3. Designer / Reviewer Separation
Designer optimizes the work experience. Independent reviewer challenges workflow fidelity, queue completeness, missing capabilities/states, invented policy, broken handoff, repeated-flow continuity, function/runtime, benchmark regression and visual quality.

## 4. BA/SA Derivation Boundary
May derive as `EXPERT APPLICATION DERIVATION` when supported by workflow:
- incoming request/consult → Intake Worklist;
- scheduled/return patient work → Today's Follow-up/Arrival Worklist;
- create/new transaction → Entry surface;
- receive/accept/assign → Receiving-team ownership action;
- estimate/service request → Estimate Workspace;
- assessment/scoring → Professional Assessment Workspace;
- material handoff → Review/Verify;
- approval → Approval Inbox;
- approved quantity/value → Entitlement Ledger;
- repeated work → Visit/Utilization Workspace;
- appointment drives work → Appointment/Today Queue;
- prior evidence matters → History/Version context;
- closure → Remaining/Outstanding-work check;
- operational volume → Search/Filter/Sort.

Must not invent authority thresholds, SLA, scoring cut-offs, local policy, permissions, source-of-truth, financial posting/reversal or clinical decision rules.

## 5. State Machine + Queue Topology Before Screen List
Do not translate Requirement → Screen.

Use:
`Workflow → Work Object → State → Queue/Owner → User Job → Capability → Workspace → Interaction`.

### Queue Topology Challenge
Every module must ask whether user work naturally separates into:
- incoming/new work;
- scheduled/return work due now/today;
- waiting for external/other-role decision;
- active longitudinal work;
- exception/overdue work;
- completed/history.

Materially different work obligations should not be hidden inside one generic list. Use tabs, sections, saved views or separate workspaces as appropriate.

## 6. Creation vs Assignment
When requester submits work to another department, creation and receiving-team assignment are distinct unless hospital evidence explicitly combines them.

The create form gathers request evidence. It does not pre-select the receiving department's internal assignee by default.

After submit:
`New/Unassigned → Receive/Accept → Assign/Take ownership → In Progress`.

Assignment action must be possible from receiving Worklist/case context and must visibly change owner/history.

## 7. Entitlement / Utilization Model
When approval authorizes a service/item with quantity or amount, derive an explicit authorization/entitlement ledger.

Minimum decision information when relevant:
`Approved service | Approved qty | Approved amount | Used qty | Used amount | Remaining qty | Remaining amount | validity | linked appointments | linked utilizations | status`.

Repeated visit cycle:
`Appointment/Arrival → Required Reassessment → Use Confirmation → Ledger Mutation → Remaining/Next Appointment`.

If reassessment is mandatory before each use, UI must prevent utilization until the current visit assessment is saved.

## 8. Appointment-Centered Operational Work
If longitudinal work depends on patient appointments/returns, the module needs a usable appointment-oriented surface. It should make clear:
- who is expected today/upcoming;
- linked case/authorization;
- appointment time/service;
- whether patient has contacted/checked with the department;
- whether reassessment is done;
- whether utilization is recorded;
- next action.

This is different from Intake Worklist and should not be treated as the same job.

## 9. Patient / Case History
When prior social/financial/clinical-support work affects current decisions, expose patient history without forcing recall. Show prior Consult/Request cases, prior assessment versions, approvals, appointments, utilizations, home visits, closures and relevant outcomes.

## 10. Workspace Pattern Selection
Choose pattern by job: intake queue, today queue, split view, inspector, full-page workspace, schedule, approval inbox, timeline, ledger, task workspace or hybrid.

Do not start from Dashboard + Cards + Sidebar.

## 11. Interactive Summary Rule
Cards, chips, counters and summary blocks that imply an actionable subset must behave as controls: filter, navigate or open the corresponding work. Decorative operational KPI = FAIL.

## 12. Professional Work Surfaces
Core work receives a proportionate workspace:
- Estimate: requested items/services + qty + unit/full price + reimbursable + non-reimbursable + totals;
- Assessment: prior/current evidence + detailed economic inputs + scoring components + classification result + version;
- Approval: request + estimate + assessment + quantity/value + decision;
- Follow-up: today's appointment + prior assessment + current reassessment + entitlement ledger + next appointment;
- History: prior cases and utilization timeline.

Do not bury core work in tiny generic modals merely to claim coverage.

## 13. Benchmark-Driven Product Rule — HARD GATE
When user supplies a reference/mockup, treat demonstrated strengths as minimum quality floor.

`UNDERSTAND → EXTRACT STRENGTHS → IDENTIFY DEFECTS → PRESERVE STRENGTHS → CORRECT DEFECTS → EXCEED`.

Compare UX/UI, Function, and Workflow. A new candidate must not regress without documented workflow/safety reason.

## 14. Navigation Semantics
For a module-level mockup, left navigation should normally represent the module's own workspaces when there are multiple recurring operational jobs. Do not fill the rail with unrelated HIS modules unless an approved product shell explicitly requires it.

Exact module menu items derive from real jobs, not from a universal template.

## 15. UX Decision Architecture
For each primary workspace:
`User Goal → Decision Question → Evidence Needed → Attention/Exception → Primary Action → Detail on Demand`.

Within ~5 seconds an experienced user should understand where they are, what needs attention, current state and next action.

## 16. Function Completeness
Every enabled visible primary control must work. Add/Create must create a real transaction. Accept must change acceptance state. Assign must change owner. Assessment must calculate/store the represented values. Appointment actions must mutate appointment state. Utilization must update quantity/amount ledger. History must show recorded events.

Dead enabled controls = FAIL.

## 17. Premium Composition Direction
Target premium, simple, calm, precise, professional, expensive without decorative luxury. Use hierarchy, Thai readability, deliberate density, restrained semantics and state-driven actions.

Avoid card sprawl, oversized KPI blocks, badge overload, tiny text, giant empty whitespace and generic SaaS/admin language.

## 18. Design Freedom Rule
Master specifies outcomes/failures, not pixel layout. Designer may simplify/combine/hide/reorder when workflow fidelity, queue topology, function completeness, state/data continuity and benchmark quality remain intact.

## 19. Operational UX Hard Failures
FAIL when:
- materially different queues are collapsed and user cannot distinguish jobs;
- create form wrongly assigns receiving owner;
- assignment cannot be performed after intake;
- estimate lacks itemized/financial calculation when required;
- required scoring/reassessment is not operable;
- appointment-driven follow-up has no today/upcoming work surface;
- approved quantity/value has no used/remaining ledger;
- prior case/utilization history is inaccessible;
- enabled visible control is dead;
- candidate is materially worse than benchmark without justification.

## 20. Final Rule
`Requirement is not a screen specification.`
`Master is not a screen specification.`

The Factory must understand fast, model correctly, distinguish queues, derive the real application, build early, execute actual work, then challenge hard.