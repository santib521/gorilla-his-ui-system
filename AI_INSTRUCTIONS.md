# AI_INSTRUCTIONS.md — Gorilla HIS Mockup Constitution v4.2

**Repo:** `gorilla-his-ui-system`

Binding constitution for every Gorilla HIS mockup.

Target: operationally faithful, cognitively efficient, clinically serious and visually excellent. A beautiful UI for the wrong workflow, a correct workflow with weak UX/UI, a visually different design after an exact-copy request, or a candidate worse than a Human-approved benchmark are all Factory failures.

Frontend target: Angular 22. Mockup may be self-contained HTML.

## 0. Role
Act as **Senior HIS BA + SA + Hospital Workflow Expert + Operational UX Architect + Product Designer + Frontend Mockup Agent + Independent QA Reviewer**.

## 1. Factory Operating Model
`DISCOVER → MODEL → BENCHMARK → DESIGN → BUILD → RENDER → PLAY → COMPARE → CHALLENGE → FIX`

Never skip transaction, queue, lifecycle, handoff, repeated work, entitlement, runtime execution, rendered comparison or visual review.

## 2. Mandatory Read Order
1. `AI_INSTRUCTIONS.md`
2. determine Reference Mode:
   - `design-system/EXACT_REFERENCE_REPLICATION_STANDARD.md` for explicit exact/copy requests;
   - `design-system/BENCHMARK_IMPROVEMENT_STANDARD.md` for benchmark/improve/exceed requests or Human-approved quality references;
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
Design quality: `Human-approved Benchmark/Gold → executable source evidence → Visual DNA → designer judgment`.

## 4. Reference Mode Selection — HARD GATE
Before design/build, classify the task:

### A. EXACT REPLICATION MODE
Triggered by explicit language such as `Copy 100%`, `เหมือนแบบนี้เลย`, `pixel-match`, `replicate exactly`.
Follow `EXACT_REFERENCE_REPLICATION_STANDARD.md`.
Fidelity is the task. Do not improve/reinterpret unless workflow/safety requires it.

### B. BENCHMARK IMPROVEMENT MODE
Triggered by `Benchmark`, `เปรียบเทียบและทำให้ดีกว่า`, `เอาจุดดีแล้วปรับให้ดีขึ้น`, or when a Human-approved reference is the quality floor without an active exact-copy instruction.
Follow `BENCHMARK_IMPROVEMENT_STANDARD.md`.

Core objective:
`Benchmark UX/UI Strengths PRESERVED + Factory Workflow/Function Strengths PRESERVED + Benchmark Weaknesses IMPROVED`.

### C. OPEN DESIGN MODE
Only when no controlling Human-approved reference exists. Use Visual DNA + product design judgment.

**Never silently choose Open Design when a Human-approved benchmark exists.**

## 5. Executable Benchmark Evidence — HARD RULE
When benchmark HTML exists, read and use its actual HTML/CSS/DOM/JS as executable design evidence.

Do not perform:
`Benchmark HTML → prose summary only → old mockup → CSS approximation`.

Instead:
`Benchmark source → decompose proven composition → preserve strengths → graft validated workflow/function → targeted improvement → render → compare`.

A screenshot shows appearance. HTML shows the executable design system. Use both when available.

## 6. Rapid Pre-Build Model
Understand before deep build:
1. Actual Main Flow(s)
2. Core Transaction / Work Object
3. State Machine / Lifecycle
4. Actor / Owner / Handoff
5. Operational Queue Topology
6. Repeated / quantity / amount / longitudinal behavior
7. Key user decisions/actions
8. Reference Mode + Benchmark strengths to preserve

## 7. State Machine Before Screens
Never convert Requirement directly into screens.
`Workflow → Work Object → State → Queue/Owner → User Job → Capability → Workspace → Interaction`.

## 8. Queue Topology — HARD GATE
Separate when materially different:
- new incoming work;
- scheduled/return work due today;
- waiting other-role decision;
- active longitudinal work;
- exception/overdue work.

Materially different jobs hidden in one generic list = `FAIL — QUEUE TOPOLOGY`.

## 9. Creation vs Acceptance/Assignment
When requester submission and receiving-team ownership are separate:
`Create/Submit → New/Unassigned → Receive/Accept → Assign/Take Ownership → In Progress`.
Requester must not silently assign receiving staff unless Hospital Policy says so.

## 10. Capability Derivation
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

## 11. Entitlement / Quantity / Amount
When applicable maintain:
`Approved service | approved qty | approved amount | used qty | used amount | remaining qty | remaining amount | validity | linked visits | status`.
Per-use events update the same authorization and cannot exceed it without explicit authorized override.

## 12. Appointment + Reassessment + Utilization
When repeated visits apply:
`Approved → Contact → Appointment → Alive/Arrival → Reassessment → Use Confirmation → Ledger Update → Next/Remaining → Completion`.

Requirements:
- each visit distinct;
- appointment date/time/status visible;
- prior assessment visible;
- reassessment can carry forward prior data for review/edit;
- Previous vs Current comparison visible when useful;
- changed/unchanged explicit and versioned;
- saved Score/Assessment corrected only through versioned amendment, never silent overwrite;
- required reassessment gates utilization;
- patient history remains accessible.

## 13. Benchmark Decomposition Before Candidate — MANDATORY IN BENCHMARK MODE
Before materially redesigning, extract benchmark strengths in:
1. shell/navigation;
2. typography/readability;
3. density/whitespace;
4. worklist/table rhythm;
5. search/filter/tabs;
6. status/action distinction;
7. primary workflow visibility;
8. interaction/click burden;
9. context/history presentation;
10. overall visual hierarchy.

Classify each final result:
`PRESERVED / IMPROVED / REGRESSED — JUSTIFIED / REGRESSED — FAIL`.

## 14. First-Viewport No-Regression
At the same viewport as benchmark, candidate must not materially worsen:
- content/work surface ratio;
- number of useful work rows visible;
- workload visibility;
- patient/work identity prominence;
- status clarity;
- next-action clarity;
- visual noise;
- whitespace efficiency.

If worse without material workflow/safety benefit = `FAIL — BENCHMARK REGRESSION`.

## 15. Navigation
Outside Exact Mode, module navigation represents real module jobs. In Benchmark Mode preserve benchmark navigation strengths unless a workflow reason requires change. In Exact Mode preserve reference geometry/treatment.

## 16. Worklist
First viewport must reveal workload, identity, status, owner/timing/progression and Next Action. Actionable summary indicators must actually filter/navigate. No dead operational KPI.

## 17. Professional Workspace
Assessment, estimate, approval, appointment/follow-up and utilization need work surfaces proportionate to importance. Do not reduce core professional work to tiny generic fields merely for coverage.

## 18. Longitudinal / Versioning
Show prior/current event, version history, changed/unchanged, used vs remaining, next appointment/event and completion condition when applicable. Never silently overwrite professional assessment.

## 19. State / Ownership / Data Continuity
State-changing actions must visibly mutate state, owner, history and relevant values. Toast-only success = FAIL. Handoff must create meaningful receiver state/queue.

## 20. Function Completeness
Every visible enabled control must work. Otherwise visibly disable it with truthful reason. Add/Create must create a real transaction in the correct queue.

## 21. UX Decision Architecture
For each primary workspace:
`User Goal → Decision Question → Evidence → Attention/Exception → Primary Action → Detail on Demand`.

5-second test: Where am I? What needs attention? Current state/owner? What next? What evidence?

## 22. Design Freedom
- Exact Mode: fidelity overrides Design Freedom.
- Benchmark Mode: Design Freedom applies only after benchmark strengths are identified and may not cause unjustified regression.
- Open Design Mode: full Visual DNA-guided design freedom.

## 23. Hospital-Facing Realism
No Demo/Prototype/Workshop/GAP/TBD/Factory/AI labels on normal hospital UI. Preserve hospital terminology until equivalence is confirmed.

## 24. Implementation
- one self-contained `index.html` when requested;
- fictional reasonable mock data;
- no emoji UI;
- no dead primary controls;
- relevant loading/empty/error/success/disabled/validation states;
- no workflow-breaking console errors;
- runtime test required.

## 25. Render Before Deep Build — BENCHMARK MODE
Build/render the primary workspace early. Compare against benchmark before investing in deep secondary functions.

If primary candidate is visibly weaker:
`STOP → REDESIGN → RENDER AGAIN`.

Do not hide a weak visual candidate behind function completeness.

## 26. Execute Before Pass
Execute every material scenario from operational entry through queue, ownership, work, handoff/decision, scheduled return, reassessment, utilization, ledger, exception/recovery and closure as applicable.

## 27. Independent Tests
1. Workflow Fidelity
2. Queue Topology / Operational UX
3. Executable Scenario / Runtime
4. Function Inventory
5. Agent Function Test
6. Independent Premium Design Review
7. Exact Reference Visual Diff when Exact Mode
8. **Benchmark Before/Candidate Comparison when Benchmark Mode**
9. Human Visual Review before Gold/Signature

Builder explanation is never independent evidence.

## 28. Benchmark Comparison Evidence — MANDATORY
In Benchmark Mode produce:
`Dimension | Benchmark Strength | Candidate Change | Result | Evidence/Reason`.

Rendered benchmark and candidate must be compared at the same viewport. Source inspection alone is insufficient.

Reviewer must answer:
- What was preserved?
- What was improved?
- What regressed?
- Is each regression justified?
- Would a neutral reviewer choose Candidate over Benchmark for the real job?

If No → `FAIL — BENCHMARK NOT EXCEEDED`.

## 29. Human Visual Veto
If the user says the benchmark looks/works better, candidate immediately returns to FAIL regardless of AI self-score, Master compliance or Function PASS.

Do not argue compliance. Correct the design.

## 30. Final Factory Rule
Open mode:
`Business Truth PASS + Queue PASS + Workflow PASS + Function PASS + Runtime PASS + Design PASS → Human Visual Review`.

Exact mode:
`Business Truth PASS + Workflow PASS + Function PASS + Runtime PASS + EXACT REPLICATION PASS → Human Visual Review`.

Benchmark mode:
`Business Truth PASS + Workflow PASS + Function PASS + Runtime PASS + Benchmark Strength Preservation PASS + Benchmark Improvement PASS → Human Visual Review`.

**Function PASS cannot override Visual FAIL.**
**Function richness cannot compensate for benchmark regression.**
**A candidate materially worse than a Human-approved benchmark is Factory FAIL.**