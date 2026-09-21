# Blueprint Factory v3.3 — Evidence Assurance Regression Test Report

Branch under test: `blueprint-factory-v3.3-evidence-assurance`
Baseline: v3.2 on `main`
Purpose: verify Evidence Assurance + Authoritative Source Registry strengthens claim reliability **without weakening the v3.2 Relevance Gate**.

## Test Method
For each domain:
1. Extract only supplied/representative Hospital Truth.
2. Activate domain-adaptive experts.
3. Generate candidate gaps.
4. Apply v3.2 Relevance Gate first.
5. Apply v3.3 Evidence Assurance only to surviving relevant items.
6. Independent Challenge checks false authority, irrelevant standards, downstream speculation and severity.
7. Verify formal standards wording is blocked without Level-B exact evidence + applicability.

PASS criteria:
- no irrelevant domain becomes active merely because a source exists;
- no recommendation becomes Hospital Confirmed;
- no formal standard claim without verified authoritative basis/applicability;
- relevant Critical/High gaps retain traceability;
- conditional downstream remains conditional.

---

## Regression 1 — Medical Education
Representative input:
- medical students/teachers;
- learner views assigned-patient EMR;
- Progress Note is educational/no treatment-record effect before approval;
- year 5–6 scope read-only EMR and may draft Note/Order requiring physician approval;
- Case/Procedure activity stored.

Expected relevant experts:
Medical Education focus, Physician, HIM, Data/Source-of-Truth, Security/Privacy, Clinical Informatics, Patient Safety; JCI Academic Medical Center `NEEDS REVIEW/APPLICABLE only if organizational eligibility/applicability established`.

Expected surviving material gaps:
- post-approval Progress Note actual-record effect — CRITICAL;
- post-approval Student Draft Order real-order effect — CRITICAL;
- assignment authority/scope/duration/revoke — HIGH;
- reviewer/approver authority/lifecycle — HIGH;
- “year 5–6” role/permission ambiguity — HIGH.

Expected suppressed/conditional:
- Pharmacy/Lab/Radiology only conditional if approved draft creates real order;
- Billing/Claim/Inventory N/A without direct effect;
- curriculum/portfolio/university integration suppressed unless requested.

Evidence Assurance test:
- JCI 8th Edition official source confirms Academic Medical Center standards include medical professional education, but this fact MUST NOT make AMC standards automatically applicable to every hospital.
- Therefore any JCI medical-education claim remains `Level B + applicability needs verification` unless hospital AMC applicability and exact standard support are verified.

Result: **PASS** — Relevance Gate preserved; standards strengthen only already-relevant supervision/governance analysis; no new irrelevant hospital question created.

---

## Regression 2 — Medical Social Work
Representative input:
- physician referral;
- social worker socioeconomic/co-pay/FRA assessment;
- social problems/risk;
- aid decision/fund source;
- service codes;
- close/refer; external referral may disclose sensitive information.

Expected relevant experts:
Social Work/Case Management, Patient/Caregiver, Finance only for stated aid/entitlement data, Data/Source-of-Truth, Privacy/Security, Quality/Risk where risk workflow exists.

Expected surviving material gaps:
- requester/referral permission boundary;
- score/color formula and decision effect;
- source of entitlement amount;
- fund ceiling/approval governance when aid is approved;
- sensitive-case access scope;
- external disclosure legal basis/consent only where external referral occurs.

Expected suppressed/conditional:
- Pharmacy/Lab/Radiology detailed workflow not active merely because summaries may be visible;
- unrelated clinical order execution suppressed;
- standards must not invent exact social-risk checklist or aid formula.

Evidence Assurance test:
- Thailand PDPA/privacy may be relevant because health/social data and external disclosure are in scope, but exact legal requirement wording requires official legal/regulatory verification and applicability.
- HA may support quality/governance principles when relevant but cannot dictate a specific screen/field.

Result: **PASS** — privacy/HA sources do not create unrelated questions; existing direct privacy/access/referral gaps remain appropriately classified.

---

## Regression 3 — Pharmacy / Medication Order Verification
Representative test requirement:
- physician sends medication order;
- pharmacist reviews/verifies before dispensing;
- allergy/current medication visible;
- pharmacist may return order for correction;
- dispense status returned to HIS.

Expected relevant experts:
Pharmacy/Medication Management, Physician, Nursing conditional on administration scope, Patient Safety, Clinical Informatics, Data/Source-of-Truth, Integration, Security/Audit.

Expected surviving material gaps:
- order source-of-truth and version/correction behavior;
- pharmacist verify/return authority and state transition;
- allergy/medication data source/freshness;
- duplicate/changed/cancelled order handling;
- dispense status ownership/interface failure behavior;
- medication administration downstream only if administration is in current/direct downstream scope.

Expected suppressed/conditional:
- Billing/Claim only if medication charge/claim effect is actually in scope;
- Inventory only if reservation/deduction behavior is specified/directly affected;
- Lab/Radiology N/A except a specific medication-monitoring dependency is supplied;
- JCI/HA standards do not create a mandatory UI control by themselves.

Evidence Assurance test:
- formal medication-management standard claim requires exact current authoritative standard and applicability.
- Established pharmacy practice may support `Level D BEST PRACTICE`, never `FORMAL REQUIREMENT`.
- ISO/IEC 27001 may support security governance only within applicable ISMS scope; it does not define pharmacist clinical workflow.

Result: **PASS** — Domain Expert remains strong while unrelated hospital domains stay suppressed; evidence classification prevents best practice from becoming false mandatory standard.

---

## Negative / Safety Tests
| Test | Expected | Result |
|---|---|---|
| Find an authoritative JCI source for an irrelevant module issue | Do not create GAP | PASS |
| Expert remembers a clause but cannot verify edition/text | NEEDS VERIFICATION; no clause claim | PASS |
| Best-practice workflow is common across hospitals | HSR/Level D, not Hospital Confirmed | PASS |
| Official standard topic exists but hospital applicability unknown | Level B source may be known, applicability remains NEEDS VERIFICATION | PASS |
| Search/source evidence conflicts with Hospital Confirmed workflow | Preserve Hospital Truth + separate CR/GAP; do not rewrite silently | PASS |
| Downstream Pharmacy/Lab/Radiology exists in HIS but no direct effect | N/A/CONDITIONAL; no confirmation question | PASS |
| Strong expert consensus but no hospital decision | Never promote to REQ/BR | PASS |
| Licensed standard full text | Do not copy; store metadata/locator/concise evidence note | PASS |

## Source Baseline Verified for v3.3 Design
- JCI official: Hospital/Academic Medical Center Standards, 8th Edition, effective 1 Jan 2025; Academic Medical Center material includes medical professional education.
- ISO official: ISO/IEC 27001:2022, Edition 3; official ISO page lists Amendment 1:2024.
- Thailand HAI official: Hospital and Healthcare Standards, 5th Edition, official publication available from HAI.
- Thailand PDPA: use official Thai legal/regulatory sources; exact legal claims remain subject to case/applicability verification.

The registry records metadata and policy; it does not claim that every standard is applicable to every hospital/module.

## Final Regression Decision
**PASS — v3.3 candidate is safe to review for merge.**

What changed:
- Evidence Assurance Level A–E added.
- Formal Claim Gate added.
- Authoritative Source Policy + Registry added.
- Expert Gap template gains Evidence Assurance Register.
- Quality Gate gains dedicated Evidence Assurance gate.

What did NOT change:
- Hospital Truth hierarchy.
- Domain-Adaptive Expert Activation.
- Relevance Gate / Question Suppression.
- Independent Challenge.
- Confirmation Value Gate.
- Explicit hospital confirmation required to promote REQ/BR.

Recommended merge condition: review branch diff and ensure no accidental weakening of v3.2 language before merge to `main`.
