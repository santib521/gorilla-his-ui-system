# Gorilla HIS — Prompt 1+2 Deliverable Contract v1.1

Status: `FACTORY MASTER`

## Purpose
Make requirement discovery, documents and operational mockup one traceable product rather than independent outputs.

Core:
`Project Session → Expert Workshop/Challenge → Shared Application Model → Executable Blueprint TXT → Review DOCX → Expert DOCX → index.html → Traceability + Runtime Proof`.

## Canonical Deliverables
1. `Application_Blueprint_<Module>.txt` — direct authority for UI build.
2. `Draft_Application_<Module>_TH.docx` — Thai hospital review document.
3. `Expert_Suggestion_<Module>_TH.docx` — Thai independent expert recommendation/concern/question document.
4. `index.html` — playable mockup derived from #1.

Additional QA/support files may be generated, but they do not replace these four.

## Single Shared Model Rule
All deliverables derive from the same workflow/transaction/state/work-obligation/role/function model. Do not separately reinterpret raw requirements for DOCX and HTML.

## 1. Application Blueprint TXT — EXECUTABLE UI CONTRACT
Must be deterministic enough that another UI Factory Agent can build `index.html` without rereading raw requirement or guessing behavior.

Minimum contract:
`Actual Workflow → Work Obligation → Worklist/Queue → Transaction → Lifecycle/State → Role/Owner → Screen → Visible Data → Action → Validation → Mutation → Handoff → Repeat/Reassess → Exception → End State`.

Stable IDs:
`AWF-* / WL-* / OBJ-* / ST-* / FN-* / REQ-* / CR-* / RPT-* / SCN-* / AC-* / WF-AC-* / Q-*`.

Mandatory Blueprint content:
- evidence/status boundary;
- scope/objective;
- actual or Standard-baseline scenarios clearly classified;
- work obligations and queue topology;
- transaction/object model;
- lifecycle/state transitions;
- role/handoff/waiting;
- repeated/longitudinal/quantity/value/reassessment;
- data/source of truth;
- screen/workspace inventory;
- per-screen field/action/validation/mutation/navigation contract;
- Function List;
- Hospital Requirements and CR;
- Standard Recommended Functions kept separate;
- reports/outputs;
- role/permission;
- exception/recovery;
- mock-data contract;
- executable scenario scripts;
- acceptance criteria;
- assumptions/open decisions;
- final UI trace table:
`UI Surface/Control | FN | REQ/CR/Recommendation | SCN | State From→To | Role | Observable Mutation | AC`.

No material function may exist only in prose.

## 2. Draft Application DOCX — HOSPITAL REVIEW
Thai, human-readable, workshop/approval oriented.

Mandatory:
- application objective/scope;
- Application Workflow;
- Role-Based Swimlane for every material multi-role scenario + Thai narrative;
- Worklist/Queue architecture;
- transaction/lifecycle explanation;
- Function List separated into `Hospital Requirement / Standard Recommended Function / CR`;
- Role Matrix / permission / responsibility;
- Reports / Outputs / Statistics;
- integration/data source when material;
- exception/operational controls;
- requirement/function trace summary;
- Open Hospital Decisions clearly separated from confirmed requirements.

Swimlane is document authority:
`Start → Role → Activity → Decision → System/Record → Handoff/Wait → Exception → End`.
Do not create a Swimlane product screen unless explicitly required.

## 3. Expert Suggestion DOCX — INDEPENDENT EXPERT REVIEW
Thai. Must not duplicate Draft Application or silently promote recommendations.

Include applicable:
- workflow/transaction/worklist recommendations;
- domain/professional recommendations;
- operational/UX concerns;
- data/integration concerns;
- privacy/security concerns;
- finance concerns;
- audit/accountability concerns;
- patient-safety concerns when relevant;
- applicable standard/compliance recommendations with source support.

Every material question:
`Q ID | Priority | Concern | Question | Why Asked | Current Evidence | Recommendation/Options | Decision Impact | Owner | Confirm When | Status`.

Group:
`MUST CONFIRM BEFORE DEV / CONFIRM DURING PROTOTYPE REVIEW / SAFE TO DEFER`.

## 4. index.html — PLAYABLE OPERATIONAL MOCKUP
Built from Blueprint, not independently from Project Session.

For every required scenario:
`Real Entry → Queue → Open Work → Validate → Action → State Mutation → Handoff/Wait → Repeat/Reassess if applicable → Exception/Recovery → Meaningful End State`.

Requirements:
- all prototype-required `FN-*` reachable/implemented;
- required `SCN-*` executable end-to-end;
- realistic mock data defined by Blueprint;
- visible mutation of state/owner/time/quantity/value/history as applicable;
- meaningful receiver queue/state after handoff;
- material exception/recovery executable when required;
- required reports/outputs reachable;
- no toast-only fake transaction completion;
- every enabled primary control works;
- no Demo/Factory/TBD/Workshop labels in normal hospital-facing UI.

## Expert Applicability Rule
The Factory may use a broad expert pool, but deliverables include only relevant activated domains. HA/JCI/ISO27001/HIPAA/etc. do not generate content merely because they exist. Follow `PROJECT_SESSION_INPUT_STANDARD.md`.

When Project Session says `ยึดตาม Standard`, the resulting flow/role/report remains `REFERENCE BASELINE / STANDARD RECOMMENDATION — NOT HOSPITAL CONFIRMED` until hospital evidence confirms it.

## Automated Blueprint ↔ HTML Traceability Gate
Must prove:
- mandatory FN coverage;
- SCN execution;
- WL/queue coverage;
- state transition coverage;
- mock-data coverage;
- prototype-required RPT coverage;
- role/permission coverage when material;
- reverse trace: no material enabled UI behavior without Blueprint authority.

Result: `PASS` or `FAIL — BLUEPRINT/HTML TRACEABILITY` with missing IDs.

## Truth Separation
Hospital evidence remains distinct from:
`REFERENCE BASELINE / STANDARD RECOMMENDATION / EXPERT RECOMMENDATION / COMPLIANCE RECOMMENDATION / WORKING ASSUMPTION / TBD`.

## Delivery Gate
`Blueprint Completeness PASS → DOCX Consistency PASS → Blueprint/HTML Traceability PASS → Workflow Fidelity PASS → Function PASS → Runtime PASS → Design Review PASS`.

Human Visual Review remains required before Gold promotion.