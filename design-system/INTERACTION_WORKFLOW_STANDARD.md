# Gorilla HIS — Interaction Completeness, Hospital Realism & Scenario Execution Standard v1.6

Binding for every interactive Gorilla HIS mockup and every module.

## 1. Core Rule
`Hospital Actual Workflow Evidence → Blueprint Business Truth → Core Transaction/Lifecycle → Real Entry → Working Interaction → Observable State → Repeat/Re-assess → Exception/Recovery → End State → Executable Scenario Acceptance → Workflow Fidelity Test → Runtime Function Test → Independent Design Review`

A mockup is an **operational simulation**, not a slide deck, workshop map or collection of forms.

**Binding dependency:** `factory-gate/EXECUTABLE_SCENARIO_ACCEPTANCE_GATE.md`.

## 2. Actual Workflow Authority
Follow `blueprint-factory/ACTUAL_WORKFLOW_DISCOVERY_STANDARD.md`.

Domain Standard Flow may challenge the design but must not replace Hospital Actual Workflow. If actual flow is not verified, show that limitation in review documents — never fabricate certainty in hospital UI.

## 3. Transaction-First Interaction
Every material scenario must identify and execute its real transaction/object. Different transactions with different trigger, authority, data, approval, quantity/value, lifecycle or closure must not be implemented as cosmetic modes of one generic record.

## 4. Real Entry Rule
Every scenario begins at earliest operational Entry in scope. Do not skip upstream intake/classification merely because it is harder to mock.

For each scenario:
`Trigger/Entry → Required Data → Validate → Create/Receive/Accept Transaction → Ownership → Main Work → Decision/Handoff → Transaction/Result → Repeat/Re-assess/Partial Use when applicable → Review/Final → Exception/Recovery → Close`.

## 5. Lifecycle / State Execution
A state diagram in documentation is insufficient. Mockup must execute material transitions and visibly mutate status, owner, dates, history, quantities/values and enabled actions.

Material Return/Reject/Cancel/Expire/Suspend/Correct/Reverse/Reopen must be executable where applicable.

Toast-only state change = FAIL.

## 6. Repeated / Longitudinal Execution — UNIVERSAL CHECK
Every scenario must determine whether work repeats across sessions/visits/cycles/episodes, consumes approved quantity/value, requires reassessment or supports partial fulfillment.

When applicable, mockup must show:
- previous events/versions;
- current event;
- used/completed quantity or value;
- remaining quantity/value where relevant;
- reassessment/carry-forward behavior;
- changed/unchanged data;
- completion condition.

Single Save → Complete for a repeated workflow = `FAIL — REPEATED FLOW MISSING`.

## 7. Assessment Versioning
When assessment repeats, do not silently overwrite prior assessment. Demonstrate initial/reassessment, author/time/context, carry-forward where allowed, changed fields/score and downstream effect where applicable.

## 8. Scenario Branch Completeness
Separate branches when Transaction, Entry, Actor, Location, Identifier/Encounter, Authority, Source-of-Truth, Handoff, Custody, Finance, Privacy, Repeated behavior, Exception or End State materially differs.

Generic case with label changes = FAIL.

## 9. Data Continuity
Data entered/approved at earlier stages persists downstream. Identifier/context/owner/status/approval/assessment/quantity must not silently change. Derived values must have visible causal basis.

## 10. Role / Permission / Handoff Execution
Blueprint Role Matrix/Swimlane governs queues, ownership, enabled actions, restricted data and handoffs. UI must make current owner, waiting state, next action and blocked reason clear. Send/Approve without receiver state or return path is PARTIAL.

Handoff must be proven from sender action into receiver queue/worklist with the same transaction and correct state/data/owner. Merely switching a role label or navigating to another cosmetic view is not proof.

## 11. Exception & Recovery Execution
Material exceptions must be executable when relevant: missing data, wrong identifier, duplicate, Reject, Return, Redirect, unavailable approver/resource, partial completion, expired authorization, Cancel, Correction, interface failure, Reversal, restricted access, downtime/reconciliation, close with outstanding work, Reopen.

## 12. Hospital-Facing Realism
No Demo/Prototype/Workshop/WA/GAP/TBD/CR/HSR/AI/internal QA labels on normal hospital-facing surfaces unless explicitly requested. Use real operational language.

No fake buttons, fake approvals, decorative worklists or success that does not alter the operational state.

## 13. Swimlane Boundary
Role-Based Swimlane is primarily a Blueprint/document artifact. Do not add a Swimlane screen solely because Blueprint contains one. UI expresses ownership through queue, status, permission and actions.

## 14. Adaptive Navigation / Workspace
Navigation must not dominate the task. Support compact/collapsed state where useful. Main work reclaims space after selection. Large unused workspace + oversized navigation = UX/Design FAIL.

## 15. Mandatory Interaction Inventory
`Control ID | Scenario | Transaction | Lifecycle Stage | Role | Expected Behavior | Data Mutation | Observable Result | Test Result`

Every primary workflow control appears.

## 16. Executable Scenario Acceptance — Independent Hard Gate
Before Workflow Fidelity or Function can PASS, execute every Critical/High Material Main Scenario in a running browser according to `factory-gate/EXECUTABLE_SCENARIO_ACCEPTANCE_GATE.md`.

Required contract:
`Scenario ID → Start State/Entry → Actor → Action → Preconditions → Expected Data Mutation → Expected State Mutation → Expected Owner/Handoff → Observable Result → Next Action → End State`.

Required runtime evidence per step:
`Step ID | Action Executed | Expected State/Data/Owner | Actual State/Data/Owner | Observable Evidence | PASS/FAIL`.

Mandatory rules:
- Clickability ≠ Functional PASS.
- Screen coverage ≠ Scenario PASS.
- Source-code inspection ≠ Runtime Test.
- No executed scenario evidence = No Function PASS.
- A broken Material Step = Scenario FAIL.
- Runtime blocked = NOT VERIFIED.

Required artifact: `EXECUTABLE_SCENARIO_TEST.md`.

## 17. Workflow Fidelity Test — Independent and Mandatory
Independent reviewer acts as actual hospital user + Senior BA + Domain Expert and compares Hospital Evidence + Blueprint + **executed runtime trace**.

Test:
1 transaction identity/boundary;
2 real trigger/entry;
3 actor/authority/owner;
4 required data and source of truth;
5 lifecycle/state transitions;
6 handoff/waiting/return;
7 repeated/longitudinal behavior;
8 quantity/value/entitlement/utilization when applicable;
9 assessment/version/carry-forward when applicable;
10 exception/recovery;
11 closure/end state;
12 absence of invented local workflow;
13 executed scenario evidence matches documented flow.

Results:
`PASS`
`FAIL — WRONG TRANSACTION MODEL`
`FAIL — WORKFLOW FIDELITY`
`FAIL — LIFECYCLE INCOMPLETE`
`FAIL — REPEATED FLOW MISSING`
`FAIL — HANDOFF BROKEN`
`FAIL — EXECUTION EVIDENCE MISSING`
`BLOCKED — ACTUAL WORKFLOW NOT VERIFIED`.

Critical/High failure blocks release.

## 18. Runtime Functional Test
Run browser/runtime, not static source only. Runtime Test is execution, not code review. Minimum:
1 every primary nav;
2 main workflow screens/tabs;
3 modal/drawer families;
4 real Entry for every material scenario;
5 required-field validation;
6 transaction creation/acceptance;
7 valid state-changing action per major stage;
8 role decision/handoff and receiver queue proof;
9 repeated/reassessment/partial-use progression when applicable;
10 material exception/recovery;
11 data continuity/history;
12 navigate away → return through normal worklist → continue from correct state;
13 search/filter/context preservation;
14 no workflow-breaking console/page error;
15 meaningful closure/end-state assertion.

If runtime blocked, cannot PASS.

## 19. Independent Agent Function Test
Separate pass must not rely on Builder explanation. Test Function Completeness, Permission, Scenario, Exception, Data Continuity, State Transition, Usability/discoverability, Dead Controls, Blueprint Traceability and executed scenario proof.

Results include `PASS / FAIL — FUNCTION MISSING / FAIL — WORKFLOW BROKEN / FAIL — SCENARIO INCOMPLETE / FAIL — EXECUTION EVIDENCE MISSING / FAIL — UNUSABLE / FAIL — REQUIREMENT TRACEABILITY`.

Loop: `BUILD → RUN → EXECUTE → FAIL → FIX → RESTART APPROPRIATE SCENARIO → RETEST`.

## 20. Usability Hard Gate
Reviewer can identify where to start, what transaction they are handling, why it is here, required information, current state/owner, next action, why blocked, remaining work/quantity when relevant, recovery path and finish state. Guessing/source-code consultation = FAIL — UNUSABLE.

## 21. Independent Premium Design Review
After Executable Scenario + Workflow Fidelity + Operational UX + functional/runtime review, run `PREMIUM_PRODUCT_DESIGN_GATE.md` on rendered screens.

`Function PASS + Design FAIL = Factory FAIL`.

And:
**`Visual PASS + Functional PASS + Workflow Fidelity/Executable Scenario FAIL = Factory FAIL`.**

## 22. Reference Benchmark
User-supplied candidate is minimum benchmark. New candidate cannot regress workflow depth, information density, usability, interaction or visual craft.

## 23. Angular Mapping
Use Angular Material/CDK as implementation primitives where appropriate while preserving Gorilla design authority/density. Material default appearance is not design authority.

## 24. QA Decision
Cannot become `Candidate — Ready for Human Visual Review` when:
- actual workflow/transaction is materially unverified;
- material scenario cannot start from real Entry;
- wrong transaction model;
- repeated lifecycle missing;
- primary controls dead;
- data continuity breaks;
- handoff cannot be proven in receiver worklist;
- material exception/recovery missing;
- no `PASS — EXECUTED END-TO-END` evidence for Critical/High Main Scenarios;
- Workflow Fidelity Test has Critical/High failure;
- Agent Function Test has Critical/High failure;
- runtime unverified;
- user cannot understand workflow;
- Independent Design Review fails or is unverified.

Target: **real-work fidelity + executed end-to-end proof + complete operational execution + independent functional proof + independent premium design proof**.