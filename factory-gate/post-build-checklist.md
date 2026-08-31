# Factory Gate — Post-Build Checklist

ตรวจ `index.html` หลัง Builder ทำ Self-QA แล้ว ก่อนส่ง Independent QA Agent

## A. Structure / Security
- [ ] Single `index.html`
- [ ] ไม่มี External CDN / external font / external JS/CSS
- [ ] ไม่มี Real API / ส่งข้อมูลออกภายนอก
- [ ] ไม่มีข้อมูลผู้ป่วยจริง
- [ ] มี header comment / required metadata ตาม `AI_INSTRUCTIONS.md`

## B. Design Compliance
- [ ] สี, spacing, font size, radius, shadow และ design values ที่ token รองรับ ใช้ `tokens.css`
- [ ] Reuse Existing Components ตาม Pre-Build Plan
- [ ] Reuse Existing Patterns ตาม Pre-Build Plan
- [ ] ไม่สร้าง design language ใหม่
- [ ] New reusable UI ถูก Declare `Proposed New Pattern`
- [ ] Gold Standard/Actual Screenshot ที่เกี่ยวข้องถูกใช้ตามแผน หรือบันทึก N/A/limitation ไว้
- [ ] Patient-safety semantic colors ใช้ถูกความหมาย

## C. Blueprint Traceability
สร้างตารางโดยใช้ ID ชุดเดียวกับ Pre-Build:

| ID | Blueprint Item | Evidence in index.html | Interaction/State | Result |
|---|---|---|---|---|

- [ ] Workflow `WF-*` ครบ
- [ ] Requirements `REQ-*` ครบ
- [ ] Functions `FN-*` ครบ
- [ ] Business Rules `BR-*` ครบ
- [ ] States/Exceptions `ST-*` ครบตาม Blueprint

สถานะ: `PASS / PARTIAL / FAIL / N/A`  
**PARTIAL ไม่ถือว่า PASS สำหรับ item ที่อยู่ใน Main Workflow หรือถูกระบุ Critical ใน Blueprint**

## D. Functional
- [ ] Main Workflow click-through ได้จริง
- [ ] Main buttons/actions ทำงาน
- [ ] Modal/Drawer/Tabs/Filter/Search ที่อยู่ใน scope ทำงาน
- [ ] ไม่มี Dead Button ใน Main Workflow
- [ ] Loading/Empty/Error และ states อื่นครบตาม `AI_INSTRUCTIONS.md`, UX rules และ Blueprint
- [ ] ไม่มี definitive diagnosis wording / hidden chain-of-thought ตามกฎเดิม

## E. Technical / Viewport
- [ ] ไม่มี Console Error
- [ ] 1366×768 ใช้งานได้
- [ ] 1920×1080 ใช้งานได้
- [ ] ไม่มี overflow/overlay ที่ทำให้ workflow/action ใช้งานไม่ได้

## F. Required Deliverables / Traceability
- [ ] Design Notes ครบตาม `AI_INSTRUCTIONS.md`
- [ ] `prompt-used.md` ถูกจัดเตรียม/อัปเดตเพื่อ trace prompt ที่ใช้
- [ ] Builder Self-QA ตาม `modules/_feature-template/review/qa-checklist.md` เสร็จแล้ว
- [ ] Pre-Build Result และ Blueprint Traceability แนบกับงาน

## Result
- [ ] **PASS → SEND TO INDEPENDENT QA AGENT**
- [ ] **FAIL → RETURN TO BUILDER**

Automatic FAIL: Hard Reject ใน `FACTORY_GATE.md`, Main Workflow FAIL/PARTIAL, Critical Requirement FAIL/PARTIAL, Console Error, หรือ required deliverable ขาด
