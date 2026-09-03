# Gorilla HIS — Expert Requirement Discovery Workshop Standard v1.1

Status: `UNIVERSAL FACTORY MASTER`

Purpose: force the Factory to behave like an experienced Domain Expert + Senior HIS BA sitting with actual hospital users, discovering **how work really operates**, not merely completing a generic HIS framework.

Binding companion: `ACTUAL_WORKFLOW_DISCOVERY_STANDARD.md`.

## Core Rule
`Hospital Evidence → Actual Workflow Reconstruction → Core Transaction Discovery → Lifecycle/State → Role/Handoff/Data → Domain Standard Challenge → Missing Decision Discovery → Question Bank → Blueprint`.

**Standard Workflow is for Challenge — not for replacing Hospital Reality.**

## 1. Workshop Mindset
Start from the user's real day, not from screens or a generic module taxonomy.

For every material flow ask:
- What event actually starts this work?
- Who initiates it and why?
- What does the user receive/see first?
- What is the real business transaction/object being handled?
- Is this the same transaction as the other similar-looking flow, or a different one?
- What data is entered, read, copied forward or generated?
- What decision changes the next path?
- Who owns the work now and next?
- Where does the user wait, call, message, print, use paper/Excel/LINE/phone or walk to another department?
- Does the work repeat across visit/session/cycle/episode?
- Is there approved quantity/value, partial use or remaining balance?
- Is assessment repeated/versioned?
- What can be returned/rejected/cancelled/expired/corrected/reversed/reopened?
- What proves completion?

Mandatory challenge:
**If a real hospital user had to operate this tomorrow, where would they stop or leave the system because our understanding of the real workflow is incomplete?**

## 2. Evidence Capture — Mandatory
For each material workflow statement classify:
`HOSPITAL OBSERVED / HOSPITAL STATED / HOSPITAL DOCUMENTED / HOSPITAL CONFIRMED / EXPERT INFERENCE / REFERENCE BASELINE / TBD`.

Hospital Primary Evidence may include workshop/interview, recording/transcript/minutes, SOP/form/report, current-system walkthrough/screenshots, observed off-system work and confirmed TOR/requirement.

No Expert Inference becomes Hospital Confirmed.

## 3. Actual Workflow Reconstruction — Mandatory
For every materially different workflow create:
`Trigger → Entry → Actor → Input → Validation → Decision → Action → Record/Transaction → Handoff → Repeat/Re-assess → Exception → Closure`.

Do not begin with “system should have screen X”. Reconstruct work first.

## 4. Core Transaction Discovery — Mandatory
For each major object/transaction determine:
`Name | Trigger | Creator | Identifier | Parent/Related Object | Source of Truth | Authority | Lifecycle | Quantity/Value | Versioning | Correction/Reversal | Closure`.

Run Transaction Boundary Test. Similar flows are separate if materially different in purpose, requester, authority, data, approval, finance, quantity/value, repeated use, lifecycle, response or closure.

HARD FAIL: different transactions collapsed into generic Case/Referral/Order without evidence.

## 5. Lifecycle / State Workshop
For every material transaction challenge:
`Create → Receive/Accept → In Progress → Review/Approve when applicable → Active/Available → Partial/Repeated Use when applicable → Complete/Close`
plus relevant `Return / Reject / Cancel / Expire / Suspend / Correct / Reverse / Reopen`.

For each transition ask Actor, precondition, data mutation, downstream effect, audit and failure/recovery.

## 6. Repeated / Longitudinal Workshop — Mandatory Check
For every scenario determine whether it is one-time, repeated sessions/visits/cycles, longitudinal across encounters, quantity/value-limited, periodically reassessed, partially fulfilled or renewed/extended.

When applicable discover:
- initial vs subsequent event;
- previous history visible;
- used/completed and remaining;
- reassessment/carry-forward;
- changed/unchanged score/data;
- completion/closure rule.

## 7. Discovery Dimensions — Mandatory
Disposition `COVERED / PARTIAL / NOT STATED / N/A / NEED HOSPITAL CONFIRMATION` for applicable:
1 Scope/case eligibility/classification
2 Trigger/Entry/request/referral
3 Core transaction/object boundary
4 Actor/requester authority
5 Intake/accept/reject/return/redirect
6 Identity/patient/case/encounter/episode
7 Ownership/assignment/worklist/waiting state
8 Core professional workflow
9 Decision/approval/dual review
10 Lifecycle/state transition
11 Repeated/longitudinal/partial-use
12 Assessment/version/carry-forward
13 Documents/forms/media/signatures
14 Orders/results/external services
15 Evidence/specimen/asset custody
16 Exception/recovery/correction/reversal
17 Integration/source of truth/timing
18 Downtime/manual continuity/reconciliation
19 Finance/payer/charge/waive/refund/reversal
20 Privacy/sensitivity/masking/reveal/export
21 Audit/accountability
22 Reporting/statistics/definitions
23 Closure/handover/discharge/release/archive
24 SLA/priority/escalation
25 Configuration/master/numbering/template/version
26 Search/history/amendment
27 Operational usability/next action/bottleneck
28 Off-system work and workaround

## 8. Question Generation
No generic “ต้องการอะไรเพิ่มไหม?”. Use:
`Current Evidence → Missing Decision → Recommended Options → Impact/Risk → Specific Question → Owner → Timing`.

Classify missing information:
1 `ALREADY ANSWERED`
2 `EXPERT RECOMMENDATION AVAILABLE`
3 `HOSPITAL DECISION REQUIRED`.

Do not burden users with questions an expert can narrow responsibly.

## 9. Workshop Question Bank — Mandatory
Fields:
`Question ID | Domain/Scenario | Transaction | Lifecycle Stage | Question | Why Asked | Current Evidence | Recommendation/Options | Decision Affected | Risk | Owner | Priority | Confirm When | Status`.

Priority: CRITICAL / HIGH / MEDIUM / LOW-REFINEMENT.

Status: OPEN / ANSWERED BY EVIDENCE / RECOMMENDATION AVAILABLE / HOSPITAL DECISION REQUIRED / DEFERRED / N/A.

Coverage matters more than question count.

## 10. Role Interview Lens
For each role discover worklist arrival, required information, permitted/blocked actions, ownership, waiting state, handoff, return path, search/recovery and closure. Do not infer authority from title alone.

## 11. Data Interview Lens
For each object discover creator, identifier, editable/immutable data, versioning, source of truth, disagreement/reconciliation and downstream correction impact.

## 12. Exception Workshop
Challenge relevant missing/invalid input, wrong patient/case, duplicate, late information, unavailable role/resource, insufficient permission, external interface unavailable, partial success, return/reject, cancel/expire, correction after approval/use, reversal, invalid handover, special route, downtime/manual work and reconciliation, close with outstanding work, reopen.

## 13. Standard Challenge Comes After Reality
Where Hospital Primary Evidence exists, reconstruct Actual Workflow first. Then compare Domain Standard Flow using Actual-vs-Standard Delta. Standard may expose a missing decision but cannot be promoted to local truth.

If actual evidence is inadequate, mark `ACTUAL WORKFLOW NOT VERIFIED`; do not fabricate a complete flow.

## 14. Mandatory Workshop Deliverables
1 Hospital Actual Workflow Evidence Register
2 Actual Workflow Map(s)
3 Core Transaction/Object Model
4 Lifecycle/State Transition Matrix
5 Repeated/Longitudinal Analysis
6 Role/Handoff/Waiting-State model
7 Data/Source-of-Truth model
8 Discovery Dimension Coverage
9 Workshop Question Bank
10 Critical Decisions Before Dev
11 Expert Recommendations for confirmation
12 Unresolved Hospital decisions
13 Independent Domain + Reality Challenge

## 15. Blueprint Promotion
Only Hospital evidence/confirmation becomes local Requirement/Business Rule. Unanswered items remain HSR/CR/WA/TBD as appropriate.

`PROTOTYPE READY` requires enough actual workflow evidence for safe bounded discovery, material transactions/lifecycles identified, applicable dimensions dispositioned and Critical/High unresolved visible.

`READY FOR DEV HANDOFF` requires implementation-blocking workflow/transaction/state/authority/data decisions answered, explicitly excluded or converted to verified rules.

## 16. Independent Reality Challenge — Mandatory
Reviewer asks:
1. Would an experienced user from this exact department recognize their real work?
2. What real work still happens outside the modeled flow?
3. Did we invent a reasonable workflow where evidence was absent?
4. Did we merge different transactions because they looked similar?
5. Can one realistic case execute from trigger to closure?

Any material failure blocks promotion.