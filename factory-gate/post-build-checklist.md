# Factory Gate — Post-Build Checklist

ตรวจ `index.html` หลัง Builder Self-QA ก่อนส่ง Independent QA

## A. Structure / Security
- [ ] Single `index.html`
- [ ] ไม่มี External CDN/font/JS/CSS รวม Font Awesome CDN/Kit
- [ ] ไม่มี Real API / data exfiltration
- [ ] ไม่มีข้อมูลผู้ป่วยจริง
- [ ] Header metadata ครบ

## B. Binding Reuse Verification — Mandatory

> ห้ามให้ PASS จากข้อความใน Design Notes หรือ Pre-Build อย่างเดียว ต้องตรวจ implementation ใน `index.html` จริง

| Pre-Build Commitment | Approved Source | Evidence in index.html | Actually Reused? | Result |
|---|---|---|---|---|
| Application Shell | `application-shell.html` | structure/class/section evidence | Yes/No | PASS/FAIL |
| Design Tokens | `tokens.css` | approved token names used directly | Yes/No | PASS/FAIL |
| Icons | `icon-rules.md` | semantic Font Awesome classes/mapping | Yes/No | PASS/FAIL |
| KPI | `enterprise-kpi-strip.html` / N/A | component structure evidence | Yes/No/N/A | PASS/N/A/FAIL |
| Operational Container | `operational-panel.html` / N/A | panel/table/divider evidence | Yes/No/N/A | PASS/N/A/FAIL |
| Other Components/Patterns | declared paths | implementation evidence | Yes/No/N/A | PASS/N/A/FAIL |

Automatic FAIL เมื่อ:
- [ ] Desktop module สร้าง custom header/nav/shell แทน `application-shell.html` โดยไม่มี approved exception
- [ ] พบ local palette/token aliases เช่น `--primary-color`, `--success-color`, `--danger-color`, `--card-bg`, `--bg-main` เมื่อ approved tokens รองรับอยู่แล้ว
- [ ] พบ hardcoded design values ที่ `tokens.css` ครอบคลุม
- [ ] Pre-Build ประกาศ Reuse แต่ implementation เขียน component/style ใหม่แทนโดยไม่มี approved exception
- [ ] Operational dashboard ใช้ stat-card grid แทน `enterprise-kpi-strip.html` ทั้งที่ component รองรับ requirement และไม่มี approved exception
- [ ] Card ถูกใช้เป็น default container อย่างเป็นระบบแทน approved operational panel/table/divider language

## C. Design Compliance
- [ ] design values ใช้ approved `tokens.css` names โดยตรง
- [ ] Reuse Existing Components/Patterns ตาม Binding Reuse Contract
- [ ] ไม่สร้าง design language ใหม่
- [ ] New reusable UI Declare Proposed New Pattern
- [ ] reference/limitation บันทึกไว้
- [ ] semantic colors ถูกความหมาย

## C2. Premium HIS Visual Gate — Mandatory
- [ ] **VG-01 Product Character:** ดูเป็น Clinical / Operational / Trustworthy / Dense / Calm / Professional Hospital Enterprise System ไม่ใช่ generic SaaS/AI dashboard
- [ ] **VG-02 Shell:** Desktop screen ใช้ implementation structure จาก `design-system/components/application-shell.html` จริง หรือมี approved exception
- [ ] **VG-03 Font Awesome Compliance:** semantic mapping ตาม `icon-rules.md`, default `fa-solid`, no Emoji, no unnecessary custom SVG, no external FA CDN/Kit
- [ ] **VG-04 Containers:** ไม่ Card Everywhere; operational data ใช้ panel/table/divider/split layout เป็นหลัก
- [ ] **VG-05 KPI:** Operational dashboard reuse `enterprise-kpi-strip.html` เมื่อรองรับ requirement; ไม่สร้าง stat-card grid ทดแทนเอง
- [ ] **VG-06 Color:** Neutral-first; ใช้ approved tokens โดยตรง; Green/Orange/Red ใช้เมื่อมี semantic meaning เท่านั้น
- [ ] **VG-07 Density:** 1366×768 แสดง key operational state และ primary action ใน first viewport เมื่อ requirement เอื้อ
- [ ] **VG-08 Scale:** ไม่มี oversized heading/KPI/button/card แบบ marketing UI
- [ ] **VG-09 AI Theme:** AI/Prediction/Recommendation ใช้ Gorilla HIS visual language ไม่มี futuristic/marketing theme

VG-01/VG-02/VG-03/VG-06/VG-09 FAIL = P0 / Automatic FAIL.
Systematic Card Everywhere หรือ bypass approved KPI/container language สามารถยกระดับ VG-04/VG-05 เป็น P0 ได้

## D. Blueprint Traceability
| ID | Blueprint Item | Evidence in index.html | Interaction/State | Result |
|---|---|---|---|---|

- [ ] WF-* ครบ
- [ ] REQ-* ครบ
- [ ] FN-* ครบ
- [ ] BR-* ครบ
- [ ] ST-* ครบตาม Blueprint

Result = PASS / PARTIAL / FAIL / N/A. PARTIAL ไม่ถือว่า PASS สำหรับ Main Workflow/Critical item.

## E. Functional
- [ ] Main Workflow click-through ได้
- [ ] Main actions ทำงาน
- [ ] Modal/Drawer/Tabs/Filter/Search ใน scope ทำงาน
- [ ] ไม่มี Dead Button ใน Main Workflow
- [ ] Loading/Empty/Error/required states ครบ
- [ ] ไม่มี definitive diagnosis wording / hidden chain-of-thought

## F. Technical / Viewport
- [ ] ไม่มี Console Error
- [ ] 1366×768 ใช้งานได้
- [ ] 1920×1080 ใช้งานได้
- [ ] ไม่มี workflow-blocking overflow/overlay

## G. Required Deliverables
- [ ] Design Notes รวม Reuse Contract result + Icon Mapping
- [ ] `prompt-used.md`
- [ ] Builder Self-QA ตาม qa-checklist
- [ ] Pre-Build Result + Blueprint Traceability
- [ ] Binding Reuse Verification Table
- [ ] Premium HIS Visual Gate result พร้อม evidence

## Result
- [ ] PASS → SEND TO INDEPENDENT QA
- [ ] FAIL → RETURN TO BUILDER

Automatic FAIL: Hard Reject, Binding Reuse Verification FAIL, VG mandatory P0, Main Workflow FAIL/PARTIAL, Critical Requirement FAIL/PARTIAL, Console Error หรือ required deliverable ขาด
