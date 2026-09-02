# Gorilla HIS — Template การวิเคราะห์ช่องว่างและข้อเสนอแนะโดยผู้เชี่ยวชาญ v1.3

**Module / Application:**  
**Analysis Version:** v0.x  
**Related Blueprint:**  
**Document Type:** ADVISORY / CHALLENGE ANALYSIS — **ยังไม่ถือเป็น HOSPITAL CONFIRMED**

> ภาษาหลักคือภาษาไทย คงคำศัพท์ HIS/Clinical/Technical ภาษาอังกฤษเมื่อชัดกว่า

## 1. สรุปผลการวิเคราะห์
- Requirement ที่ชัดเจน/แข็งแรง:
- Critical/High gaps ที่ผ่าน Relevance Gate:
- Candidate gaps ที่ Suppress:
- ผลต่อ Prototype:
- ผลต่อ Dev Handoff:

## 2. Domain Classification & Expert Coverage Matrix
| มุมมอง / Agent | สถานะ | เหตุผล / Trigger | ประเด็นที่ตรวจ |
|---|---|---|---|
| Patient / Caregiver | | | |
| Registration / Patient Access | | | |
| Medical Records / HIM | | | |
| Nursing | | | |
| Physician / Clinical | | | |
| ER / IPD / OR / Specialty | | | |
| Pharmacy | | | |
| Lab / Blood Bank | | | |
| Radiology / PACS | | | |
| Quality / Patient Safety / Risk | | | |
| Finance / Billing | | | |
| Hospital Operations | | | |
| HIS Solution Architect | | | |
| Clinical Informatics / BA | | | |
| Integration / Interoperability | | | |
| Data / Source of Truth | | | |
| UX / Human Factors | | | |
| Security / Audit | | | |
| Privacy / Minimum Necessary | | | |
| Forensic Medicine / Mortuary | RELEVANT / N/A | activate only for forensic/mortuary scope | identity, custody, mortuary, report/evidence/handover |
| JCI | | | |
| HA / HAI | | | |
| HIPAA | | | |
| ISO/IEC 27001:2022 | | | |
| Thailand PDPA | | | |

## 3. ความเข้าใจ Workflow ที่ผู้ใช้ร้องขอ
`Start → ... → End`

### Actors / Handoffs
| ขั้นตอน | ผู้ปฏิบัติ | Input | Action / Decision | Output / Record | ผู้รับช่วงถัดไป | Evidence |
|---|---|---|---|---|---|---|
| | | | | | | |

## 4. Relevance Filter Summary
| Candidate | เหตุผลที่ Suppress | Trigger ที่จะทำให้กลับมา Relevant |
|---|---|---|
| | | |

## 5. Gap Register — Surviving Gaps Only
| ID | ด้าน | Gap / Risk | Trace Source | Relevance | ทำไมสำคัญ | Impact | Evidence Basis | Reviewing Agent | Verification | Classification | Confirmation Owner | Blocks |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| GAP-01 | | | | DIRECT / CONDITIONAL | | CRITICAL/HIGH/MEDIUM/LOW | | | | HSR/CR/WA/TBD | | Prototype/Dev/Neither |

## 6. Independent Challenge Review
| Ref | Reviewer Challenge | Disposition | เหตุผล |
|---|---|---|---|
| | | ACCEPT / DOWNGRADE / RECLASSIFY / SUPPRESS / NEEDS VERIFICATION | |

## 7. ผลกระทบข้ามหน่วยงาน / Upstream-Downstream
| หน่วยงาน / ระบบ | Effect Type | Trigger / Evidence | ผลกระทบ | Gap / Recommendation |
|---|---|---|---|---|
| | DIRECT / CONDITIONAL | | | |

## 8. Patient / Clinical / Forensic Safety Review
- Patient/deceased identification/context:
- Medication/Order effect:
- Documentation ownership / actual record effect:
- Evidence/specimen integrity when relevant:
- Body movement/release when relevant:
- Critical result/alert/escalation:
- Handoff/continuity:
- Correction/cancellation/reversal:

## 9. Permission / Accountability Review
| Action | Create | Edit | Review | Approve | Cancel / Reverse | Audit | Evidence / Gap |
|---|---|---|---|---|---|---|---|
| | | | | | | | |

## 10. Data / Integration / Source-of-Truth Review
| Data / Object | Source of Truth | Producer | Consumer | Timing | Failure / Exception | Evidence / Gap |
|---|---|---|---|---|---|---|
| | | | | | | |

## 11. Privacy / Security Review
พิจารณา Minimum Necessary Access, Authentication/Authorization, Sensitive Data, Auditability, Export/Download/Print, Retention, Correction, Disclosure, Interface Security และ Downtime เฉพาะที่ relevant.

## 12. Standards / Governance Review
| มาตรฐาน / แหล่งอ้างอิง | Applicability | Topic / Principle | Evidence Source | Recommendation | Verification |
|---|---|---|---|---|---|
| JCI | | | | | |
| HA / HAI | | | | | |
| HIPAA | | | | | |
| ISO/IEC 27001:2022 | | | | | |
| Thailand PDPA | | | | | |
| Domain Authority | | | | | |

### 12A. Authoritative Source Registry — Mandatory when external standards/guidance are used
| Source Organization | Document / Resource | Source Type | Publication / Effective Date | Topic / Principle | Applicability | Verification | URL / Repo Ref |
|---|---|---|---|---|---|---|---|
| | | | | | | | |

### 12B. Forensic Standard Compliance Review — Mandatory for Forensic/Mortuary
| Domain Topic | REQ / Workflow Trace | Authoritative Source | Principle Supported | Coverage | Classification | Verification | Decision / Owner |
|---|---|---|---|---|---|---|---|
| Deceased / Case Identity | | | | COVERED/PARTIAL/GAP/N/A | | | |
| Body Custody / Movement / Release | | | | | | | |
| Evidence / Specimen Chain of Custody | | | | | | | |
| Forensic Photography / Media | | | | | | | |
| Medico-Legal Report Governance | | | | | | | |
| Diagnostic Source of Truth | | | | | | | |
| Sensitive Access / Disclosure | | | | | | | |
| Handover / Audit / History | | | | | | | |
| Correction / Amendment | | | | | | | |

Rules:
- Use MOPH/CIFS/HA/applicable Thai authority and Hospital-approved SOP/forms as source families when relevant.
- Wikipedia/social media/marketing pages are not authoritative evidence for Critical/High compliance claims.
- External forensic guidance can verify a principle but cannot establish this hospital's local workflow without confirmation.
- Use `PRINCIPLE VERIFIED — LOCAL IMPLEMENTATION NEEDS HOSPITAL CONFIRMATION` when appropriate.

## 13. Recommended Future Flow
แยกจาก Hospital Confirmed Flow ชัดเจน; ทุก step เพิ่มต้องอ้าง HSR/CR/WA/TBD.

## 14. Recommended Requirements / Controls
| Ref | ข้อเสนอแนะ | Trace / Evidence | Risk ที่แก้ | Priority | Proposed Classification | Verification |
|---|---|---|---|---|---|---|
| | | | | | | |

## 15. Confirmation Value Gate
### MUST CONFIRM BEFORE DEV
| Question | Decision affected | Why needed | Owner |
|---|---|---|---|
| | | | |
### CONFIRM DURING PROTOTYPE REVIEW
| Question | Decision affected | Why needed | Owner |
|---|---|---|---|
| | | | |
### LATER REFINEMENT
| Question | Decision affected | Why needed | Owner |
|---|---|---|---|
| | | | |

## 16. ข้อสรุปจาก Expert Panel
- สามารถทำ Prototype ต่อได้: Yes / No / Conditional
- Critical/High gaps ที่ผ่าน Gate:
- จำนวนคำถามที่ Suppress:
- ความเสี่ยงสำคัญที่สุด:
- หัวข้อที่ควรคุยกับโรงพยาบาลลำดับถัดไป:

> Expert Gap Analysis เป็น Advisory. รายการจะกลายเป็น Hospital Requirement / Business Rule ได้ต่อเมื่อโรงพยาบาลหรือผู้ใช้ยืนยันอย่างชัดเจนและ Update เข้า Application Blueprint แล้วเท่านั้น.