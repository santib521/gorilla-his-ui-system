# QA Checklist — Directory สำหรับ "ตรวจสอบ Mockup" (1.2)

**Feature:** hospital-command-center/mission-control
**ผู้ตรวจ (Design QA Agent หรือ Design QA Lead/Human):** Claude (self-QA ด้วย headless browser + manual screenshot review) — ยังต้องให้ Design QA Lead/มนุษย์ยืนยันซ้ำก่อน approve จริง
**วันที่ตรวจ:** 2026-08-31 (v1 self-QA) / อัปเดต 2026-08-31 (v2 "Premium Light" revision — re-verify แล้ว ดู `prompt-used.md` § Revision 2)
**ผลตรวจโดยรวม:** ⬜ Approved ⬜ Rejected — ต้องแก้ไข ☑ Approved with comments (self-QA ผ่านครบ แต่ต้องรอ weekly design sync อนุมัติ 6 Proposed New Pattern ก่อนให้ทีมอื่นใช้ต่อ)

> ใช้ checklist นี้ทั้งแบบ **Human review** และแบบ **AI Design QA Agent** (ป้อน prompt ด้านล่างสุดของไฟล์นี้ให้ AI ตรวจแทนคน แล้วให้คนยืนยันผลอีกที)

## 1. Compliance กับกฎเหล็ก (AI_INSTRUCTIONS.md § 2)

- [x] เป็นไฟล์ `index.html` ไฟล์เดียว ไม่มีไฟล์ `.css`/`.js` แยก
- [x] ไม่มีการเรียก CDN ภายนอกใด ๆ (brief เดิมอนุญาต Tailwind/Chart.js/FontAwesome/Google Fonts แต่จงใจไม่ใช้ เพื่อยึดกฎเหล็กของระบบหลัก — ดู open question ใน `prompt-used.md`)
- [x] ไม่มีค่าสี/spacing hardcode ที่ไม่ได้มาจาก `tokens.css` (สุ่ม inspect แล้ว มีเพียง SVG chart ที่คำนวณตำแหน่งเป็นตัวเลข geometry ซึ่งไม่ใช่ "ค่า design" แต่เป็นพิกัดกราฟ — สีเส้นกราฟยังอ้าง `var(--color-...)` ทั้งหมด)
- [x] มี header comment ครบตามรูปแบบ (module, feature, author, date, based-on, version)
- [x] ไม่เชื่อมต่อ API จริงหรือส่งข้อมูลออกภายนอก

## 2. Component & Pattern Reuse (design-rules.md § 5)

- [x] Component ที่มีอยู่แล้วถูกนำมาใช้จริง (buttons/status-badges/stat-card/modal-dialog/notification-toast/worklist/alert-banner/tabs/drawer/form-controls — ดูรายละเอียดใน `prompt-used.md`)
- [x] Component ใหม่ 6 จุด (Command Center Shell, Scenario Simulator, Trend/Bar Chart, Bed Status Grid, AI Data Flow Diagram, Rule Builder) มีเหตุผลชัดเจนระบุไว้ในคอมเมนต์หัวไฟล์แต่ละจุด + `prompt-used.md` § Design Notes — **ยังไม่ผ่านที่ประชุม weekly design sync** ห้ามทีมอื่นเอาไปใช้ต่อจนกว่าจะอนุมัติ
- [x] หน้าตา/พฤติกรรมของ component ที่ reuse มาตรงกับต้นแบบใน `design-system/components/` (class name และโครง markup เดียวกัน)

## 3. Semantic Color & Patient Safety (design-rules.md § 4, § 8)

- [x] สีแดง (critical) ใช้เฉพาะ KPI/สถานการณ์ที่วิกฤตจริง (bed occupancy ≥95%, overcrowding index ≥1.5, Clinical Alert รายผู้ป่วย) ไม่ใช้ตกแต่ง
- [x] Alert banner (Bottleneck/Clinical Alert) อยู่ตำแหน่งบนสุดของ section ที่เกี่ยวข้องเสมอ
- [x] ไม่มีการสื่อความหมายด้วยสีอย่างเดียว — ทุกจุดมี icon/badge label ข้อความกำกับ

## 4. Mock Data (design-rules.md § 7)

- [x] ไม่มีข้อมูลผู้ป่วยจริง — ใช้ mock pool เดียวกับ module อื่น (นายสมชาย ใจดี ฯลฯ, HN6805-XXXXX)
- [x] มี record ผิดปกติ/edge case ชัดเจน (EWS สูง, Sepsis/Code Blue Risk, Bed Gridlock scenario ที่ available beds = 0)
- [x] ค่า/ตัวเลขอยู่ในช่วงที่สมเหตุสมผลเทียบสถานการณ์จริงของ Hospital Operations

## 5. States ครบถ้วน (design-rules.md § 8)

- [x] Loading state — ไม่จำเป็นเพราะ mock data โหลดพร้อม render ทันที (ระบุไว้ใน error-handling.md ว่าไม่บังคับถ้าไม่มี async จริง)
- [x] Empty state — มีครบ (ไม่มี Decision รอดำเนินการ / ไม่มี Task ในคิว / ไม่พบ Bottleneck / widget ปิดอยู่)
- [x] Error state — มี field-level validation ที่ Metric Mapping (กรอก source field ว่างแล้วกดบันทึกไม่ผ่าน + toast error)

## 6. Functional QA

- [x] เปิดไฟล์ใน browser (Playwright headless) แล้วไม่มี error ใน Console — รันทดสอบ end-to-end (nav 5 view, scenario switch, dispatch→approve→task→complete, threshold slider, rule builder, add mapping, widget toggle) ครบทุกจุด ไม่มี PAGEERROR/CONSOLE error
- [x] ปุ่ม/ลิงก์/interaction หลักทำงานได้จริงทุกจุดที่ทดสอบ (ดูผลทดสอบด้านล่าง)
- [x] ทดสอบที่ความกว้างจอ 1366px และ 1920px แล้วเลย์เอาต์ไม่แตก (ตรวจ `scrollWidth`/`clientWidth` ของ topbar nav ไม่มี horizontal overflow ทั้ง 2 ขนาด)
- [x] ตรวจตาม `ux-rules.md` § 2-4 และ § 5 — action สำคัญผ่าน modal, worklist ใช้ถูกบริบท, drawer ใช้กับ patient context (บริบทเดียว ไม่ออกจากหน้าหลัก)
- [x] ไม่มีข้อความฟันธงวินิจฉัยโรค — Clinical Alert ใช้ถ้อยคำ "ความเสี่ยงที่ระบบตรวจพบ" ไม่ใช่คำวินิจฉัยแพทย์ ไม่มี chain-of-thought หลุดปนมาในไฟล์

## 7. ผลสรุปและ Action

**ปัญหาที่พบ:**
```
(ไม่พบปัญหาระดับ blocking จาก self-QA — ดูหมายเหตุ)
1. [หมายเหตุ ไม่ใช่บั๊ก] ตัวเลข Bed Grid (24 เตียง Ward 5A) เป็นข้อมูลอิสระจาก KPI ภาพรวม (bedOccupancyPct) ไม่ได้ผูกสมการกันแบบเป๊ะ ๆ — เหมาะสำหรับ demo แต่ไม่ใช่การคำนวณจริง ระบุไว้แล้วใน prompt-used.md § Assumptions
2. [ต้องดำเนินการก่อนใช้กว้าง] 6 Proposed New Pattern ยังไม่ผ่าน weekly design sync — ต้องเสนอก่อนให้ทีมอื่นเอาไปต่อยอด

=== v2 "Premium Light" revision (ดู prompt-used.md § Revision 2) ===
3. [พบเองระหว่าง final QA ของ v2 — แก้แล้ว] กราฟ Bed Occupancy Trend คำนวณเส้น predicted ผิด (ทำให้ % เกิน 100% ใน scenario Gridlock) → แก้เป็นสูตร asymptotic แล้ว, re-verify ผ่าน
4. [พบเองระหว่าง final QA ของ v2 — แก้แล้ว] Toast notification ทับ topbar controls → แก้ตำแหน่ง CSS แล้ว, re-verify ผ่าน
5. [หมายเหตุ ไม่ใช่บั๊ก — ข้อเสนอ refinement รอบถัดไป] bed-grid tile (Level 2/3) และ rec-card ยังไม่ได้ยกระดับ icon/visual เท่าจุดอื่นในรอบ v2 นี้

=== v3 "Master Template v2 Compliance" revision (ดู prompt-used.md § Revision 3, factory-gate-report.md §F) ===
6. [แก้ตาม user feedback "ดูเป็น AI ทำมากเกินไป" — แก้แล้วที่ระดับ repo + feature] Emoji icon, gradient/glow, card เกินจำเป็น, KPI ใหญ่เกินบริบท, สีตกแต่งไม่สื่อความหมาย, marketing wording, shell ที่ไม่ตรง master — ปิดครบทั้ง 7 ข้อของ Premium HIS Visual Gate ใหม่ (`factory-gate/premium-his-visual-gate.md`)
7. [พบเองระหว่าง final QA ของ v3 — แก้แล้ว] `.kpi-strip__label` ใช้ `white-space: nowrap` ทำให้ label ยาวล้นทับ column ถัดไปเมื่อพื้นที่แคบ → เปลี่ยนเป็น wrap ได้ (`overflow-wrap: break-word`)
8. [พบเองระหว่าง final QA ของ v3 — แก้แล้ว] หน้า AI Brain Engine เกิน viewport 1366×768 ทำให้ Recommendation card (primary action) ต้อง scroll ถึงจะเห็น → ลดความสูง feed-panel, ปรับ Data Flow diagram เป็น grid แทน column เดี่ยว, ลด padding/margin เฉพาะจุด — ตรวจซ้ำผ่านแล้ว (ไม่ต้อง scroll)
```

**Action ถัดไป:**
- ⬜ ส่งกลับให้ผู้สร้าง mockup แก้ไขตามข้อ (ระบุเลข) ด้านบน
- ☑ **รอ Design QA Lead/มนุษย์ยืนยัน self-QA นี้ซ้ำ + เสนอ 6 Proposed New Pattern เข้าที่ประชุม weekly design sync ก่อน** จึงย้ายไฟล์ไปที่ `approved-mockups/hospital-command-center/mission-control/`, ถ่าย screenshot ใส่ `screenshots/`, เพิ่มแถวใน `approved-mockups/INDEX.md`

---

## Prompt สำหรับใช้กับ "Design QA Agent" (AI ตรวจแทนคนขั้นแรก)

```
คุณคือ Design QA Agent ของระบบ Gorilla HIS
ตรวจสอบไฟล์ index.html ที่แนบมา โดยเทียบกับกฎใน AI_INSTRUCTIONS.md, design-system/design-rules.md,
และไฟล์ component ต้นแบบใน design-system/components/ ที่เกี่ยวข้อง

ให้ตรวจตาม checklist นี้ทีละข้อ (คัดลอก 6 หัวข้อด้านบนของไฟล์นี้) และตอบกลับเป็น:
1. ตาราง ผ่าน/ไม่ผ่าน ทีละข้อ พร้อมเหตุผลสั้น ๆ
2. รายการปัญหาที่ต้องแก้ (ถ้ามี) เรียงตามความรุนแรง
3. สรุปผล: Approved / Rejected / Approved with comments
```
