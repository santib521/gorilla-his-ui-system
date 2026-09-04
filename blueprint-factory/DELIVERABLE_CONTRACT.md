# Gorilla HIS — Prompt 1+2 Deliverable Contract v1.0

Status: `FACTORY MASTER`

## Purpose
Make the document set and operational mockup one traceable product rather than independent outputs.

Core:
`Hospital Evidence → Shared Application Model → Executable Blueprint TXT → Review DOCX → Expert DOCX → index.html → Automated Traceability + Runtime Proof`

## Canonical Deliverables
1. `Application_Blueprint_<Module>.txt` — direct authority for UI build.
2. `Draft_Application_<Module>_TH.docx` — Thai hospital review document.
3. `Expert_Suggestion_<Module>_TH.docx` — Thai independent expert recommendation/concern/question document.
4. `index.html` — playable mockup derived from #1.

Additional QA/support files may be generated, but they do not replace these four.

## Single Shared Model Rule
All deliverables derive from the same workflow/transaction/state/role/function model. Do not separately reinterpret raw requirements for DOCX and HTML.

## Blueprint TXT Definition
Blueprint TXT is a machine/human-readable **Executable UI Contract**. It must define enough behavior for a different UI agent to implement without guessing.

Minimum build contract:
`Work Obligation → Worklist/Queue → Transaction → State → Screen → Visible Data → Action → Validation → Mutation → Handoff → Exception → End State`.

Stable IDs required:
- `AWF-*` Actual Workflow
- `WL-*` Worklist/Queue
- `OBJ-*` Transaction/Object
- `ST-*` State/Transition where useful
- `FN-*` Function
- `REQ-*` Hospital Requirement
- `CR-*` Change Request
- `RPT-*` Report/Output
- `SCN-*` Executable Scenario
- `AC-*` / `WF-AC-*` Acceptance Criteria
- `Q-*` Open Decision

Mandatory final trace table:
`UI Surface/Control | FN | REQ/CR | SCN | State From→To | Role | Observable Mutation | AC`.

## Draft Application DOCX Definition
Hospital-facing Thai review document. Must contain workflow swimlanes plus narrative explanation, Function List by source/status, CR, reports, Role Matrix, queue/worklist architecture, key states, integration/data, exceptions, and open decisions.

Swimlane is document authority and should show:
`Start → Role → Activity → Decision → System/Record → Handoff/Wait → Exception → End`.

Do not add a Swimlane UI screen unless explicitly required by the application.

## Expert Suggestion DOCX Definition
Independent Thai expert review. Must contain recommendations, concerns and decision-valued questions. Recommendations are not Hospital Truth.

Every material question includes:
`Priority | Concern | Question | Why Asked | Recommendation/Options | Impact | Owner | Confirm When | Status`.

## index.html Definition
`index.html` consumes the Blueprint contract conceptually as its source of truth.

For every required scenario:
`Real Entry → Queue → Open Work → Validate → Action → State Mutation → Handoff/Wait → Repeat/Reassess if applicable → Exception/Recovery → Meaningful End State`.

Mock data is part of the contract, not decoration. It must be designed to demonstrate normal, waiting, aged/attention, repeated/partial-use and material exception cases where applicable.

## Automated Traceability Gate
A QA pass must compare Blueprint IDs and declared behaviors with the mockup.

Required checks:
- Function coverage: mandatory FN implemented/reachable.
- Scenario coverage: SCN executable.
- Queue coverage: WL exists and contains correct object/state.
- State coverage: required transition is triggerable and observable.
- Data coverage: scenario has usable mock record.
- Report coverage: required prototype RPT reachable.
- Role coverage: restricted actions represented when material.
- Reverse trace: no material enabled UI behavior without Blueprint authority.

Allowed result:
`PASS` or `FAIL — BLUEPRINT/HTML TRACEABILITY` with missing IDs listed.

## Separation of Truth
Hospital stated/confirmed requirements remain distinct from:
- Standard Recommended Function
- Expert Recommendation
- Compliance Recommendation
- Working Assumption
- TBD/Open Decision

The mockup may safely demonstrate a recommendation only when visibly treated as prototype behavior and it does not falsely establish Hospital Policy.

## Delivery Gate
Deliver only after:
`Blueprint Completeness PASS → DOCX Consistency PASS → Blueprint/HTML Traceability PASS → Workflow Fidelity PASS → Runtime PASS → Design Review PASS`.

Human Visual Review remains required before Gold promotion.