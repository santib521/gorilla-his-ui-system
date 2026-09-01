# Gorilla HIS — Template การวิเคราะห์ช่องว่างและข้อเสนอแนะโดยผู้เชี่ยวชาญ v1.1

**Module / Application:**  
**Analysis Version:** v0.x  
**Related Blueprint:**  
**Document Type:** เอกสารวิเคราะห์/ข้อเสนอแนะ (ADVISORY / CHALLENGE ANALYSIS) — **ยังไม่ถือเป็น HOSPITAL CONFIRMED**

> ภาษาหลักของเอกสารนี้คือ **ภาษาไทย** เพื่อให้ BA, PM, ผู้ใช้งาน และคณะทำงานโรงพยาบาลสามารถ Review ได้โดยตรง  
> คำศัพท์ HIS/Clinical/Technical ที่ใช้กันทั่วไป เช่น EMR, Order, Review, Approve, Audit Trail, Source of Truth, Workflow, Integration, JCI, HA, HIPAA, ISO 27001, PDPA สามารถคงภาษาอังกฤษไว้เพื่อความชัดเจน

## 1. สรุปผลการวิเคราะห์ (Executive Assessment)
- สิ่งที่ Requirement ปัจจุบันมีความชัดเจน/แข็งแรง:
- ประเด็นสำคัญที่ยังขาด:
- จำนวน Gap ระดับ Critical/High:
- ผลต่อ Prototype:
- ผลต่อ Dev Handoff:

## 2. Expert Coverage Matrix
| มุมมอง / Agent | สถานะ | เหตุผลที่เกี่ยวข้อง / N/A | ประเด็นสำคัญที่ตรวจ |
|---|---|---|---|
| Patient / Caregiver | RELEVANT / N/A / NEEDS REVIEW | | |
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

ห้ามบังคับทุก Agent ให้เกี่ยวข้องกับทุก Module ให้ระบุ `N/A` พร้อมเหตุผลเมื่อไม่เกี่ยวข้อง

## 3. ความเข้าใจ Workflow ปัจจุบัน / Workflow ที่ผู้ใช้ร้องขอ
`Start → ... → End`

### Actors / Handoffs
| ขั้นตอน | ผู้ปฏิบัติ | Input | Action / Decision | Output / Record | ผู้รับช่วงถัดไป |
|---|---|---|---|---|---|
| | | | | | |

## 4. Gap Register
| ID | ด้าน | สิ่งที่ขาด / ความเสี่ยง / คำถาม | ทำไมจึงสำคัญ | Impact | ข้อเสนอแนะ | Classification | ผู้ที่ควรยืนยัน | Blocks |
|---|---|---|---|---|---|---|---|---|
| GAP-01 | Workflow / Safety / Role / Data / Integration / Privacy / etc. | | | CRITICAL/HIGH/MEDIUM/LOW | | HSR/CR/WA/TBD | | Prototype / Dev / Neither |

Gap แต่ละรายการต้องเขียนให้ทีมโรงพยาบาลเข้าใจได้ทันทีว่า **ขาดอะไร → เสี่ยงอะไร → ควรทำอย่างไร → ใครต้อง Confirm → ต้อง Confirm เมื่อใด**

## 5. ผลกระทบข้ามหน่วยงาน / Upstream-Downstream
| หน่วยงาน / ระบบ | รับข้อมูลจาก / ส่งข้อมูลไป | ผลกระทบที่อาจเกิดขึ้น | Gap / Recommendation |
|---|---|---|---|
| | | | |

## 6. Patient Safety / Clinical Risk Review
- Patient identification / Patient context:
- Medication / Order effect:
- Documentation ownership / Legal or Actual Medical Record effect:
- Critical result / Alert / Escalation:
- Handoff / Continuity:
- Correction / Cancellation / Reversal:
- อื่น ๆ:

## 7. Permission / Accountability Review
| Action | Create | Edit | Review | Approve | Cancel / Reverse | ต้องมี Audit | Gap |
|---|---|---|---|---|---|---|---|
| | | | | | | | |

## 8. Data / Integration / Source-of-Truth Review
| Data / Object | Source of Truth | Producer | Consumer | Timing | Failure / Exception | Gap |
|---|---|---|---|---|---|---|
| | | | | | | |

## 9. Privacy / Security Review
พิจารณาตามความเกี่ยวข้อง เช่น Minimum Necessary Access, Authentication/Authorization, Sensitive Data, Auditability, Export/Download/Print, Retention, Correction, Disclosure, Interface Security และ Downtime

## 10. Standards / Governance Review
| มาตรฐาน / แหล่งอ้างอิง | Applicability | Topic / Principle | Observation / Recommendation | Verification |
|---|---|---|---|---|
| JCI | Applicable / N/A / Needs Review | | | VERIFIED / NEED STANDARD VERIFICATION |
| HA / HAI | | | | |
| HIPAA | | | | |
| ISO/IEC 27001:2022 | | | | |
| Thailand PDPA | | | | |

ห้ามถือว่า HIPAA มีผลบังคับใช้กับโรงพยาบาลไทยโดยอัตโนมัติ และห้ามสร้าง Clause หรือ Mandatory Claim ที่ไม่ได้ Verify

## 11. Recommended Future Flow
แสดง Workflow ที่ Expert Panel เสนอแนะเป็นภาษาไทย โดยแยกจาก Hospital Confirmed Flow อย่างชัดเจน

`Start → ... → End`

ทุก Step ที่เพิ่มและยังไม่ได้รับการยืนยันต้องอ้างอิง `HSR-xx`, `CR-xx`, `WA-xx` หรือ `TBD-xx`

## 12. Recommended Requirements / Controls
| Ref | ข้อเสนอแนะ | ประโยชน์ / Risk ที่แก้ | Priority | Proposed Classification |
|---|---|---|---|---|
| | | | CRITICAL/HIGH/MEDIUM/LOW | HSR/CR/WA/TBD |

## 13. แผนการยืนยัน Requirement (Confirmation Plan)
### ต้องยืนยันก่อน Dev (MUST CONFIRM BEFORE DEV)
1.

### ยืนยันระหว่าง Prototype Review (CONFIRM DURING PROTOTYPE REVIEW)
1.

### ปรับรายละเอียดภายหลัง (LATER REFINEMENT)
1.

## 14. ข้อสรุปจาก Expert Panel
- สามารถทำ Prototype ต่อได้: Yes / No / Conditional
- ความเสี่ยงที่ยังไม่ Resolve และสำคัญที่สุด:
- หัวข้อที่ควรคุยกับโรงพยาบาลเป็นลำดับถัดไป:

> **Expert Gap Analysis เป็นเอกสาร Advisory** รายการในเอกสารนี้จะกลายเป็น Hospital Requirement / Business Rule ได้ต่อเมื่อโรงพยาบาลหรือผู้ใช้ยืนยันอย่างชัดเจนและมีการ Update เข้า Application Blueprint แล้วเท่านั้น