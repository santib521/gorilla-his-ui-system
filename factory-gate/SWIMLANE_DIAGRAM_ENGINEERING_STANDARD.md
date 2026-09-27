# Gorilla HIS — Swimlane Diagram Engineering & Review Standard v1.0

## 1. Purpose
This standard upgrades Factory workflow-diagram production from “place shapes and connect them” to professional cross-functional process modeling.

Reference baseline:
- OMG BPMN 2.0.2 semantics for Activities, Gateways, Sequence Flow, Pools/Lanes.
- Microsoft cross-functional flowchart principle: each process step belongs to the functional unit/role responsible for that step.
Hospital evidence and confirmed workflow remain authoritative for business truth.

## 2. Mandatory Agent Roles
Every material Swimlane must pass three distinct review roles. One role may not self-approve all three.

### A. Workflow Architect
Owns semantic correctness:
- identify actors/roles and lane ownership;
- define start/end, tasks, decisions, branches, loops, exceptions;
- define sender, receiver and receiving obligation for each handoff;
- ensure decision diamond belongs to the role with authority;
- prevent invented hospital workflow.

### B. Diagram Layout Engineer
Owns diagram geometry and visual routing:
- establish one dominant reading direction;
- align nodes to a grid;
- use orthogonal routing by default;
- connect shape boundary/connection points, never center-to-center through shapes;
- reserve routing corridors between nodes and lanes;
- minimize crossings, bends and long reverse paths;
- never route a connector through a process, decision, label, lane header or another label;
- place branch labels adjacent to their branch, not floating ambiguously;
- split a complex workflow into numbered continuation diagrams when clean routing cannot be achieved on one page.

### C. Independent Visual QA Reviewer
Owns rendered-artifact acceptance:
- inspect the rendered slide/page at normal review size;
- trace every path from Start to End without reading source code;
- verify no line crosses text or shapes;
- verify no ambiguous branch;
- verify lane ownership visually;
- verify connector arrow direction;
- compare against approved/reference quality;
- reject visual clutter even if semantics are technically correct.

## 3. Diagram Grammar — HARD RULES
1. Lane = real actor/role or truly automated system.
2. Task = rounded rectangle.
3. Decision/Gateway = diamond.
4. Every decision has >=2 explicitly labeled outgoing branches.
5. Sequence/Handoff connector has one source and one target.
6. Flow may cross lane boundaries when responsibility changes.
7. System lane contains automatic system actions only.
8. Worklist/Status/Screen/Module are not role lanes.
9. Use a consistent primary direction (top→bottom or left→right) within one diagram.
10. Return/rework loops must be visibly routed around the outside of the main flow, not through it.

## 4. Connector Routing Gate — ZERO-TOLERANCE
A diagram FAILS if any connector:
- passes through any shape;
- passes through text or a branch label;
- begins/ends in the visual center of another unrelated object;
- creates an unexplained diagonal across multiple lanes;
- overlaps another connector for a meaningful distance;
- has an ambiguous arrow direction;
- uses a long cross-page route when the workflow should be split;
- forces the reader to guess which branch it belongs to.

Default routing order:
1. same lane: vertical straight connector;
2. adjacent lane handoff: short horizontal orthogonal connector;
3. non-adjacent lane handoff: dedicated horizontal routing corridor;
4. return loop: outside-edge corridor;
5. if routing still crosses objects: split diagram.

## 5. Complexity Budget
Per diagram:
- target <= 12 task/decision nodes;
- target <= 4 lanes; 5 allowed only when still readable;
- target <= 3 decision gateways;
- zero connector/shape collisions;
- zero connector/text collisions;
- zero ambiguous crossings.
Exceeding the target does not automatically fail, but requires the Layout Engineer to justify why splitting would reduce comprehension.

## 6. Two-Pass Construction
### Pass 1 — Semantic Skeleton
Produce a text/structured flow first:
ID | Role | Type | Activity | Next | Branch label | Handoff receiver.
Workflow Architect signs off semantics before visual layout.

### Pass 2 — Geometry
Layout Engineer places lanes/nodes, then routes connectors. Do not auto-connect center-to-center and “fix later”.

## 7. Render-First QA
Source inspection is insufficient.
Required evidence:
- render every slide/page;
- inspect at 100% and fit-to-page;
- trace all Start→End/Return paths;
- record PASS/FAIL for collision, crossing, label clarity, branch clarity, role ownership, visual hierarchy;
- any FAIL blocks delivery.

## 8. Human Veto / Learning Rule
Explicit human feedback that a diagram is confusing, childish, visually broken, or below the approved reference is a hard FAIL.
The rejected artifact must be retained as a negative example and its failure pattern added to the Factory checklist.
Do not make small cosmetic edits to a structurally rejected layout; return to Semantic Skeleton / Geometry pass as appropriate.

## 9. Deliverable Rule
Editable PPTX may be used as the Swimlane master when explicitly accepted for the project.
All shapes, diamonds, labels and connectors must remain editable.
A raster screenshot may be used only for preview, never as the editable master.

## 10. Acceptance Checklist
- [ ] roles are real actors/systems
- [ ] each activity is inside responsible lane
- [ ] decision authority is correct
- [ ] each decision branch is labeled
- [ ] dominant reading direction is obvious
- [ ] connectors attach at shape boundaries
- [ ] no connector crosses a shape
- [ ] no connector crosses text
- [ ] no unexplained diagonal multi-lane connector
- [ ] return loops use outside corridor
- [ ] Start→End trace is unambiguous
- [ ] rendered artifact visually inspected
- [ ] independent visual reviewer PASS
- [ ] human veto resolved
