# Gorilla HIS — Interaction Completeness, Hospital Realism & Scenario Execution Standard v1.3

This standard is binding for every interactive Gorilla HIS mockup.

## 1. Core Rule
`Blueprint Business Truth → Scenario Entry → Working Interaction → Observable State → Exception → End State → Independent Test`

The mockup proves that the workflow described in the Blueprint can actually be operated. It is not a workflow-documentation canvas.

## 2. Swimlane Boundary
Role-Based Swimlane is primarily a **Blueprint/document artifact** used to explain actors, decisions and handoffs.

UI Factory MUST NOT add a Swimlane screen solely because the Blueprint contains a Swimlane. Add a workflow/swimlane visualization to hospital-facing UI only when:
1. the Hospital Requirement explicitly asks for workflow monitoring/visualization; or
2. the product genuinely needs an operational workflow tracker and the Blueprint marks it as a product function.

Role/handoff truth still governs permissions, ownership, queues and executable actions in the mockup.

## 3. Entry-First Scenario Rule
Every material in-scope scenario must begin from its real operational Entry, not only from a pre-populated case.

Examples: New Request, Key Request, Referral, Registration, Order, Appointment, Admission, Specimen Receipt, Stock Request — according to the domain.

For each scenario, reviewer must be able to:
`Entry → Key required data → Validate → Decision → Create/Accept work → Assignment/Handoff → Main work → Transaction/Result → Review/Final → Handover/Close`

Only include steps relevant to that domain.

A mockup containing only completed/pre-created cases when Blueprint requires creation/intake = FAIL.

## 4. Scenario Branch Completeness
Each materially distinct Blueprint scenario is a separate Main Workflow test path. Differences may include entry trigger, actor, identifier/encounter, authority, source-of-truth, handoff, finance, privacy, exception or end state.

For each in-scope scenario:
1. start from real Entry;
2. enter/choose meaningful data;
3. validate required information;
4. exercise material decision(s);
5. create observable state/data;
6. perform scenario-specific main work;
7. exercise material handoff/transaction;
8. reach meaningful end state;
9. exercise at least one relevant exception;
10. test branch separately.

One generic case with label changes = FAIL.

## 5. Interaction Completeness
Every visible primary workflow control must have meaningful observable behavior. Material state-changing actions must mutate visible state/data; toast-only success is insufficient.

Dead primary navigation/menu/tab/action, fake success, broken confirm/cancel, unreachable next stage = FAIL.

## 6. Data Continuity
Data entered at Entry must persist through downstream screens where the Blueprint requires it. Identifier/context/owner/status must not silently change. A workflow that visually advances but loses or contradicts entered data = FAIL.

## 7. Role / Permission Execution
Role model comes from Blueprint Swimlane/Role Matrix. Mockup must enforce relevant ownership and permission behavior through worklists, enabled/disabled actions, restricted data and handoffs. Do not create a decorative role diagram as a substitute.

## 8. Exception Execution
Material exceptions from Blueprint must be executable when relevant: Reject, Return for Information, Cancel, Correction, Wrong Identifier, Missing Required Data, Duplicate, Unavailable Resource/Person, Failed Interface, Reversal, Restricted Access.

## 9. Hospital-Facing Realism
Do not expose Demo/Prototype/WA/GAP/TBD/CR/HSR/AI/internal QA language in normal hospital-facing UI unless explicitly requested. Use realistic operational statuses.

## 10. Mandatory Interaction Inventory
Create:
| Control ID / Label | Scenario | Entry/Stage | Role | Expected Behavior | Observable Result | Test Result |

Every primary Main Workflow control appears.

## 11. Runtime Functional Smoke Test
Run browser/runtime, not static source only. Minimum:
1. every primary nav;
2. every main workflow tab/screen;
3. modal/drawer families;
4. Entry/create/intake for every material scenario;
5. required-field validation;
6. valid state-changing action per major stage;
7. scenario-specific decision/handoff;
8. one material exception per scenario where relevant;
9. data continuity from Entry to downstream work;
10. search/filter/context preservation when relevant;
11. no workflow-breaking console/page error;
12. meaningful end state for every required scenario.

If runtime execution is blocked, Functional Smoke Test cannot be PASS.

## 12. Independent Agent Function Test — Mandatory Release Gate
After Builder completes the mockup, a separate review pass acts as Hospital User + Senior BA + Domain Expert + QA Tester. It must not rely on Builder explanation to understand how to work.

Test dimensions:
- Workflow Completeness
- Function Completeness
- Role/Permission
- Scenario Completeness
- Exception Handling
- Data Continuity
- State Transition
- Usability / discoverability
- Dead Controls
- Blueprint Traceability

Allowed results:
- `PASS`
- `FAIL — FUNCTION MISSING`
- `FAIL — WORKFLOW BROKEN`
- `FAIL — SCENARIO INCOMPLETE`
- `FAIL — UNUSABLE`
- `FAIL — REQUIREMENT TRACEABILITY`

Critical/High failure blocks release.

Required loop:
`BUILD → AGENT FUNCTION TEST → FAIL → FIX → RETEST`

Stop the loop only when PASS or when an unresolved Hospital Decision prevents safe completion. In the latter case report `BLOCKED — HOSPITAL DECISION REQUIRED`, not PASS.

## 13. Usability Hard Gate
The independent reviewer must be able to identify:
- where to start;
- what information is required;
- current status/owner;
- next action;
- why an action is blocked;
- how to recover from relevant error/return;
- how to finish the work.

If the reviewer must guess the workflow or consult source code, `FAIL — UNUSABLE`.

## 14. Reference Benchmark
A user-supplied existing mockup is a minimum benchmark. New candidate must not regress workflow depth, interaction completeness, information density, product continuity or usability.

## 15. Angular Mapping
Use Angular Material/CDK as implementation primitives where appropriate while preserving Gorilla HIS design authority and clinical density. Scenario state, permission state and transaction state must map cleanly to implementable Angular state/services.

## 16. QA Decision
Cannot become Candidate — Ready for Human Visual Review when:
- a material scenario cannot start from real Entry;
- primary controls are dead;
- scenario branch is cosmetic-only;
- data continuity breaks;
- material exception is missing;
- Independent Agent Function Test has Critical/High failure;
- runtime test is unverified;
- user cannot understand how to complete the workflow.

Target: **complete operational scenario execution + independent functional proof + premium Gorilla HIS craft**.