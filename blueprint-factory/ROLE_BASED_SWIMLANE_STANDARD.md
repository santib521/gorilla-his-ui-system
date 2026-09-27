# Gorilla HIS — Role-Based Swimlane Workflow Standard v1.2

Status: `FACTORY MASTER — HARD GATE`

## 1. Purpose
Define the mandatory form of Application Workflow diagrams used in Blueprint/Draft Application review. A role matrix or prose table is not a Swimlane Workflow.

## 2. Core Rule
A valid Swimlane must visualize responsibility and handoff:
`Start → Role Lane → Activity → Decision → Cross-Lane Handoff → System/Record → Alternate/Exception → End`.

**One lane represents one accountable actor/role/team or an explicitly automated system.**
Do not use Worklist, Status, Module, Screen, or narrative category as a Role Lane.

## 3. Editable Master Rule — HARD GATE
The authoritative Swimlane embedded in `Draft_Application_<Module>_TH.docx` or English/Bilingual equivalent must be **editable**, not image-only.

Default hierarchy:
1. **Editable Word-native Swimlane** — preferred master. Use editable Word objects/cells/shapes/connectors so reviewers can change Role, Process, Decision and Handoff in Word.
2. Structured workflow source may be retained for deterministic regeneration.
3. PNG/SVG/PDF may be generated as preview/export only. It must not be the sole authoritative workflow artifact.

A PNG/JPG screenshot of a Swimlane by itself = `FAIL — IMAGE-ONLY SWIMLANE`.

An editable Word table is allowed **only when it behaves as a visual swimlane**: visible role lanes, chronological process steps, explicit decision/branch markers and handoff markers. A prose role matrix/table remains invalid.

## 4. Mandatory Diagram Semantics
For every material multi-role workflow:
- show explicit Start and meaningful End;
- place each activity inside the lane of the actor who performs it;
- place each Decision in the lane of the role that has authority to decide;
- label material branches such as Yes/No, Approve/Return/Reject;
- show actual cross-role handoff/waiting responsibility;
- use the System lane only for automated actions such as create transaction, update state/owner, create queue item, persist version, integration, notification, or audit;
- show Return/Reject/Cancel/Correction/Reversal/Reopen branches when material;
- show repeated/longitudinal cycles when material;
- keep transaction identity/context continuous across lanes.

## 5. Role vs System Separation
Human work must not be placed in the System lane.
System mutation must not be attributed to a human role when it is automatic.
If a human action triggers an automatic mutation, show:
`Human Activity → System Mutation → Receiver Queue/Handoff`.

## 6. What Does Not Count
The following do not satisfy this standard:
- role matrix / RACI table;
- table with roles as columns but only prose descriptions and no process/decision/handoff semantics;
- numbered workflow list;
- state transition table;
- screenshots;
- image-only Swimlane;
- diagram where arrows/markers do not show responsibility transfer.

Supporting tables may accompany the editable Swimlane but cannot replace it.

## 7. Diagram Decomposition
Do not force a complex application into one unreadable diagram. Split when needed:
1. Main Flow;
2. material Alternate/Exception flow(s);
3. repeated/longitudinal flow;
4. integration/financial subflow when ownership or transaction state materially changes.

A split diagram must preserve transaction continuity and cross-reference the parent workflow.

## 8. Blueprint Trace
Every material Swimlane activity/decision/handoff must trace to Blueprint IDs where applicable:
`AWF / FN / ST / WL / OBJ / SCN / AC`.
The diagram remains human-readable; the accompanying workflow detail provides IDs.

## 9. Language Rule
This standard applies equally to Thai, English and Bilingual deliverables.
- Thai document → Thai labels/process/decisions, except accepted domain/system terms.
- English document → English labels/process/decisions.
- Bilingual document → bilingual labels when requested.
The structural Gate is identical in every language.

## 10. Visual + Editability Quality Gate
PASS requires:
- lanes visibly separated and titled by role/system;
- chronological direction obvious;
- process/decision stays in responsible lane;
- branches readable and labelled;
- handoffs understandable without a separate prose explanation;
- readable at normal document zoom;
- reviewer can edit Role/Process/Decision/Handoff directly in the DOCX;
- image export, if present, is secondary.

Any material violation = `FAIL — ROLE-BASED SWIMLANE`.

## 11. Draft Application Contract
For each material multi-role scenario, the Draft Application must contain a **Word-native editable visual Role-Based Swimlane** plus narrative/detail as needed. The DOCX itself is canonical; companion formats cannot replace it.

Recommended order:
`Editable Application Workflow → Narrative → Detailed Workflow/Decision Table → Role Matrix`.

## 12. Final Rule
**Swimlane answers “Who does what, who decides, and where does the work go next?” The master must also be editable by the hospital/project team.**
