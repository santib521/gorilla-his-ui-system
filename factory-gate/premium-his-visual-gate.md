# Factory Gate — Premium HIS Visual Gate

**เพิ่มเข้า Factory Gate ตาม `design-system/design-rules.md` § 0.5.8**

> เหตุผลที่ต้องมี gate นี้แยกจาก Design Compliance เดิม: การตรวจ token/component/pattern (Post-Build Checklist § B) ไม่จับ "ความรู้สึกโดยรวม" (overall tone) ของหน้าจอ — mockup อาจใช้ token ถูกทุกตัว, reuse component ถูกทุกไฟล์ แต่ยัง**ประกอบกันออกมาเป็น AI/SaaS Dashboard Visual Stereotype** ได้ (gradient เกินจำเป็น, การ์ดใหญ่โล่ง, ตัวเลขใหญ่เกินบริบท, สีหลายสีแข่งกัน) โดยเฉพาะ feature ที่มีคำว่า "AI"/"Command Center"/"Intelligence" อยู่ใน requirement — gate นี้ตรวจจุดนั้นโดยเฉพาะ

ใช้ควบคู่กับ `post-build-checklist.md` § G — ตอบทั้ง 7 ข้อก่อนถือว่า Post-Build Gate ผ่านได้ ข้อใดตอบ "ไม่ผ่าน" ถือเป็น **Hard Reject** ตาม `FACTORY_GATE.md` (ต้องแก้ก่อนส่ง Independent QA)

## 7 คำถามบังคับ

### 1. ดูเหมือนระบบงานโรงพยาบาลหรือ SaaS Dashboard?
เกณฑ์ผ่าน: หน้าจอให้ความรู้สึก Clinical/Operational/Trustworthy/Dense/Calm/Professional (ตาม § 0.5) ไม่ใช่ความรู้สึกแบบ marketing landing page, fintech dashboard หรือ AI product showcase
**ไม่ผ่านถ้า:** มี hero banner, ข้อความหัวข้อเชิงโฆษณา, หรือ layout ที่เน้น "ว้าว" แยกแต่ละ section แทนที่จะเป็นระบบงานเดียวกัน

### 2. มี Emoji หรือ decorative icon หรือไม่?
เกณฑ์ผ่าน: ไอคอนทั้งหมดเป็น inline SVG line icon โทนสีเดียว (monochrome) ตาม § 0.5.1 ไม่มี emoji (🧠⚡🏥⚙️✨ ฯลฯ) ใช้เป็น production icon ที่ไหนเลย (ยกเว้นโลโก้ 🦍 ของแบรนด์ที่กำหนดไว้แล้วในทุกหน้า)
**ไม่ผ่านถ้า:** เจอ emoji แม้แต่จุดเดียวนอกเหนือโลโก้แบรนด์

### 3. มี Card มากเกินจำเป็นหรือไม่?
เกณฑ์ผ่าน: ใช้ card เฉพาะข้อมูลที่เป็นอิสระจริง ส่วนที่เหลือใช้ section/table/divider/split-panel ตาม § 0.5.2 — ไม่มีการห่อทุกกล่องข้อมูลด้วย card ที่มี shadow/border/radius เดียวกันซ้ำ ๆ จนหน้าจอดูเป็น "กล่องมนเรียงกัน"
**ไม่ผ่านถ้า:** นับ card ที่ box-shadow+border-radius ในหน้าเดียวมากกว่าที่จำเป็นต่อการแยกข้อมูลจริง (ใช้วิจารณญาณเทียบกับ wireframe ใน § 0.5.2)

### 4. มีสีที่ไม่ได้สื่อ semantic meaning หรือไม่?
เกณฑ์ผ่าน: สีที่ไม่ใช่กลาง (ขาว/เทา) ทุกจุดตอบได้ว่าสื่อความหมายอะไรตาม § 0.5.4 (indigo=nav/primary action, เขียว=normal, ส้ม=warning, แดง=critical) ไม่มีสีที่ใส่เพื่อความสวยงามล้วน ๆ
**ไม่ผ่านถ้า:** ปุ่ม action ทั่วไปใช้สี warning/critical เพื่อให้เด่น ทั้งที่ไม่ใช่สถานะ warning/critical จริง, หรือมี gradient/สีตกแต่งที่ไม่ใช่ token semantic

### 5. มี oversized heading/KPI หรือไม่?
เกณฑ์ผ่าน: ตัวเลข KPI ใช้ `--font-size-xl` หรือเล็กกว่า (ตาม `enterprise-kpi-strip.html`) ไม่ใหญ่กว่าหรือเท่า page title โดยไม่มีเหตุผล
**ไม่ผ่านถ้า:** ตัวเลข KPI ใช้ font-size ใหญ่กว่า page title หรือใหญ่จนดูเป็นจุดขายเชิงภาพมากกว่าข้อมูลที่ต้องอ่านเร็ว

### 6. Shell ตรงกับ Master Application Shell หรือไม่?
เกณฑ์ผ่าน: ใช้โครง `components/application-shell.html` ตรงตาม § 0.5.5 ทั้งหมด (Topbar สูง 56px สีเดียวกัน, Sidebar กว้าง 220px พื้นหลัง `--color-bg-sidebar`, Logo/Module selector/User profile ตำแหน่งเดียวกัน) ไม่มีการออกแบบ shell เอง
**ไม่ผ่านถ้า:** feature ทำ top-nav-tabs, dark header เฉพาะตัว, หรือ shell รูปแบบอื่นที่ต่างจาก master

### 7. ที่ 1366×768 information density เหมาะกับ HIS หรือไม่?
เกณฑ์ผ่าน: เปิดหน้าจอแรกที่ 1366×768 แล้วเห็น Page context + KPI + Alert + ข้อมูลปฏิบัติการหลัก + Primary Action ครบโดยไม่ต้อง scroll (ตาม § 0.5.6) — ทดสอบจริงด้วย screenshot ไม่ใช่ประมาณเอา
**ไม่ผ่านถ้า:** ต้อง scroll ก่อนเห็นองค์ประกอบใดข้างต้น หรือมี whitespace ว่างเปล่าเกินจำเป็นจนดันเนื้อหาสำคัญลงไปนอกจอ

## บันทึกผล

| # | คำถาม | ผ่าน/ไม่ผ่าน | หมายเหตุ/หลักฐาน (screenshot path) |
|---|---|---|---|
| 1 | ระบบงานโรงพยาบาล vs SaaS Dashboard | ✅ ผ่าน | ไม่มี hero banner/ข้อความโฆษณา — shell แบบ topbar+sidebar เรียบ, การ์ดแบน, โทนสีนิ่ง (`/tmp/hcc_v6_aibrain_1366.png`, `hcc_v6_level1_1366.png`, `hcc_v6_level2_1366.png`, `hcc_v6_level3_1366.png`) |
| 2 | Emoji/decorative icon | ✅ ผ่าน | เปลี่ยน icon ทั้งหมดเป็น inline SVG monochrome (`icon()` helper) แล้ว เหลือเฉพาะ 🦍 โลโก้แบรนด์ตามข้อยกเว้นใน § 0.5.1 |
| 3 | Card เกินจำเป็น | ✅ ผ่าน | เปลี่ยน `.panel-banner`→`.panel-header` (ไม่ใช่ card), KPI ใช้ `enterprise-kpi-strip` แถวเดียวแทนการห่อ card แยกรายตัว, ลด card ที่ไม่จำเป็นใน AI Brain Engine/Level 1/2 |
| 4 | สีไม่สื่อความหมาย | ✅ ผ่าน | ตรวจ `.rec-card`/`.kpi-strip__value`/`.flow-node` ทุกจุด สีที่ไม่ใช่กลางสื่อ semantic (indigo=nav/primary, เขียว=normal, ส้ม=warning, แดง=critical) เท่านั้น ไม่มี gradient ตกแต่งเหลืออยู่ |
| 5 | Oversized heading/KPI | ✅ ผ่าน | `kpi-strip__value` ใช้ `--font-size-xl` เท่ากับ/เล็กกว่า page title เสมอ ตรวจผ่าน screenshot ทุก view |
| 6 | Shell ตรง Master | ✅ ผ่าน | ใช้โครง `components/application-shell.html` ตรงทุกจุด: Topbar 56px (`--layout-topbar-height`) พื้น `--color-blue-600`, Sidebar 220px พื้น `--color-bg-sidebar`, Logo/Module label/User profile ตำแหน่งเดียวกัน |
| 7 | Density ที่ 1366×768 | ✅ ผ่าน | ยืนยันด้วย Playwright bounding-rect + screenshot จริงที่ 1366×768: AI Brain Engine เห็น Page context+KPI(Predictive Analytics)+Data Flow+Recommendation card (primary action "Dispatch to Level 2") ครบไม่ต้อง scroll (`contentScrollHeight` 731px < `contentClientHeight` 712px หลังปรับความสูง `feed-panel`/`flow-diagram`/`section-title` margin); Level 1/2/3 ผ่านเช่นกัน |

**ผลรวม:** ✅ ผ่านทั้ง 7 ข้อ (Post-Build Gate ไปต่อได้) ⬜ ไม่ผ่านอย่างน้อย 1 ข้อ (Hard Reject — กลับไปแก้ที่ Builder)

> บันทึกโดย Builder เมื่อทำ Master Template v2 rollout เสร็จ (2026-08-31) — ยังต้องผ่าน Independent QA Agent/Human Review ตามปกติ การติ๊กผ่านที่นี่ไม่ใช่ Approval ขั้นสุดท้าย
