# Gorilla HIS — Forensic Medicine Domain Knowledge Pack v1.1

Status: `REFERENCE DOMAIN KNOWLEDGE — NOT HOSPITAL CONFIRMED`

## 1. Domain Overview
Forensic Medicine is not only a mortuary/autopsy application. In Thailand the domain can span medico-legal death classification, scene/post-mortem examination, body/specimen/evidence custody, forensic pathology, living clinical forensic cases, medico-legal reports, investigator/public-agency handoff, body disposition and restricted longitudinal records.

This Pack covers at least:
1. deceased forensic case originating inside hospital;
2. deceased case originating outside hospital;
3. scene examination / decision whether body proceeds for further post-mortem examination when applicable;
4. living forensic patient / Clinical Forensic Medicine;
5. unknown/unidentified deceased and later identification;
6. sensitive evidence/report/body handoff.

Use with `domain-baselines/FORENSIC_STANDARD_FLOW_BASELINE.md` and `universal-analysis/UNIVERSAL_WORKFLOW_CHALLENGE.md`.

## 2. Thai Authoritative Domain Basis
Primary evidence families:
- Thailand MOPH official forensic/post-mortem manuals including `คู่มือชันสูตรพลิกศพ 2561` and `คู่มือการตรวจผู้ป่วยคดี`.
- Central Institute of Forensic Science (CIFS), Ministry of Justice: forensic pathology, clinical forensic, scene/post-mortem service, evidence/custody, unidentified body and service workflow material.
- Office of Justice Affairs / Justice Channel for public legal-process explanation; exact legal conclusions still require current legal verification.
- Current applicable HA/HAI standards for quality, identification, information/privacy/security and continuity.
- JCI Hospitals only when hospital applies/seeks JCI or explicitly selects it as benchmark.
- Hospital SOP/forms/policies remain mandatory for local truth.

Do not copy external agency workflow directly into Hospital Confirmed workflow.

## 3. Thai Medico-Legal Death Classification Challenge — Mandatory
Before designing deceased workflow, explicitly determine whether the case is within a medico-legal/post-mortem route and what classification changes the process.

Thai public legal guidance identifies unnatural death categories including:
1. suicide;
2. death caused by another person;
3. death caused by an animal;
4. accidental death;
5. death where the cause is not yet apparent.

A separate material branch is death while in official custody/control under the law/court order.

These classifications are **REFERENCE LEGAL/OPERATIONAL CONTEXT**, not automatic hospital dropdown values. Exact coding, wording, decision authority and legal applicability must be verified against current law and Hospital SOP before production.

For every deceased case challenge:
- natural / suspected unnatural / cause not apparent / custodial-special route;
- who makes/records the initial classification;
- what evidence/reference supports it;
- whether scene examination is involved;
- whether body proceeds for further autopsy/post-mortem examination;
- who decides/requests the next stage;
- whether investigator/other authority must participate;
- how classification may be corrected and audited.

## 4. Scene-to-Disposition Lifecycle — Reference
Official CIFS service material demonstrates a materially broader lifecycle than a mortuary-only flow:
`Notification → Police/authorized request context → Scene post-mortem examination → Decision: body not sent vs sent for autopsy → if sent, request/referral/body documentation → autopsy room examination → specimen/evidence/property collection and custody → scientific examination/results → medico-legal report to investigator/requester → body/report disposition`.

Hospital applicability varies. The Factory must ask whether the hospital:
- performs scene examination;
- only receives bodies after scene examination;
- receives referrals from another authority;
- decides whether autopsy is performed;
- performs only mortuary storage for some cases;
- manages evidence/property or only specimens;
- sends tests externally;
- reports to investigator or another authorized requester.

## 5. Standard Workflow Summary
### 5.1 Internal deceased
Death/clinical event → medico-legal classification/referral decision → internal request → Accept/Return/Reject/Redirect → AF creation/link HN/encounter → positive identity → physician assignment → receive body → examination/autopsy decision → valid diagnostic order context → specimen/evidence/property custody → results → report lifecycle → finance/mortuary → report/body handover/disposition → closure.

### 5.2 External deceased
External notification/request/body arrival → requester/authority/document review → case classification + scene/referral context → Accept/Return/Reject/Redirect → AF as case anchor → identity/body receipt → historical HN search/match when appropriate → HN-link governance → physician assignment → examination/autopsy → valid HN/VN/Encounter if required for downstream orders → custody/results/report → finance/mortuary → release/disposition → closure.

### 5.3 Scene examination branch when hospital provides it
Notification → requester/incident context → team/physician assignment → travel/scene arrival → scene identity/circumstance documentation → external examination → evidence/photography where within service scope → decision whether body is sent for further examination → if not sent, authorized disposition/handover → if sent, referral/body transfer with traceable custody → autopsy workflow.

### 5.4 Living forensic patient
Referral/request → eligibility/intake → HN/VN/Encounter → sensitive queue/access → responsible physician → forensic history/examination/injury documentation/photo/evidence → Lab/Radiology → report/certificate → controlled handover → restricted longitudinal record.

## 6. Role Matrix — Reference
Potential roles; activate only when relevant/local evidence supports them:
- Internal referring physician/unit/ER/Ward
- Forensic staff/intake
- Forensic physician / forensic pathology physician
- Scene examination team where applicable
- HIM/Registration
- Lab/Radiology/other scientific testing service
- Mortuary staff
- Finance/Billing
- Investigator/police/authorized public-agency requester
- Evidence/property custodian where applicable
- Relative/foundation/authorized body recipient
- Authorized report recipient
- Privacy/Security/Audit oversight

Exact legal/operational authority remains Hospital Policy/current-law verification/TBD unless confirmed.

## 7. Scenario Catalog
- F-S01 Internal hospital death with existing HN/encounter.
- F-S02 External deceased with no HN at intake.
- F-S03 External deceased with historical HN candidate.
- F-S04 Unknown identity later identified/corrected.
- F-S05 Living forensic patient.
- F-S06 Sensitive living case requiring restricted identity/media handling.
- F-S07 Request returned/rejected/redirected.
- F-S08 Diagnostic order requiring creation/correction of encounter context.
- F-S09 Body/report handover exception/correction.
- F-S10 Scene examination → body not sent for further autopsy.
- F-S11 Scene examination → body sent for autopsy/post-mortem examination.
- F-S12 Custodial/special medico-legal death route requiring special authority review.
- F-S13 Evidence/specimen/property transfer with Chain of Custody.
- F-S14 Unidentified deceased → later identity established → controlled correction.

## 8. Identity / Data / Source of Truth
- AF = forensic case identifier; does not automatically replace HN/VN/Encounter.
- Historical HN link and new clinical order encounter are separate concepts.
- Provisional/unknown identity must support controlled later identification/correction when relevant.
- HN-link approval is not universally mandated; wrong-link risk makes governance a mandatory hospital confirmation question.
- Do not show AF-only production ordering unless downstream integration contract confirms it.
- Body location/custody, evidence/specimen/property custody, report version/finalization and billing posting require explicit source-of-truth ownership.
- Scene event, request/referral, body receipt and autopsy episode may be distinct records; do not silently collapse them.

## 9. Evidence / Specimen / Property Custody
Challenge separately:
- body custody;
- specimen custody;
- physical evidence custody;
- personal property custody;
- forensic photographs/media integrity;
- external laboratory/scientific testing handoff.

For applicable objects challenge receive/collect, label, seal/container, collector, date/time/location, transfer, sender/receiver, condition, storage, return/release/disposition, correction and audit.

Exact barcode/seal/signature requirements are local policy unless verified.

## 10. Autopsy / Examination Decision
Do not assume every forensic deceased case is autopsied. Determine:
- external examination only vs autopsy/post-mortem examination;
- who requests/decides according to applicable authority/local workflow;
- reason/status;
- required documentation;
- effect on specimen collection/report/body disposition/statistics.

## 11. Report Lifecycle
Challenge:
- author;
- reviewer;
- finalizer/signatory;
- draft/review/final/amend/correct;
- version retention;
- print/reprint reason and audit;
- recipient authority;
- report handover evidence;
- report to investigator/requesting authority where applicable.

## 12. Body Receive / Store / Move / Release
Challenge positive identification at every material movement:
`Receive → Cabinet/Location → Move → Examination transfer → Return to storage → Ready for release → Recipient verification → Release/Disposition`.

Include unidentified body, unclaimed body/foundation route and wrong-location/wrong-identity correction where relevant.

## 13. Integration Map
Potential integrations: Patient Master/HIM, Registration/ADT, LIS, RIS/PACS, Billing/Finance, Document/Media repository, Audit/Identity, external scientific testing, evidence/property registry where applicable. Exact interfaces are Hospital/Project evidence.

## 14. Finance Impact
Challenge payer, HN/VN/AF context, chargeable vs internal-cost/non-charge, quantity/time basis, waive/exempt, posting, cancellation/refund/reversal, and external-authority route.

## 15. Privacy / Security
Challenge masked worklists, role-based reveal, restricted photos/documents, print/export/download, access audit, sensitive living cases, unidentified/custodial/high-profile cases where relevant. Exact masking/reveal/break-glass policy requires hospital confirmation.

## 16. Statistics / Management Information
Do not stop at counts requested by TOR. Challenge definition/source for:
- scene examinations;
- bodies sent/not sent for further examination where applicable;
- autopsy vs external examination;
- medico-legal death classification;
- unidentified/identified cases;
- specimen/evidence testing;
- turnaround time from request to report;
- report handover;
- mortuary services and revenue;
- monthly/quarterly/annual aggregation.

Only include metrics relevant to hospital scope.

## 17. Expert Challenge Checklist — Mandatory
Every forensic run explicitly challenges and dispositions:
1. living vs deceased population;
2. medico-legal death classification / trigger;
3. scene examination applicability;
4. request/referral origin and authority;
5. Accept/Reject/Return/Redirect;
6. AF/HN/VN/Encounter/provisional identity;
7. HN match/link/unlink/correction governance;
8. physician/team roster/assignment/handoff;
9. autopsy/examination decision and no-autopsy branch;
10. diagnostic order context;
11. specimen/evidence/property/media Chain of Custody;
12. finance/payer/posting/reversal;
13. sensitive identity/name/media handling;
14. report author/review/final/amend/print/handover;
15. body receive/store/move/release/disposition;
16. unknown/unidentified body lifecycle;
17. custodial/special authority branch relevance;
18. external scientific testing/result return;
19. exceptions/downtime/correction;
20. closure/statistics/source definitions.

If an applicable item is absent without N/A/reason, Quality Gate FAIL.

## 18. Source Verification Notes
At each run record retrieval date and authoritative URL. Current known source families include MOPH PHDB forensic manuals, CIFS official service/manual pages, CIFS Open Data for real service categories, Office of Justice Affairs legal-process education, HA/HAI and applicable JCI.

Never call a legal classification/current requirement verified solely from this repository text; re-verify current authority when it affects Critical/High legal behavior.