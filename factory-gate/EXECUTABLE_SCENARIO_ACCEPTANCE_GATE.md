# Gorilla HIS — Executable Scenario Acceptance Gate v1.0

**Status: UNIVERSAL FACTORY MASTER — HARD GATE**

Applies to every module and every interactive mockup.

## 1. Purpose
A mockup is not functional because screens exist, buttons click, handlers exist, or source code appears complete. It is functional only when an actual user scenario can be executed in a running browser from the real Entry to the intended End State with correct state, data, ownership and history continuity.

## 2. Non-negotiable rules
- **Clickability ≠ Functional PASS.**
- **Screen coverage ≠ Scenario PASS.**
- **JavaScript/function existence ≠ Runtime PASS.**
- **Source-code inspection ≠ Runtime Test.**
- **Toast/navigation-only behavior ≠ State execution.**
- **No executed scenario evidence = No Function PASS.**
- **No state/data/owner continuity = No Workflow Fidelity PASS.**
- **A broken Material Step = Scenario FAIL.**
- **Runtime blocked or not executed = NOT VERIFIED, never PASS.**

## 3. Executable Scenario Contract
Before build, every Material Main/Alternate/Exception scenario must be converted into an executable contract:

`Scenario ID → Start State/Entry → Actor → Action → Preconditions → Expected Data Mutation → Expected State Mutation → Expected Owner/Handoff → Observable Result → Next Action → End State`

For repeated/longitudinal work also include:
`Iteration/Visit/Cycle → Previous Version → Current Assessment → Used/Completed → Remaining → Completion Condition`.

The contract is acceptance truth for the running mockup.

## 4. Mandatory Runtime Execution
The test agent must execute the running mockup step-by-step. For every step capture:

`Step ID | Actor | Action Executed | Expected State/Data/Owner | Actual State/Data/Owner | Observable Evidence | PASS/FAIL`

Evidence must come from the running UI/runtime: rendered state, visible values/status/history, receiver queue/worklist, browser/runtime observation or equivalent runtime evidence. A code snippet alone is not evidence.

## 5. Cross-role Handoff Proof
When a scenario sends work to another role/team:
1. sender performs handoff;
2. sender state visibly changes;
3. receiver can find the same transaction in the correct queue/worklist;
4. identity/context/data remain consistent;
5. receiver action continues the same lifecycle;
6. Return/Reject path returns to a meaningful sender state when applicable.

Changing a role label while keeping a fake shared screen without receiver-state proof is not sufficient.

## 6. Repeated Flow Proof
If workflow repeats, one iteration is not enough to prove the lifecycle. Test must demonstrate at least:
- first iteration;
- an intermediate iteration with preserved history;
- final iteration/completion;
- used/completed and remaining values;
- reassessment/version behavior when applicable;
- attempt beyond limit or another material boundary when relevant.

For an authorization of N uses, the runtime must prove progression and completion logic; tests may use a representative accelerated sequence only if state transitions are genuinely executed and final counters/history are verified.

## 7. Persistence and Return-to-Work Proof
After a state-changing action, navigate away and return through the normal operational entry/worklist. The transaction must appear in the correct state/owner/filter context and continue from the correct Next Action. A state that exists only inside the current panel is FAIL.

## 8. Material Exception Proof
At least the material exceptions identified by Blueprint/Actual Workflow must be executed, not merely documented. Examples: required validation, Return, Reject, Cancel, expired entitlement, insufficient remaining quantity, correction/reversal, missing authority, integration failure/recovery.

## 9. Test Independence
Builder self-QA cannot grant final PASS. Runtime scenario execution must be performed as an independent test pass that does not rely on Builder explanation.

If the test agent needs to read source code to discover how to continue the user flow, usability/function result is FAIL or NOT VERIFIED.

## 10. Required Artifact — EXECUTABLE_SCENARIO_TEST.md
For every Material Scenario include:
- Scenario purpose and evidence/Blueprint trace;
- actor(s);
- preconditions/test data;
- complete step table;
- expected vs actual state/data/owner;
- runtime evidence;
- end-state assertion;
- exceptions tested;
- defects found;
- fix/retest history;
- final result.

Allowed results:
- `PASS — EXECUTED END-TO-END`
- `FAIL — BROKEN STEP`
- `FAIL — STATE/DATA CONTINUITY`
- `FAIL — HANDOFF NOT EXECUTABLE`
- `FAIL — REPEATED FLOW NOT EXECUTABLE`
- `FAIL — END STATE NOT REACHED`
- `FAIL — EXCEPTION NOT EXECUTABLE`
- `BLOCKED — RUNTIME NOT VERIFIED`

## 11. Build-Test-Fix Loop
Mandatory loop:

`BUILD → RUN → EXECUTE SCENARIO → CAPTURE ACTUAL → FAIL? → FIX → RESTART SCENARIO → RETEST → PASS`

Do not patch a failed late step and test only that step when earlier state transitions materially establish its context. Restart from the appropriate Entry/precondition.

## 12. Release Gate
A module cannot claim Function PASS, Workflow Fidelity PASS, Runtime PASS, Premium Candidate, or Ready for Human Visual Review unless all Critical/High Material Main Scenarios have `PASS — EXECUTED END-TO-END` and required material exceptions are executed.

**Functional PASS + Visual PASS + no executable scenario proof = FACTORY FAIL.**

Target: **the user can actually do the job, not merely click through a presentation of the job.**