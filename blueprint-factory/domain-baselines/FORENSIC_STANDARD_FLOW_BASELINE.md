# Gorilla HIS — Forensic Medicine / Mortuary Standard Flow Baseline v1.1

Status: `REFERENCE BASELINE — NOT HOSPITAL CONFIRMED`

Purpose: provide a source-backed starting workflow for forensic/autopsy/mortuary analysis before overlaying Hospital Requirement and HA/JCI/privacy/security considerations.

## Authority / Evidence Notes
Use current official sources where available and record retrieval/verification date in each Blueprint run.

Primary source families:
1. Thailand Ministry of Public Health (MOPH) — official forensic/post-mortem practice manuals and guidance.
2. Central Institute of Forensic Science (CIFS), Ministry of Justice — official forensic pathology, clinical forensic, evidence/custody and service material.
3. Healthcare Accreditation Institute (HAI) — current applicable Hospital and Healthcare Standards.
4. Joint Commission International — current Hospital standards only when hospital applies/seeks JCI or explicitly uses it as benchmark.
5. Hospital-approved Forensic/Mortuary SOPs, forms, finance rules and privacy policy — required to establish local workflow.

Official source locators:
- MOPH forensic manuals: https://phdb.moph.go.th/main/index/downloadlist/53/7
- CIFS Clinical Forensic Medicine mission: https://www.cifs.go.th/index.php?mod=department
- CIFS evidence service / Chain of Custody: https://eservice.cifs.go.th/index.php?mod=service&page=witness&route=government
- CIFS e-service / requester categories: https://eservice.cifs.go.th/
- HA standards: https://www.ha.or.th/TH/Contents/มาตรฐานโรงพยาบาลและบริการสุขภาพ%20(HA)
- JCI Hospital 8th Edition overview: https://store.jointcommissioninternational.org/joint-commission-international-standards-for-hospitals-8th-edition/

Do not copy copyrighted standards text into repository. Store metadata, principles, workflow implications and verification status only.

---

# 1. Mandatory Forensic Case Lifecycle Challenge
Every Forensic Blueprint run MUST explicitly review these lifecycle questions, even when Raw Requirement does not mention them. A missing answer becomes GAP/HSR/TBD only when it passes Relevance Gate.

## FLC-01 Case Population — Living / Deceased
- Does the service cover deceased forensic cases?
- Does it cover **living forensic patients (Clinical Forensic Medicine / Forensic OPD)** such as injury assessment, sexual assault/violence-related examination, evidence collection and medico-legal certification?
- Are living and deceased cases separated in identifier/encounter/workflow/access/reporting?

Evidence note: CIFS officially maintains a Clinical Forensic Medicine service that examines living case-patients, including injury/assault/sexual-offence related examinations. Therefore a forensic domain review must not assume “forensic = deceased only”.

## FLC-02 Request / Referral Origin
For each scenario identify:
- who initiates the request;
- requester type (internal hospital unit/physician, police/investigator, court/authorized agency, patient/relative where locally permitted, other);
- request document/reference number;
- receiving unit;
- date/time;
- urgency/priority if relevant;
- who accepts responsibility for the case.

External requester examples from CIFS service context include investigator/case owner, authorized representative, directly affected person and direct relative, but this MUST NOT be copied as the hospital's accepted requester list without confirmation.

## FLC-03 Accept / Reject / Return-for-Information
Every intake workflow MUST challenge whether request can be:
- Accepted;
- Rejected;
- Returned/Pending for missing information;
- Redirected to another service.

If reject/return exists, capture reason, actor, date/time, notification recipient and audit history. Exact reject criteria are Hospital Policy/TBD unless authoritative local criteria are supplied.

## FLC-04 Identity Context — AF / HN / VN / Encounter
Challenge separately:
- AF-only external body;
- AF linked to existing HN history;
- living forensic patient using HN/VN/Encounter;
- unknown identity and later identity correction;
- multiple possible HN match / duplicate identity.

Important distinction:
`Can link/read historical HN` does NOT automatically mean `may use that HN/VN for new clinical orders`.

## FLC-05 HN Link Governance
When an AF-only case is later linked to an HN, review:
- search/match method;
- evidence supporting the match;
- whether dual review/approval is required by hospital policy;
- who may link/unlink/correct;
- audit before/after;
- effect on existing forensic records/orders/results;
- duplicate/wrong-link reversal.

There is no universal rule in this Master that HN linkage **must** require approval. Approval is a material governance question that must be confirmed when wrong-link risk is significant.

## FLC-06 Physician Coverage / Duty Roster
Review how a request is assigned to a forensic physician:
- duty/on-call/exam roster;
- service date/time/location;
- responsible physician;
- substitute/coverage/consult;
- unavailable/no physician path;
- handover between physicians.

A physician roster is an operational recommendation unless Hospital Requirement/SOP confirms it. It becomes relevant when request routing, ownership or SLA depends on physician availability.

## FLC-07 Diagnostic Order Context
Before any Lab/Radiology/CT order, explicitly determine:
- whether the target system requires HN/VN/Encounter;
- whether an AF-only case may order directly;
- whether a temporary/special encounter must be created;
- which identifier is sent downstream;
- how specimen/accession/order/result returns to AF;
- cancellation/result correction behavior.

Do not show a production order path from AF alone unless the integration contract confirms it.

## FLC-08 Finance / Charging
For each scenario challenge:
- chargeable vs non-chargeable cost;
- payer/recipient of charge;
- HN/VN/AF billing context;
- service price/quantity/time basis (e.g. cold storage days) where hospital defines it;
- waive/exempt/discount if relevant;
- posting source of truth;
- cancellation/refund/reversal;
- whether external/public-authority cases follow a different finance route.

MOPH service fee schedules may be reference evidence only when applicable to the hospital; they do not automatically set this hospital's price.

## FLC-09 Sensitive Identity / Name Masking
Review whether highly sensitive forensic cases require:
- masked name in worklists/queues;
- restricted photographs/documents;
- role-based reveal of full identity;
- print/export/download restrictions;
- access log / break-glass where locally defined;
- special handling of sexual-assault, child, violence or other sensitive cases.

HA information security/privacy principles support confidentiality and protection against unauthorized access, but exact masking rule must be Hospital Policy/Privacy-confirmed.

---

# 2. Scenario A — Death Occurring Inside Hospital / Existing HN

### Entry Trigger
Patient with existing HN/encounter dies in hospital and is referred/requested into forensic/post-mortem pathway.

### Reference Flow
A1. Death event recorded in clinical context.
A2. Internal requester/referring unit submits forensic request; requester/authority must be identified.
A3. Forensic service reviews request → Accept / Return / Reject if local policy allows.
A4. Create AF and link existing HN/encounter.
A5. Verify deceased identity and HN↔AF relationship; HN-link approval requirement = LOCAL POLICY/TBD.
A6. Assign responsible forensic physician using local roster/coverage model where applicable.
A7. Register investigator/informant/context.
A8. Receive body into forensic/mortuary custody; record location/time/staff.
A9. Forensic physician reviews clinical history.
A10. Perform forensic/post-mortem examination.
A11. Before Lab/Radiology/CT, verify valid HN/VN/Encounter/order context required by downstream system.
A12. Collect/label/transfer specimens/evidence with traceable custody where applicable.
A13. Review results and complete medico-legal report workflow.
A14. Record mortuary services/costs with confirmed billing context.
A15. Store/move body with location history.
A16. Print / hand over report with recipient traceability.
A17. Verify authority/identity/supporting documents for body release.
A18. Record disposition, close case and include in statistics.

### Material Distinctions
- Existing HN/encounter available.
- Historical clinical data can be referenced.
- AF and clinical encounter remain distinct source-of-truth contexts.

---

# 3. Scenario B — External Death / Body Brought from Outside Hospital

### Entry Trigger
Police/authorized external party/relevant service requests or brings a deceased person from outside hospital.

### Reference Flow
B1. Receive external request and requester authority/document context.
B2. Review request → Accept / Return / Reject if local policy permits.
B3. Create AF as primary forensic case identifier.
B4. Record known/unknown identity, place found, circumstances, police/investigator/informant.
B5. Receive body + identity evidence + receiving staff/time/location.
B6. Search for possible existing HN only when identifying data makes this appropriate; historical HN may be linked for review after match governance.
B7. If HN candidate found, Link/Approve/Reject Match according to Hospital Policy; preserve audit and reversible unlink/correction.
B8. If no HN exists, AF remains case anchor. Whether a new HN/encounter/VN must be created for clinical orders is LOCAL INTEGRATION POLICY/TBD.
B9. Assign forensic physician / duty coverage.
B10. Perform forensic/post-mortem examination.
B11. If Lab/Radiology/CT is required, establish valid order context first; do not assume AF-alone ordering is accepted by downstream systems.
B12. Collect/label/transfer specimens/evidence with Chain of Custody where applicable.
B13. Review results and complete report.
B14. Record mortuary cabinet/movement/services/costs with scenario-specific finance path.
B15. Hand over report to authorized recipient.
B16. Verify body release recipient/authority; support relative/foundation/unclaimed-body route as applicable.
B17. Record disposition/closure/statistics.

### Material Distinctions
- HN may be absent at entry.
- AF is primary case anchor.
- Historical HN linking and new HN/VN/encounter creation are separate decisions.
- Unknown identity/later correction can be material.

---

# 4. Scenario C — Forensic OPD / Living Patient

### Entry Trigger
Living patient presents/referred for forensic clinical assessment, injury documentation, sexual-assault/violence-related examination or other medico-legal service.

### Reference Flow
C1. Receive/referral/request and identify requester/source.
C2. Review intake → Accept / Return / Redirect/Reject if local service criteria permit.
C3. Identify patient using HN/VN/Encounter; create valid visit context before orders/documentation according to HIS policy.
C4. Apply sensitive-name masking/restricted queue behavior if Hospital Privacy Policy requires it.
C5. Establish attending/consult/forensic physician access relationship.
C6. Assign responsible forensic physician / roster where relevant.
C7. Review relevant clinical history.
C8. Perform forensic examination/injury documentation.
C9. Capture restricted photographs/documents/evidence.
C10. Order Lab/Radiology using HN/VN/Encounter source of truth.
C11. Draft/review/finalize forensic report/certificate according to hospital policy.
C12. Print/handover with recipient/contact/supporting-document traceability.
C13. Maintain restricted longitudinal record/audit/history.

### Material Distinctions
- Person is alive and remains in normal clinical HN/VN context.
- Clinical Forensic Medicine is a valid forensic service branch.
- Permission/name masking may be stricter than ordinary OPD.

---

# 5. Cross-Scenario Control Baseline
1. Request/Referral Source + requester authority.
2. Accept / Reject / Return-for-information lifecycle.
3. Living vs deceased case classification.
4. AF/HN/VN/Encounter identity and source-of-truth.
5. HN link/unlink/correction governance and approval question.
6. Physician duty roster/assignment/handover.
7. Diagnostic order context and downstream identifiers.
8. Chain of Custody for relevant specimens/evidence/media/documents.
9. Forensic photography/media access/integrity.
10. Report author/reviewer/final/amend/print/handover.
11. Mortuary receive/store/move/release identity checks.
12. Finance/charging/reversal by scenario.
13. Sensitive identity masking/confidentiality/access audit.
14. Correction/cancellation/reversal/history.
15. Downtime/manual continuity only when material to project scope.

---

# 6. Standards Overlay Guidance
## HA
Use current applicable HA edition to review quality/safety, identification, information/record governance, confidentiality/information security, diagnostic process and continuity/handoff. Do not infer exact UI fields solely from HA principles.

## JCI
If applicable/selected, use current Hospital standards relevant to patient safety, information/medical records, healthcare technology/EHR/cybersecurity, governance and clinical/service processes. Do not claim exact clause compliance without verified source/applicability.

## CIFS / MOPH
Use to strengthen domain completeness for living forensic patients, autopsy/post-mortem, evidence integrity, Chain of Custody, forensic photography and specimen handling. Do not copy organizational workflow as this hospital's exact process.

---

# 7. Blueprint / Mockup Coverage Rule
Forensic Blueprint must classify Scenario A, B and C as `IN SCOPE / OUT OF SCOPE / PARTIAL / TBD`.

If IN SCOPE, UI Factory must provide a playable end-to-end case path and Smoke Test it separately.

For every in-scope scenario, mockup must also demonstrate where relevant:
- Request source;
- Accept/Reject/Return path;
- case identifier context;
- physician assignment/roster;
- order-context rule;
- finance route;
- sensitive-name behavior;
- HN-link governance.

A mockup that shows only examination/report tabs but omits intake, ownership, order context and closure is not a complete forensic workflow review.