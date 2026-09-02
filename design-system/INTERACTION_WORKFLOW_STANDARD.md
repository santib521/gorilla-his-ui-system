# Gorilla HIS — Interaction Completeness, Hospital Realism, Scenario Branch & Role Swimlane Standard v1.1

This standard is binding for every interactive Gorilla HIS mockup.

## 1. Purpose
A mockup is not complete merely because it renders. It must behave like a coherent hospital application, communicate scenario branches and cross-role workflow, and be suitable for realistic hospital review without looking like an AI prototype.

Core rule:

`Business Truth → Scenario Branch Model → Role/Handoff Model → Working Interaction → Premium Clinical Composition → QA Evidence`

## 2. Reference Baseline Rule
When the user supplies an existing mockup, screenshot, HTML candidate or explicit visual benchmark, treat it as a **minimum benchmark**, not as optional inspiration.

Before rebuilding, record:
- what the reference does well;
- what interaction depth must be preserved;
- what visual/UX weaknesses must be materially improved;
- what must not regress.

The new candidate must be materially better in at least three dimensions: workflow clarity, interaction completeness, decision hierarchy, component finish, information density/scanability, role/handoff visibility, product continuity, hospital-facing realism.

A candidate that is only visually different/cleaner/recolored but loses interaction depth = FAIL.

## 3. Interaction Completeness Gate — Mandatory
Every primary interactive control visible in the main workflow must have observable behavior.

Includes when present: primary/secondary navigation; worklist open; tabs; search/filter/sort; workflow buttons; modal/drawer open-close-confirm-cancel; status actions; add/edit/save/cancel/reverse; upload/select/lookup; role switch/permission; dashboard drill-down.

Observable behavior means at least one of:
- navigate to another screen/workspace;
- open populated modal/drawer;
- mutate visible local state/data;
- filter/search/sort visible data;
- add/update/remove visible row/object;
- change workflow state with visible feedback;
- enforce validation/disabled/permission behavior;
- display intended detail/result context.

A toast without visible state/workflow evidence is insufficient for a material workflow action.

### Dead-Control Hard Reject
FAIL when visible primary menu, main-workflow tab or primary workflow button has no meaningful behavior, modal confirm/cancel fails, or action claims success without represented state change where expected.

## 4. Scenario Branch Completeness — Mandatory
When File 1 Blueprint defines materially distinct in-scope scenarios, each scenario is a separate Main Workflow test path.

Examples of material difference:
- different entry trigger or starting actor;
- different primary identifier/context (e.g. existing HN vs no HN);
- different source-of-truth relationship;
- different custody/authorization/handoff;
- different end state/output;
- different access or legal/operational boundary.

### Scenario Requirements
For every in-scope scenario:
1. the worklist/intake must let the reviewer select/create a representative case;
2. scenario identity/context must remain visible during the workflow;
3. all required stages must be reachable without manually editing source code;
4. scenario-specific fields/steps/exceptions must actually differ where Blueprint says they differ;
5. the path must reach a meaningful end state/output;
6. state changes must be observable;
7. the Smoke Test must execute the scenario separately.

A single generic case with labels changed to imitate multiple scenarios = FAIL.

If Scenario A requires HN linkage and Scenario B explicitly may have no HN, both must be exercised as distinct paths rather than one case with a cosmetic HN value.

## 5. Mandatory Interaction Inventory
Before Post-Build PASS create:

| Control ID / Label | Type | Scenario | Screen / Role | Expected Behavior | Observable Result | Test Result |
|---|---|---|---|---|---|---|

Every visible primary menu and Main Workflow control must appear.

## 6. Mandatory Functional Smoke Test
Run the mockup, not only static source inspection.

Minimum test:
1. click every primary navigation item;
2. click every main-workflow tab;
3. open/close every modal/drawer family;
4. execute at least one valid save/add/update for each major stage;
5. exercise at least one validation/permission/error path when relevant;
6. verify visible state/data changes after material actions;
7. verify no workflow-breaking console error;
8. verify search/filter if present;
9. verify context preservation where workflow relies on it;
10. **execute every Blueprint scenario marked `Smoke Test Required = Yes` end-to-end**;
11. verify each tested branch demonstrates its actual scenario-specific difference, not merely a different label.

If runtime/browser execution is blocked, candidate cannot claim Functional Smoke Test PASS.

## 7. Hospital-Facing Realism Rule
Rendered product surface should look like intended application, not Factory documentation.

Do not show normal hospital-facing UI labels such as Demo/Discovery Mockup/Prototype, WA/GAP/TBD/CR/HSR identifiers, AI/internal QA text, or “simulation” wording used only for Factory limitations unless user explicitly requests them.

Keep governance truth in Blueprint, Gap Analysis, Design Notes, START_HERE and QA/Post-Build evidence.

When unresolved rule must be visible for safety, use realistic product language such as `รอการยืนยันสิทธิ์`, `รอตรวจทาน`, `ยังไม่อนุมัติ`, `ข้อมูลไม่ครบ`, while preserving governance classification in supporting docs.

## 8. Role-Based Swimlane Workflow — Mandatory When Applicable
When workflow has 3+ meaningful roles or repeated cross-role handoffs/approvals, include a Role-Based Swimlane view.

Lane rules:
- one lane per meaningful hospital role/team;
- chronological steps;
- visible cross-lane handoffs;
- current case position/status;
- obvious next-action ownership;
- exceptions/returns as secondary branches where useful;
- no decorative BPMN complexity.

For multi-scenario modules, Swimlane must either:
- switch between scenarios, or
- clearly show scenario-specific entry/branch paths.

A single swimlane that hides a materially different entry scenario = incomplete workflow communication.

## 9. Role Consistency Rule
Role labels in Swimlane, permission behavior, worklists and action ownership must agree. If lane owner and executable role conflict without explanation, FAIL.

## 10. Premium Interaction Craft Rule
Premium is not larger cards/more whitespace.

Require precise primary/secondary/quiet/destructive hierarchy; integrated hover/focus/pressed/selected states; compact comfortable targets; contextual action placement; causal state feedback; no default-browser-looking controls; no generic SaaS card-grid grammar; no decorative empty zones reducing hospital working area.

## 11. Benchmark Delta Evidence
When reference candidate exists:

| Dimension | Reference Baseline | New Candidate | Better / Same / Worse | Evidence |
|---|---|---|---|---|

Any `Worse` in Main Workflow interaction, scenario coverage, role clarity or hospital-facing realism = RETURN TO BUILDER.

## 12. Angular Mapping
Typical mapping:
- scenario selector/worklist → Angular state/router + Material/CDK list/table;
- role swimlane → authored Angular component using CSS grid/flex + CDK accessibility;
- tabs → MatTabs;
- dialogs → MatDialog;
- drawers → MatSidenav/CDK Overlay;
- state feedback → MatSnackBar or inline state region;
- permission/disabled → authorization state + Material/CDK accessible disabled behavior.

## 13. QA Decision
A mockup cannot be `Candidate — Ready for Human Visual Review` when:
- primary navigation/menu/tab is dead;
- role workflow cannot be explained end-to-end;
- an in-scope material scenario branch cannot be played end-to-end;
- two distinct scenarios are represented only by cosmetic text changes.

The target is both: **scenario-complete operational review + purpose-built premium Gorilla HIS craft**.