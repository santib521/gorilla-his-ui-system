# Feature Spec — hospital-command-center/mission-control

## Module
Hospital Command Center (โมดูลใหม่ระดับ cross-module — ไม่ใช่ business module เดี่ยวแบบ OPD/Lab แต่เป็น "ศูนย์บัญชาการ" ที่รวมข้อมูลจากทุก module ผ่าน AI Brain Engine)

## Users (ผู้ใช้งาน)
- Level 1 — ผู้บริหารระดับสูง (C-Level): ผู้อำนวยการ, รองผู้อำนวยการฝ่ายการแพทย์
- Level 2 — ผู้บริหารระดับกลาง/Hospital Command Center staff: หัวหน้าพยาบาลเวร, Bed Manager, หัวหน้าฝ่าย ER
- Level 3 — หน้างาน: พยาบาลหอผู้ป่วย, เจ้าหน้าที่ Housekeeping, เจ้าหน้าที่ Transport
- Self-Service Config: IT/Business Analyst ของโรงพยาบาลที่ปรับ Rule/KPI/Dashboard เอง

## Objective (วัตถุประสงค์ทางธุรกิจ)
Demo แนวคิด "Real-Time Operational Intelligence" — จำลองว่าถ้า Gorilla HIS มี AI Brain Engine ที่วิเคราะห์ข้อมูลจากทุกระบบ (ADT/ER/LIS/RIS/Bed/EWS) แล้วกระจายคำแนะนำไปยังผู้ใช้ 3 ระดับแบบ Real-Time จะหน้าตาและใช้งานอย่างไร ใช้ประกอบการนำเสนอ/ตัดสินใจลงทุนกับโรงพยาบาล ไม่ใช่ feature ที่ผูกกับ backend จริง

## Main Workflow
```text
เลือก Scenario (Normal/ER Surge/Gridlock) → AI Brain Engine ตรวจพบความเสี่ยง/โอกาส
  → เกิด Recommendation → กด Dispatch ไปยัง Level ที่เกี่ยวข้อง
  → Level 1/2 เห็น Alert/Decision → Approve หรือกด Recommended Action
  → เกิด Task ที่ Level 3 → พยาบาล/จนท. หน้างาน Start Task → Complete Task
  → ตัวเลข Capacity/KPI ทั่วทั้งระบบ (Level 1/2) ปรับตัวดีขึ้นแบบ real-time
```

## Functions (ฟังก์ชันที่ต้องมี)
1. Navigation สลับ 5 ส่วน: AI Brain Engine / Level 1 / Level 2 / Level 3 / Self-Service Config + สถานะ LIVE HIMS SYNC
2. Scenario Simulator — 3 scenario (Normal / Peak ER Surge / Bed Gridlock Critical) ที่ปรับค่า KPI/Alert/Recommendation ทั้งระบบพร้อมกัน
3. AI Brain Engine: Data Flow Diagram, Live Raw Data Feed (จำลอง event ต่อเนื่อง), Predictive Analytics, Recommendation Engine (dispatch ได้)
4. Level 1: KPI Dashboard, กราฟ (Bed Occupancy Trend+Prediction, Department Throughput, Bottleneck Overview), Strategic Decision Console (Approve/Confirm ผ่าน modal)
5. Level 2: ER Flow, IPD Bed Management (grid), Logistics/Housekeeping, Bottleneck Detection + Recommended Action (dispatch → Level 3 task), Threshold Simulation
6. Level 3: View switcher (ER/Ward 5A/Housekeeping/Transport), Bed Grid รายเตียง + Patient Context (mock, EWS/Risk/Discharge), Task list ที่เปลี่ยนสถานะได้ (Pending→In Progress→Completed)
7. Self-Service Config: Rule Builder (IF/AND/THEN), Dashboard Widget on/off ต่อ Level, Metric Mapping (HIMS field → Command Center metric)
8. Interactivity ปลายทางถึงปลายทางตาม demo story ใน requirement เดิม (ข้อ 9)

## Business Rules (กฎทางธุรกิจ/คลินิกที่ต้องยึด)
- Action ที่มีผลกระทบระดับปฏิบัติการ/งบประมาณ (Approve Flex Ward, Initiate Diversion, Trigger Gridlock Protocol) ต้องผ่าน confirm modal ตาม pattern `approval-confirmation.md` ระดับ "ยืนยันซ้ำ" ขึ้นไป — ห้ามกดครั้งเดียวผ่าน
- ห้ามให้ mockup นี้ฟันธง "วินิจฉัยโรค" ของผู้ป่วยรายบุคคล (เช่น Sepsis Risk/Code Blue Risk ต้องแสดงเป็น "ความเสี่ยงที่ระบบตรวจพบ" ไม่ใช่คำวินิจฉัยของแพทย์) ตาม `AI_INSTRUCTIONS.md` § 2 ข้อ 11
- สีเชิงความหมาย (critical/warning/normal/info) ต้องตรงตามนิยามใน `design-rules.md` § 4 แม้จะใช้กับ KPI ระดับบริหารก็ตาม (เช่น occupancy สูงมาก = critical ไม่ใช่แค่สีสวย)
- Mock Data ต้องเป็นข้อมูลสมมติทั้งหมด (ชื่อผู้ป่วยในบริบท bed grid ใช้รูปแบบเดียวกับ module อื่น เช่น "นายสมชาย ใจดี", HN6805-XXXXX)

## Demo Scenarios (เคสที่ต้อง demo ได้)
- Normal Operations: ทุกค่าปกติ, มี recommendation เบา ๆ (discharge candidate)
- Peak ER Surge: ER Queue/Waiting Time/Bed Demand/Staff Workload สูงขึ้นชัดเจน, AI แจ้งเตือน forecast +23% และเริ่มเสนอเปิด Flex Ward
- Bed Gridlock Critical: Bottleneck วิกฤต, ต้องมี Escalation และ Recommended Action ที่ dispatch เป็น task จริงให้ Level 3 ทำจนจบ แล้วเห็นตัวเลขดีขึ้น

## Reused Components / Patterns
- `design-system/components/`: `buttons.html`, `status-badges.html`, `stat-card.html`, `modal-dialog.html`, `notification-toast.html`, `worklist.html`, `alert-banner.html`, `tabs.html`, `drawer.html`, `form-controls.html`
- `design-system/patterns/`: `dashboard-home.md` (stat-card row + worklist), `approval-confirmation.md` (Strategic Decision Console + Gridlock Protocol confirm), `search-and-table.md` (Metric Mapping table), `list-detail-page.md` (Ward Bed Grid + Patient Context)

## New Pattern Proposal (จำเป็นจริง — ไม่มี pattern เดิมรองรับ)
ดูรายละเอียดเต็มใน `prompt-used.md` § Design Notes — สรุป: (1) Command Center App Shell (nav 5 ส่วน + Scenario Simulator + Live Sync status), (2) Scenario Simulator เป็นแนวคิดใหม่ (global state injection ไม่มีมาก่อนในระบบ), (3) Trend/Bar Chart (inline SVG — ไม่เคยมี chart component ในระบบมาก่อน), (4) Bed Status Grid, (5) AI Data Flow Diagram, (6) Rule Builder (IF/AND/THEN) — ทั้งหมดต้องเสนอเข้า weekly design sync ก่อนให้ทีมอื่นเอาไปใช้ต่อ ตาม `design-rules.md` § 5

---

> กรอกไฟล์นี้เสร็จแล้ว ใช้เนื้อหาในนี้เป็น input หลักตอนกรอก `MOCKUP_PROMPT_TEMPLATE.md` (ที่ root ของ repo) — ในเคสนี้ผู้ใช้ส่ง requirement แบบละเอียดมาโดยตรงแล้ว จึงใช้เป็น prompt-used.md โดยตรง
