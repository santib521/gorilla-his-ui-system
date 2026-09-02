# Gorilla HIS — Interaction Completeness, Hospital Realism, Scenario Branch & Role Swimlane Standard v1.2

This standard is binding for every interactive Gorilla HIS mockup.

## 1. Purpose
A mockup is not complete merely because it renders. It must behave like a coherent hospital application, communicate scenario branches and cross-role workflow, and be suitable for realistic hospital review without looking like an AI prototype.

Core rule:
`Business Truth → Scenario Branch Model → Role/Handoff Model → Working Interaction → Premium Clinical Composition → QA Evidence`

## 2. Reference Baseline Rule
User-supplied existing mockup/screenshot/HTML is a minimum benchmark. Record what works, interaction depth to preserve, UX weaknesses to improve and no-regression points.

New candidate must be materially better in at least three dimensions: workflow clarity, interaction completeness, decision hierarchy, component finish, information density/scanability, role/handoff visibility, product continuity, hospital-facing realism.

## 3. Interaction Completeness Gate
Every primary interactive control in Main Workflow must have observable behavior: navigation, worklist open, tabs, search/filter/sort, workflow buttons, modal/drawer, state actions, add/edit/save/cancel/reverse, upload/select/lookup, role switch/permission, KPI drill-down when actionable.

Observable result = navigation, populated overlay, visible state/data mutation, filter/sort, object add/update/remove, workflow state change, validation/permission behavior, or intended detail/result.

Toast-only success without visible material state change is insufficient.

### Dead-Control Hard Reject
Visible primary menu/tab/button with no meaningful behavior, broken confirm/cancel, or fake success without represented state change = FAIL.

## 4. Scenario Branch Completeness
Each materially distinct in-scope Blueprint scenario is a separate Main Workflow test path.

Material differences include entry trigger, starting actor, primary identifier/context, source-of-truth, custody/authorization/handoff, end state/output, access/legal boundary.

For each in-scope scenario:
1. reviewer can select/create representative case;
2. scenario context remains visible;
3. all required stages reachable without editing source;
4. scenario-specific steps/fields actually differ;
5. path reaches meaningful end state;
6. state changes observable;
7. Smoke Test executes scenario separately.

One generic case with label changes = FAIL.

## 5. Forensic Lifecycle Interaction Coverage — Mandatory when Forensic Blueprint activates FLC
For Forensic/Mortuary/Forensic OPD, UI Factory must make the Blueprint lifecycle decisions reviewable, not hide them in documentation.

When relevant to the Blueprint, the mockup must visibly support:

### FUI-01 Living vs Deceased
- separate deceased case and living Forensic OPD pathways;
- no shared tab structure that falsely implies identical record context.

### FUI-02 Request Source
- intake shows who requested/referred the case and request source/type;
- internal and external request paths must differ when Blueprint says they differ.

### FUI-03 Accept / Reject / Return
- request intake has working Accept and, where Blueprint marks relevant, Reject/Return-for-information actions;
- Reject/Return requires reason and creates visible status/audit evidence.

### FUI-04 AF / HN / VN Context
- External body can remain AF-only before hospital identity/encounter policy is resolved;
- historical HN lookup/link must be separate from creation of a new HN/VN/Encounter;
- living Forensic OPD must show HN/VN/Encounter context.

### FUI-05 HN Link Governance
- when Blueprint marks HN-link approval/review as relevant, mockup must show Match Candidate → Review/Approve/Reject Link or equivalent governance;
- link action must update visible case context and history;
- unlink/correction path represented when required by Blueprint.

### FUI-06 Physician Assignment / Duty Roster
- request can be assigned to responsible forensic physician from duty/exam roster or equivalent operational ownership model when relevant;
- unavailable/substitute path should be reviewable if Blueprint requires it.

### FUI-07 Diagnostic Order Context
- order action must show required identifier context before sending;
- if AF-only case lacks required HN/VN/Encounter, order is blocked or routes through the defined create/link encounter step;
- do not allow a fake successful AF-only Lab/Radiology order when Blueprint says downstream context is unresolved/required.

### FUI-08 Finance
- chargeable vs non-charge cost visible;
- scenario/payer/billing context visible where relevant;
- add/change/cancel/reverse must mutate visible financial state where represented.

### FUI-09 Sensitive Identity / Name Masking
- sensitive living forensic case worklist supports masked display when Blueprint requires it;
- authorized role may reveal full identity through controlled interaction;
- unauthorized role remains masked/restricted;
- print/export/photo access follows role behavior represented by Blueprint.

## 6. Mandatory Interaction Inventory
Create:
| Control ID / Label | Type | Scenario | Screen / Role | Expected Behavior | Observable Result | Test Result |

Every primary menu/Main Workflow control appears.

## 7. Mandatory Functional Smoke Test
Run browser/runtime, not static source only.

Minimum:
1. click every primary nav;
2. every main tab;
3. every modal/drawer family;
4. valid save/add/update per major stage;
5. one validation/permission/error path when relevant;
6. visible state/data change after material action;
7. no workflow-breaking console error;
8. search/filter;
9. context preservation;
10. every Blueprint scenario with Smoke Test Required=Yes end-to-end;
11. each branch demonstrates actual difference, not label-only;
12. Forensic FLC/FUI controls required by Blueprint are exercised, including Accept/Reject/Return, HN-link governance, order-context blocking/enabling, finance path and sensitive-name permission where applicable.

If runtime execution blocked, cannot claim Functional Smoke Test PASS.

## 8. Hospital-Facing Realism
Do not expose Demo/Prototype/WA/GAP/TBD/CR/HSR/AI/internal QA language in normal hospital-facing UI unless explicitly requested. Use realistic states such as รอข้อมูลเพิ่มเติม, ไม่รับคำขอ, รออนุมัติเชื่อม HN, รอเปิด Visit, จำกัดสิทธิ์.

Governance truth stays in Blueprint/Gap/Design Notes/QA.

## 9. Role-Based Swimlane
When 3+ meaningful roles or repeated handoffs exist, include Role Swimlane.

One lane per role/team; chronological steps; cross-lane handoffs; current case position; next-action ownership; exceptions/returns as useful.

For multi-scenario modules, Swimlane must switch scenario or clearly show distinct branch entry. A single swimlane hiding material scenario difference = incomplete.

For forensic flows, requester/intake, forensic physician, diagnostic service, mortuary, finance when material, and recipient handoffs should appear only when relevant to the selected scenario.

## 10. Role Consistency
Swimlane role, permission behavior, worklist ownership and executable actions must agree.

## 11. Premium Interaction Craft
Premium = precise hierarchy, deliberate control states, compact comfortable targets, contextual actions, causal state feedback, no browser-default controls, no generic SaaS card-grid grammar, no decorative dead space.

## 12. Benchmark Delta
Any Worse in Main Workflow interaction, scenario coverage, role clarity or hospital-facing realism = RETURN TO BUILDER.

## 13. Angular Mapping
- scenario/worklist → Angular state/router + Material/CDK table/list
- swimlane → authored Angular component + CDK accessibility
- tabs → MatTabs
- dialogs → MatDialog
- overlays → MatSidenav/CDK Overlay
- state feedback → MatSnackBar/inline region
- permissions → authorization state + accessible disabled behavior

## 14. QA Decision
Cannot be Candidate — Ready for Human Visual Review when primary navigation/menu/tab dead, role flow unclear, in-scope scenario unplayable, distinct scenarios are cosmetic-only, or required Forensic Lifecycle interaction is absent.

Target: **scenario-complete operational review + purpose-built premium Gorilla HIS craft**.