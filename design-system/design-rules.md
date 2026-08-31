# Design Rules — Gorilla HIS Design System

กฎเหล่านี้ผูกพันกับทุก mockup ที่สร้างในระบบ ไม่ว่าจะทำโดย AI ตัวไหนหรือคนไหน เป้าหมายคือให้ mockup จากคน 10 คน **ดูเหมือนออกมาจากทีมเดียวกัน**

> เรื่อง**พฤติกรรม/การโต้ตอบ**ของ UI (worklist, action, state, detail pattern) ย้ายไปอยู่ที่ [`ux-rules.md`](./ux-rules.md) แล้ว — ไฟล์นี้เน้นเฉพาะ**หน้าตา/ภาพ**

> **v2 (2026-08-31):** เพิ่ม § 0.5 "Enterprise HIS Visual Character" หลังพบว่า feature ที่มีคำว่า AI/Command Center ในชื่อ ถูก AI builder ตีความเป็น AI/SaaS dashboard stereotype (gradient, glow, emoji, การ์ดใหญ่, ตัวเลขใหญ่, ข้อความ marketing) — อ่าน § 0.5 **ก่อน**เริ่มออกแบบ feature ใหม่ทุกครั้ง ไม่ว่า requirement จะใช้คำว่า "AI" หรือไม่

## 0. Product Character

**อัปเดตแล้วตาม Visual Audit จริง** (เทียบจากภาพใน `screenshots/actual-gorilla-his/` 29 ภาพ — เดิมเป็นแค่ baseline สมมติ ตอนนี้อ้างอิงของจริงแล้ว):

- **โทนสีหลัก:** Indigo/Periwinkle blue (ไม่ใช่ฟ้าสดแบบเดิม) ใช้กับ top bar, ปุ่มหลัก, ลิงก์ — ปรับใน `tokens.css` แล้ว (`--color-blue-*`)
- **แบรนด์:** โรงพยาบาลใช้โลโก้สีเขียวอมฟ้า (teal) — เก็บเป็น `--color-brand-mark` แยกจากสีเชิงความหมาย ใช้เฉพาะจุดโลโก้/หัวเอกสารพิมพ์เท่านั้น
- **ความหนาแน่นของข้อมูลสูงมาก** — ตารางงานจริง (worklist, order, billing) แน่นกว่าที่ mockup เดิมออกแบบไว้พอสมควร มีคอลัมน์เยอะ, scroll แนวนอนเป็นเรื่องปกติ, ฟอนต์เล็ก (~12-14px) ทั่วทั้งตาราง
- **Dashboard ใช้ stat card แบบวงกลมสี** — ไอคอนวงกลมสี + ตัวเลขใหญ่ + label (ดู pattern `dashboard-home.md` และ component `stat-card.html` ที่เพิ่มใหม่)
- **Patient panel ด้านข้างมีรายละเอียดเยอะกว่าที่คิด** — ไม่ใช่แค่ HN/ชื่อ/อายุ แต่มี Vitals mini-table, Allergy, Underlying conditions, Social History อยู่ในแผงเดียวกัน (ดู component `patient-summary-panel.html` ที่เพิ่มใหม่ — ใช้แทน `patient-banner.html` เดิมได้เมื่อหน้าจอต้องการรายละเอียดเยอะ)
- **แถวที่ต้องการความสนใจ ใช้พื้นหลังไฮไลต์สีเหลือง/ส้มอ่อนทั้งแถว** (ไม่ใช่แค่ badge) เมื่อมีไอคอนเตือนประกอบ (เช่น OR Worklist ที่มีเคสรอ) — เป็นอีกวิธีหนึ่งที่ยอมรับได้นอกจาก left-border-stripe ที่ใช้ใน `lab-result-table.html`
- **ค่าวิกฤต/ผิดปกติในตัวเลข** แสดงด้วยสีข้อความแดงตรง ๆ (ไม่ใช่ badge เสมอไป) ตรงกับแนวทางที่ `vitals-form.html` ทำอยู่แล้ว — ยืนยันว่าถูกทาง

**ช่องว่างที่ยังไม่มี component รองรับ (รู้ไว้ ยังไม่ได้สร้าง):** กราฟสัญญาณชีพแบบ time-series ระดับ Critical Care Flowsheet (ดู `17Graphic sheet.jpg`) ซับซ้อนกว่า component ปัจจุบันมาก — ถ้ามี feature ต้องใช้ ให้ปรึกษาที่ weekly design sync ก่อนแทนที่จะเดาออกแบบเอง

## 0.5 Enterprise HIS Visual Character (Master Rule — บังคับทุก Feature) — v2

> เพิ่มเข้ามาหลังพบว่า mockup หลายชิ้น (โดยเฉพาะ feature ที่มีคำว่า "AI"/"Command Center" ใน requirement) มีแนวโน้มถูก AI ตีความเป็น **AI/SaaS Dashboard Visual Stereotype** (gradient ฉูดฉาด, glow, การ์ดใหญ่โล่ง, ตัวเลขใหญ่เกินบริบท, emoji, ข้อความเชิง marketing) ทั้งที่ระบบนี้คือ **Enterprise Hospital Application** ไม่ใช่ AI Showcase — กฎในหมวดนี้มีอำนาจเหนือ "รสนิยม"/"ความคิดสร้างสรรค์" ของ AI ที่สร้างงานเสมอ ขัดกับ §1-§10 ข้อไหนไม่ได้ ให้หมวดนี้ชนะเฉพาะเรื่อง "ความรู้สึกโดยรวม" (tone) เท่านั้น ส่วนกฎ Semantic Color/Accessibility ของหมวดอื่นยังใช้เต็มเหมือนเดิม

**คำประกาศหลัก:**

> Gorilla HIS เป็นแอปพลิเคชันระดับองค์กรของโรงพยาบาล (professional hospital enterprise application) **ไม่ใช่** marketing dashboard, AI showcase, fintech dashboard หรือ consumer SaaS product

UI ต้องให้ความรู้สึก: **Clinical / Operational / Trustworthy / Dense / Calm / Professional**

**หลีกเลี่ยงเด็ดขาด (ไม่ว่า feature จะมีคำว่า "AI"/"Intelligence"/"Command Center" อยู่ใน requirement หรือไม่ก็ตาม):**
- oversized card (การ์ดใหญ่โล่งเกินเนื้อหา)
- excessive rounded corners (มุมโค้งมนเกินความจำเป็น)
- decorative gradient (ไล่สีเพื่อความสวยงามล้วน ๆ ไม่ได้สื่อความหมาย)
- emoji icon ใน production UI (ดูข้อถัดไป)
- colorful dashboard block (หลายสีแข่งขันกันในหน้าเดียว)
- excessive whitespace (พื้นที่ว่างเกินจำเป็นจนข้อมูลสำคัญต้อง scroll ถึงจะเห็น)
- oversized KPI typography (ตัวเลข KPI ใหญ่เกินบริบทงาน เช่น เท่าหัวข้อหน้า)
- "AI futuristic" visual language (dark panel เรืองแสง, glow, สีม่วง/น้ำเงินเข้มแบบ sci-fi, sparkle ✨)
- hero banner / ข้อความหัวข้อเชิง marketing (เช่น "✨ AI Brain & Predictive Intelligence Engine")
- ปุ่ม action ขนาดใหญ่เต็มการ์ดที่ใช้สี warning/critical เป็นการตกแต่งแทนที่จะสื่อความหมายจริง

### 0.5.1 ห้ามใช้ Emoji เป็น Production UI Icon เด็ดขาด

**Emoji are prohibited as production UI icons.** ต้องใช้ **inline SVG line icon โทนสีเดียว (monochrome, `stroke="currentColor"`)** จาก icon set ที่อนุมัติแทนเสมอ — รวมถึงไอคอนใน component เดิมที่ยังใช้ emoji อยู่ (เช่น ตัวอย่างใน `stat-card.html` ที่สร้างไว้ก่อนกฎนี้ — ให้ถือเป็น debt ที่ต้องแก้ ไม่ใช่ของที่ยกเว้น)

ตัวอย่างการแปลความหมายเป็น icon (ไม่ใช่ literal 1:1 กับคำ แต่สื่อความหมายเชิงหน้าที่):
- "AI/สมองระบบ" → ใช้ icon เชิง circuit/network ไม่ใช่รูปสมองการ์ตูนหรือ 🧠
- "ภาพรวม/Strategic" → icon เชิง dashboard/grid
- "ปฏิบัติการ/Tactical" → icon เชิง activity/pulse
- "หน้างาน/Frontline" → icon เชิง worklist/bed
- "ตั้งค่า/Config" → icon เชิง gear/settings มาตรฐาน (ไม่ใช้ ⚙️)

### 0.5.2 Card ไม่ใช่ Container เริ่มต้น (Card is not the default container)

**ใช้ card เฉพาะเมื่อข้อมูลนั้นเป็นอิสระจากบริบทรอบข้างจริง ๆ** (เช่น ผลลัพธ์สรุปที่ต้องแยกสายตาชัดเจน) หน้าจอเชิงปฏิบัติการ (operational screen) ให้เลือกใช้ `section` (หัวข้อ + เส้นแบ่ง `divider`), `table`, และ split-panel เป็นหลักก่อนคิดถึง card — โครงหน้าอ้างอิง:

```
Page Header
────────────────────────────────────────
KPI strip
Bed Occupancy 84.2% | ALOS 3.4 | ER Wait 32m | Census 428 | ...
────────────────────────────────────────
Operational Trend                  Decision / Alert
[ graph / timeline ]               [ compact panel ]
────────────────────────────────────────
Department Situation / Worklist / Details
```

### 0.5.3 Enterprise KPI Strip ก่อน Stat Card เสมอสำหรับ Operational Dashboard

ตัวเลขสรุปในหน้าจอเชิงปฏิบัติการ (Level 1-3 ของ Command Center, ER Flow, Bed Management ฯลฯ) **ต้องใช้ `components/enterprise-kpi-strip.html`** (แถวเดียว compact, ตัวเลขขนาดพอเหมาะกับบริบทงาน ไม่ใหญ่เกินหัวข้อหน้า) — **`stat-card.html`** (ไอคอนวงกลมสี + ตัวเลขใหญ่) **สงวนไว้เฉพาะ** หน้า Home Dashboard ของแต่ละ module หรือ Executive Summary ที่เหมาะสมเท่านั้น (ตาม `patterns/dashboard-home.md` เดิม) ห้ามใช้ผสมกันในหน้าเดียวโดยไม่มีเหตุผล

### 0.5.4 สีต้องเหลือ "90% Neutral + 10% Meaning"

หน้าจอส่วนใหญ่ต้องเป็นโทนกลาง (ขาว/เทา) 80-90% ของพื้นที่ทั้งหมด สีที่ไม่ใช่กลางใช้ได้เฉพาะ:
- **Gorilla Indigo** (`--color-blue-*`) → navigation, primary action เท่านั้น
- **เขียว** (`--color-status-normal`) → success/normal เท่านั้น
- **ส้ม** (`--color-status-warning`) → warning เท่านั้น (**ห้าม**ใช้กับปุ่ม action ทั่วไปเพื่อให้ปุ่มเด่น — ปุ่มที่ไม่ใช่ warning state จริงต้องเป็น `btn--secondary`/`btn--primary` ปกติ)
- **แดง** (`--color-status-critical`) → critical เท่านั้น

สีมีไว้ "บอกความหมาย" ไม่ใช่ "ทำให้หน้าจอสวย" — ถ้าจะเพิ่มสีต้องตอบได้ว่าสีนั้นสื่อความหมายเชิง semantic อะไร ตอบไม่ได้ = ห้ามใส่

### 0.5.5 Application Shell ต้องมีแบบเดียว ห้าม AI ออกแบบเอง

โครง Shell (Top bar + Left sidebar navigation ตาม §2) ถูก**ล็อกตายตัว**ไว้ที่ `components/application-shell.html` แล้ว **ห้าม feature ใดออกแบบ Shell ของตัวเอง** (ไม่ว่าจะเป็น top-nav-tabs, dark header, หรือรูปแบบอื่น) AI มีสิทธิ์ออกแบบเฉพาะ **Main Content Area** เท่านั้น ส่วนที่ห้ามแตะ: Logo placement, Top bar, Sidebar, Module selector, User profile, Navigation width, Header height (รายละเอียดดู component file)

### 0.5.6 Premium HIS Density Rule

จอ Desktop HIS ต้องออกแบบเพื่อ **operational scanning** ไม่ใช่จอโฆษณา หลีกเลี่ยง whitespace ที่มากเกินจำเป็น ที่ความละเอียด **1366×768 หน้าจอแรกที่เปิดมาต้องเห็นครบโดยไม่ต้อง scroll**: Page context, KPI, Alert, ข้อมูลปฏิบัติการหลัก, Primary Action

### 0.5.7 Feature ที่เกี่ยวกับ AI ต้องไม่มี "AI Visual Theme"

Feature ที่ใช้ AI/Predictive logic ภายใน **ต้องแสดงผลเหมือน Clinical/Operational Intelligence ปกติ** ไม่ใช่ AI showcase — ห้ามใช้ gradient, dark futuristic panel, glow, สีม่วง, emoji สมอง, sparkle ✨ ประกอบ ตัวอย่าง:

- ❌ "✨ AI Brain & Predictive Intelligence Engine"
- ✅ "Operational Intelligence" พร้อมบรรทัดกำกับ `Updated 14:38 | Source: ADT, ER, Bed Management`

และ AI Recommendation ให้ใช้ panel แบบเดียวกับ Clinical Recommendation ปกติของระบบ (ไม่ใช่ card พิเศษแยกสไตล์)

### 0.5.8 Premium HIS Visual Gate (เพิ่มเข้า Factory Gate)

QA/Builder ต้องตอบ 7 ข้อนี้ก่อนถือว่างานผ่าน (รายละเอียดเต็มดู `factory-gate/premium-his-visual-gate.md`): (1) ดูเหมือนระบบงานโรงพยาบาลหรือ SaaS Dashboard? (2) มี Emoji/decorative icon หรือไม่? (3) มี Card มากเกินจำเป็นหรือไม่? (4) มีสีที่ไม่สื่อ semantic meaning หรือไม่? (5) มี oversized heading/KPI หรือไม่? (6) Shell ตรงกับ Master Application Shell หรือไม่? (7) ที่ 1366×768 information density เหมาะกับ HIS หรือไม่?

## 1. หลักการออกแบบ (Design Principles)

1. **Patient Safety First** — ข้อมูลที่กระทบความปลอดภัยผู้ป่วย (แพ้ยา, ค่า Lab วิกฤต, Drug interaction) ต้อง**เด่นที่สุดในหน้าจอเสมอ** ห้ามให้จมไปกับ UI อื่น
2. **Clarity over decoration** — บุคลากรทางการแพทย์ใช้งานภายใต้ความกดดันเรื่องเวลา ห้ามใช้ลูกเล่นภาพที่ไม่ช่วยการอ่านข้อมูล (เงา/gradient ฉูดฉาด, font แฟนซี)
3. **Consistency ก่อน Creativity** — ความสม่ำเสมอข้าม module สำคัญกว่าความคิดสร้างสรรค์ส่วนบุคคล ถ้าจะเบี่ยงจาก pattern เดิมต้องมีเหตุผลทางธุรกิจรองรับ
4. **Information density ที่เหมาะสม** — จอ HIS ส่วนใหญ่แสดงข้อมูลจำนวนมาก (ตาราง, รายการ) ให้ออกแบบเพื่อการสแกนสายตาเร็ว ไม่ใช่จอโฆษณา
5. **Standard UI ก่อนเสมอ** — ทุก module ควรประกอบจาก Search, Filter, Worklist/Table, Patient Header, Tabs, Form, Modal/Drawer, Status Badge, Alert/Toast ที่มีอยู่แล้ว **ห้ามสร้าง Design System เฉพาะของ module ตัวเอง**

## 2. Layout & Grid

- **Baseline resolution:** ออกแบบสำหรับจอ desktop 1366×768 เป็นหลัก (เครื่อง PC ที่ใช้ในโรงพยาบาลส่วนใหญ่) รองรับการขยายได้ถึง 1920px แบบ fluid แต่ไม่ต้อง responsive ระดับ mobile เว้นแต่ระบุใน requirement
- **โครงหน้าจอมาตรฐาน:** Top bar (โลโก้ + ชื่อผู้ใช้ + module switcher) + Left sidebar navigation (แบบ collapsible) + Content area
- **Spacing scale:** ใช้ค่าใน `tokens.css` (`--space-1` ถึง `--space-8`) เท่านั้น ห้ามใส่ px เอง
- **Grid:** เนื้อหาหลักใช้ 12-column grid, gutter = `--space-4`, max-width content = 1600px แล้ว center

## 3. Typography

- Font stack: `var(--font-family-base)` (รองรับภาษาไทยเป็นหลัก ดู `tokens.css`)
- ใช้ scale ที่กำหนดเท่านั้น: `--font-size-xs` ถึง `--font-size-2xl`
- หัวข้อหน้าจอ (page title) = `--font-size-xl` + `--font-weight-bold`
- ตัวเลขทางคลินิก (vitals, lab values) ใช้ `--font-family-mono` เพื่อให้ตัวเลขอ่านง่าย เรียงคอลัมน์ตรงกัน

## 4. Semantic Color — กฎที่ห้ามฝ่าฝืน

สีเชิงความหมาย (semantic color) สงวนไว้สำหรับสถานะทางคลินิกเท่านั้น **ห้ามนำไปใช้ตกแต่งหรือสื่อความหมายอื่นเด็ดขาด**

| Token | สี | ความหมาย | ตัวอย่างการใช้งาน |
|---|---|---|---|
| `--color-status-critical` | แดง | วิกฤต/อันตรายถึงชีวิต | แพ้ยารุนแรง, ค่า Lab critical, vitals ผิดปกติรุนแรง |
| `--color-status-warning` | ส้ม/เหลือง | ต้องระวัง/ผิดปกติ | ค่า Lab สูง/ต่ำกว่าเกณฑ์, คิวล่าช้า |
| `--color-status-normal` | เขียว | ปกติ/สำเร็จ | ค่าปกติ, เช็คอินสำเร็จ |
| `--color-status-info` | น้ำเงิน | ข้อมูลทั่วไป | คำแนะนำ, สถานะกำลังดำเนินการ |
| `--color-status-inactive` | เทา | ไม่ใช้งาน/ปิด | รายการที่ถูกยกเลิก, ปิดสิทธิ์ |

**กฎเพิ่มเติม:**
- Banner แพ้ยา/allergy ต้องใช้ `--color-status-critical` เสมอ และต้องอยู่ตำแหน่งบนสุดของหน้าจอผู้ป่วย (ดู `components/alert-banner.html`)
- ห้ามใช้สีแดงกับปุ่ม "ลบ" ทั่วไปที่ไม่เกี่ยวกับความปลอดภัยผู้ป่วย ให้ใช้ `--color-danger-action` แทน (คนละความหมายกับ critical ทางคลินิก)

## 5. Component Reuse Policy (กฎสำคัญที่สุด)

ก่อนสร้าง component ใหม่ ต้องตอบคำถามเหล่านี้ให้ได้ก่อน:

1. มี component ใน `design-system/components/` ที่ตรงกับ 80% ของ requirement หรือไม่? → ถ้ามี **ต้องใช้ตัวนั้นแล้วขยาย** (เพิ่ม prop/variant) ไม่ใช่สร้างใหม่ทั้งหมด
2. ถ้าไม่มีตัวที่ตรง ให้เช็คว่ามี pattern ระดับหน้าจอใน `design-system/patterns/` ที่ประกอบจาก component เดิมได้หรือไม่
3. ถ้าจำเป็นต้องสร้างใหม่จริง ๆ ต้องระบุเหตุผลใน Design Notes และ**เสนอเข้า design system กลาง**ผ่านที่ประชุม weekly sync (ดู `docs/TEAM_ONBOARDING.md`) ก่อนให้คนอื่นเอาไปใช้ต่อ — ห้ามต่างคนต่างสร้าง component ซ้ำซ้อนกันโดยไม่มีใครรู้

## 6. Accessibility ขั้นต่ำ

- Contrast ratio ข้อความ/พื้นหลัง ≥ 4.5:1 (WCAG AA)
- ปุ่ม/พื้นที่กดต้องมีขนาดขั้นต่ำ 44×44px (บาง ward ใช้จอสัมผัส/แท็บเล็ตข้างเตียงผู้ป่วย)
- ทุก interactive element ต้องกด Tab ถึงได้ และมี focus state ที่มองเห็นชัด
- ห้ามสื่อความหมายด้วยสีอย่างเดียว (เช่น critical ต้องมีทั้งสี + icon + label ข้อความ ไม่ใช้สีแดงลอย ๆ)

## 7. Clinical Data Rules (สำหรับ Mock Data)

- ค่าปกติ (reference range) อ้างอิงมาตรฐานทางการแพทย์ทั่วไป เช่น:
  - Body temperature: 36.1–37.2°C (ปกติ), ≥38.0°C = fever (warning), ≥39.5°C = critical
  - Heart rate: 60–100 bpm (ปกติผู้ใหญ่)
  - Blood pressure: <120/80 (ปกติ), ≥140/90 = warning (hypertension)
  - SpO2: ≥95% ปกติ, <90% = critical
- ทุก mockup ที่มีตาราง Lab/Vitals ต้องมีอย่างน้อย **1 record ที่ผิดปกติ** เพื่อ demo การแสดงผล status color
- ชื่อผู้ป่วยและ HN ใน mock data ต้องเป็นข้อมูลสมมติที่ดูสมจริง (เช่น "นายสมชาย ใจดี", HN รูปแบบ `HN6805-XXXXX`) **ห้ามใช้ข้อมูลผู้ป่วยจริงเด็ดขาด**

## 8. States

State ครบ 6 แบบ (Normal/Loading/Empty/Error/Success/Disabled) อยู่ที่ [`ux-rules.md`](./ux-rules.md) § 5 แล้ว — หมวดนี้เก็บไว้เฉพาะกฎเชิงภาพของ **Critical Alert** ซึ่งเป็น state พิเศษด้าน patient-safety:

| State | เมื่อไหร่ต้องมี | วิธีจำลอง |
|---|---|---|
| Critical Alert | ผู้ป่วยมีความเสี่ยง (แพ้ยา, ค่าวิกฤต) | Banner สีแดงเด่นชัดตำแหน่งบนสุด ไม่ปิดได้ง่าย ๆ โดยไม่ตั้งใจ |

## 9. Naming Convention

- ชื่อไฟล์/โฟลเดอร์ feature: `kebab-case` เช่น `patient-queue-checkin`
- ชื่อ CSS class: `bem-like` prefix ด้วยชื่อ component เช่น `.vitals-form__row--abnormal`
- ชื่อ mock data variable: ภาษาอังกฤษ, ตั้งชื่อสื่อความหมาย เช่น `mockPatients`, `mockLabResults`

## 10. Do / Don't สรุป

**Do:**
- ใช้ tokens.css ทุกครั้ง, reuse component เดิมก่อนเสมอ, ใส่ mock data ที่มี edge case, ใส่ header comment ทุกไฟล์

**Don't:**
- ห้าม hardcode สี/spacing, ห้ามใช้ CDN ภายนอก, ห้ามใช้สีเชิงความหมายผิดความหมาย, ห้ามสร้าง component ซ้ำโดยไม่เช็คของเดิมก่อน, ห้ามใช้ข้อมูลผู้ป่วยจริง
