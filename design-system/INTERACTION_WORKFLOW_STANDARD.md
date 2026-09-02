# Gorilla HIS — Interaction Completeness, Hospital Realism & Role Swimlane Standard v1.0

This standard is binding for every interactive Gorilla HIS mockup.

## 1. Purpose
A mockup is not complete merely because it renders. It must behave like a coherent hospital application, communicate cross-role workflow, and be suitable for realistic hospital review without looking like an AI prototype.

Core rule:

`Business Truth → Role/Handoff Model → Working Interaction → Premium Clinical Composition → QA Evidence`

## 2. Reference Baseline Rule
When the user supplies an existing mockup, screenshot, HTML candidate or explicit visual benchmark, treat it as a **minimum benchmark**, not as optional inspiration.

Before rebuilding, record:
- what the reference does well;
- what interaction depth must be preserved;
- what visual/UX weaknesses must be materially improved;
- what must not regress.

The new candidate must be materially better in at least three of these dimensions:
1. workflow clarity;
2. interaction completeness;
3. decision hierarchy;
4. component/control finish;
5. information density and scanability;
6. role/handoff visibility;
7. product continuity;
8. hospital-facing realism.

A candidate that is only visually different, cleaner, more spacious, or recolored but loses interaction depth = FAIL.

## 3. Interaction Completeness Gate — Mandatory
Every primary interactive control visible in the main workflow must have observable behavior.

This includes, when present:
- primary navigation menu;
- secondary module navigation;
- worklist row/open action;
- tabs;
- search/filter/sort controls;
- primary and secondary workflow buttons;
- modal/drawer open/close/confirm/cancel;
- status/state-changing actions;
- add/edit/save/cancel/reverse interactions;
- upload/select/lookup actions represented in the mockup;
- role switch / permission behavior when present;
- dashboard drill-down where a KPI is presented as actionable.

Observable behavior means at least one of:
- navigate to another screen/workspace;
- open a populated modal/drawer;
- mutate visible local state/data;
- filter/search/sort visible data;
- add/update/remove a visible row/object;
- change workflow state with visible feedback;
- enforce validation/disabled/permission behavior;
- display the intended detail/result context.

A toast that says an action happened while no state or workflow evidence changes is not sufficient for a material workflow action.

### Dead-Control Hard Reject
FAIL immediately when:
- a visible primary menu does nothing;
- a main-workflow tab has no meaningful content;
- a primary workflow button has no behavior;
- modal confirm/cancel does not work;
- action claims success but the represented data/state does not change where a state change is expected.

## 4. Mandatory Interaction Inventory
Before Post-Build PASS, create an inventory:

| Control ID / Label | Type | Screen / Role | Expected Behavior | Observable Result | Test Result |
|---|---|---|---|---|---|

Every visible primary menu and every Main Workflow control must appear in this inventory.

## 5. Mandatory Functional Smoke Test
Run the mockup, not only static source inspection.

Minimum test:
1. click every primary navigation item at least once;
2. click every main-workflow tab at least once;
3. open and close every modal/drawer family at least once;
4. execute at least one valid save/add/update action for each major workflow stage;
5. exercise at least one validation/permission/error path when relevant;
6. verify visible state/data changes after material actions;
7. verify no workflow-breaking console error;
8. verify search/filter if present;
9. verify back/context preservation where the workflow relies on it.

If runtime/browser execution is blocked, the candidate cannot claim Functional Smoke Test PASS. Record the limitation and keep status below QA Passed.

## 6. Hospital-Facing Realism Rule
The rendered product surface used for hospital review should look like the intended application, not like Factory documentation.

Do not show these governance labels in normal hospital-facing UI unless the user explicitly asks for them:
- Demo / Discovery Mockup / Prototype;
- WA / Working Assumption;
- GAP / TBD / CR / HSR identifiers;
- AI-generated / AI note;
- internal Factory QA text;
- “simulation” wording used only to explain Factory limitations.

Keep governance truth in:
- Blueprint;
- Gap Analysis;
- Design Notes;
- START_HERE;
- QA/Post-Build evidence.

When an unresolved rule must be visible for safety, express it as realistic product language such as `รอการยืนยันสิทธิ์`, `รอตรวจทาน`, `ยังไม่อนุมัติ`, `ข้อมูลไม่ครบ`, or a disabled state — while preserving the real governance classification in supporting documents.

## 7. Role-Based Swimlane Workflow — Mandatory When Applicable
When the workflow has **3 or more meaningful roles**, or has repeated handoffs/approvals across roles, include a Role-Based Swimlane view in the mockup or a directly accessible workflow view.

### Lane Rules
- one lane per meaningful role/team;
- lane labels use hospital roles, not system components;
- steps appear in chronological order;
- handoffs visibly cross lane boundaries;
- current case position/status is distinguishable;
- ownership of the next action is obvious;
- exceptions/returns may be shown as secondary branches;
- avoid decorative BPMN complexity unless required.

### Recommended Swimlane Contents
For each step show only what helps hospital review:
- action;
- responsible role;
- input/context;
- resulting record/state;
- next handoff.

The Swimlane is a workflow-communication instrument, not a decorative process diagram.

## 8. Role Consistency Rule
Role labels used in Swimlane, permission behavior, worklists and action ownership must be consistent.

If an action is shown in one role lane but executable by a different role in the mockup without explanation, FAIL role consistency.

## 9. Premium Interaction Craft Rule
Premium is not achieved by larger cards or more whitespace.

For interactive controls, require:
- precise visual hierarchy between primary/secondary/quiet/destructive actions;
- integrated selected/hover/focus/pressed states;
- compact but comfortable hit targets;
- contextual actions located where the decision is made;
- state changes that feel causal and immediate;
- no browser-default-looking controls;
- no generic SaaS card grid as the main grammar;
- no large decorative empty zones that reduce hospital working area.

## 10. Benchmark Delta Evidence
When a reference candidate exists, Post-Build must include:

| Dimension | Reference Baseline | New Candidate | Better / Same / Worse | Evidence |
|---|---|---|---|---|

Any `Worse` result in Main Workflow interaction, role clarity, or hospital-facing realism = RETURN TO BUILDER.

## 11. Angular Mapping
Role Swimlane and interactive controls must still have a feasible Angular 22 path.

Typical mapping:
- role swimlane → authored Angular component using CSS grid/flex + CDK accessibility; no special external diagram library required unless justified;
- tabs → MatTabs;
- dialogs → MatDialog;
- drawers → MatSidenav/CDK Overlay;
- worklists → Material/CDK table/list as appropriate;
- state feedback → MatSnackBar or inline state region;
- permission/disabled state → Angular authorization state + Material/CDK accessible disabled behavior.

## 12. QA Decision
A mockup cannot be `Candidate — Ready for Human Visual Review` when any primary navigation/menu/tab is dead or when the role-based workflow cannot be explained end-to-end.

A visually attractive but functionally shallow mockup = FAIL.
A functionally rich but generic/AI-looking mockup = FAIL.
The target is both: **operationally complete enough for review + purpose-built premium Gorilla HIS craft**.