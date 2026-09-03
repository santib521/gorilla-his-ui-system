# Gorilla HIS — Actual Workflow Discovery & Transaction Fidelity Standard v1.0

Status: `UNIVERSAL FACTORY MASTER`

Applies to: **EVERY Gorilla HIS module** — clinical, ancillary, administrative, financial, operational and platform workflows.

## Core Principle
`Standard Workflow is for Challenge — not for replacing Hospital Reality.`

The Factory must not design a plausible hospital workflow and treat it as the hospital's workflow. Before solution design it must reconstruct the actual operating model from Hospital Primary Evidence whenever available, identify the real business transactions and their lifecycle, then use domain standards/expert knowledge to challenge gaps.

## Mandatory Architecture
`Hospital Primary Evidence → Actual Workflow Reconstruction → Core Transaction Discovery → Object/Lifecycle/State Model → Role/Handoff/Data Model → Domain Standard Challenge → Missing Decision Discovery → Hospital Confirmation → Blueprint → Operational Mockup → Scenario Execution Test → Premium UX Review`

If Hospital Primary Evidence is insufficient:
`Known Hospital Truth → ACTUAL WORKFLOW NOT VERIFIED → targeted Workshop Questions → safe Discovery Prototype only`

Never silently fill the unknown flow with generic HIS practice.

## 1. Hospital Primary Evidence
Evidence may include:
- direct workshop/interview with actual users;
- recording/transcript/minutes;
- current SOP/work instruction;
- real forms/reports/screenshots;
- current-system walkthrough;
- observed work including paper, Excel, phone, LINE or cross-department handoff;
- confirmed TOR/requirement.

For every material statement record source and confidence. Distinguish:
`HOSPITAL OBSERVED / HOSPITAL STATED / HOSPITAL DOCUMENTED / HOSPITAL CONFIRMED / EXPERT INFERENCE / REFERENCE BASELINE / TBD`.

No inference is promoted to Hospital Confirmed.

## 2. Actual Workflow Reconstruction — Mandatory
For each materially different workflow reconstruct:
`Trigger → Entry → Actor → Input → Validation → Decision → Action → Record/Transaction → Handoff → Repeat/Re-assess → Exception → Closure`.

Capture work outside the application. Ask where users call, message, print, write, walk to another unit, wait for approval, manually reconcile or re-key data.

Mandatory question:
**What does the real user do next, and what evidence proves that this is what actually happens?**

## 3. Core Transaction Discovery — Mandatory
Before Function List or screen design, identify the real business transactions/objects. Do not collapse different transactions merely because the same department owns them.

For each object:
`Object ID | Name | Created By | Trigger | Identifier | Parent/Related Object | Source of Truth | Mutable Fields | State Model | Quantity/Value | Versioning | Closure | Correction/Reversal`.

Examples are illustrative only: Consult, Request, Order, Referral, Encounter, Episode, Approval, Entitlement, Utilization, Assessment Version, Specimen, Claim, Stock Issue.

The Factory must discover module-specific objects from evidence; examples are not a prescribed model.

## 4. Transaction Boundary Test
For every pair of similar-looking flows ask whether they differ in any of:
- trigger/requester;
- purpose;
- authority/approval;
- required data;
- financial effect;
- quantity/value;
- repeated use;
- state/lifecycle;
- response/closure;
- audit/legal effect.

If materially different, model them as separate transactions/scenarios.

## 5. Lifecycle & State Model — Mandatory
Every material transaction must have an explicit lifecycle.

Challenge:
`Create → Receive/Accept → In Progress → Review/Approve when applicable → Active/Available → Partial/Repeated Use when applicable → Complete/Close` plus relevant `Return / Reject / Cancel / Expire / Suspend / Correct / Reverse / Reopen`.

State names must come from Hospital Truth where confirmed. Expert-proposed states remain recommendations/WA/TBD.

Every transition defines:
`From | Event/Action | Actor | Preconditions | Data Mutation | Downstream Effect | To | Audit | Failure/Recovery`.

## 6. Repeated / Longitudinal Workflow Gate
Every module must explicitly determine whether work is:
- one-time;
- repeated sessions/visits/cycles;
- longitudinal across encounters;
- quantity/amount-limited;
- periodically reassessed;
- partially consumed/fulfilled;
- renewed/extended/re-authorized.

If repeated, the Blueprint and mockup must model progression and remaining obligation/quantity/value where relevant. A single Save that jumps directly to completion = FAIL.

## 7. Assessment / Version / Carry-Forward Gate
When professional assessment repeats, define:
- initial vs reassessment;
- copy-forward/carry-forward behavior;
- changed vs unchanged values;
- score/formula version;
- author/date/context;
- amendment/correction;
- downstream effect when assessment changes.

Do not overwrite history silently.

## 8. Role, Handoff & Waiting State
For every transition identify current owner, next owner, queue/worklist, notification, waiting state, SLA/escalation when material, return route and proof of handoff.

A workflow that says only “send/approve/complete” without ownership and return path is PARTIAL.

## 9. Data & Source-of-Truth Continuity
For each material object/data element identify source, creator, consumer, edit authority, timing, version, reconciliation and downstream dependencies.

Mockup must preserve entered/approved/used data across stages. Silent reset or fabricated downstream values = FAIL.

## 10. Exception & Recovery
At minimum challenge relevant:
missing/invalid input; wrong patient/case; duplicate; return/reject; unavailable approver/resource; partial completion; cancelled/expired authorization; interface failure; late result/information; changed assessment; correction after approval/use; reversal; downtime/reconciliation; close with outstanding work; reopen.

## 11. Actual-vs-Standard Delta
Only after Actual Workflow Reconstruction, compare against Domain Standard Flow.

Use:
`ACTUAL MATCH / ACTUAL PARTIAL / ACTUAL CONFLICT / ACTUAL NOT EVIDENCED / STANDARD N/A`.

Standard/domain knowledge may reveal a missing decision, but never becomes local workflow without confirmation.

## 12. Blueprint Mandatory Artifacts
Every module Blueprint must contain or reference:
1. Hospital Actual Workflow Evidence Register;
2. Actual Workflow Map(s);
3. Core Transaction/Object Model;
4. Transaction Lifecycle/State Transition Matrix;
5. Repeated/Longitudinal Analysis;
6. Role/Handoff/Waiting-State model;
7. Data/Source-of-Truth model;
8. Actual-vs-Standard Delta;
9. Scenario + Exception catalog;
10. unresolved Actual Workflow questions.

If evidence is inadequate, visibly mark `ACTUAL WORKFLOW NOT VERIFIED`.

## 13. Operational Mockup Rule
A mockup is not a slide deck and not a workshop diagram. Hospital-facing surfaces must behave like the application users would operate.

For every material scenario the mockup must support:
`Real Entry → enter/select real task data → validation → transaction creation/acceptance → state transition → role handoff/decision → repeated work/reassessment if applicable → observable quantity/value/history changes → exception/recovery → meaningful end state`.

No Demo/Workshop/Factory/WA/TBD language on normal hospital-facing UI.

## 14. Workflow Fidelity Test — Mandatory Independent Gate
Independent reviewer compares Hospital Evidence + Blueprint + rendered/running mockup.

Test:
- transaction identity correct;
- entry/trigger correct;
- actors/authority/handoff correct;
- state progression correct;
- repeated/longitudinal behavior correct;
- quantity/value/entitlement/utilization behavior correct when applicable;
- assessment/version history correct when applicable;
- source-of-truth/data continuity correct;
- exceptions/recovery executable;
- closure/end state meaningful;
- no invented local workflow presented as fact.

Result:
`PASS / FAIL — WRONG TRANSACTION MODEL / FAIL — WORKFLOW FIDELITY / FAIL — LIFECYCLE INCOMPLETE / FAIL — REPEATED FLOW MISSING / FAIL — HANDOFF BROKEN / BLOCKED — ACTUAL WORKFLOW NOT VERIFIED`.

## 15. Universal Hard Gate
`Business Truth PASS + Workflow Fidelity PASS + Function PASS + Runtime PASS + Independent Design PASS → Candidate — Ready for Human Visual Review`

**Visual PASS + Functional PASS + Workflow Fidelity FAIL = FACTORY FAIL.**

A beautiful mockup that models the wrong work is a Factory failure.

## 16. Promotion Rules
- `DRAFT`: Actual Workflow insufficient or major transaction boundaries unknown.
- `PROTOTYPE READY`: enough Hospital Truth for safe discovery; unresolved workflow is visible and contained.
- `HOSPITAL CONFIRMED`: actual main workflows, material transactions/lifecycles and critical rules confirmed.
- `READY FOR DEV HANDOFF`: implementation-blocking workflow/transaction/state/authority/data decisions resolved or explicitly excluded.

## 17. Independent Reality Challenge
Before promotion ask:
1. Would an experienced user from this exact department recognize their day-to-day work?
2. What real work still happens outside this flow?
3. Did the Factory invent a reasonable workflow where evidence was absent?
4. Did it merge different transactions because they looked similar?
5. Can a user execute one realistic case from trigger to closure without explanation from the Builder?

Any material failure blocks promotion.