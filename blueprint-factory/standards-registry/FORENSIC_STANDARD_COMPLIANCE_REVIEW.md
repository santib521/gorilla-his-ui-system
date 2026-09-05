# Gorilla HIS — Forensic Standard Compliance Review v1.0

Purpose: mandatory domain review when a Blueprint includes forensic medicine, medicolegal examination, autopsy/post-mortem, mortuary/body custody, forensic evidence/specimen, forensic photography, forensic report handover, or forensic OPD.

This review is additive to the Blueprint Factory. It MUST NOT bypass Hospital Truth, Domain Activation, Relevance Gate, Evidence Assurance, Independent Challenge, or Confirmation Value Gate.

## Mandatory Ordering
`Hospital Truth → Domain Activation → Candidate Gap → Relevance Gate → Forensic Standard Compliance Review → Evidence Assurance → Independent Challenge → Confirmation Value Gate → Quality Gate`

A forensic source may strengthen an already-relevant issue. It MUST NOT manufacture scope or silently turn a recommended forensic control into Hospital Confirmed.

## Authoritative Source Priority
1. Hospital-approved forensic policy / SOP / TOR / workflow — Level A.
2. Thai law / official regulator / Ministry of Public Health / Institute of Forensic Science / Healthcare Accreditation Institute — Level B when exact requirement and applicability are verified.
3. Official professional/national guidance — Level C unless it is proven mandatory for the hospital.
4. Established forensic/HIS practice — Level D.
5. Expert reasoning — Level E.

Do not use Wikipedia, social media, vendor pages, AI memory, search snippets, or general educational pages as proof of a formal forensic requirement.

## Current Thai Source Baseline — verified 2026-09-02
### Institute of Forensic Science (CIFS), Ministry of Justice
- `คู่มือการให้บริการงานชันสูตรศพ`, document SD-FSP-007, issue date 25 September 2025.
- Official CIFS publication describes medicolegal autopsy service, identity/cause-of-death purpose, relevant unnatural-death context, service steps, required documents and report/contact process.
- Use as Level B/C according to the exact claim and demonstrated applicability. Do not infer that CIFS internal workflow is automatically the hospital's workflow.

### Institute of Forensic Science — Mortuary Staff / Prosector guidance
- Official CIFS mortuary/prosector manual published in 2026.
- Relevant verified topics include direct supervision by forensic physician, evidence integrity, chain of custody, forensic photography, specimen/evidence handling and biosafety.
- Use to support relevance of custody/integrity/supervision controls. Exact hospital checkpoints/fields remain Hospital Policy / NEEDS VERIFICATION unless explicitly mandated by an applicable authority.

### Ministry of Public Health — Health Administration Division
- Official download catalogue includes `คู่มือการดำเนินงานชันสูตรพลิกศพ` and `คู่มือการปฏิบัติงานนิติเวช (สำหรับแพทย์และบุคลากรทางการแพทย์)`.
- The catalogue also records an updated post-mortem operations manual procurement/publication in 2018.
- Use the newest accessible official edition applicable to the hospital; do not assume an older manual is current when a later official edition exists.

### Thailand HA / HAI
- Hospital and Healthcare Standards, 6th Edition: HAI states it becomes effective for accreditation assessment from 1 October 2026.
- Before 1 October 2026, record the transition state and verify which edition applies to the hospital's assessment/go-live date.
- HA can support governance, patient/process safety, medical records/information and privacy/accountability topics when relevant; it does not define a forensic UI or automatically create a forensic function.

## Mandatory Forensic Review Dimensions
Activate only where traceable to the supplied forensic workflow or a direct material dependency.

1. **Case / Deceased Identity**
   - case identifier (e.g. AF) uniqueness, lifecycle, duplicate/concurrency, void/reissue;
   - HN ↔ forensic-case relationship and external-body/no-HN handling;
   - positive identity checkpoints where the workflow receives, moves, examines, stores or releases a body.

2. **Body Custody / Mortuary Movement**
   - receive, cabinet assignment, move, temporary removal, return and release;
   - actor + date/time + from/to location + reason where material;
   - mismatch, unknown/unidentified body, unavailable cabinet, conflicting occupancy and correction behavior.

3. **Evidence / Specimen Chain of Custody**
   - evidence/specimen/photo/document identity;
   - collection/receipt/transfer/handover actor and time;
   - from/to custody, reason/purpose, condition/seal where hospital policy requires it;
   - correction must preserve history rather than silently overwrite material custody events.

4. **Forensic Photography / Media Integrity**
   - case association, uploader/creator, timestamp and access control;
   - image evidence integrity and required case/scale metadata when applicable to the hospital workflow;
   - export/download/print/disclosure and audit policy.

5. **Autopsy / Examination Record Governance**
   - author/reviewer/supervisor where applicable;
   - draft/final/amended/superseded semantics;
   - signature/finality only when hospital/legal policy is verified;
   - no silent overwrite of a finalized forensic report.

6. **Diagnostic Order / Result Source of Truth**
   - HN/AF/encounter/order/specimen/result identifiers;
   - external deceased without HN;
   - cancellation, correction and amended result linkage;
   - LIS/RIS/PACS transmission only when interface behavior is confirmed.

7. **Sensitive Access / Disclosure**
   - forensic case/photo least-necessary access;
   - attending/consult/forensic physician relationship source where applicable;
   - print/export/download/handover audit;
   - recipient authorization and identity verification are hospital/legal-policy decisions.

8. **Body / Report Release**
   - release authority;
   - recipient identity, relationship/agency, supporting documents and contact;
   - unclaimed-body/foundation/burial route when supplied;
   - do not invent legal authority or mandatory dual-check rules without evidence.

9. **Financial / Service Records**
   - chargeable vs non-charge internal cost;
   - HN/AF relationship;
   - Billing/ERP source of truth, posting and reversal only if directly in scope.

10. **Statistics / Reporting Definitions**
   - numerator/denominator, case classification, time band, autopsy status, preservation method and revenue basis;
   - prevent management/statutory statistics from relying on ambiguous derived states.

## Mandatory Compliance Matrix in Forensic File 2
For every surviving forensic compliance item include:
`Review Dimension | Trace to REQ/WF/FN | Source | Assurance Level | Verified Topic | Applicability | Current Coverage | Gap/Recommendation | Hospital Confirmation Needed | Owner | Timing`

Coverage values:
- `COVERED — HOSPITAL CONFIRMED`
- `COVERED — RECOMMENDATION ONLY`
- `PARTIAL`
- `GAP`
- `N/A / SUPPRESSED`

## Hard Rejects
Reject the analysis when any of the following occurs:
1. a forensic legal/standard claim is made from Wikipedia/social media/general web content;
2. CIFS/MOPH/HA guidance is copied into Hospital Truth without explicit hospital confirmation;
3. chain of custody is claimed complete without identifying the actual custody checkpoints relevant to the workflow;
4. body release is treated as safe without unresolved identity/authority issues being surfaced;
5. forensic photo/document access is treated like ordinary OPD access despite an explicit restricted-access requirement;
6. real LIS/RIS/PACS, billing, report finality/signature, or external-agency effect is invented;
7. a source is used to create an irrelevant GAP that fails the Relevance Gate.

## Prototype Rule
A forensic Blueprint may be `PROTOTYPE READY` with unresolved production controls only when unsafe effects are explicitly contained in the Blueprint and traceability documents. The mockup may look production-realistic, but documentation must preserve the distinction between a prototype interaction and a confirmed production rule.

## Dev Handoff Rule
`READY FOR DEV HANDOFF` requires explicit resolution/confirmation of every Critical forensic identity/custody/release gap and every High source-of-truth/permission/report-governance gap that materially changes production behavior.
