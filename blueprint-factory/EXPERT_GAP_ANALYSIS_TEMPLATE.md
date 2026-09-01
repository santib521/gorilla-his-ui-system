# Gorilla HIS — Template การวิเคราะห์ช่องว่างและข้อเสนอแนะโดยผู้เชี่ยวชาญ v1.3

**Module / Application:**
**Analysis Version:** v0.x
**Related Blueprint:**
**Document Type:** ADVISORY / CHALLENGE ANALYSIS — **ยังไม่ถือเป็น HOSPITAL CONFIRMED**

## 1. Executive Assessment
- Requirement ที่ชัดเจน/แข็งแรง:
- Critical/High gaps ที่ผ่าน Relevance Gate:
- Candidate gaps ที่ Suppress:
- ผลต่อ Prototype:
- ผลต่อ Dev Handoff:

## 2. Domain Classification & Expert Coverage Matrix
| มุมมอง / Agent | สถานะ | เหตุผล / Trigger | ประเด็นที่ตรวจ |
|---|---|---|---|
| Patient/Caregiver | RELEVANT / CONDITIONAL / N/A / NEEDS REVIEW | | |
| Registration/Patient Access | | | |
| Medical Records/HIM | | | |
| Nursing | | | |
| Physician/Clinical | | | |
| ER/IPD/OR/Specialty | | | |
| Pharmacy | | | |
| Lab/Blood Bank | | | |
| Radiology/PACS | | | |
| Allied Health | | | |
| Infection Control | | | |
| Quality/Patient Safety/Risk | | | |
| Case Management/Referral | | | |
| Finance/Billing | | | |
| Claim/Coding/DRG | | | |
| Inventory/Supply | | | |
| Hospital Operations | | | |
| HIS Solution Architect | | | |
| Clinical Informatics/BA | | | |
| Integration/Interoperability | | | |
| Data/Source of Truth | | | |
| UX/Human Factors | | | |
| Security/Audit | | | |
| Privacy/Minimum Necessary | | | |
| JCI | | | |
| HA/HAI | | | |
| HIPAA | | | |
| ISO/IEC 27001 | | | |
| Thailand PDPA | | | |

Do not activate every Agent. CONDITIONAL requires explicit trigger.

## 3. Requested Workflow
`Start → ... → End`
### Actors / Handoffs
| ขั้นตอน | ผู้ปฏิบัติ | Input | Action/Decision | Output/Record | Next | Evidence |
|---|---|---|---|---|---|---|

## 4. Relevance Filter Summary
| Candidate | เหตุผลที่ Suppress | Trigger to become Relevant |
|---|---|---|

**Expert curiosity is not sufficient. Evidence/source existence is also not sufficient to create relevance.**

## 5. Gap Register — Surviving Gaps Only
| ID | ด้าน | Gap/Risk | Trace Source | Relevance | Why Material | Impact | Evidence Basis | Assurance | Reviewing Agent | Verification | Classification | Confirmation Owner | Blocks |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| GAP-01 | | | REQ/BR/WF/Risk/Standard | DIRECT/CONDITIONAL | | CRITICAL/HIGH/MEDIUM/LOW | allowed basis | A/B/C/D/E | | VERIFIED/PARTIAL/NEEDS VERIFICATION/N/A | HSR/CR/WA/TBD | | Prototype/Dev/Neither |

Critical/High expert-created item requires complete evidence trail and assurance classification.

## 6. Evidence Assurance Register — v3.3
Use only for items that already passed Relevance Gate.
| Ref | Assurance Level | Claim Type | Source Owner | Document / Source | Edition / Effective Date | Section / Topic / Clause | Official Source Locator | Verified Date | Applicability | Verification Status |
|---|---|---|---|---|---|---|---|---|---|---|
| GAP/HSR/CR | A/B/C/D/E | HOSPITAL REQUIREMENT / FORMAL REQUIREMENT / AUTHORITATIVE GUIDANCE / BEST PRACTICE / EXPERT REASONING | | | | exact only if verified | | YYYY-MM-DD | | VERIFIED / PARTIALLY VERIFIED / NEEDS VERIFICATION / N/A |

Rules:
- Level A is hospital/project primary evidence, not external standards.
- Formal external requirement wording requires verified Level B + exact support + applicability.
- Level C/D/E MUST NOT be described as a formal mandatory standard requirement.
- If evidence is incomplete, downgrade wording/status; do not inflate severity.
- Source evidence MUST NOT resurrect a candidate suppressed by Relevance Gate.

## 7. Independent Challenge Review
| Ref | Reviewer Challenge | Disposition | เหตุผล |
|---|---|---|---|
Reviewer must challenge unsupported evidence level, stale edition, unverified clause, relevance-by-standard, duplicates and overstated severity.

## 8. Upstream-Downstream
Direct or Conditional with explicit trigger only.
| หน่วยงาน/ระบบ | Effect Type | Trigger/Evidence | Impact | Gap/Recommendation |
|---|---|---|---|---|

## 9. Patient Safety / Clinical Risk Review
Use N/A rather than invented issues. Review patient context; medication/order effect; documentation ownership/actual record effect; critical result/escalation; handoff; correction/cancel/reversal when relevant.

## 10. Permission / Accountability Review
| Action | Create | Edit | Review | Approve | Cancel/Reverse | Audit | Evidence/Gap |
|---|---|---|---|---|---|---|---|

## 11. Data / Integration / Source-of-Truth Review
| Data/Object | Source of Truth | Producer | Consumer | Timing | Failure/Exception | Evidence/Gap |
|---|---|---|---|---|---|---|

## 12. Privacy / Security Review
Only relevant access, authorization, sensitive data, audit, export/download/print, retention, correction, disclosure, interface security and downtime.

## 13. Standards / Governance Review
| Standard / Source | Applicability | Topic/Principle | Assurance | Claim Type | Evidence Source | Recommendation | Verification |
|---|---|---|---|---|---|---|---|
| JCI | Applicable/N/A/Needs Review | | B/C/E | | | | VERIFIED/NEED STANDARD VERIFICATION |
| HA/HAI | | | | | | | |
| HIPAA | | | | | | | |
| ISO/IEC 27001 | | | | | | | |
| Thailand PDPA | | | | | | | |

Never fabricate clause or mandatory claim. Do not assume HIPAA. Follow standards-registry policy.

## 14. Recommended Future Flow
Separate from Hospital Confirmed Flow. Every added step references HSR/CR/WA/TBD.

## 15. Recommended Requirements / Controls
| Ref | Recommendation | Trace/Evidence | Risk | Priority | Classification | Assurance | Verification |
|---|---|---|---|---|---|---|---|

## 16. Confirmation Value Gate
### MUST CONFIRM BEFORE DEV
| Question | Decision affected | Why needed | Owner |
|---|---|---|---|
### CONFIRM DURING PROTOTYPE REVIEW
| Question | Decision affected | Why needed | Owner |
|---|---|---|---|
### LATER REFINEMENT
| Question | Decision affected | Why needed | Owner |
|---|---|---|---|
If Decision affected/Why needed is unclear, suppress.

## 17. Expert Panel Conclusion
- Prototype Yes/No/Conditional
- Critical/High surviving gaps
- Suppressed question count/groups
- Highest risks
- Next hospital confirmation topics
- Evidence Assurance exceptions still needing verification

> Expert Gap Analysis remains Advisory. HSR/CR/WA/TBD becomes Hospital Requirement/Business Rule only after explicit hospital/user confirmation and Blueprint update.
