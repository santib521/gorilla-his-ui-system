# Factory Gate Report — hospital-command-center/mission-control

**Blueprint:** `Application blueprint_Hospital Command Center.txt` (v1.0)
**Builder:** Claude (Claude Code / Cowork)
**วันที่:** 2026-08-31
**อ้างอิงกระบวนการ:** `GORILLA_HIS_MOCKUP.md` (Factory Gate v1.0)

> หมายเหตุลำดับเหตุการณ์: `index.html` ของ feature นี้ถูกสร้างและอนุมัติ self-QA ไปแล้วรอบหนึ่งก่อนที่ทีมจะเพิ่ม `factory-gate/` เข้า repo และก่อนที่ผู้ใช้จะแนบ Application Blueprint แบบทางการ (พร้อม WF/REQ/FN/BR/ST) มาให้ รายงานนี้คือการนำงานที่มีอยู่แล้วมาผ่านกระบวนการ Factory Gate อย่างเป็นทางการย้อนหลัง (retroactive) ตามคำสั่งล่าสุด: ทำ Pre-Build Analysis + Gate ก่อน แล้วจึงปิด Gap ที่พบให้ตรงกับ Blueprint ทุกข้อ ก่อนสรุปเป็น Post-Build Gate

---

## A. Pre-Build Analysis

### A.1 Source Readiness — Evidence

อ่านตามลำดับที่ `GORILLA_HIS_MOCKUP.md` §1 กำหนดจริงทุกไฟล์ ก่อนวิเคราะห์ Gap:

| # | ไฟล์ | Evidence / Path ที่อ่านจริง |
|---|---|---|
| 1 | `AI_INSTRUCTIONS.md` | `/home/claude/gorilla-his-ui-system/AI_INSTRUCTIONS.md` (ยืนยันตรงกับต้นฉบับล่าสุดบน GitHub ผ่าน `raw.githubusercontent.com/santib521/gorilla-his-ui-system/main/AI_INSTRUCTIONS.md` — content เหมือนกัน v1.2) |
| 2 | `factory-gate/FACTORY_GATE.md` | Fetch จาก `raw.githubusercontent.com/.../factory-gate/FACTORY_GATE.md` (โฟลเดอร์นี้ยังไม่มีใน local clone ตอนเริ่ม session — fetch ใหม่จาก GitHub โดยตรง) |
| 3 | `factory-gate/pre-build-checklist.md` | Fetch จาก GitHub เช่นเดียวกัน |
| 4 | `factory-gate/post-build-checklist.md` | Fetch จาก GitHub เช่นเดียวกัน |
| 5 | `design-system/design-rules.md`, `ux-rules.md`, `tokens.css` | `/home/claude/gorilla-his-ui-system/design-system/` (อ่านแล้วในรอบสร้างงานเดิม — เนื้อหาไม่เปลี่ยน) |
| 6 | `design-system/components/*` | `alert-banner.html, buttons.html, drawer.html, form-controls.html, modal-dialog.html, notification-toast.html, stat-card.html, status-badges.html, tabs.html, worklist.html` ฯลฯ |
| 7 | `design-system/patterns/*` | `dashboard-home.md, approval-confirmation.md, search-and-table.md, list-detail-page.md` |
| 8 | `modules/README.md` | ระบุ Hospital Command Center เป็น cross-module feature (ไม่มี module README เดี่ยว) |
| 9 | `approved-mockups/INDEX.md` | มีเพียงแถวตัวอย่าง (placeholder) — ยังไม่มี Gold Standard จริงในระบบ ณ วันที่ทำงาน |
| 10 | `screenshots/actual-gorilla-his/` | `02-main-menu.jpg`, `06-doctor-screen_Dashboard01.jpg`, `18 IPD dashboard.jpg` |
| 11 | Application Blueprint | `Application blueprint_Hospital Command Center.txt` (แนบมากับ prompt นี้) |

**Result: Source Readiness = PASS** (เข้าถึงได้ครบทุกไฟล์บังคับ รวม `factory-gate/*` ที่ต้อง fetch จาก GitHub โดยตรงเนื่องจาก local clone ยังไม่มีโฟลเดอร์นี้)

### A.2 Blueprint Understanding (สรุป)

1. **Objective:** ศูนย์บัญชาการข้อมูล Real-Time ของโรงพยาบาล รวมข้อมูลจาก HIMS/HIS ผ่าน AI Brain Engine (Predict/Detect/Recommend/Dispatch) กระจายให้ผู้ใช้ 3 ระดับ + Self-Service Config
2. **Users/Roles:** Level 1 (C-Level/Strategic), Level 2 (Middle Management/Tactical), Level 3 (Operational Frontline), System/Command Center Administrator (Self-Service Config)
3. **Scope:** 5 Functional Areas (AI Brain Engine, L1, L2, L3, Self-Service Config) + สถานะ Data Sync (LIVE HIMS SYNC/Last Refresh/Sync Status) — Out of Scope: ไม่ระบุใน Blueprint (`N/A — not present in Blueprint`)
4. **Main Workflow:** ดู WF-01…WF-16 ด้านล่าง
5. **Function สำคัญ:** ดู FN Traceability ด้านล่าง (จัดกลุ่มตาม Functional Area)
6. **Business Rule สำคัญ:** BR-01…BR-10 (ตรงกับ Blueprint §12 ทุกข้อ ไม่มีการแต่งเพิ่ม)
7. **States/Exceptions สำคัญ:** ST-01…ST-07 + ตัวอย่างเฉพาะ 5 กรณีใน Blueprint §13

### A.3 Blueprint Traceability IDs

#### Workflow (WF) — จาก Blueprint §4

| ID | Blueprint Step |
|---|---|
| WF-01 | Normal Operations |
| WF-02 | ER Patient Volume เพิ่มขึ้น |
| WF-03 | ระบบเข้าสู่ Peak ER Surge |
| WF-04 | AI Brain Engine ตรวจพบแนวโน้มความเสี่ยง |
| WF-05 | AI วิเคราะห์ผลกระทบ ER Queue/Waiting Time/Bed Demand/Staff Workload |
| WF-06 | AI สร้าง Recommendation |
| WF-07 | Recommendation ถูกส่งไป Level 2 |
| WF-08 | Level 2 ตรวจสอบ Alert และ Recommendation |
| WF-09 | Level 2 Approve/Dispatch Action |
| WF-10 | Level 3 ได้รับ Operational Task |
| WF-11 | เจ้าหน้าที่ Start Task |
| WF-12 | Task Status → In Progress |
| WF-13 | เจ้าหน้าที่ Complete Task |
| WF-14 | Task Status → Completed |
| WF-15 | Hospital Capacity/Operational Status ปรับดีขึ้น |
| WF-16 | Dashboard/KPI แสดงผลสถานการณ์ล่าสุด |

(Blueprint §16 "Main Demo Acceptance Flow" ระบุลำดับเดียวกันซ้ำ — ใช้ WF-01…WF-16 ชุดเดียวอ้างอิงทั้งสองที่)

#### Requirements (REQ) — จาก Blueprint §5,6,7,8,9,10,11

| ID | Requirement |
|---|---|
| REQ-01 | Navigation ครบ 5 Functional Areas |
| REQ-02 | รักษา Scenario/Operational State เดิมเมื่อเปลี่ยน Functional Area |
| REQ-03 | Scenario Simulator ≥3 scenario (Normal/Peak ER Surge/Bed Gridlock Critical) |
| REQ-04 | เปลี่ยน Scenario แล้ว Dashboard/KPI/Alert/Recommendation/Operational Status เปลี่ยนตาม |
| REQ-05 | แสดงสถานะเชื่อมต่อ HIMS/HIS (LIVE HIMS SYNC/Last Refresh/Sync Status) รวมถึงกรณี Error |
| REQ-06 | AI Brain Engine: Data Sources + Conceptual Data Flow Diagram |
| REQ-07 | AI Brain Engine: Live Raw Data Feed (mock event ต่อเนื่อง) |
| REQ-08 | AI Brain Engine: Predictive Analytics (ER Admission Forecast, Discharge Predictor, EWS Deterioration Prediction) |
| REQ-09 | AI Brain Engine: Recommendation Engine (Situation/Recommendation/Reason/Priority/Target Level/Recommended Action) + Dispatch |
| REQ-10 | Level 1 KPI (Bed Occupancy %, ALOS, ER Overcrowding Index, ER Waiting Time, Daily Census, Revenue/Census Correlation) |
| REQ-11 | Level 1 Visualization (Bed Occupancy Trend+24h Prediction, Department Throughput, Bottleneck Overview) |
| REQ-12 | Level 1 Strategic Decision Console (Approve Flex Ward, Initiate Diversion) + Confirmation |
| REQ-13 | Level 2 ER Flow (Triage Queue/Waiting Doctor/Waiting Bed/Diversion Status) |
| REQ-14 | Level 2 IPD Bed Management (Occupied/Reserved/Cleaning/Available) |
| REQ-15 | Level 2 Logistics/Housekeeping (Cleaning Turnaround/Transport Queue/Pending Tasks) |
| REQ-16 | Level 2 Bottleneck Detection + Recommended Action + Dispatch ไป Level 3 |
| REQ-17 | Level 2 Threshold Simulation (simulation-only, ไม่แก้ production) |
| REQ-18 | Level 3 Operational View switcher (ER/Ward 5A/Housekeeping/Transport) |
| REQ-19 | Level 3 Ward Bed Grid (Occupied/Available/Reserved/Cleaning/Discharge Ready) |
| REQ-20 | Level 3 Patient Context (mock) |
| REQ-21 | Level 3 Clinical/Operational Alert (EWS/Deterioration/Discharge Readiness/Clinical Alert) — non-diagnostic wording |
| REQ-22 | Level 3 Operational Task Pending→In Progress→Completed |
| REQ-23 | Self-Service Rule Builder (IF/AND/THEN: Metric/Operator/Threshold/Logical Condition/Action/Target Level) |
| REQ-24 | Self-Service Dashboard Configuration (widget/KPI on-off ต่อ Level) |
| REQ-25 | Self-Service Metric Mapping (Source System/Field/Target Metric/Status) |

#### Business Rules (BR) — จาก Blueprint §12 (คงข้อความเดิมทุกข้อ)

BR-01 Scenario Consistency · BR-02 Recommendation Routing · BR-03 Strategic Action Confirmation · BR-04 Level 2 Dispatch · BR-05 Task Lifecycle (ห้ามข้าม In Progress) · BR-06 Operational Feedback · BR-07 Mock Patient Data · BR-08 Clinical Recommendation (Decision Support เท่านั้น) · BR-09 Simulation Isolation · BR-10 Live Data Status

#### States/Exceptions (ST) — จาก Blueprint §13

| ID | State |
|---|---|
| ST-01 | Normal |
| ST-02 | Loading — `N/A — not present as async in Blueprint`: mock data โหลดพร้อม render ทันที ไม่มี async จริง (ยกเว้นตาม `error-handling.md` ที่ไม่บังคับ Loading เมื่อไม่มี async) |
| ST-03 | Empty (Bottleneck ไม่มี / Decision รอดำเนินการไม่มี / Task ไม่มี / **Recommendation ไม่มี** / Widget ปิด) |
| ST-04 | Error (**Data Sync Error**, Metric Mapping ไม่ครบ, **Rule Builder/Invalid Rule**) |
| ST-05 | Success (Toast ยืนยันหลัง Dispatch/Approve/Save/Complete) |
| ST-06 | Disabled (**Task Already Completed** — ปุ่ม Start/Complete หายไปเมื่อ Task เสร็จแล้ว) |
| ST-07 | Validation (Metric Mapping field ว่าง, **Rule Builder Threshold ไม่ถูกต้อง**) |

ตัวอย่างเฉพาะ 5 กรณีใน Blueprint §13 ทั้งหมด map เข้ากับ ST-03/04/06/07 ข้างต้นครบ (ตัวหนา = จุดที่พบเป็น Gap และแก้ในรอบนี้ — ดู §B)

### A.4 Gorilla HIS Design Reference

- **Existing Components ที่ reuse:** `buttons.html, status-badges.html, stat-card.html, modal-dialog.html, notification-toast.html, worklist.html, alert-banner.html, tabs.html, drawer.html, form-controls.html`
- **Existing Patterns ที่ reuse:** `dashboard-home.md, approval-confirmation.md, search-and-table.md, list-detail-page.md`
- **Gold Standard ที่ใกล้เคียง:** `N/A — no relevant Gold Standard found` (`approved-mockups/INDEX.md` ยังไม่มี entry จริงในระบบ ณ วันที่ทำงาน — ไม่ถือเป็น FAIL ตาม Reference Availability Rule)
- **Actual Screenshot references:** `screenshots/actual-gorilla-his/02-main-menu.jpg` (โทนสี topbar), `06-doctor-screen_Dashboard01.jpg` (ต้นแบบ stat-card row), `18 IPD dashboard.jpg` (ต้นแบบ bed grid) — และภาพอ้างอิง "Registered Patients" ที่ผู้ใช้แนบเพิ่มระหว่างงาน (ใช้ปรับ panel-banner/pill badge ในรอบ Premium Light)
- **Design Rules/UX Rules ที่มีผล:** Product Character indigo/periwinkle (`design-rules.md` §0), Semantic Color บังคับใช้แม้กับ KPI บริหาร (§4), Confirmation ก่อน Critical Action (`ux-rules.md` §2, `approval-confirmation.md`), no external CDN (`AI_INSTRUCTIONS.md` §2)

### A.5 Gap Analysis

ของเดิม (`index.html` ที่สร้างไปแล้ว) ครอบคลุม REQ/FN เกือบทั้งหมดตรงตาม Blueprint อยู่แล้ว (เพราะสร้างจาก informal brief ที่เนื้อหาตรงกับ Blueprint นี้เกือบทุกข้อ) จุดที่ตรวจพบว่า**ยังไม่ครบ**เมื่อเทียบกับ Blueprint แบบเป็นทางการ (มี ID ชัดเจน) มี 3 จุด — ไม่มีจุดใดต้องสร้าง Proposed New Pattern เพิ่ม ใช้ CSS/JS pattern เดิมที่มีอยู่แล้วทั้งหมด:

| # | Gap ที่พบ | Blueprint ref | เดิมเป็นอย่างไร | แก้อย่างไร |
|---|---|---|---|---|
| 1 | ไม่มี Data Sync Error state | REQ-05, BR-10, ST-04 | `LIVE HIMS SYNC` แสดงแค่ normal/syncing (เขียว/เหลือง) ไม่มี error state | เพิ่ม state `syncError` + คลิกที่ sync-status เพื่อ demo toggle → แสดง "Sync Error · Last Successful Sync HH:MM:SS" (จุดแดง, toast error) และคลิกซ้ำเพื่อจำลองกลับมาเชื่อมต่อ — ใช้ token สี/รูปแบบ toast เดิมทั้งหมด |
| 2 | Rule Builder ไม่มี Invalid Rule validation | REQ-23, ST-04/07 | `+ Save Rule` เอา `parseFloat()` ของ threshold ไปใช้ตรง ๆ ถ้าว่าง/ไม่ใช่ตัวเลขจะได้ `NaN` เงียบ ๆ ไม่มี error ใด ๆ | เพิ่ม validation ก่อน save: threshold ว่าง/ไม่ใช่ตัวเลข → ไฮไลต์กรอบสีแดง (ใช้ `--color-status-critical` เดิม) + toast error บล็อกการบันทึก (รูปแบบเดียวกับ Metric Mapping validation ที่มีอยู่แล้ว) |
| 3 | ไม่มี "No Recommendation" empty state ที่ demo ได้จริง | ST-03, Acceptance #15 | Recommendation การ์ดไม่หายไปหลัง Dispatch (กดซ้ำได้ไม่มีผลเสีย แต่ไม่มีทางเห็น empty state) | Dispatch แล้วเอาการ์ดออกจากรายการ (ตาม scenario) — เมื่อ dispatch ครบทุกใบ แสดง `.wl-empty` message แบบเดียวกับจุดอื่นในระบบ (`ไม่มีคำแนะนำจาก AI ในสถานการณ์นี้ขณะนี้...`) |

**Gap อื่นที่ตรวจแล้วไม่พบ (ของเดิมครอบคลุมอยู่แล้ว):** Revenue/Census Correlation KPI, ALOS, Bottleneck Overview (Level 1), Action Pending Confirmation (Strategic Decision Console ใช้ modal เดิม), Task Already Completed (ปุ่ม Start/Complete หายไปเมื่อ task เสร็จแล้วอยู่แล้ว — ตรวจโค้ดยืนยันแล้ว)

### A.6 Screen/View Plan

ไม่มีการเปลี่ยนแปลงจากแผนเดิม — ยังคง 5 view เดียวกัน: `view-aibrain`, `view-level1`, `view-level2`, `view-level3`, `view-config` ภายใน SPA shell เดียว (`index.html`) ทั้งหมด Mapping WF/REQ/FN/BR/ST เข้ากับแต่ละ view ตรงตาม Blueprint §3 Scope 1:1

### A.7 Pre-Build Factory Gate — Evidence Table

| Gate Item | Evidence / Repo Path / Blueprint Section | Result |
|---|---|---|
| Source readiness | ดู §A.1 — อ่านครบทุกไฟล์บังคับ รวม fetch `factory-gate/*` จาก GitHub โดยตรง | PASS |
| Blueprint extraction | WF-01…16, REQ-01…25, BR-01…10, ST-01…07 (§A.3) | PASS |
| Design references | `design-system/*`, screenshots 3 ไฟล์, Gold Standard = N/A (ไม่ถือ FAIL ตาม Reference Availability Rule) | PASS |
| Screen/flow plan | §A.6 — 5 view เดิม ตรงกับ Blueprint Scope ทุกข้อ | PASS |

### **Pre-Build Gate Result: PASS — BUILD ALLOWED**

(ไม่มี Hard Reject ข้อใดใน `FACTORY_GATE.md` เกิดขึ้น — ไม่มี CDN ภายนอก, ไม่ hardcode ค่า token, ไม่มี design language ใหม่, ไม่มี Main Workflow/Critical Requirement หายไป)

---

## B. Build — สิ่งที่ทำในรอบนี้

ปิด 3 Gap ใน §A.5 ทั้งหมดใน `modules/hospital-command-center/index.html` (โค้ดจริง, ไม่ใช่ mockup ใหม่) โดยใช้ token/component/toast pattern เดิมทุกจุด ไม่มี Proposed New Pattern เพิ่มเติมจาก 6 จุดเดิมที่เคย declare ไว้ในรอบสร้างงานแรก

---

## C. Builder Self-QA

ทำตาม `modules/_feature-template/review/qa-checklist.md` (ผลเต็มอยู่ใน `review/qa-checklist.md` ของ feature นี้) — สรุปเฉพาะจุดที่เกี่ยวกับรอบนี้:

- [x] div-balance check ผ่าน (248 opens / 248 closes)
- [x] `node --check` บน `<script>` content ผ่าน ไม่มี syntax error
- [x] Playwright headless: sync-error toggle ทำงานถูกต้องทั้ง 2 ทิศทาง, Rule Builder บล็อก invalid threshold ได้จริง (rule count ไม่เพิ่มขึ้นเมื่อกรอกว่าง, เพิ่มขึ้นเมื่อกรอกถูก), Recommendation empty state แสดงถูกต้องหลัง dispatch ครบ, chain เดิม (gridlock→flexward dispatch→approve→task) ยังทำงานถูกต้องเหมือนก่อนแก้
- [x] ไม่มี PAGEERROR/CONSOLE error ตลอดการทดสอบ
- [x] Screenshot 1440×900 ยืนยันภาพทั้ง sync-error state และ recommendation empty-state ตรงตามที่ตั้งใจ

**Self-QA Result: PASS** (ไม่พบ FAIL ที่ต้องแก้ก่อนส่ง Post-Build Gate)

---

## D. Post-Build Factory Gate

### D.1 Structure/Security
Single `index.html` · ไม่มี external CDN/font/JS/CSS · ไม่มี real API · ไม่มีข้อมูลผู้ป่วยจริง · มี header comment ครบ → **PASS**

### D.2 Design Compliance
สี/spacing/font/radius/shadow ใหม่ทั้งหมด (sync-error, rule validation, rec empty-state) อ้าง `var(--color-status-critical)` และ class `.wl-empty`/`.toast--error` เดิม ไม่ hardcode ค่าใหม่ใด ๆ · ไม่มี design language ใหม่ · ไม่มี reusable UI ใหม่ที่ยังไม่ Declare (ใช้ pattern เดิมทั้งหมด) → **PASS**

### D.3 Blueprint Traceability Table (สรุปย่อ — เต็มดูใน §A.3 ที่ map กับ view ใน §A.6)

| ID กลุ่ม | Evidence ใน index.html | Interaction/State | Result |
|---|---|---|---|
| WF-01…16 (Main Workflow) | Scenario Simulator → `dispatchRecommendation()` → `state.decisions`/`state.level2Alerts` → `advanceTask()` → `state.ward5aBeds` update | Normal→erSurge/gridlock→AI detect→Recommend→Dispatch L2→Approve→L3 Task→Complete→Capacity update — ทดสอบ end-to-end ด้วย Playwright ผ่านครบ | PASS |
| REQ-01…25 | ทุก view/section ที่ระบุใน §A.6 | คลิกทดสอบครบทุก interaction หลัก | PASS |
| BR-01…10 | Scenario-driven re-render, `dispatchRecommendation()` routing by target level, `modalConfirm`, Level2→Level3 dispatch, task status guard, mock data only, non-diagnostic wording, threshold-sim ไม่แก้ scenario object จริง, sync-status label | ตรวจโค้ด+ทดสอบจริงทุกข้อ | PASS |
| ST-01…07 | รวม 3 จุดที่เพิ่งปิด gap (§B) + จุดเดิมที่มีอยู่แล้ว | Screenshot + Playwright ยืนยันครบ | PASS |

**ไม่มี Critical Requirement หรือ Main Workflow item ใดอยู่ในสถานะ PARTIAL/FAIL**

### D.4 Functional
Main Workflow click-through ได้จริงตั้งแต่ต้นจนจบ · ปุ่ม/Modal/Drawer/Tabs หลักทำงานครบ · ไม่มี Dead Button ใน Main Workflow · States ครบตาม `ux-rules.md` §5 และ Blueprint §13 (รวมจุดที่เพิ่งปิด gap) · ไม่มี definitive diagnosis wording / hidden chain-of-thought → **PASS**

### D.5 Technical/Viewport
ไม่มี Console Error (ยืนยันซ้ำหลังแก้ทุกจุด) · ใช้งานได้ที่ 1366×768 และ 1920×1080 (ตรวจ `scrollWidth`/`clientWidth` ของ topbar nav ไม่ overflow) → **PASS**

### D.6 Required Deliverables
Design Notes ครบใน `prompt-used.md` (Revision 1-3) · `prompt-used.md` อัปเดตแล้ว · Builder Self-QA เสร็จ (`review/qa-checklist.md`) · Pre-Build Result + Blueprint Traceability แนบในไฟล์นี้ → **PASS**

### **Post-Build Gate Result: PASS → READY FOR INDEPENDENT QA**

---

## E. หมายเหตุสำคัญ — Promotion

ตาม `FACTORY_GATE.md` § Gold Standard Rule: การผ่าน Post-Build Gate **ยังไม่ใช่ Gold Standard หรือ Approved Mockup** — ต้องผ่าน Independent QA Agent → Human Review → Promotion ตาม `approved-mockups/GOLD_STANDARD.md` ก่อน จึงจะย้ายไปที่ `approved-mockups/` และบันทึกใน `approved-mockups/INDEX.md` ได้ (Claude/Builder **ห้าม Promote เอง**) นอกจากนี้ feature นี้ยังมี **6 Proposed New Pattern** (Command Center App Shell, Scenario Simulator, Trend/Bar Chart, Bed Status Grid, AI Data Flow Diagram, Rule Builder) ที่ยังไม่ผ่าน weekly design sync ตามที่ระบุไว้ตั้งแต่รอบสร้างงานแรก — ต้องเสนอเข้าที่ประชุมก่อนให้ทีมอื่นเอาไปใช้ต่อ

---

## F. Revision — Master Template v2 Rollout (2026-08-31, หลัง Post-Build Gate PASS รอบแรก)

หลังผู้ใช้ให้ feedback ว่า UI "ดูเป็น AI ทำมากเกินไป" และสั่งให้แก้ที่ **Design Authority ระดับ repo** ไม่ใช่แค่ feature นี้ (เพื่อไม่ให้ AI builder คนอื่นผลิตซ้ำ) จึงมีการเพิ่ม/แก้ไขไฟล์ระดับ Master Template ต่อไปนี้ **นอกเหนือ** จาก `modules/hospital-command-center/index.html`:

| ไฟล์ | การเปลี่ยนแปลง |
|---|---|
| `design-system/design-rules.md` | เพิ่ม § 0.5 "Enterprise HIS Visual Character (Master Rule)" — 8 sub-rules บังคับทุก feature ในอนาคต (ห้าม emoji, card ต้องไม่ใช่ container เริ่มต้น, ใช้ enterprise-kpi-strip ก่อน stat-card, 90/10 color discipline, ล็อก Application Shell, Density Rule ที่ 1366×768, AI feature ห้ามมี AI Visual Theme, Premium HIS Visual Gate) |
| `design-system/components/enterprise-kpi-strip.html` | Component ใหม่ — แถบ KPI แนวนอนแบนสำหรับหน้าปฏิบัติการ แทน stat-card grid |
| `design-system/components/application-shell.html` | Component ใหม่ — Master Application Shell ที่ล็อกตายตัว (Topbar 56px + Sidebar 220px ตามภาพอ้างอิง "Registered Patients") |
| `design-system/components/README.md` | ระบุ stat-card ห้ามใช้กับหน้าปฏิบัติการ + เพิ่มแถว component ใหม่ 2 ตัว |
| `factory-gate/FACTORY_GATE.md` | เพิ่ม Hard Reject item: ไม่ผ่าน Premium HIS Visual Gate |
| `factory-gate/post-build-checklist.md` | เพิ่ม § G Premium HIS Visual Gate |
| `factory-gate/premium-his-visual-gate.md` | Gate ใหม่ทั้งไฟล์ — 7 คำถามบังคับ พร้อมผลตรวจของ feature นี้ (ผ่านทั้ง 7 ข้อ — ดูไฟล์นั้น) |

### F.1 การแก้ไขใน `index.html` ให้ตรงกับ Master Template v2

- **Shell rebuild:** เปลี่ยนจาก topbar+topnav เดิม เป็นโครง Sidebar (220px, `--color-bg-sidebar`) + Topbar (56px, `--color-blue-600`) ตาม `application-shell.html` ทุกจุด — breadcrumb, page title/subtitle (พร้อมเวลาล่าสุด+source) ย้ายเข้า shared header pattern (`PAGE_META`/`setPageHeader()`)
- **KPI conversion:** `renderPredictCards()`, `renderLevel1()`, `renderLevel2()` เปลี่ยนจาก stat-card grid (การ์ดใหญ่ + ไอคอนวงกลมสี) เป็น `kpiStrip()` (แถบแนวนอน ตัวเลขไม่ใหญ่กว่า page title, สีมีความหมายเฉพาะจุด critical/warning เท่านั้น)
- **De-cliché:** เอา gradient/glow ออกจาก `.flow-node--brain`, เอา gradient+glossy shadow ออกจาก bed-tile ทุกสถานะ, ลด `.rec-card` เหลือ border-left accent เดียว (ไม่มี colored-circle icon), เปลี่ยน `.panel-banner` (gradient) เป็น `.panel-header` (text header ธรรมดา)
- **Density fix (1366×768):** ลดความสูง `.feed-panel` (220px→96px), ปรับ `.flow-diagram` จาก column เดี่ยว 6 แถวเป็น grid 3 คอลัมน์ 2 แถว (และ Level 1/2/3 จาก column เป็น row), ลด padding/margin ของ Data Flow card และ "Recommendation Engine" section heading — ยืนยันด้วย Playwright ว่า `#shell-main` เนื้อหาทั้งหมด (Data Flow + Live Feed + Predictive Analytics KPI + Recommendation card พร้อม primary action) แสดงครบใน viewport 1366×768 โดยไม่ต้อง scroll

### F.2 Re-verification หลังแก้ (ทำซ้ำครบตาม Post-Build Checklist)

- Div/tag balance (Python regex): `div` 207/207, `section` 5/5, `nav` 1/1, `ul` 1/1, `li` 5/5 — สมดุลทุกตัว
- `node --check` บน extracted `<script>`: **OK** ไม่มี syntax error
- Playwright regression suite: nav switching ครบ 5 view, scenario switching (normal/erSurge/gridlock) กระทบ KPI strip ถูกต้อง, dispatch→recommendation empty-state ทำงาน, sync-error toggle ทำงาน, Rule Builder validation (invalid→red border→block save, valid→save สำเร็จ) ทำงาน — **console errors: 0**
- Screenshot ยืนยันภาพจริงที่ 1366×768 (ทุก view) และ 1920×1080 (AI Brain Engine) — ไม่มี overflow ที่กระทบ workflow/action หลัก
- Premium HIS Visual Gate (7 ข้อ): **ผ่านทั้งหมด** — บันทึกละเอียดใน `factory-gate/premium-his-visual-gate.md`

### **Post-Build Gate Result (Revision): PASS → READY FOR INDEPENDENT QA**

หมายเหตุ: Revision นี้ยังอยู่ในสถานะเดียวกับ §E คือผ่าน Post-Build Gate แต่ยังไม่ใช่ Gold Standard/Approved Mockup จนกว่าจะผ่าน Independent QA + Human Review + Promotion Criteria
