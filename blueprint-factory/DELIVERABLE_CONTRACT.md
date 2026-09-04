# Gorilla HIS — Prompt 1+2 Deliverable Contract v1.2

Status: `FACTORY MASTER`

## Purpose
Make requirement discovery, documents, design knowledge and operational mockup one traceable product rather than independent outputs.

Core:
`Project Session → Expert Workshop/Challenge → Shared Application Model → Executable Blueprint TXT → Compiled Design Knowledge → Operational UX Contract → Review DOCX → Expert DOCX → Primary Render Gate → index.html → Traceability + Runtime + Design Evidence`.

## Canonical Deliverables
1. `Application_Blueprint_<Module>.txt` — direct business/UI behavior authority.
2. `Draft_Application_<Module>_TH.docx` — Thai hospital review document.
3. `Expert_Suggestion_<Module>_TH.docx` — Thai independent expert recommendation/concern/question document.
4. `index.html` — playable mockup derived from #1 and constrained by approved design knowledge.

These four remain canonical. The following **mandatory QA/design evidence artifacts** support the build and gates and do not replace the four:
- `Compiled_Design_Knowledge_<Module>.md`
- `Operational_UX_Contract_<Module>.md`
- `Benchmark_Strength_Contract_<Module>.md` when Benchmark Mode applies, or equivalent `BM-*` section in compiled knowledge
- Primary Workspace Render/Comparison evidence
- Blueprint↔HTML Traceability
- Workflow Fidelity Test
- Runtime Functional Test
- Independent Premium/Benchmark Design Review

## Single Shared Model Rule
All deliverables derive from the same workflow/transaction/state/work-obligation/role/function model. Do not separately reinterpret raw requirements for DOCX and HTML.

Design artifacts do not invent business truth. They compile how approved knowledge and benchmark strengths should shape the presentation and interaction of the Blueprint-defined work.

## 1. Application Blueprint TXT — EXECUTABLE UI CONTRACT
Must be deterministic enough that another UI Factory Agent can build behavior without rereading raw requirement or guessing.

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

## 2. Compiled Design Knowledge — DESIGN CONSTRAINT CONTRACT
Follow `design-system/KNOWLEDGE_TO_DESIGN_COMPILATION_STANDARD.md`.

Purpose: prove that applicable Gorilla/Claude knowledge, Visual DNA, Gold/benchmark evidence and approved patterns are transformed into actionable build constraints.

Minimum trace:
`KD/BM ID | Source | Applicable Rule/Strength | Design Consequence | Required UI Evidence | Verification`.

Reading/summarizing knowledge alone does not satisfy this artifact.

## 3. Operational UX Contract — WORKSPACE CONTRACT
Follow `design-system/OPERATIONAL_UX_CONTRACT_STANDARD.md`.

For each material Work Obligation define:
`User Job → Decision Question → Primary Evidence → Attention/Exception → Primary Action → Mutation → Handoff → First Viewport → Dominant Work Surface → Supporting Surfaces`.

This contract bridges Blueprint behavior to non-generic product composition.

## 4. Draft Application DOCX — HOSPITAL REVIEW
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

## 5. Expert Suggestion DOCX — INDEPENDENT EXPERT REVIEW
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

## 6. Primary Workspace Render Evidence — PRE-FULL-BUILD GATE
Follow `factory-gate/PRIMARY_WORKSPACE_RENDER_GATE.md`.

Before full/secondary build, prove the most important recurring operational workspace against applicable KD/BM constraints and Human-approved quality floor.

If failed:
`STOP → REDESIGN → RENDER AGAIN`.

Do not build the full candidate first and discover at the end that the composition is weak.

## 7. index.html — PLAYABLE OPERATIONAL MOCKUP
Built from Blueprint behavior and constrained by Compiled Design Knowledge + Operational UX Contract.

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
- material professional workspaces meet UX Contract depth;
- no Demo/Factory/TBD/Workshop labels in normal hospital-facing UI.

## Expert Applicability Rule
Use a broad expert pool, but deliverables include only relevant activated domains. HA/JCI/ISO27001/HIPAA/etc. do not generate content merely because they exist.

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

## Design Evidence Gate
Must prove:
- critical KD coverage;
- BM preservation/improvement when Benchmark Mode applies;
- Operational UX Contract coverage;
- Primary Workspace Render PASS;
- generic-template rejection;
- professional workspace depth;
- independent design challenge;
- Human review status.

A prose QA file without executed/rendered evidence cannot declare PASS.

## Truth Separation
Hospital evidence remains distinct from:
`REFERENCE BASELINE / STANDARD RECOMMENDATION / EXPERT RECOMMENDATION / COMPLIANCE RECOMMENDATION / WORKING ASSUMPTION / TBD`.

## Delivery Gate
`Blueprint Completeness PASS → DOCX Consistency PASS → Knowledge Compilation PASS → Operational UX Contract PASS → Primary Workspace Render PASS → Blueprint/HTML Traceability PASS → Workflow Fidelity PASS → Function PASS → Runtime PASS → Independent Design/Benchmark PASS`.

Human Visual Review remains required before Gold promotion.