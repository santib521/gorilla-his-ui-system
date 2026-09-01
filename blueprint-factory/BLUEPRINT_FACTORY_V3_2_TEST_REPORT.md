# Gorilla HIS Blueprint Factory v3.2 — Scenario Test Report

**Branch:** `blueprint-factory-v3.2-evidence-gate`  
**Purpose:** verify that v3.2 finds material gaps while suppressing irrelevant/speculative questions.

## Test Method
Each scenario is evaluated against:
1. Domain-Adaptive Expert Activation
2. Relevance Gate
3. Evidence Strength Gate
4. Independent Challenge Pass
5. Confirmation Value Gate
6. Quality Gate v2.2 Hard Reject rules

A PASS requires both:
- material risks are not missed; and
- unrelated/hypothetical questions are not surfaced to hospital users.

---

## TEST-01 — Medical Education (Regression Test)

### Raw Requirement Summary
- Medical students access EMR only for assigned patients.
- Student Progress Note has no effect on actual treatment history.
- Year 5–6 view EMR Read Only.
- Year 5–6 may create Progress Note and Order; no clinical effect before physician approval.
- Retain examined cases and performed procedures.

### Expected Domain Activation
**RELEVANT:** Medical Education, Physician/Clinical, Medical Records/HIM, Quality/Patient Safety, HIS Architecture, Clinical Informatics/BA, Data/Source of Truth, UX/Human Factors, Security/Audit, Privacy.

**CONDITIONALLY RELEVANT:** Nursing, Pharmacy, Lab, Radiology, Finance/Inventory — only if approved Student Order becomes a real Clinical Order and creates downstream effects.

**N/A / NOT CURRENT QUESTION:** Claim/DRG, Infection Control, Case Management, unrelated specialty workflows unless later requirement creates a direct dependency.

### Material Gaps That SHOULD Survive
1. Post-approval Student Progress Note effect on actual Clinical Record — CRITICAL.
   - Trace: requirement explicitly says pre-approval has no effect, leaving post-approval effect undefined.
   - Evidence Basis: RAW REQUIREMENT + DIRECT WORKFLOW DEPENDENCY.
2. Post-approval Student Order execution effect — CRITICAL.
   - Trace: Order + physician approval explicitly supplied; actual downstream effect undefined.
   - Evidence Basis: RAW REQUIREMENT + DIRECT WORKFLOW DEPENDENCY.
3. Patient assignment authorization model — HIGH.
   - Trace: access is explicitly based on assignment.
   - Evidence Basis: RAW REQUIREMENT.
4. Approval authority/state behavior — HIGH.
   - Trace: physician approval is explicitly required.
   - Evidence Basis: RAW REQUIREMENT + DIRECT WORKFLOW DEPENDENCY.
5. Audit/accountability for access and approval — HIGH/MEDIUM depending final risk rating.
   - Trace: real patient EMR + learner/supervisor activity.
   - Evidence Basis: ESTABLISHED HIS/HOSPITAL PRACTICE; privacy/security review needed.
6. Student-year permission ambiguity — MEDIUM.
   - Trace: raw wording distinguishes general student Progress Note vs Year 5–6 features.
   - Evidence Basis: RAW REQUIREMENT.

### Candidate Gaps/Questions That MUST BE SUPPRESSED NOW
- “How will the Order affect Billing?” — SUPPRESS now; conditional trigger = real Clinical Order creation confirmed.
- “How will Inventory be deducted?” — SUPPRESS now; no current direct effect.
- “How does Claim/DRG consume the Order?” — SUPPRESS; outside current scope/no established effect.
- “What Infection Control workflow is required?” — SUPPRESS; no trace to supplied requirement.
- “What critical-result escalation should students receive?” — SUPPRESS; not requested and no direct dependency established.
- “What stock reservation occurs?” — SUPPRESS; speculative downstream scope.

### Confirmation Questions That SHOULD Surface
Before Dev:
1. After physician approval, what happens to Student Progress Note in the actual Clinical Record?
   - Decision affected: record architecture / clinical-document ownership.
2. After physician approval, what happens to Student Order?
   - Decision affected: order execution / downstream integration.
3. Who may assign patients, for what scope/duration?
   - Decision affected: authorization/access model.
4. Who may approve/return/reject/cancel/reverse student activity?
   - Decision affected: approval workflow/permission.
5. What audit/privacy constraints are required for student access?
   - Decision affected: access/logging/security design.

Prototype Review:
- Is Assigned Patient Worklist appropriate?
- Is explicit Education/Training Mode treatment acceptable?
- What minimum Case/Procedure fields are needed?
- Clarify student-year permission matrix.

### Independent Challenge Dispositions
- Pharmacy/Lab/Radiology as current confirmation owners → RECLASSIFY to CONDITIONALLY RELEVANT.
- Finance/Inventory questions → SUPPRESS until real-order trigger exists.
- Claim/DRG → SUPPRESS.
- Infection Control → SUPPRESS.
- Generic downtime question → DOWNGRADE/LATER unless availability requirement emerges.

### Result
**PASS** — v3.2 rules preserve material clinical/data gaps while explicitly suppressing unrelated downstream questions.

---

## TEST-02 — Simple Appointment Module (Over-analysis Negative Test)

### Raw Requirement Summary
Patient can choose clinic/date/time; staff confirm/reschedule/cancel appointment; send appointment reminder.

### Expected Relevant Perspectives
Patient Access, Clinic Operations, Physician schedule/clinic resource where applicable, HIS/BA, Integration if reminder service exists, Security/Privacy.

### Must NOT Automatically Activate as Questions
Pharmacy, Lab, Blood Bank, Radiology, Inventory, Claim/DRG, OR/Anesthesia, Infection Control.

### Material Questions
- Source of truth for appointment slot/capacity.
- Who can override/reschedule/cancel.
- duplicate/conflicting appointment behavior if material.
- reminder channel only if notification is in scope.

### Suppression Assertions
- No medication safety question.
- No lab result question.
- No DRG/billing question unless payment/preauthorization explicitly enters scope.
- No inventory question.

### Result
**PASS by rule inspection** — Relevance Gate and Domain Activation explicitly prohibit activating unrelated HIS domains merely because they exist.

---

## TEST-03 — Medication Order Module (Safety Recall Test)

### Raw Requirement Summary
Physician orders medication; pharmacist verifies; nurse administers; cancellation/change supported.

### Expected Relevant Perspectives
Physician, Pharmacy/Medication Management, Nursing, Patient Safety, Data/Source of Truth, Audit, Integration; Billing/Inventory may be DIRECT or CONDITIONAL depending confirmed charge/stock effects.

### Material Gaps That MUST NOT Be Suppressed
- medication/order lifecycle and source of truth.
- prescriber/pharmacist/nurse permissions.
- verify/reject/clarify/cancel/change behavior.
- administration effect and traceability.
- patient/encounter/medication context.

### Evidence Requirement
Any claim such as a mandatory medication rule must be traceable to Raw Requirement, direct workflow dependency, authoritative verified source, or clearly labeled established practice / needs verification.

### Result
**PASS by rule inspection** — v3.2 retains safety-critical domain activation while preventing unsupported compliance claims.

---

# Overall Test Result

| Test | Focus | Result |
|---|---|---|
| TEST-01 Medical Education | Regression + irrelevant-question suppression | PASS |
| TEST-02 Appointment | Negative over-analysis | PASS |
| TEST-03 Medication Order | Safety recall / under-analysis prevention | PASS |

## Acceptance Assertions
- PASS: No relevance → no active GAP/question.
- PASS: Conditional downstream effect → no current confirmation request until trigger becomes true.
- PASS: Critical/High expert-created items require evidence trail.
- PASS: Independent reviewer must remove questions as well as discover missing risks.
- PASS: Every surfaced confirmation question must state decision value.
- PASS: Recommendations cannot become Hospital Confirmed through confidence or expert consensus.

## Remaining Human Review
This scenario test validates Master behavior/rules, not clinical certification. Human hospital/product review remains required before `HOSPITAL CONFIRMED` or `READY FOR DEV HANDOFF` status.