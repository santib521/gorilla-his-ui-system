# Gorilla HIS — Universal Workflow Challenge v1.0

Status: `UNIVERSAL FACTORY MASTER`

## Purpose
Prevent Blueprint Factory from treating Raw Requirement as a complete workflow. This framework applies to every HIS module before domain-specific analysis.

## Core Model
For every material workflow challenge:

`ENTRY → AUTHORITY → IDENTITY/CONTEXT → OWNERSHIP → WORK → TRANSACTION → FINANCE → PRIVACY → EXCEPTION → EXIT`

This is a completeness challenge, not Hospital Truth.

## Mandatory Universal Questions
### UWC-01 Entry / Request
- How does work enter the module?
- Who may request/refer/initiate it?
- What source/reference/time/priority is captured?

### UWC-02 Authority / Decision
- Who may Accept / Reject / Return / Redirect / Cancel?
- Is approval required? By whom?
- Are reason, actor, date/time and audit required?

### UWC-03 Identity / Encounter / Context
- What is the primary identifier?
- Is HN/VN/AN/Encounter/Order/Case ID required?
- Can historical records be linked without becoming the transaction context?
- What happens on duplicate/wrong-link/correction?

### UWC-04 Ownership / Assignment
- Who owns the work now?
- Is there roster/queue/assignment/consult/coverage/handover?
- What happens when the expected owner is unavailable?

### UWC-05 Core Work
- What are the real operational/clinical steps?
- What information is read, created, reviewed and finalized?
- What states and transitions matter?

### UWC-06 Transaction / Downstream Effect
- Does the module create Orders, Results, Medication, Documents, Inventory, Claims, Charges, Appointments or other downstream records?
- What is the downstream Source of Truth?
- How do Cancel/Correction/Amendment/Reversal work?

### UWC-07 Finance
- Who pays or bears cost?
- What identifier/encounter/case is charged?
- What is the price/quantity/time basis?
- How do waive/refund/cancel/reverse/posting work?

### UWC-08 Privacy / Sensitive Data
- Who can see full identity and sensitive details?
- Is masking/reveal/break-glass/restricted media/document needed?
- What print/export/download/access audit is needed?

### UWC-09 Exceptions
- What are the material non-happy paths?
- Missing data/document, unavailable resource, rejected request, failed integration, duplicate identity, corrected result, cancelled transaction, downtime where relevant.

### UWC-10 Exit / Closure / Handoff
- What makes the work complete?
- Who confirms/finalizes?
- What is handed off, to whom, with what traceability?
- What remains open after the main task finishes?

## Gate
A Blueprint cannot be `PROTOTYPE READY` until each applicable UWC item is classified:
`CONFIRMED / PARTIAL / NOT STATED / N/A / NEEDS CONFIRMATION`.

`NOT STATED` does not automatically become a GAP; Relevance and Confirmation Value Gates still apply.

## Scenario Rule
Run UWC separately for materially different scenario branches. Do not use one generic answer when entry, identity, actor, source-of-truth, finance, privacy, downstream effect or end state differs.
