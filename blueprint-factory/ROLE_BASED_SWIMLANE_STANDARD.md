# Gorilla HIS — Role-Based Swimlane Workflow Standard v1.0

Status: `FACTORY MASTER — HARD GATE`

## 1. Purpose
Define the mandatory form of Application Workflow diagrams used in Blueprint/Draft Application review. A role matrix or prose table is not a Swimlane Workflow.

## 2. Core Rule
A valid Swimlane must visualize responsibility and handoff:
`Start → Role Lane → Activity → Decision → Cross-Lane Handoff → System/Record → Alternate/Exception → End`.

**One lane represents one accountable actor/role/team or an explicitly automated system.**
Do not use columns merely as categories, statuses, modules, or narrative headings.

## 3. Mandatory Diagram Semantics
For every material multi-role workflow:
- show explicit Start and meaningful End;
- place each activity inside the lane of the actor who performs it;
- place each Decision in the lane of the role that has authority to decide;
- label material branches such as Yes/No, Approve/Return/Reject;
- draw cross-lane arrows for actual handoff/waiting responsibility;
- use the System lane only for automated system actions such as create transaction, update state/owner, create queue item, persist version, integration, notification, or audit;
- show Return/Reject/Cancel/Correction/Reversal/Reopen branches when material;
- show repeated/longitudinal cycles when material;
- keep transaction identity/context continuous across lanes.

## 4. Role vs System Separation
Human work must not be placed in the System lane.
System mutation must not be attributed to a human role when it is automatic.
If a human action triggers an automatic mutation, show both:
`Human Activity → System Mutation → Receiver Queue/Handoff`.

## 5. Swimlane Is Not a Table
The following do **not** satisfy this standard:
- a table with roles as columns and paragraphs in cells;
- a RACI/role matrix;
- a numbered workflow list;
- a state transition table;
- a sequence of screenshots;
- a diagram where arrows do not show responsibility transfer.

Those artifacts may support the Swimlane but cannot replace it.

## 6. Diagram Decomposition
Do not force a complex application into one unreadable diagram.
Use:
1. Main Flow Swimlane;
2. material Alternate/Exception Swimlane(s);
3. repeated/longitudinal Swimlane when relevant;
4. integration/financial subflow when it materially changes ownership or transaction state.

## 7. Blueprint Trace
Every material Swimlane activity/decision/handoff must trace to Blueprint IDs where applicable:
`AWF / FN / ST / WL / OBJ / SCN / AC`.
The diagram may remain human-readable, but the accompanying workflow table/narrative must provide the IDs.

## 8. Visual Quality Gate
PASS requires:
- lanes visibly separated and titled by role/system;
- chronological direction is obvious;
- process boxes do not cross lane boundaries;
- connectors do not run through unrelated process boxes;
- decision branches are readable and labelled;
- no ambiguous arrow direction;
- handoffs can be understood without reading a separate prose explanation;
- diagram remains readable at normal document zoom.

Any material violation = `FAIL — ROLE-BASED SWIMLANE`.

## 9. Draft Application Contract
For each material multi-role scenario, `Draft_Application_<Module>_TH.docx` must contain an actual rendered Role-Based Swimlane Diagram. A table-only representation is insufficient.

Recommended order:
`Application Workflow Diagram → Thai narrative → detailed workflow/decision table → Role Matrix`.

## 10. Final Rule
**Swimlane exists to answer “Who does what, who decides, and where does the work go next?” If the diagram cannot answer those questions visually, it is not a valid Gorilla HIS Swimlane.**
