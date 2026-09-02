# Gorilla HIS — Forensic Medicine Domain Knowledge Pack v1.0

Status: `REFERENCE DOMAIN KNOWLEDGE — NOT HOSPITAL CONFIRMED`

## Domain Overview
Covers three materially different branches:
1. deceased forensic case originating inside hospital;
2. deceased forensic case originating outside hospital;
3. living forensic patient / Clinical Forensic Medicine.

Use together with `domain-baselines/FORENSIC_STANDARD_FLOW_BASELINE.md` and `universal-analysis/UNIVERSAL_WORKFLOW_CHALLENGE.md`.

## Standard Workflow Summary
### Internal deceased
Death/Referral → Request review → Accept/Return/Reject → AF creation/link HN/encounter → identity verification → physician assignment → receive body → examination → valid diagnostic order context → evidence/specimen custody → report → finance/mortuary → report/body handover → closure.

### External deceased
External request/body arrival → requester/authority review → Accept/Return/Reject → AF as primary case ID → identity/body receipt → historical HN search/match when appropriate → HN-link governance → physician assignment → examination → create valid HN/VN/Encounter if required for downstream orders → custody/results/report → finance/mortuary → release/disposition → closure.

### Living forensic patient
Referral/request → intake decision → HN/VN/Encounter → sensitive queue/access → responsible physician → forensic examination/photo/evidence → Lab/Radiology orders → report/certificate → controlled handover → longitudinal restricted record.

## Role Matrix — Reference
Potential roles, activate only when relevant/local evidence supports them:
- Internal referring physician/unit/ER/Ward
- Forensic staff/intake
- Forensic physician
- HIM/Registration for identity/HN governance
- Lab/Radiology
- Mortuary staff
- Finance/Billing
- Investigator/authorized external requester
- Relative/foundation/authorized recipient
- Privacy/Security/Audit oversight

Exact authority remains Hospital Policy/TBD unless confirmed.

## Scenario Catalog
- F-S01 Internal hospital death with existing HN/encounter.
- F-S02 External deceased with no HN at intake.
- F-S03 External deceased with historical HN candidate.
- F-S04 Unknown identity later identified/corrected.
- F-S05 Living forensic patient.
- F-S06 Sensitive living case requiring restricted identity/media handling.
- F-S07 Request returned/rejected.
- F-S08 Diagnostic order requiring creation/correction of encounter context.
- F-S09 Body/report handover exception or correction.

## Data / Source of Truth
- AF = forensic case identifier; does not automatically replace HN/VN/Encounter.
- Historical HN link and new clinical order encounter are separate concepts.
- HN-link approval is not universally mandated; wrong-link risk makes governance a mandatory hospital confirmation question.
- Do not show AF-only production ordering unless downstream integration contract confirms it.
- Body location/custody, evidence custody, report version/finalization and billing posting each require explicit source-of-truth ownership.

## Integration Map
Potential integrations: Patient Master/HIM, Registration/ADT, LIS, RIS/PACS, Billing/Finance, Document/Media repository, Audit/Identity services. Exact interfaces are Hospital/Project evidence, not assumed.

## Finance Impact
Challenge payer, HN/VN/AF context, chargeable vs internal-cost/non-charge, quantity/time basis, waive/exempt, posting, cancellation/refund/reversal, and external-authority route.

## Privacy / Security
Challenge masked worklists, role-based reveal, restricted photos/documents, print/export/download, access audit and sensitive living cases. Exact masking/reveal/break-glass policy requires hospital confirmation.

## Standards / Authority Families
- Thailand MOPH official forensic/post-mortem manuals/guidance.
- CIFS official forensic pathology/clinical forensic/evidence/custody material.
- Current applicable HA/HAI standards.
- JCI Hospitals current edition only when applicable/selected benchmark.
- Thai law/regulation only when exact current authority/applicability is verified.
- Hospital SOP/forms/policies remain required for local operational truth.

## Expert Challenge Checklist
Every forensic run explicitly challenges:
1. living vs deceased population;
2. request/referral origin;
3. Accept/Reject/Return/Redirect;
4. AF/HN/VN/Encounter identity;
5. HN match/link/unlink/correction governance;
6. physician roster/assignment/handoff;
7. diagnostic order context;
8. finance/payer/posting/reversal;
9. sensitive identity/name/media handling;
10. chain of custody;
11. report author/review/final/amend/print/handover;
12. body receive/store/move/release;
13. exceptions and closure.

If an applicable item is absent from Blueprint analysis without N/A/reason, Quality Gate FAIL.
