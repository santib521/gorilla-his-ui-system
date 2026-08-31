# Gorilla HIS Mockup QA Checklist — v2.0

**Feature:** << module/feature >>  
**Blueprint:** << Application blueprint_*.txt >>  
**Reviewer:** << QA Agent / Human >>  
**Overall:** ⬜ Approved ⬜ Rejected ⬜ Approved with comments

> QA ต้องตรวจจาก 3 Source พร้อมกัน: **Application Blueprint + Gorilla HIS Repository + index.html**

## 1. Blueprint Traceability — Mandatory
อ่าน Blueprint แล้วสกัด/ยืนยัน ID เดียวกับ Builder:
- `WF-*` Workflow
- `REQ-*` Requirements
- `FN-*` Functions
- `BR-*` Business Rules
- `ST-*` States/Exceptions

สร้างตาราง:

| ID | Blueprint Item | Expected | Evidence in index.html | Result | Issue/Fix |
|---|---|---|---|---|---|

Result = `PASS / PARTIAL / FAIL / N/A`

- [ ] Main Workflow ครบและ click-through ได้
- [ ] Critical Requirements ไม่มี FAIL
- [ ] Function List ครบตาม Scope
- [ ] Business Rules สำคัญถูก enforce/represent ใน UI
- [ ] Required States/Exceptions ครบ

## 2. Factory Compliance
- [ ] ผ่าน `factory-gate/post-build-checklist.md`
- [ ] Single `index.html`
- [ ] ไม่มี External CDN/font/CSS/JS
- [ ] ไม่มี Real API / data exfiltration
- [ ] ไม่มีข้อมูลผู้ป่วยจริง
- [ ] Header comment ครบ

## 3. Component / Pattern / Gold Standard
- [ ] Existing Components ถูก reuse ตาม Design Notes
- [ ] Existing Patterns ถูก reuse ตาม Design Notes
- [ ] ถ้ามี Gold Standard ที่เกี่ยวข้อง ถูกใช้เป็น reference โดยไม่ copy business context ผิดงาน
- [ ] New reusable UI ทุกจุด Declare `Proposed New Pattern`
- [ ] ไม่มีการสร้าง Design System ใหม่ซ่อนอยู่

## 4. Visual / UX / Patient Safety
- [ ] ใช้ tokens ตาม `tokens.css`
- [ ] Semantic color ถูกความหมาย
- [ ] Critical/Allergy/Patient-safety alert มี icon + text ไม่พึ่งสีอย่างเดียว
- [ ] Action hierarchy ถูกต้อง
- [ ] Table/Form/Tabs/Modal/Drawer สอดคล้อง pattern ของ Gorilla HIS

## 5. Interaction QA
ทดสอบ action สำคัญจริง ไม่ตรวจจากหน้าตาอย่างเดียว:
- [ ] Buttons
- [ ] Tabs/navigation
- [ ] Search/filter (ถ้ามี)
- [ ] Modal/Drawer/Confirmation (ถ้ามี)
- [ ] Status/Scenario/Task transitions (ถ้ามี)
- [ ] Validation และ Disabled state
- [ ] ไม่มี Dead Button ใน Main Workflow

## 6. States / Mock Data
- [ ] Loading ตามบริบท
- [ ] Empty ตามบริบท
- [ ] Error ตามบริบท
- [ ] Success/confirmation ตามบริบท
- [ ] Edge case ตาม Blueprint
- [ ] Clinical mock values สมเหตุสมผลเมื่อเกี่ยวข้อง

## 7. Technical QA
- [ ] ไม่มี Console Error ที่กระทบการใช้งาน
- [ ] 1366×768 layout ใช้งานได้
- [ ] 1920×1080 layout ใช้งานได้
- [ ] ไม่มี overflow/overlay ที่ทำให้ action สำคัญใช้ไม่ได้

## 8. Severity / Decision
จัด Issue:
- `P0` Critical — Main workflow, patient safety, critical requirement, broken app
- `P1` Major — function/compliance สำคัญไม่ครบ
- `P2` Minor/Enhancement

**Automatic Reject:** มี P0, Critical Requirement FAIL, Main Workflow FAIL, External CDN, Real Patient Data, หรือ Post-Build Gate FAIL

### Action
- `RETURN TO MOCKUP BUILDER` — ถ้าไม่ผ่าน
- `READY FOR HUMAN REVIEW` — ถ้าผ่าน QA

> AI QA ไม่มีสิทธิ์ Promote เป็น Gold Standard เอง ต้อง Human Approved ก่อน

## QA Agent Prompt
```text
คุณคือ Gorilla HIS Mockup QA & Design Compliance Agent
อ่าน Application Blueprint, factory-gate/FACTORY_GATE.md, post-build-checklist.md,
AI_INSTRUCTIONS.md, design-system, approved references และ index.html ที่ต้องตรวจ

ห้ามตรวจเฉพาะความสวยงาม ให้สร้าง Blueprint Traceability Table (WF/REQ/FN/BR/ST),
ตรวจ Factory Compliance, UI/UX, interaction และ technical QA ตาม checklist v2.0 นี้

รายงาน:
1. Overall PASS / PASS WITH ISSUES / FAIL
2. Blueprint Traceability Table
3. Design/Factory deviations
4. Interaction/Technical issues
5. Fix List เรียง P0/P1/P2
6. Final: RETURN TO MOCKUP BUILDER หรือ READY FOR HUMAN REVIEW
```
