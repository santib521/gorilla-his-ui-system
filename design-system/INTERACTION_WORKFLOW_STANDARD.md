# Gorilla HIS — Interaction Completeness, Hospital Realism & Scenario Execution Standard v1.4

Binding for every interactive Gorilla HIS mockup.

## 1. Core Rule
`Blueprint Business Truth → Real Domain Entry → Classification/Decision → Working Interaction → Observable State → Exception → End State → Independent Function Test → Independent Design Review`

## 2. Swimlane Boundary
Role-Based Swimlane is primarily a Blueprint/document artifact. Do not add a Swimlane screen solely because Blueprint contains one. Add operational workflow visualization only when Hospital Requirement/product function requires it.

## 3. Classification-First Entry Rule
Every material scenario must begin at the earliest operational Entry that is in scope. If the domain requires classification/triage before registration, the mockup must not skip directly to a pre-created case.

Examples:
- forensic: death/event/notification → medico-legal classification → request/referral → intake;
- ER: arrival → triage;
- OR: surgical request → scheduling/readiness;
- lab: order/specimen receipt according to scope.

For each scenario:
`Entry → Classification/Eligibility → Required Data → Validate → Decision → Create/Accept Work → Assignment/Handoff → Main Work → Transaction/Result → Review/Final → Handover/Disposition/Close`.

Only include domain-relevant steps, but never omit an upstream stage merely because it is harder to mock.

## 4. Scenario Branch Completeness
Separate branches when Classification, Entry, Actor, Location, Identifier/Encounter, Authority, Source-of-Truth, Handoff, Custody, Finance, Privacy, Exception or End State materially differs.

Each in-scope branch must start from real Entry, enter meaningful data, validate, exercise material decision, create observable state, perform scenario-specific work/handoff, reach meaningful end state and execute at least one relevant exception.

Generic case with label changes = FAIL.

## 5. Interaction Completeness
Every visible primary workflow control has meaningful observable behavior. State-changing actions mutate visible state/data; toast-only success insufficient. Dead nav/menu/tab/action, fake success, broken confirm/cancel, unreachable stage = FAIL.

## 6. Data Continuity
Data entered at Entry/classification persists downstream where Blueprint requires it. Identifier/context/owner/status/classification must not silently change.

## 7. Role / Permission Execution
Blueprint Swimlane/Role Matrix governs ownership/permissions through worklists, enabled actions, restricted data and handoffs. Decorative role diagrams do not substitute.

## 8. Exception Execution
Material exceptions must be executable when relevant: Reject, Return, Redirect, Cancel, Correction, Wrong Identifier, Missing Data, Duplicate, Unavailable Resource/Person, Failed Interface, Reversal, Restricted Access, invalid classification/route.

## 9. Hospital-Facing Realism
No Demo/Prototype/WA/GAP/TBD/CR/HSR/AI/internal QA labels on normal hospital-facing surfaces unless requested. Use real operational language.

## 10. Adaptive Navigation / Workspace
Navigation must not dominate the task. Where workflow benefits, support expanded/compact/collapsed state while preserving orientation. Main work should reclaim space after selection when appropriate. Large unused blank workspace + oversized navigation = UX/Design FAIL.

## 11. Mandatory Interaction Inventory
`Control ID | Scenario | Entry/Stage | Role | Expected Behavior | Observable Result | Test Result`
Every primary Main Workflow control appears.

## 12. Runtime Functional Smoke Test
Run browser/runtime, not static source only. Minimum:
1 every primary nav;
2 main workflow screens/tabs;
3 modal/drawer families;
4 real Entry + classification/intake for every material scenario;
5 required-field validation;
6 valid state-changing action per major stage;
7 scenario decision/handoff;
8 material exception per scenario where relevant;
9 data continuity;
10 search/filter/context preservation;
11 no workflow-breaking console/page error;
12 meaningful end state.

If runtime blocked, cannot PASS.

## 13. Independent Agent Function Test
Separate pass acts as Hospital User + Senior BA + Domain Expert + QA Tester and must not rely on Builder explanation.

Test: Workflow Completeness, Function Completeness, Domain Classification, Role/Permission, Scenario, Exception, Data Continuity, State Transition, Usability/discoverability, Dead Controls, Blueprint Traceability.

Results:
`PASS`
`FAIL — FUNCTION MISSING`
`FAIL — WORKFLOW BROKEN`
`FAIL — SCENARIO INCOMPLETE`
`FAIL — DOMAIN CLASSIFICATION MISSING`
`FAIL — UNUSABLE`
`FAIL — REQUIREMENT TRACEABILITY`

Critical/High failure blocks release.
Loop: `BUILD → TEST → FAIL → FIX → RETEST`.
Unresolved Hospital Decision: `BLOCKED — HOSPITAL DECISION REQUIRED`.

## 14. Usability Hard Gate
Reviewer can identify where to start, why this case belongs in this workflow, required information, current status/owner, next action, why blocked, recovery path and finish state. Guessing/source-code consultation = FAIL — UNUSABLE.

## 15. Independent Premium Design Review
After functional review, run `design-system/PREMIUM_PRODUCT_DESIGN_GATE.md` on rendered screens.

`Function PASS + Design FAIL = Factory FAIL`.

Design review must explicitly inspect navigation footprint, space utilization, Thai typography, hierarchy/task focus, progressive disclosure, component craft, generic-admin appearance, Gorilla continuity and responsive/collapse behavior.

## 16. Reference Benchmark
User-supplied candidate is minimum benchmark. New candidate cannot regress workflow depth, information density, usability, interaction or visual craft.

## 17. Angular Mapping
Use Angular Material/CDK as implementation primitives where appropriate while preserving Gorilla design authority/density. Material default appearance is not design authority.

## 18. QA Decision
Cannot become Candidate — Ready for Human Visual Review when:
- material scenario cannot start from real Entry/classification;
- primary controls dead;
- scenario cosmetic-only;
- data continuity breaks;
- material exception missing;
- Agent Function Test has Critical/High failure;
- runtime unverified;
- user cannot understand workflow;
- Independent Design Review fails or is unverified when rendered review is required.

Target: complete operational execution + independent functional proof + independent premium design proof.