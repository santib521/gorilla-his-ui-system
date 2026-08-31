# Prompt ที่ใช้จริงสำหรับ feature นี้

**AI ที่ใช้:** Claude (Claude Code / Cowork)
**ผู้ทำ:** Ti MKT
**วันที่:** 2026-08-31

---

```
Gorilla HIS Mockup Task
Hospital Command Center — Mission Control

คุณเป็น AI UI/UX Designer และ Frontend Prototype Developer ของ Gorilla HIS

[... requirement เต็มตามที่ผู้ใช้ส่งมา 13 หัวข้อ: Step 0 อ่าน repo ก่อน, Design Authority,
Project Goal, Application Navigation, Scenario Simulator, AI Brain Engine,
Level 1/2/3, Self-Service Configuration, Interactivity, Technical Output,
Output Location modules/hospital-command-center/, Required Response Before
Coding (รายงานก่อนเริ่ม code), Acceptance Criteria — เก็บฉบับเต็มไว้ในประวัติแชท
ของทีม ไม่ paste ซ้ำที่นี่เพื่อไม่ให้ไฟล์ยาวเกินจำเป็น ]
```

---

## Design Notes ที่ AI ตอบกลับมา

### พบ Design Rules อะไรจาก Gorilla HIS Repository
- Product Character (v1.2 หลัง Visual Audit): โทน indigo/periwinkle, ความหนาแน่นข้อมูลสูง, dashboard ใช้ stat-card วงกลมสี, ค่าวิกฤตใช้สีข้อความแดงตรง ๆ (`design-rules.md` § 0)
- Semantic color ผูกกับความหมายคลินิกเท่านั้น ห้ามใช้ตกแต่ง (`design-rules.md` § 4) — นำมาบังคับใช้กับ KPI ระดับบริหารด้วย (occupancy/overcrowding สูง = critical จริง ไม่ใช่แค่สีเข้ม)
- Action ที่กระทบสำคัญต้องยืนยันผ่าน modal เสมอ, ห้ามใช้สีเดียวกับปุ่ม primary ทั่วไป (`ux-rules.md` § 2, `patterns/approval-confirmation.md`)
- Baseline 1366×768, fluid ถึง 1920px, ไม่ต้อง responsive มือถือ (`design-rules.md` § 2)
- ห้าม CDN ภายนอก, ห้าม hardcode ค่า design, ต้อง inline tokens.css ทั้งไฟล์ (`AI_INSTRUCTIONS.md` § 2) — **ใช้กฎนี้แทนข้อยกเว้น CDN ที่ brief อนุญาตไว้** เพื่อความสม่ำเสมอกับ mockup อื่นทั้งหมดในระบบและใช้งานได้แม้เครือข่ายโรงพยาบาลปิด internet (กราฟทำเป็น inline SVG แทน Chart.js, ไม่ใช้ Tailwind/FontAwesome/Google Fonts)
- ห้ามฟันธงวินิจฉัยโรค (`AI_INSTRUCTIONS.md` § 2 ข้อ 11) — Clinical Alert ใน Level 3 ใช้ถ้อยคำ "ความเสี่ยงที่ระบบตรวจพบ" ไม่ใช่คำวินิจฉัย

### พบ Existing Components ที่ Reuse ได้
`buttons.html`, `status-badges.html`, `stat-card.html`, `modal-dialog.html`, `notification-toast.html`, `worklist.html`, `alert-banner.html`, `tabs.html`, `drawer.html`, `form-controls.html`

### พบ Existing Patterns ที่ Reuse ได้
`dashboard-home.md` (stat-card row + worklist — ใช้เป็นฐานของ Level 1/AI Brain Engine), `approval-confirmation.md` (Strategic Decision Console, Gridlock Protocol confirm), `search-and-table.md` (Metric Mapping table), `list-detail-page.md` (Ward Bed Grid ซ้าย + Patient Context ขวา/drawer)

### Screenshot ที่ใช้เป็น Visual Reference
`02-main-menu.jpg` (โทนสี topbar indigo/periwinkle + โครง sidebar), `06-doctor-screen_Dashboard01.jpg` (OR Team Dashboard — ต้นแบบโดยตรงของ stat-card row ใช้กับ KPI แถวบน), `18 IPD dashboard.jpg` (ต้นแบบแนวคิด grid รายเตียง/ไอคอนสถานะ สำหรับ Bed Status Grid ใหม่)

### Requirement ที่ยังไม่มี Existing Pattern (ต้องสร้างใหม่)
1. **Command Center App Shell** — nav สลับ 5 มุมมองระดับต่างกัน (ไม่ใช่ module ธุรกิจเดี่ยวแบบเดิม) + สถานะ LIVE HIMS SYNC ค้างตลอด
2. **Scenario Simulator** — global state injection ที่ปรับทั้งระบบพร้อมกัน ไม่มีแนวคิดนี้ในระบบเดิมเลย (ของเดิมเป็น workflow เชิงเส้นทั้งหมด)
3. **Trend / Bar Chart (inline SVG)** — ระบบไม่เคยมี chart component มาก่อน (design-rules.md § 0 เคยระบุช่องว่างกราฟ time-series ไว้แล้วสำหรับ Critical Care Flowsheet — อันนี้เป็นอีกจุดที่ยืนยันช่องว่างเดียวกัน)
4. **Bed Status Grid** — ตาราง/กริดสถานะเตียงรายเตียง (Occupied/Reserved/Cleaning/Available/Discharge Ready) ต่างจาก worklist/table เดิมที่เป็นรายการ ไม่ใช่ grid เชิงพื้นที่
5. **AI Data Flow Diagram** — แผนภาพอธิบายสถาปัตยกรรม ไม่ใช่หน้าจอปฏิบัติงาน
6. **Rule Builder (IF/AND/THEN)** — ไม่มี pattern การสร้าง logic แบบ visual ในระบบเดิม

ทั้ง 6 อย่างนี้ถูกออกแบบให้ "กลมกลืน" กับภาษาภาพเดิม (ใช้ tokens.css, สี semantic เดิม, สไตล์ card/badge/button เดิมทั้งหมด) และถูกทำเครื่องหมาย **"Proposed New Pattern"** ในคอมเมนต์หัวไฟล์ — ต้องเสนอเข้าที่ประชุม weekly design sync ก่อนให้ทีมอื่นเอาไปใช้ต่อ (ตาม `design-rules.md` § 5)

### File ที่สร้าง
- `modules/hospital-command-center/index.html` (mockup หลัก — ไฟล์เดียว)
- `modules/hospital-command-center/feature-spec.md`
- `modules/hospital-command-center/prompt-used.md` (ไฟล์นี้)
- `modules/hospital-command-center/review/qa-checklist.md`

### Mock Data / Assumptions
- ตัวเลข KPI ทั้งหมดเป็นค่าสมมติที่ออกแบบให้ต่างกันชัดเจนระหว่าง 3 scenario เพื่อ demo ได้ชัด ไม่ใช่ค่าจริงจากโรงพยาบาลใด
- Bed Grid ของ Ward 5A (24 เตียง) เป็นข้อมูลอิสระจากตัวเลข KPI ภาพรวม (illustrative) ไม่ได้ผูกสมการกันแบบเป๊ะ ๆ — เหมาะสำหรับ demo ไม่ใช่การคำนวณจริง
- ชื่อผู้ป่วยมี mock pool เดียวกับ module อื่นในระบบ ("นายสมชาย ใจดี" ฯลฯ) รูปแบบ HN `HN6805-XXXXX`

### Open Questions (ถ้ามี ให้ทีมช่วยตัดสินใจภายหลัง)
- ถ้าต้องการ Chart.js/Tailwind ของจริงตาม brief เดิม (แทน inline SVG) แจ้งทีม Design QA ก่อน เพราะขัดกับกฎ no-CDN ของระบบหลัก — ต้องตัดสินใจเป็นกรณีพิเศษระดับ weekly design sync

---

## Revision 2 — "Premium Light" Visual Upgrade (2026-08-31)

**เหตุผล:** ผู้ใช้รีวิว v1 แล้วให้ feedback ว่า UI ยังไม่ถึงระดับ "Premium Hospital" — ระบุปัญหาหลัก 2 จุด (icon ใช้ emoji, กราฟดูแบน/ไม่มีมิติ) พร้อมส่งภาพอ้างอิงจริง (หน้าจอ "Registered Patients" worklist) เป็นต้นแบบ ผู้ใช้เลือกทิศทาง **"Premium Light — ยกระดับของเดิม"** (ไม่ใช่ dark mode/mission-control ตามที่เคยเสนอเป็นตัวเลือก)

**สิ่งที่แก้ไข (ไม่มีการเปลี่ยน component/pattern class name หรือโครงสร้างข้อมูลใด ๆ — เป็น visual polish ล้วน):**
1. **Icon system ใหม่** — เพิ่ม `ICON_PATHS` + helper `icon(name, size)` เป็น inline SVG icon library (~22 ไอคอน, `stroke="currentColor"` รับสีจาก CSS class เดิม เช่น `.stat-card__icon--critical`) แทน emoji ทั้งหมดในไฟล์ (คงเหลือเฉพาะ 🦍 mascot ของแบรนด์ตามเดิม) — ไม่ใช้ icon font/CDN ใด ๆ ยึดกฎ no-CDN เดิม
2. **กราฟยกระดับ** — เส้น Bed Occupancy Trend ใช้ quadratic-bezier smoothing + gradient area fill ใต้เส้น (แทนเส้นตรงเดิม); กราฟแท่ง Department Throughput เพิ่ม gradient fill + animate ความกว้างตอน render (stagger delay ต่อแถว)
3. **Panel banner ใหม่** (`.panel-banner` — solid indigo gradient, ตัวอักษรขาวหนา) ใช้กับหัวข้อ panel ที่เป็นจุดสนใจหลัก 3 จุด: "Live Raw Data Feed", "IPD Bed Management", "Ward Bed Grid — 5A" — ทำตามภาพอ้างอิงที่ผู้ใช้ส่งมาโดยตรง (banner header สีทึบ)
4. **AI Data Flow Diagram** สร้างใหม่เป็น `renderFlowDiagram()` (JS-rendered แทน static HTML เดิม) — ทุก node มี icon กำกับ, node "AI Brain Engine" ตรงกลางใช้ gradient + glow effect เน้นเป็นจุดศูนย์กลาง, ลูกศรเปลี่ยนจาก "→" เป็น `chevron-right` SVG icon

**บั๊กที่พบเองระหว่าง final QA (ไม่ใช่จาก user report) และแก้แล้ว:**
- กราฟ Bed Occupancy Trend คำนวณเส้น predicted ผิด (เอา % การเพิ่ม ER admission forecast บวกตรงกับ % bed occupancy ทำให้ scenario Gridlock ขึ้นถึง 142% ซึ่งเป็นไปไม่ได้) → แก้เป็นสูตร asymptotic เข้าใกล้ 100% ตามค่า runway ที่เหลือจริง (ดูคอมเมนต์ในโค้ดจุด `renderLevel1()`)
- Toast notification ทับ scenario simulator/sync status บน topbar → ปรับ `.toast-stack` ให้อยู่ใต้ topbar เสมอ (`top: calc(var(--layout-topbar-height) + var(--space-3))`)

**ยืนยันซ้ำหลังแก้ (re-run เต็มชุด):** div-balance check, `node --check` ของ script, Playwright end-to-end interaction test (nav 5 view, scenario switch ทั้ง 3, dispatch→approve→task→complete chain, ward5a task list) — ผ่านทั้งหมด ไม่มี console/page error, screenshot 1440×900 ทั้ง 4 หน้าหลัก (AI Brain Engine, Level 1, Level 2, Level 3) ตรวจแล้วไม่มี layout regression

**ยังไม่ได้ทำ (ทิ้งไว้เป็นข้อเสนอ refinement รอบถัดไปถ้าต้องการ):** ~~bed-grid tile (Level 2 IPD grid, Level 3 Ward 5A grid) และ recommendation card (`.rec-card`) ยังเป็นสไตล์เดิม~~ → แก้แล้วใน Revision 2.1 ด้านล่าง

---

## Revision 2.1 — Bed Grid & Recommendation Card polish (2026-08-31)

**เหตุผล:** ต่อจาก Revision 2 — user ยังรู้สึกว่าจุดสองจุดนี้ยังไม่ premium (bed tile แบบสี่เหลี่ยมสีทึบเรียบ ๆ, recommendation card ไม่มี icon)

**สิ่งที่แก้:**
1. `.bed-tile` (Bed Status Grid ทั้ง Level 2 IPD grid และ Level 3 Ward 5A grid) — เปลี่ยนจากพื้นสีทึบเรียบเป็น gradient สองโทน + เงานุ่ม (soft shadow) ให้ดูมีมิติ, เพิ่มไอคอนสถานะ (เตียง/นาฬิกา/ไม้กวาด/เครื่องหมายถูก/ลูกศรย้าย) กำกับทุกช่อง, hover ยกตัวขึ้นเล็กน้อย
2. `.bed-summary__item` (แถบสรุปจำนวนเตียงแต่ละสถานะ) — เปลี่ยนจาก dot+ตัวเลขเปล่า ๆ เป็น pill badge ขอบมน พื้นหลังอ่อน ตามสไตล์ภาพอ้างอิงที่ผู้ใช้ส่งมา (status-count pill)
3. `.rec-card` (Recommendation Engine card ใน AI Brain Engine) — เพิ่มไอคอนวงกลมสีตามระดับความสำคัญ (แดง=วิกฤต/ส้ม=แนะนำ/ฟ้า=ข้อมูล), เพิ่มแถบสีด้านซ้าย (accent border) ตามระดับเดียวกัน, เพิ่มเงานุ่มและ hover ยกตัว

**Re-verify:** div-balance, `node --check`, Playwright end-to-end test — ผ่านทั้งหมด ไม่มี console/page error; screenshot ยืนยันภาพแล้วทั้ง 3 จุด

---

## Revision 3 — Master Template v2 Compliance (2026-08-31)

**Prompt เดิมจากผู้ใช้ (สรุปสาระสำคัญ):** หลังส่งงานที่ผ่าน Factory Gate (Post-Build PASS) รอบแรกไปแล้ว ผู้ใช้ให้ feedback ว่า UI "ดูเป็น AI ทำมากจนเกินไป" (Emoji เป็น icon, card ใหญ่โล่งเกินไป, ตัวเลข KPI ใหญ่มาก, สีหลายสีแข่งขันกัน, header/nav ดูเหมือน landing page, ข้อความเชิง marketing เช่น "AI Brain & Predictive Intelligence Engine") และสั่งชัดเจนว่า **"อย่าแก้เฉพาะ Command Center ครับ ต้องแก้ Master Template / Design Authority เลย เพื่อไม่ให้ AI อีก 10 คนผลิตหน้าตาแบบนี้ซ้ำ"** พร้อมให้ spec ละเอียด 8 ข้อ (emoji ban, card discipline, enterprise-kpi-strip, 90/10 color rule, locked Application Shell, density rule ที่ 1366×768, ห้าม AI Visual Theme, Premium HIS Visual Gate 7 ข้อ) และยืนยันรูปแบบ shell ที่ต้องการ = **Left Sidebar + Topbar** (ตามภาพอ้างอิง "Registered Patients")

**สิ่งที่แก้ที่ระดับ repo (นอกเหนือจาก feature นี้ — ดูรายละเอียดเต็มใน `factory-gate-report.md` §F):**
- `design-system/design-rules.md` เพิ่ม § 0.5 Master Rule (8 sub-rules)
- Component ใหม่ 2 ตัว: `enterprise-kpi-strip.html`, `application-shell.html`
- `design-system/components/README.md` ปรับปรุง
- `factory-gate/` เพิ่ม Premium HIS Visual Gate (ไฟล์ใหม่ + ผูกเข้า Hard Reject ใน `FACTORY_GATE.md` และ § G ใน `post-build-checklist.md`)

**สิ่งที่แก้ใน `index.html` ของ feature นี้:**
1. รื้อ shell เดิม (topbar+topnav) เป็น sidebar (220px)+topbar (56px) ตาม `application-shell.html` ทุกจุด — breadcrumb + page header (title/subtitle พร้อมเวลา+source) แบบ shared pattern
2. แทนที่ stat-card grid ทั้งหมด (`renderPredictCards`, `renderLevel1`, `renderLevel2`) ด้วย `kpiStrip()` — แถบ KPI แนวนอนแบน ตัวเลขไม่เกิน `--font-size-xl`, สีมีความหมายเฉพาะจุดวิกฤต/เตือนจริงเท่านั้น (ไม่ใช่ตกแต่ง)
3. เอา gradient/glow ออกจาก AI Brain node, bed-tile ทุกสถานะ, และลด `.rec-card` เหลือ border-left accent (ไม่มี colored-circle icon อีกต่อไป) — เปลี่ยน `.panel-banner` (gradient) เป็น `.panel-header` (text header เรียบ)
4. ลบ CSS `.stat-card`/`.stat-row` เดิมที่กลายเป็น dead code หลังเปลี่ยนมาใช้ kpi-strip
5. แก้ density ให้ผ่าน 1366×768 no-scroll: ลดความสูง `.feed-panel` (220→96px), เปลี่ยน Data Flow diagram จาก column เดี่ยว 6 แถวเป็น grid 3 คอลัมน์ 2 แถว (ประหยัดพื้นที่แนวตั้งได้มาก), ลด padding/margin เฉพาะจุดของ Data Flow card และ "Recommendation Engine" heading

**Bug ที่พบเองระหว่าง verify และแก้แล้ว:** `.kpi-strip__label` เดิมตั้ง `white-space: nowrap` ทำให้ label ยาว (เช่น "ER ADMISSION FORECAST (4H)") ล้นทับ column ถัดไปเมื่อพื้นที่แคบ — แก้เป็น `overflow-wrap: break-word` + `overflow: hidden` ที่ item

**Re-verify (เต็มชุดตาม Post-Build Checklist):** div/tag-balance (div 207/207, section 5/5, nav 1/1, ul 1/1, li 5/5), `node --check` OK, Playwright regression (nav 5 view, scenario switch 3 แบบ, dispatch→empty-state, sync-error toggle, rule validation invalid/valid) — console errors: 0; screenshot ยืนยันที่ 1366×768 ทุก view และ 1920×1080 — ยืนยันด้วยตัวเลขจริง (`contentScrollHeight` 731px < `contentClientHeight` 712px ที่ AI Brain Engine หลังปรับความสูง) ว่าไม่ต้อง scroll เพื่อเห็น Page context+KPI+ข้อมูลหลัก+Primary Action

**Premium HIS Visual Gate:** ผ่านทั้ง 7 ข้อ — บันทึกเต็มใน `factory-gate/premium-his-visual-gate.md`
