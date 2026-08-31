# Gorilla HIS Mockup QA Checklist — v2.1

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

## 4. Visual / UX / Patient Safety
- [ ] Semantic color ถูกความหมาย
- [ ] Critical/Allergy/Patient-safety alert มี icon + text ไม่พึ่งสีอย่างเดียว
- [ ] Action hierarchy ถูกต้อง
- [ ] Table/Form/Tabs/Modal/Drawer สอดคล้อง Gorilla HIS
- [ ] ถ้ามี clinical decision support ไม่มี definitive diagnosis wording
- [ ] ไม่มี hidden chain-of-thought

## 5. Interaction QA
ทดสอบจริง ไม่ตรวจจากหน้าตาอย่างเดียว:
- [ ] Buttons
- [ ] Tabs/navigation
- [ ] Search/filter (ถ้ามี)
- [ ] Modal/Drawer/Confirmation (ถ้ามี)
- [ ] Status/Scenario/Task transitions (ถ้ามี)
- [ ] Validation/Disabled state
- [ ] ไม่มี Dead Button ใน Main Workflow

## 6. States / Mock Data
- [ ] Loading ตามบริบท
- [ ] Empty ตามบริบท
- [ ] Error ตามบริบท
- [ ] Success/confirmation ตามบริบท
- [ ] Edge case ตาม Blueprint
- [ ] Clinical mock values สมเหตุสมผลเมื่อเกี่ยวข้อง

## 7. Technical QA
- [ ] ไม่มี Console Error
- [ ] 1366×768 ใช้งานได้
- [ ] 1920×1080 ใช้งานได้
- [ ] ไม่มี overflow/overlay ที่ทำให้ action สำคัญใช้ไม่ได้

## 8. Severity / Decision
- `P0` Critical — Main workflow, patient safety, critical requirement, broken app, Hard Reject
- `P1` Major — function/compliance สำคัญไม่ครบ
- `P2` Minor/Enhancement

**Automatic FAIL:** มี P0, Critical Requirement FAIL/PARTIAL, Main Workflow FAIL/PARTIAL, Hard Reject, Console Error, หรือ Post-Build Gate FAIL

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

ตรวจ Blueprint Traceability (WF/REQ/FN/BR/ST), Factory Compliance, UI/UX,
interaction, technical QA และ required deliverables ตาม checklist v2.1

รายงาน:
1. Overall PASS / PASS WITH ISSUES / FAIL
2. Blueprint Traceability Table พร้อม evidence
3. Design/Factory deviations
4. Interaction/Technical issues
5. Fix List P0/P1/P2
6. Final: RETURN TO MOCKUP BUILDER หรือ READY FOR HUMAN REVIEW
```
