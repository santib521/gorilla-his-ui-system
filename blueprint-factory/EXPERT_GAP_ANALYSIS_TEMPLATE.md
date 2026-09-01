# Gorilla HIS — Template การวิเคราะห์ช่องว่างและข้อเสนอแนะโดยผู้เชี่ยวชาญ v1.2

**Module / Application:**  
**Analysis Version:** v0.x  
**Related Blueprint:**  
**Document Type:** เอกสารวิเคราะห์/ข้อเสนอแนะ (ADVISORY / CHALLENGE ANALYSIS) — **ยังไม่ถือเป็น HOSPITAL CONFIRMED**

> ภาษาหลักคือภาษาไทย คงคำศัพท์ HIS/Clinical/Technical ภาษาอังกฤษเมื่อชัดกว่า

## 1. สรุปผลการวิเคราะห์ (Executive Assessment)
- Requirement ที่ชัดเจน/แข็งแรง:
- Critical/High gaps ที่ผ่าน Relevance Gate แล้ว:
- Candidate gaps ที่ถูก Suppress เพราะไม่เกี่ยว/ยังไม่ถึงเวลา:
- ผลต่อ Prototype:
- ผลต่อ Dev Handoff:

## 2. Domain Classification & Expert Coverage Matrix
| มุมมอง / Agent | สถานะ | เหตุผล / Trigger | ประเด็นที่ตรวจ |
|---|---|---|---|
| Patient / Caregiver | RELEVANT / CONDITIONALLY RELEVANT / N/A / NEEDS REVIEW | | |
| Registration / Patient Access | | | |
| Medical Records / HIM | | | |
| Nursing | | | |
| Physician / Clinical | | | |
| ER / IPD / OR / Specialty | | | |
| Pharmacy | | | |
| Lab / Blood Bank | | | |
| Radiology / PACS | | | |
| Allied Health | | | |
| Infection Control | | | |
| Quality / Patient Safety / Risk | | | |
| Case Management / Referral | | | |
| Finance / Billing | | | |
| Claim / Coding / DRG | | | |
| Inventory / Supply | | | |
| Hospital Operations | | | |
| HIS Solution Architect | | | |
| Clinical Informatics / BA | | | |
| Integration / Interoperability | | | |
| Data / Source of Truth | | | |
| UX / Human Factors | | | |
| Security / Audit | | | |
| Privacy / Minimum Necessary | | | |
| JCI | | | |
| HA / HAI | | | |
| HIPAA | | | |
| ISO/IEC 27001:2022 | | | |
| Thailand PDPA | | | |

ห้ามบังคับทุก Agent ให้เกี่ยวข้องทุก Module. `CONDITIONALLY RELEVANT` ต้องระบุ trigger ชัดเจน เช่น “เฉพาะเมื่อ approved order สร้าง real Clinical Order”.

## 3. ความเข้าใจ Workflow ที่ผู้ใช้ร้องขอ
`Start → ... → End`

### Actors / Handoffs
| ขั้นตอน | ผู้ปฏิบัติ | Input | Action / Decision | Output / Record | ผู้รับช่วงถัดไป | Evidence |
|---|---|---|---|---|---|---|
| | | | | | | |

## 4. Relevance Filter Summary
ก่อนสร้าง Gap Register ให้สรุป candidate ที่ถูกคัดออก

| Candidate | เหตุผลที่ Suppress | Trigger ที่จะทำให้กลับมา Relevant |
|---|---|---|
| | Not current scope / no direct effect / duplicate / reversible detail / future-only | |

**กฎ:** Expert curiosity ไม่เพียงพอที่จะสร้าง GAP หรือคำถามให้โรงพยาบาล

## 5. Gap Register — Surviving Gaps Only
| ID | ด้าน | Gap / Risk | Trace Source | Relevance | ทำไมสำคัญ | Impact | Evidence Basis | Reviewing Agent | Verification | Classification | Confirmation Owner | Blocks |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| GAP-01 | | | REQ/BR/WF/Risk/Standard | DIRECT / CONDITIONAL | | CRITICAL/HIGH/MEDIUM/LOW | RAW REQUIREMENT / DIRECT WORKFLOW DEPENDENCY / DIRECT DOWNSTREAM EFFECT / ESTABLISHED HIS-HOSPITAL PRACTICE / AUTHORITATIVE STANDARD-LAW / STANDARD PRINCIPLE-NEED VERIFICATION / EXPERT REASONING ONLY | | VERIFIED / NEEDS VERIFICATION / NOT APPLICABLE | HSR/CR/WA/TBD | | Prototype / Dev / Neither |

Gap ทุกข้อจะต้องตอบได้ว่า: **มาจากอะไร → เกี่ยวกับ Module นี้อย่างไร → ถ้าไม่ตอบจะเปลี่ยน decision/risk อะไร → ใครควรยืนยัน → เมื่อใด**

Critical/High ที่เป็น Expert-created item ต้องมี Evidence Basis + Reviewing Agent + Trace Source + Verification + Confirmation Owner ครบ

## 6. Independent Challenge Review
| Ref | Reviewer Challenge | Disposition | เหตุผล |
|---|---|---|---|
| GAP/HSR/CR | unsupported / irrelevant / duplicate / overstated / missing risk / standards issue | ACCEPT / DOWNGRADE / RECLASSIFY / SUPPRESS / NEEDS VERIFICATION | |

Reviewer มีหน้าที่ทั้งหา “สิ่งที่ขาด” และ “สิ่งที่ถามเกินจำเป็น”

## 7. ผลกระทบข้ามหน่วยงาน / Upstream-Downstream
แสดงเฉพาะ Direct effect หรือ Conditional effect ที่มี trigger ชัดเจน

| หน่วยงาน / ระบบ | Effect Type | Trigger / Evidence | ผลกระทบ | Gap / Recommendation |
|---|---|---|---|---|
| | DIRECT / CONDITIONAL | | | |

ห้ามขอ Confirmation จาก downstream department เพียงเพราะ department นั้นมีอยู่ใน HIS

## 8. Patient Safety / Clinical Risk Review
ระบุ `N/A` เมื่อไม่เกี่ยวข้องแทนการสร้างประเด็นสมมติ
- Patient identification/context:
- Medication/Order effect:
- Documentation ownership / Actual Medical Record effect:
- Critical result / Alert / Escalation:
- Handoff / Continuity:
- Correction / Cancellation / Reversal:
- อื่น ๆ:

## 9. Permission / Accountability Review
| Action | Create | Edit | Review | Approve | Cancel / Reverse | Audit | Evidence / Gap |
|---|---|---|---|---|---|---|---|
| | | | | | | | |

## 10. Data / Integration / Source-of-Truth Review
| Data / Object | Source of Truth | Producer | Consumer | Timing | Failure / Exception | Evidence / Gap |
|---|---|---|---|---|---|---|
| | | | | | | |

## 11. Privacy / Security Review
พิจารณาเฉพาะสิ่งที่มี relevance ต่อข้อมูล/สิทธิ์/การเปิดเผยจริง เช่น Minimum Necessary Access, Authentication/Authorization, Sensitive Data, Auditability, Export/Download/Print, Retention, Correction, Disclosure, Interface Security และ Downtime.

## 12. Standards / Governance Review
| มาตรฐาน / แหล่งอ้างอิง | Applicability | Topic / Principle | Evidence Source | Recommendation | Verification |
|---|---|---|---|---|---|
| JCI | Applicable / N/A / Needs Review | | | | VERIFIED / NEED STANDARD VERIFICATION |
| HA / HAI | | | | | |
| HIPAA | | | | | |
| ISO/IEC 27001:2022 | | | | | |
| Thailand PDPA | | | | | |

ห้ามสร้าง Clause หรือ Mandatory Claim ที่ไม่ได้ Verify และห้ามถือว่า HIPAA ใช้กับโรงพยาบาลไทยโดยอัตโนมัติ

## 13. Recommended Future Flow
แยกจาก Hospital Confirmed Flow อย่างชัดเจน
`Start → ... → End`
ทุก step ที่เพิ่มต้องอ้าง HSR/CR/WA/TBD

## 14. Recommended Requirements / Controls
| Ref | ข้อเสนอแนะ | Trace / Evidence | Risk ที่แก้ | Priority | Proposed Classification | Verification |
|---|---|---|---|---|---|---|
| | | | | CRITICAL/HIGH/MEDIUM/LOW | HSR/CR/WA/TBD | |

## 15. Confirmation Value Gate
เฉพาะคำถามที่ผ่าน Relevance Gate เท่านั้น

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

ถ้าอธิบาย `Decision affected` หรือ `Why needed` ไม่ได้ ให้ Suppress คำถาม

## 16. ข้อสรุปจาก Expert Panel
- สามารถทำ Prototype ต่อได้: Yes / No / Conditional
- Critical/High gaps ที่ผ่าน Gate:
- จำนวนคำถามที่ถูก Suppress เพราะไม่เกี่ยว/ยังไม่ถึงเวลา:
- ความเสี่ยงสำคัญที่สุด:
- หัวข้อที่ควรคุยกับโรงพยาบาลลำดับถัดไป:

> **Expert Gap Analysis เป็นเอกสาร Advisory** รายการจะกลายเป็น Hospital Requirement / Business Rule ได้ต่อเมื่อโรงพยาบาลหรือผู้ใช้ยืนยันอย่างชัดเจนและ Update เข้า Application Blueprint แล้วเท่านั้น