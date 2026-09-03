# Gorilla HIS — Application Blueprint Template v2.5

**Blueprint Version:** v0.x / v1.x  
**Status:** DRAFT / PROTOTYPE READY / HOSPITAL CONFIRMED / READY FOR DEV HANDOFF  
**Actual Workflow Status:** VERIFIED / PARTIAL / ACTUAL WORKFLOW NOT VERIFIED  
**Related Expert Suggestion:**  
**Related Workshop Question Bank:**

> Business Source of Truth for UI Factory. Follow `ACTUAL_WORKFLOW_DISCOVERY_STANDARD.md`. Standard/domain knowledge challenges Hospital Reality; it does not replace it.

## Evidence Classification
`HOSPITAL OBSERVED / HOSPITAL STATED / HOSPITAL DOCUMENTED / HOSPITAL CONFIRMED / HOSPITAL STANDARD RECOMMENDATION / COMPLIANCE RECOMMENDATION / EXPERT INFERENCE / WORKING ASSUMPTION / TBD / REFERENCE BASELINE`.

## 1. Product
Application Name / Product / Objective / In Scope / Out of Scope.

## 2. Users & Roles
| Role | Responsibility | Permission / Constraint | Evidence | Related Q IDs |
|---|---|---|---|---|

## 3. Hospital Actual Workflow Evidence Register — MANDATORY
| Evidence ID | Source Type | Role/Source | Workflow/Transaction Supported | What It Proves | Evidence Class | Confidence | Verification Needed |
|---|---|---|---|---|---|---|---|

If evidence is inadequate, state `ACTUAL WORKFLOW NOT VERIFIED`.

## 4. Actual Workflow Map — MANDATORY
For every material workflow:
`Trigger → Entry → Actor → Input → Validation → Decision → Action → Record/Transaction → Handoff → Repeat/Re-assess → Exception → Closure`.

| AWF ID | Scenario | Trigger/Entry | Actor | Real Work | Handoff | Off-System Work | Repeat/Reassess | Exception | Closure | Evidence IDs |
|---|---|---|---|---|---|---|---|---|---|---|

## 5. Core Transaction / Object Model — MANDATORY
Do not collapse different transactions because the same department owns them.

| OBJ ID | Transaction/Object | Trigger | Created By | Identifier | Parent/Related | Source of Truth | Authority | Quantity/Value | Versioning | Closure | Evidence/Q IDs |
|---|---|---|---|---|---|---|---|---|---|---|---|

### 5A. Transaction Boundary Decision
Document why similar-looking flows are SAME or DIFFERENT transaction based on purpose, requester, authority, data, approval, financial effect, quantity/value, repeated use, lifecycle and closure.

## 6. Lifecycle / State Transition Matrix — MANDATORY
| Object | From State | Event/Action | Actor | Preconditions | Data Mutation | Downstream Effect | To State | Audit | Failure/Recovery | Evidence/Q IDs |
|---|---|---|---|---|---|---|---|---|---|---|

Challenge Return / Reject / Cancel / Expire / Suspend / Correct / Reverse / Reopen when relevant.

## 7. Repeated / Longitudinal Workflow Analysis — MANDATORY
| Object/Scenario | One-time / Repeated / Longitudinal | Session/Visit/Cycle/Episode | Approved Qty/Value | Used/Completed | Remaining | Reassessment | Renewal/Extension | Completion Rule | Evidence/Q IDs |
|---|---|---|---|---|---|---|---|---|---|

If not applicable, record N/A with reason.

### 7A. Assessment / Version / Carry-Forward
| Assessment | Initial/Reassessment | Version Rule | Carry Forward | Changed/Unchanged | Author/Context | Amendment | Downstream Effect | Evidence/Q IDs |
|---|---|---|---|---|---|---|---|---|

## 8. Legal / Operational Classification
| CLS ID | Type/Trigger | Actor/Authority | Required Evidence/Data | Workflow Branch | End State | Evidence | Q IDs |
|---|---|---|---|---|---|---|---|

## 9. Role / Handoff / Waiting State
| Stage/Transition | Current Owner | Action | Next Owner | Queue/Worklist | Waiting State | Notification/SLA | Return Route | Proof of Handoff | Evidence/Q IDs |
|---|---|---|---|---|---|---|---|---|---|

## 10. Data / Source-of-Truth Continuity
| Data/Object | Created By/System | Source of Truth | Consumer | Editable By | Version/Timing | Downstream Dependency | Correction/Reconciliation | Evidence/Q IDs |
|---|---|---|---|---|---|---|---|---|

## 11. Domain Standard Flow Baseline
Label: `REFERENCE BASELINE — NOT HOSPITAL CONFIRMED`.

| Baseline ID | Scenario | Reference Step/Handoff | Source/Evidence | Applicability |
|---|---|---|---|---|

## 12. Actual-vs-Standard Delta
Run only after Actual Workflow Reconstruction where evidence exists.

| Baseline/Scenario | Actual Hospital Evidence | Coverage | Difference/Missing Decision | Impact | Recommendation | Confirmation | Q IDs |
|---|---|---|---|---|---|---|---|

Coverage: `ACTUAL MATCH / ACTUAL PARTIAL / ACTUAL CONFLICT / ACTUAL NOT EVIDENCED / STANDARD N/A`.

## 13. Scenario / Exception Catalog
| SCN ID | Transaction | Trigger/Entry | Actor | Core Path | Repeated Behavior | Material Exception/Recovery | End State | Hospital Coverage | Q IDs |
|---|---|---|---|---|---|---|---|---|---|

## 14. Role-Based Swimlane — DOCUMENT ONLY
For every material multi-role scenario show Starting Event, Transaction, Decision, Role, Activity, Handoff, System Action, Record/Source of Truth, Waiting State, Exception and End State.

Do not automatically turn this into a mockup screen.

## 15. Expert Requirement Discovery Coverage
| Discovery Dimension | Status | Missing Decision | Q IDs | Blueprint Treatment |
|---|---|---|---|---|

Status: COVERED / PARTIAL / NOT STATED / N/A / NEED HOSPITAL CONFIRMATION.

## 16. Workshop Question Summary
| Q ID | Priority | Decision Affected | Owner | Confirm When | Status | Blueprint Impact |
|---|---|---|---|---|---|---|

## 17. Core Functions
| FN ID | Function | Description | Transaction/Scenario | Evidence | Related REQ/Q IDs |
|---|---|---|---|---|---|

## 18. Hospital Requirements
| REQ ID | Requirement | Evidence | Related Questions Resolved |
|---|---|---|---|

Only Hospital-confirmed/stated evidence belongs as Hospital Requirement; preserve evidence status.

## 19. Confirmed Business Rules
| BR ID | Business Rule | Evidence | Source Confirmation/Q ID |
|---|---|---|---|

Do not place expert/domain recommendations here.

## 20. Recommendations / Compliance
### Hospital Standard Recommendations
| HSR ID | Recommendation | Rationale | Gap | Q ID | Confirmation Needed |
|---|---|---|---|---|---|

### Standards & Compliance Review
| CR ID | Standard/Source | Applicability | Principle | Workflow Trace | Recommendation | Verification | Gap/Q ID |
|---|---|---|---|---|---|---|---|

## 21. Permission / Accountability
| Action | Object/State | Role | Create/Edit/Review/Approve/Reverse | Audit | Evidence/Q IDs |
|---|---|---|---|---|---|

## 22. Reports / Outputs / Statistics
| Output | Definition/Trigger | Source | Version/Amendment | Recipient | Q IDs |
|---|---|---|---|---|---|

## 23. Working Assumption Register
| WA ID | Assumption | Scenario | Why Needed | Risk if Wrong | Safe Boundary | Q ID | Confirm When |
|---|---|---|---|---|---|---|---|

## 24. TBD / Conflict Register
| TBD ID | Missing/Conflict | Scenario | Why It Matters | Safe Prototype Treatment | Q ID |
|---|---|---|---|---|---|

## 25. Prototype Scenario Coverage / UI Contract
| SCN ID | Required? | Real Entry | Core Transaction | Lifecycle to Execute | Repeat/Reassess/Partial Use | Material Exception | Observable End State | Open Q IDs | Smoke Test |
|---|---|---|---|---|---|---|---|---|---|

UI Factory must not skip a material upstream stage or replace a real transaction with a generic case.

## 26. Workflow Fidelity Acceptance Criteria
| WF-AC ID | Scenario | Evidence to Match | Expected Transaction/State Behavior | Expected Handoff/Data Mutation | Expected Exception/Recovery | Pass Evidence |
|---|---|---|---|---|---|---|

## 27. General Acceptance Criteria
| AC ID | Acceptance Criterion | Scenario(s) | Related IDs | Evidence |
|---|---|---|---|---|

## 28. Confirmation Plan
### MUST CONFIRM BEFORE DEV
| Q ID | Decision | Owner | Why Blocking |
|---|---|---|---|

### CONFIRM DURING PROTOTYPE REVIEW
| Q ID | Decision | Owner | What Prototype Demonstrates |
|---|---|---|---|

### SAFE TO DEFER
| Q ID | Reason | Trigger |
|---|---|---|

## 29. Expert / Reality Review Summary
Record:
- Actual Workflow evidence status;
- transaction boundaries;
- repeated/longitudinal findings;
- off-system work discovered;
- Critical/High open questions;
- Domain Baseline used;
- Independent Reality Challenge findings;
- advisory items intentionally excluded from Hospital Truth.

Mandatory reviewer questions:
1. Would an experienced user from this exact department recognize their real work?
2. What work still happens outside the modeled flow?
3. Did we invent a plausible workflow where evidence was absent?
4. Did we merge different transactions because they looked similar?
5. Can one realistic case execute from trigger to closure?

## 30. Blueprint Readiness
**Status:** DRAFT / PROTOTYPE READY / HOSPITAL CONFIRMED / READY FOR DEV HANDOFF  
**Actual Workflow Status:**  
**Critical unresolved items:**  
**Open Q IDs:**  
**Prototype-safe assumptions:**  
**Scenario coverage required:**  
**Compliance verification pending:**

### Readiness Rule
`PROTOTYPE READY` requires enough Hospital Truth for bounded discovery, explicit actual-workflow evidence status, material transaction/lifecycle/scenario definition, visible Critical/High decisions and safe prototype treatment.

`READY FOR DEV HANDOFF` requires implementation-blocking workflow/transaction/state/authority/data/integration decisions resolved or explicitly excluded.

### Separation Rule
`Hospital Actual Workflow ≠ Domain Standard Flow.`  
`Domain Standard Flow = Challenge Baseline.`  
`Expert Suggestion ≠ Hospital Truth.`  
`Workshop Question ≠ Hospital Requirement.`  
Only explicit Hospital evidence/confirmation promotes local truth.