# Gorilla HIS — Forensic Medicine / Mortuary Standard Flow Baseline v1.2

Status: `REFERENCE BASELINE — NOT HOSPITAL CONFIRMED`

Purpose: provide a Thailand-aware, source-backed workflow baseline for forensic/autopsy/mortuary/clinical-forensic analysis before Hospital Requirement and standards overlay.

## Authority / Evidence Notes
Primary source families:
1. Thailand Ministry of Public Health (MOPH) official forensic/post-mortem manuals and `คู่มือการตรวจผู้ป่วยคดี`.
2. Central Institute of Forensic Science (CIFS), Ministry of Justice — official forensic pathology, scene examination, clinical forensic, evidence/custody, unidentified-body and service material.
3. Office of Justice Affairs / Justice Channel — public explanation of medico-legal death categories/process; exact current legal effect must be verified against current law.
4. HAI current applicable Hospital and Healthcare Standards.
5. JCI current Hospital standards only when applicable/selected.
6. Hospital-approved Forensic/Mortuary SOPs/forms/finance/privacy policy for local truth.

Do not copy external agency workflow as hospital-local workflow. Record source retrieval/verification date in each Blueprint run.

# 1. Thai Forensic Entry Classification — Mandatory
Before Request/Registration, determine whether the workflow requires a medico-legal classification/trigger.

Challenge at least:
- living vs deceased;
- internal hospital vs external origin;
- suspected natural vs suspected unnatural/cause-not-apparent route;
- public Thai guidance categories for unnatural death: suicide, caused by another person, animal-related death, accident, cause not apparent;
- death while in official custody/control as a materially distinct authority route;
- known vs unknown identity;
- scene examination performed by hospital vs already performed externally vs not in hospital scope;
- body sent vs not sent for further autopsy/post-mortem examination;
- autopsy vs external examination only.

These are reference classifications. Exact local codes, legal decision maker and authority require current legal/Hospital verification.

# 2. Mandatory Forensic Lifecycle Challenge
Every run explicitly dispositions:
FLC-01 Living / Deceased
FLC-02 Medico-legal death classification / trigger
FLC-03 Scene examination applicability and scene-to-hospital handoff
FLC-04 Request / Referral Origin + authority/document/reference
FLC-05 Accept / Reject / Return / Redirect
FLC-06 AF / HN / VN / Encounter / provisional identity
FLC-07 HN Link Governance
FLC-08 Physician/team duty roster, assignment, substitute and handoff
FLC-09 Autopsy/examination decision + no-autopsy branch
FLC-10 Diagnostic Order Context
FLC-11 Specimen/Evidence/Property/Media Chain of Custody
FLC-12 Finance / Charging / Payer / Posting / Reversal
FLC-13 Sensitive Identity / Name Masking / Access Audit
FLC-14 Report Draft / Review / Final / Amend / Print / Handover
FLC-15 Body Receive / Store / Move / Release / Disposition
FLC-16 Unknown/Unidentified → identified/corrected lifecycle
FLC-17 Custodial/special-authority route relevance
FLC-18 External scientific testing / result return
FLC-19 Exception / downtime / correction
FLC-20 Closure / statistics / source definitions

Any applicable silent omission = Quality Gate FAIL.

# 3. Scenario A — Death Occurring Inside Hospital / Existing HN
Entry: patient dies in hospital.

Reference Flow:
A1 Death event recorded in clinical context.
A2 Determine whether medico-legal/forensic referral route is triggered; record classification/evidence according to local policy/current authority.
A3 Internal requester submits forensic request/referral.
A4 Forensic intake reviews → Accept / Return / Reject / Redirect if local policy permits.
A5 Create AF and link existing HN/encounter; verify identity and relationship.
A6 Assign forensic physician/team according to local coverage.
A7 Receive body into custody; record positive identity, staff, time, location.
A8 Determine examination/autopsy route; do not assume every forensic case is autopsied.
A9 Review clinical history and perform relevant examination.
A10 Before Lab/Radiology/CT verify valid HN/VN/Encounter/order context.
A11 Collect/label/transfer specimens/evidence/property with custody where applicable.
A12 Review results and complete report lifecycle.
A13 Mortuary storage/movement/services/finance.
A14 Controlled report handover.
A15 Verify recipient authority/identity/supporting documents and release/disposition.
A16 Close case/statistics.

# 4. Scenario B — External Death / Body Brought from Outside Hospital
Entry: external request/referral/body transfer.

Reference Flow:
B1 Capture external notification/requester/authority/document/incident context.
B2 Capture medico-legal classification and whether scene examination has already occurred.
B3 If hospital provides scene service and case begins before body transfer, branch to Scenario D.
B4 Intake reviews → Accept / Return / Reject / Redirect.
B5 Create AF as primary case anchor.
B6 Record known/unknown/provisional identity, place/circumstance, investigator/informant.
B7 Receive body + identity evidence + custody.
B8 Search possible historical HN only when appropriate; apply match/link/unlink/correction governance.
B9 Assign forensic physician/team.
B10 Determine external examination vs autopsy/post-mortem route.
B11 If Lab/Radiology/CT required establish valid downstream order context first.
B12 Collect/transfer specimens/evidence/property/media with custody.
B13 Results → report lifecycle.
B14 Mortuary cabinet/movement/services/finance.
B15 Controlled report handover.
B16 Verify body recipient/authority; relative/foundation/unclaimed route as applicable.
B17 Disposition/closure/statistics.

# 5. Scenario C — Forensic OPD / Living Patient
Entry: living patient presents/is referred for medico-legal assessment.

Reference Flow:
C1 Receive/referral/request and source/authority/context.
C2 Intake eligibility → Accept / Return / Redirect / Reject if local criteria permit.
C3 Identify patient using HN/VN/Encounter.
C4 Apply sensitive queue/name masking if local privacy policy requires.
C5 Establish attending/consult/forensic physician relationship and assignment.
C6 History + forensic examination/injury documentation.
C7 Restricted photographs/documents/evidence and custody where applicable.
C8 Lab/Radiology using valid encounter.
C9 Draft/review/finalize report/certificate.
C10 Controlled print/handover with recipient/contact/document traceability.
C11 Restricted longitudinal record/audit/closure.

# 6. Scenario D — Scene Examination → Disposition Decision
Activate only when hospital scope includes scene/post-mortem examination outside the hospital.

D1 Receive notification/request from authorized source.
D2 Validate incident/location/requester/contact/reference.
D3 Assign physician/team and record availability/handoff.
D4 Travel/arrive at scene; record timestamps/location/team.
D5 Verify/record identity status and circumstances.
D6 Perform scene/external post-mortem examination and permitted documentation/photography/evidence activity.
D7 Decision: body NOT sent for further autopsy vs body SENT for autopsy/post-mortem examination.
D8A Not sent: authorized body disposition/handover + report/record + close relevant scene episode.
D8B Sent: create/continue forensic case, body transfer/referral documentation + custody → Scenario B/autopsy path.

Official CIFS service material demonstrates this scene → send/not-send → autopsy-room → specimen/evidence → scientific examination → report lifecycle. Hospital applicability must be confirmed.

# 7. Scenario E — Unknown / Unidentified Deceased
E1 Create provisional identity under AF.
E2 Capture distinguishing/identity evidence per hospital scope.
E3 Maintain body/evidence/report linkage to provisional identity.
E4 Identity candidate discovered.
E5 Review/verify identity according to local authority/process.
E6 Controlled correction/link to patient identity/HN where applicable.
E7 Preserve before/after audit and prevent orphaned orders/results/reports.
E8 Continue normal disposition/handover.

# 8. Scenario F — Custodial / Special Authority Death
Activate only when relevant. Do not invent local legal workflow.

F1 Detect special authority/custodial trigger.
F2 Record authority/reference/context.
F3 Apply current-law/local-SOP actor and notification requirements after verification.
F4 Preserve separate decision/handoff/audit path.
F5 Continue examination/report/disposition only under confirmed authority model.

# 9. Cross-Scenario Controls
1. Classification/trigger before workflow.
2. Request/referral source + authority.
3. Accept/Reject/Return/Redirect.
4. Living/deceased and internal/external/scene branch.
5. AF/HN/VN/Encounter/provisional identity.
6. HN link/unlink/correction.
7. Physician/team assignment/handoff.
8. Autopsy/no-autopsy decision.
9. Diagnostic order context.
10. Body/specimen/evidence/property/media custody.
11. Report lifecycle.
12. Mortuary movement/release positive identity.
13. Finance/reversal.
14. Sensitive access/masking/audit.
15. External testing/result return.
16. Unknown identity correction.
17. Exception/downtime/reconciliation.
18. Closure/statistics definitions.

# 10. Standards Overlay
Thai domain authority first; HA/HAI for applicable quality/information/privacy/safety; JCI only when applicable/selected. Do not infer local fields/roles/retention from general standards.

# 11. Blueprint / Mockup Coverage Rule
Blueprint must classify Scenarios A-F as `IN SCOPE / OUT OF SCOPE / PARTIAL / TBD` with reason/evidence.

For every in-scope material scenario UI Factory must provide a playable path from the real operational Entry and demonstrate the relevant classification/decision gate, actor/owner, identifier context, custody/order/finance/privacy controls, exception and meaningful end state.

A mockup that begins at a pre-created AF case while the real domain begins at death classification/notification/request is incomplete when that upstream stage is in scope.