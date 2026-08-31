# Factory Gate — Post-Build Checklist

ตรวจ `index.html` หลัง Builder Self-QA ก่อนส่ง Independent QA

## A. Structure / Security
- [ ] Single `index.html`
- [ ] ไม่มี External CDN/font/JS/CSS
- [ ] ไม่มี Real API / data exfiltration
- [ ] ไม่มีข้อมูลผู้ป่วยจริง
- [ ] Header metadata ครบ

## B. Design Compliance
- [ ] design values ใช้ `tokens.css`
- [ ] Reuse Existing Components/Patterns ตาม Pre-Build
- [ ] ไม่สร้าง design language ใหม่
- [ ] New reusable UI Declare Proposed New Pattern
- [ ] reference/limitation บันทึกไว้
- [ ] semantic colors ถูกความหมาย

## B2. Premium HIS Visual Gate — Mandatory
- [ ] **VG-01 Product Character:** ดูเป็น Clinical / Operational / Trustworthy / Calm / Professional Hospital Enterprise System ไม่ใช่ generic SaaS/AI dashboard
- [ ] **VG-02 Shell:** Desktop screen ใช้ `design-system/components/application-shell.html` หรือมี approved exception
- [ ] **VG-03 Icons:** ไม่มี Emoji เป็น UI/navigation/section/decorative icon
- [ ] **VG-04 Containers:** ไม่ Card Everywhere; operational data ใช้ panel/table/divider/split layout เป็นหลัก
- [ ] **VG-05 KPI:** Operational dashboard ตรวจ/use `enterprise-kpi-strip.html` ก่อน stat-card grid
- [ ] **VG-06 Color:** Neutral-first; Green/Orange/Red ใช้เมื่อมี semantic meaning เท่านั้น
- [ ] **VG-07 Density:** 1366×768 แสดง key operational state และ primary action ใน first viewport เมื่อ requirement เอื้อ
- [ ] **VG-08 Scale:** ไม่มี oversized heading/KPI/button/card แบบ marketing UI
- [ ] **VG-09 AI Theme:** AI/Prediction/Recommendation ใช้ Gorilla HIS visual language ไม่มี futuristic/marketing theme

VG-01/VG-02/VG-03/VG-06/VG-09 FAIL = P0 / Automatic FAIL.

## C. Blueprint Traceability
| ID | Blueprint Item | Evidence in index.html | Interaction/State | Result |
|---|---|---|---|---|

- [ ] WF-* ครบ
- [ ] REQ-* ครบ
- [ ] FN-* ครบ
- [ ] BR-* ครบ
- [ ] ST-* ครบตาม Blueprint

Result = PASS / PARTIAL / FAIL / N/A. PARTIAL ไม่ถือว่า PASS สำหรับ Main Workflow/Critical item.

## D. Functional
- [ ] Main Workflow click-through ได้
- [ ] Main actions ทำงาน
- [ ] Modal/Drawer/Tabs/Filter/Search ใน scope ทำงาน
- [ ] ไม่มี Dead Button ใน Main Workflow
- [ ] Loading/Empty/Error/required states ครบ
- [ ] ไม่มี definitive diagnosis wording / hidden chain-of-thought

## E. Technical / Viewport
- [ ] ไม่มี Console Error
- [ ] 1366×768 ใช้งานได้
- [ ] 1920×1080 ใช้งานได้
- [ ] ไม่มี workflow-blocking overflow/overlay

## F. Required Deliverables
- [ ] Design Notes
- [ ] `prompt-used.md`
- [ ] Builder Self-QA ตาม qa-checklist
- [ ] Pre-Build Result + Blueprint Traceability
- [ ] Premium HIS Visual Gate result พร้อม evidence

## Result
- [ ] PASS → SEND TO INDEPENDENT QA
- [ ] FAIL → RETURN TO BUILDER

Automatic FAIL: Hard Reject, VG mandatory P0, Main Workflow FAIL/PARTIAL, Critical Requirement FAIL/PARTIAL, Console Error หรือ required deliverable ขาด
