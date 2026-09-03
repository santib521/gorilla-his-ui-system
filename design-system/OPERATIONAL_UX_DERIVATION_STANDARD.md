# Gorilla HIS — Operational UX Derivation Standard v1.0

Status: `UNIVERSAL UX FACTORY MASTER`

Applies to **EVERY Gorilla HIS module**.

## 1. Core Principle
The Factory must never translate Requirement directly into Screens.

Mandatory derivation:

`Hospital Actual Workflow → User Work Obligation → Operational Capability → Workspace/Work Surface → Transaction/State → Primary Action → Information Needed for Decision → Interaction Pattern → Screen Composition`

A BA/SA is expected to derive obvious operational capabilities from a confirmed workflow without asking the hospital to specify every screen.

Example principle: if confirmed flow says work arrives, is received, assessed, verified, handed off and followed up, the Factory should derive queue/worklist, accept/assign, assessment workspace, verification, handoff state and follow-up workspace. The hospital should be asked about policy/authority/business rules — not whether an obvious operational surface is needed.

## 2. BA/SA Derivation Boundary
The Factory MAY derive as `EXPERT APPLICATION DERIVATION`:
- worklist/queue when work arrives asynchronously;
- create/new transaction surface when users initiate work;
- accept/assign/claim ownership when work must be received;
- assessment workspace when professional assessment is required;
- review/verify surface before material handoff/approval;
- approval inbox/work queue when another authority decides;
- follow-up/longitudinal workspace when work repeats;
- history/timeline/version view when prior events affect current work;
- closure/outstanding-work check when a case must end;
- search/filter/sort when operational volume makes retrieval material;
- next-action/status/owner visibility when lifecycle drives work.

The Factory MUST NOT silently derive as Hospital Truth:
- who has authority;
- approval threshold;
- SLA/escalation time;
- formula/score cut-off;
- legal/local policy;
- exact permission;
- source-of-truth ownership when not evidenced;
- financial posting/reversal rule;
- clinical decision rule.

Those remain Recommendation / Hospital Decision Required / TBD as appropriate.

## 3. Operational Capability Derivation Matrix — Mandatory
Before UI composition create:

`Workflow Event | User Goal | Work Obligation | Required Capability | Required Data | Primary Action | State Mutation | Handoff/Next Owner | UI Pattern Candidate | Evidence/Derivation Status`

Every material workflow event must map to an operable capability or be explicitly N/A/out-of-scope.

## 4. Workspace Derivation Rules
Derive the work surface from the nature of work, not from component availability.

Common patterns are candidates, never prescriptions:
- incoming asynchronous work → Worklist/Queue;
- time/resource allocation → Schedule/Planner/Resource Board;
- high-acuity monitoring → Acuity/Status Board;
- repeated task execution → Work Queue + Task Workspace;
- inventory movement → Stock/Transaction Ledger + Action Workspace;
- longitudinal patient/case management → Case Workspace + Timeline;
- approval → Approval Inbox + Decision Workspace;
- high-volume result review → Dense Result Worklist + Detail Inspector.

Do not force every module into Dashboard, Cards, Table, Kanban or Sidebar templates.

## 5. Worklist / Queue Derivation Gate
If work arrives for a team/user and must be triaged, accepted, assigned, prioritized, progressed or handed off, a work-management surface is normally required.

The Factory must derive and challenge:
- All Work / My Work / Unassigned where relevant;
- transaction type;
- patient/case/task identity;
- reason/request/service summary;
- source/requester;
- priority/urgency when applicable;
- current state;
- owner;
- received/age/due information when material;
- quantity/progression when relevant;
- **Next Action**;
- search/filter/sort appropriate to expected volume.

Do not ask a broad question such as “Do you need a Worklist?” when the confirmed workflow clearly creates queued work. Ask only unresolved policy/details.

## 6. New Transaction Derivation
If workflow starts with a user creating Consult/Request/Order/Referral/etc., provide a real entry surface with the minimum baseline needed to create the transaction.

Baseline must be derived from evidence and downstream needs. If downstream decisions depend on service/procedure, quantity, price estimate, patient context or requester, those belong in entry or must have an explicit later capture point.

## 7. Receive / Assign / Ownership
If flow says receive/accept/assign, UI must support that action and visibly mutate owner, received time, state and next action. A row opening without ownership mutation is not Receive.

## 8. Assessment / Scoring Workspace
When flow requires assessment/scoring/classification:
- give it a dedicated work surface proportionate to the task;
- show prior relevant evidence without forcing recall;
- calculate/preview derived score transparently;
- show resulting group/classification;
- preserve assessment version/history;
- separate professional narrative from score controls when useful;
- expose validation before completion.

A tiny textarea inside a generic detail page is not an adequate professional assessment workspace when assessment is a core transaction stage.

## 9. Verify Before Handoff
When a material decision is sent to another role, derive a Verify/Review step when completeness/accuracy materially matters.

Review surface should summarize what the receiver will decide from: request, key evidence, assessment, score, financial/quantity context and unresolved warnings. The primary action must clearly state the handoff.

Do not invent an approval policy; derive the review capability and ask only who/what rule governs approval.

## 10. Follow-up / Longitudinal Work
If the patient/case returns repeatedly, derive a longitudinal work surface. It must answer:
- what was authorized/planned;
- what happened previously;
- what is due now;
- what changed since last time;
- what must be reassessed;
- used/completed vs remaining;
- what event can happen between visits;
- when work is complete/off/closed.

Repeated workflow cannot be represented as reopening the same form and overwriting old values.

## 11. UX Decision Architecture
For every primary workspace define:

`User Goal → Decision Question → Primary Evidence → Exception/Attention → Primary Action → Secondary Action → Detail on Demand`

Within 5 seconds an experienced user should know:
1. where they are;
2. what work needs attention;
3. what state/owner it is in;
4. what they should do next;
5. what evidence supports that action.

## 12. Cognitive UX Laws — Applied, Not Decorative
Use established interaction principles as operational rules:
- **Jakob / familiarity:** preserve familiar HIS/work-domain mental models unless there is a measurable reason to change;
- **Hick:** reduce simultaneous choices; stage actions by lifecycle and priority;
- **Fitts:** primary/high-frequency actions must be easy to acquire and near the object they affect;
- **Miller / cognitive load:** chunk complex information; use progressive disclosure; do not make users memorize prior-state data;
- **Proximity:** related evidence/action stays together;
- **Similarity:** consistent visual grammar for same semantic role; do not make different actions look identical;
- **Aesthetic-usability:** visual polish supports trust/readability but never hides workflow weakness;
- **Peak-End:** critical completion/handoff/closure must provide clear confidence and meaningful end-state feedback.

These principles do not justify copying a reference UI.

## 13. Recognition over Recall
Operational UI should surface prior values, last assessment, status, owner, pending action, quantity remaining and relevant context when the user needs them. Do not require memory or navigation across unrelated screens to reconstruct the case.

## 14. Pattern Selection Test
Before choosing Table/Card/Kanban/Schedule/Board/Timeline/Inspector answer:
- What does the user scan?
- What do they compare?
- What do they decide?
- What is high-frequency?
- What is urgent?
- What must remain visible while acting?
- What volume is expected?
- What changes after the action?

Pattern chosen without these answers = Pre-Build FAIL.

## 15. Hard Gate
A mockup FAILS Operational UX when any material workflow stage has no usable work surface/action, including:
- queued work but no operable queue/worklist;
- create flow but no real entry;
- receive/assign flow but no ownership action;
- assessment but no adequate assessment workspace;
- handoff/approval but no review/verify and receiver state;
- repeated work but no longitudinal follow-up;
- closure but no meaningful closure path;
- user must guess the next action.

**Workflow exists in document + cannot be performed naturally in UI = FACTORY FAIL.**

## 16. Final Rule
`Requirement is not a screen specification.`

The Factory's job is to understand real work deeply enough to derive the application needed to perform it — while keeping Expert Application Derivation clearly separate from Hospital Policy/Business Truth.