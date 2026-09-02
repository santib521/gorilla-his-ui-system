# Gorilla HIS — Forensic Medicine / Mortuary Standard Flow Baseline v1.0

Status: `REFERENCE BASELINE — NOT HOSPITAL CONFIRMED`

Purpose: provide a source-backed starting workflow for forensic/autopsy/mortuary analysis before overlaying Hospital Requirement and HA/JCI/privacy/security considerations.

## Authority / Evidence Notes
Use current official sources where available and record retrieval/verification date in each Blueprint run.

Primary source families:
1. Thailand Ministry of Public Health (MOPH) — official forensic/post-mortem practice manuals and guidance, including the published `คู่มือการดำเนินงานชันสูตรพลิกศพ` and `คู่มือการปฏิบัติงานนิติเวช (สำหรับแพทย์และบุคลากรทางการแพทย์)` available on the MOPH download portal.
2. Central Institute of Forensic Science (CIFS), Ministry of Justice — current official forensic knowledge/service material, including autopsy support manuals and evidence-handling / Chain of Custody guidance.
3. Healthcare Accreditation Institute (HAI) — current applicable Hospital and Healthcare Standards. HA 6th Edition becomes effective for assessment from 1 October 2026.
4. Joint Commission International — Hospital 8th Edition, effective 1 January 2025, used only where the hospital adopts/seeks JCI and only for relevant patient-safety, records/information, healthcare-technology, governance and related principles.
5. Hospital-approved Forensic/Mortuary SOPs, forms and policies — required to establish actual local workflow, authority, custody checkpoints, report finality and release rules.

Official source locators:
- MOPH forensic manuals: https://phdb.moph.go.th/main/index/downloadlist/53/7
- CIFS evidence service / Chain of Custody: https://eservice.cifs.go.th/index.php?mod=service&page=witness&route=government
- CIFS knowledge base: https://www.cifs.go.th/
- HA standards: https://www.ha.or.th/TH/Contents/มาตรฐานโรงพยาบาลและบริการสุขภาพ%20(HA)
- JCI Hospital 8th Edition overview: https://store.jointcommissioninternational.org/joint-commission-international-standards-for-hospitals-8th-edition/

Do not copy copyrighted standards text into the repository. Store only metadata, principles, workflow implications and verification status.

---

## Scenario A — Death Occurring Inside Hospital / Existing HN

### Entry Trigger
A patient with an existing HN/encounter dies in the hospital and enters the forensic/post-mortem pathway according to hospital/legal criteria.

### Reference Flow
A1. Detect/record death event in hospital clinical context.
A2. Determine/receive forensic referral or post-mortem request according to local authority.
A3. Create/assign forensic case identifier (e.g. AF) and link existing HN/encounter.
A4. Verify deceased identity and preserve HN↔AF relationship.
A5. Register request/investigator/informant/context required for the forensic case.
A6. Receive body into forensic/mortuary custody and record location/time/staff.
A7. Forensic physician reviews clinical history and available investigations.
A8. Perform/document forensic examination / post-mortem examination as applicable.
A9. Create Lab / Radiology / CT or other investigation requests when clinically/forensically required; maintain HN/AF/order/result source-of-truth linkage.
A10. Collect/label/transfer specimens or evidence with traceable custody where applicable.
A11. Review results and complete medico-legal report workflow.
A12. Store body / record mortuary services and movements as applicable.
A13. Print / hand over report with recipient traceability.
A14. Verify authority/identity/supporting documents for body release/disposition.
A15. Record release/disposition, close case status and include case in reporting/statistics.

### Material Distinctions
- Existing HN and hospital encounter are available.
- Historical diagnosis/treatment/lab/radiology data may be referenced.
- Death event and forensic AF record must not silently overwrite each other's source of truth.

---

## Scenario B — External Death / Body Brought from Outside Hospital

### Entry Trigger
Police/authorized external party or relevant service brings/refers a deceased person from outside the hospital for forensic examination/autopsy/mortuary services.

### Reference Flow
B1. Receive forensic request/referral and external case context.
B2. Create AF as primary forensic case identifier.
B3. Record known/unknown identity, place found, preliminary circumstances, police/investigator/informant details.
B4. Record body receipt, identity evidence available, date/time, receiving staff and current location.
B5. If no HN exists, continue forensic workflow using AF as the case anchor; whether/when a hospital HN is created is `LOCAL POLICY / TBD` unless explicitly confirmed.
B6. Perform/document forensic examination / post-mortem examination as applicable.
B7. Request Lab/Radiology/CT using an explicitly defined AF/HN/encounter/order linkage model; no silent assumption that HN exists.
B8. Collect/label/transfer specimens/evidence with traceable Chain of Custody where applicable.
B9. Review results and complete medico-legal report workflow.
B10. Manage mortuary cabinet/location/movement and relevant services/costs.
B11. Hand over report to authorized recipient with identity/request-document traceability.
B12. Verify authority/identity/supporting documents for body release; support relative/foundation/unclaimed-body path as applicable.
B13. Record disposition and close case; include in statistics.

### Material Distinctions
- HN may be absent at entry.
- AF is the primary case anchor until local policy determines whether an HN/encounter is created/linked.
- Police/investigator/external recipient context is commonly more central.
- Unknown/unidentified deceased and later identity correction/linkage must be considered when relevant.

---

## Scenario C — Forensic OPD / Living Patient

### Entry Trigger
A living patient presents for forensic clinical assessment, injury documentation, sexual-assault/violence-related examination or another medico-legal OPD service within hospital scope.

### Reference Flow
C1. Identify patient using HN/VN/encounter.
C2. Establish access relationship/authorization for attending physician, consulted case physician and forensic physician according to hospital policy.
C3. Review relevant clinical history.
C4. Perform/document forensic clinical examination and injury findings.
C5. Capture/upload forensic photographs/documents with restricted access and audit.
C6. Order relevant diagnostic tests when required, preserving normal clinical source-of-truth and result linkage.
C7. Draft/review/finalize forensic report/certificate according to hospital policy.
C8. Print/handover report/certificate with printer/date/recipient/contact/supporting-document traceability.
C9. Maintain restricted longitudinal record/audit/history.

### Material Distinctions
- Patient is alive and remains within normal clinical HN/VN context.
- Forensic documentation may have medico-legal sensitivity but must not be confused with deceased/mortuary workflow.
- Permission scope may be narrower than ordinary OPD access.

---

## Cross-Scenario Control Baseline
The following are reference control topics and still require relevance + local confirmation:

1. Identity / case linkage: HN, AF, encounter, unknown identity and later correction.
2. Role / authority: who may create, edit, review, finalize, amend, print, hand over, move or release.
3. Chain of Custody: specimens/evidence/documents/media where custody materially affects forensic integrity.
4. Forensic photography/media: case association, uploader, time, access, audit and integrity controls.
5. Diagnostic source of truth: Lab/Radiology/CT order/result IDs and HN/AF/encounter mapping.
6. Report governance: author/reviewer/final/sign/amend/supersede/print/handover history.
7. Mortuary movement: receive/store/move/release location history and identity checks.
8. Release/handover: recipient authority, identity and supporting documents.
9. Correction/cancellation/reversal: identity corrections, order cancellations/result corrections, report amendments, cabinet movement corrections and financial reversals where relevant.
10. Sensitive access/disclosure: minimum necessary access, print/export/download and audit.
11. Downtime/manual continuity: only when material to hospital workflow and current project scope.

---

## Standards Overlay Guidance
### HA
Use the current applicable HA edition to review quality/safety, patient/person identification, information/record governance, diagnostic process, continuity/handoff, privacy/security and organizational controls when relevant. Do not infer UI fields/buttons solely from HA principles.

### JCI
If JCI is applicable/selected by the hospital, use Hospital 8th Edition principles relevant to patient safety, information management/medical records, Healthcare Technology/EHR/cybersecurity, governance and applicable clinical/service processes. Do not claim exact JCI clause compliance without verified licensed source and applicability.

### CIFS / MOPH
Use to strengthen domain workflow completeness, evidence integrity, Chain of Custody, forensic photography, autopsy/post-mortem practice and evidence/specimen handling. Do not copy CIFS/MOPH local organizational workflow as this hospital's exact process.

---

## Blueprint / Mockup Coverage Rule
Forensic Blueprint must classify Scenario A, B and C as `IN SCOPE / OUT OF SCOPE / PARTIAL / TBD` from the supplied requirement.

If a scenario is IN SCOPE, UI Factory must provide a playable end-to-end case path for that scenario, and Functional Smoke Test must execute at least one representative case for the branch.

For the current Gorilla HIS forensic requirement family, both **Scenario A: in-hospital death with HN** and **Scenario B: external death without guaranteed HN** are materially distinct and must not be collapsed into one generic AF case flow. Forensic OPD is a third distinct branch when included by requirement.
