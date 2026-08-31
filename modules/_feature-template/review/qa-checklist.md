# Gorilla HIS Mockup QA Checklist — v2.2

**Feature:** << module/feature >>  
**Blueprint:** << Application blueprint_*.txt >>  
**Reviewer Mode:** ⬜ Builder Self-QA ⬜ Independent QA Agent ⬜ Human  
**Overall:** ⬜ PASS ⬜ PASS WITH ISSUES ⬜ FAIL

> ใช้ checklist เดียวกันได้ แต่ **Builder Self-QA ไม่มีสิทธิ์ตัดสิน READY FOR HUMAN REVIEW**; ต้องผ่าน Independent QA อีกครั้ง

## 1. Blueprint Traceability — Mandatory
ใช้ ID ชุดเดียวกับ Pre-Build; ถ้า Blueprint ไม่มีประเภทนั้นให้ N/A ห้ามแต่งเพิ่ม

| ID | Blueprint Item | Expected | Evidence in index.html | Result | Issue/Fix |
|---|---|---|---|---|---|

Result = `PASS / PARTIAL / FAIL / N/A`

- [ ] Main Workflow ครบและ click-through ได้
- [ ] Critical Requirements จาก Blueprint ไม่มี FAIL/PARTIAL
- [ ] Function List ครบตาม Scope
- [ ] Business Rules ที่ Blueprint ระบุถูก represent/enforce
- [ ] Required States/Exceptions ครบ

## 2. Factory Compliance
- [ ] ผ่าน `factory-gate/post-build-checklist.md` (Independent QA ต้อง verify ซ้ำ ไม่เชื่อ Builder Result อย่างเดียว)
- [ ] Single `index.html`
- [ ] ไม่มี External CDN/font/CSS/JS
- [ ] design values ที่ token รองรับไม่มี hardcode แทน token
- [ ] ไม่มี Real API / data exfiltration
- [ ] ไม่มีข้อมูลผู้ป่วยจริง
- [ ] Header comment / required metadata ครบ
- [ ] Design Notes และ `prompt-used.md` พร้อมสำหรับ traceability

## 3. Component / Pattern / Gold Standard
- [ ] Existing Components ถูก reuse ตาม Design Notes
- [ ] Existing Patterns ถูก reuse ตาม Design Notes
- [ ] Gold Standard/reference ใช้เฉพาะเมื่อเกี่ยวข้อง; ถ้าไม่มีให้ N/A
- [ ] New reusable UI ทุกจุด Declare `Proposed New Pattern`
- [ ] ไม่มีการสร้าง Design System ใหม่ซ่อนอยู่

## 4. Premium HIS Visual Gate — v2.2 Additive

> ส่วนนี้เพิ่มจาก QA v2.1; ไม่แทนที่ Blueprint, Factory, Patient Safety, Interaction หรือ Technical QA เดิม

| ID | Check | Result | Evidence / Fix |
|---|---|---|---|
| VG-01 | Hospital Enterprise Product Character; not generic SaaS/AI dashboard | | |
| VG-02 | Approved Application Shell or approved exception | | |
| VG-03 | No Emoji/decorative UI icon; consistent approved icon language | | |
| VG-04 | No Card Everywhere; dense operational containers used appropriately | | |
| VG-05 | Compact KPI strip considered/preferred on operational dashboard; N/A if not relevant | | |
| VG-06 | Neutral-first and semantic clinical colors retain strict Design Rules meaning | | |
| VG-07 | 1366×768 operational density appropriate when feasible | | |
| VG-08 | No oversized heading/KPI/button/card | | |
| VG-09 | AI is capability, not futuristic visual theme | | |

**VG-01/VG-02/VG-03/VG-06/VG-09 FAIL = P0 / Automatic FAIL เมื่อเป็น clear violation และไม่มี approved exception.**

Independent QA ต้องตอบคำถามนี้ด้วยประโยคเดียว:
> “ถ้าเอาชื่อ Gorilla HIS ออกจากหน้าจอ หน้านี้ยังดูเป็นระบบ Hospital Enterprise ที่ออกแบบอย่างเป็นมืออาชีพ หรือดูเป็น generic AI/SaaS template?”

ถ้าคำตอบคือ generic AI/SaaS template → VG-01 FAIL.

ถ้า tool ไม่สามารถ render หน้าจอจริงได้ ให้ระบุ `VISUAL REVIEW LIMITATION` และห้ามสรุป Visual Gate PASS จาก code อย่างเดียว; ส่งต่อ Human/Visual QA สำหรับข้อที่ต้องดูภาพ

## 5. Visual / UX / Patient Safety
- [ ] Semantic color ถูกความหมายตาม `design-system/design-rules.md`
- [ ] Critical/Allergy/Patient-safety alert มี icon + text ไม่พึ่งสีอย่างเดียว
- [ ] Action hierarchy ถูกต้อง
- [ ] Table/Form/Tabs/Modal/Drawer สอดคล้อง Gorilla HIS
- [ ] ถ้ามี clinical decision support ไม่มี definitive diagnosis wording
- [ ] ไม่มี hidden chain-of-thought

## 6. Interaction QA
ทดสอบจริง ไม่ตรวจจากหน้าตาอย่างเดียว:
- [ ] Buttons
- [ ] Tabs/navigation
- [ ] Search/filter (ถ้ามี)
- [ ] Modal/Drawer/Confirmation (ถ้ามี)
- [ ] Status/Scenario/Task transitions (ถ้ามี)
- [ ] Validation/Disabled state
- [ ] ไม่มี Dead Button ใน Main Workflow

## 7. States / Mock Data
- [ ] Loading ตามบริบท
- [ ] Empty ตามบริบท
- [ ] Error ตามบริบท
- [ ] Success/confirmation ตามบริบท
- [ ] Edge case ตาม Blueprint
- [ ] Clinical mock values สมเหตุสมผลเมื่อเกี่ยวข้อง

## 8. Technical QA
- [ ] ไม่มี Console Error
- [ ] 1366×768 ใช้งานได้
- [ ] 1920×1080 ใช้งานได้
- [ ] ไม่มี overflow/overlay ที่ทำให้ action สำคัญใช้ไม่ได้

## 9. Severity / Decision
- `P0` Critical — Main workflow, patient safety, critical requirement, broken app, Hard Reject, mandatory Visual Gate clear violation
- `P1` Major — function/compliance สำคัญไม่ครบ หรือ visual hierarchy/density inconsistency ที่มีนัยสำคัญ
- `P2` Minor/Enhancement

**Automatic FAIL:** มี P0, Critical Requirement FAIL/PARTIAL, Main Workflow FAIL/PARTIAL, Hard Reject, mandatory Visual Gate P0, Console Error, หรือ Post-Build Gate FAIL

### Decision by Mode
- Builder Self-QA PASS → `READY FOR POST-BUILD GATE / INDEPENDENT QA` เท่านั้น
- Independent QA FAIL → `RETURN TO MOCKUP BUILDER`
- Independent QA PASS → `READY FOR HUMAN REVIEW`
- Human Approved → Approved Mockup; การ Promote เป็น Gold Standard เป็นขั้นตอนแยกตาม `approved-mockups/GOLD_STANDARD.md`

## Independent QA Agent Prompt
```text
คุณคือ Independent Gorilla HIS Mockup QA & Design Compliance Agent
ห้ามอาศัยผล PASS ของ Builder โดยไม่ตรวจซ้ำ
อ่าน Application Blueprint, AI_INSTRUCTIONS.md, factory-gate, design-system,
approved references ที่เกี่ยวข้อง, Builder traceability และ index.html

ตรวจ Blueprint Traceability (WF/REQ/FN/BR/ST), Factory Compliance, Premium HIS Visual Gate,
UI/UX, patient safety, interaction, technical QA และ required deliverables ตาม checklist v2.2

ต้องตรวจ rendered UI จริงสำหรับ Visual Gate เมื่อ tool รองรับ
ถ้า render ไม่ได้ ให้ระบุ VISUAL REVIEW LIMITATION ห้ามเดาว่า PASS

รายงาน:
1. Overall PASS / PASS WITH ISSUES / FAIL
2. Blueprint Traceability Table พร้อม evidence
3. Factory + Premium HIS Visual Gate deviations
4. Interaction/Technical issues
5. Fix List P0/P1/P2
6. Final: RETURN TO MOCKUP BUILDER หรือ READY FOR HUMAN REVIEW
```
