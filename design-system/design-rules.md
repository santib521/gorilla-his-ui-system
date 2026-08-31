# Design Rules — Gorilla HIS Design System

กฎเหล่านี้ผูกพันกับทุก mockup ที่สร้างในระบบ ไม่ว่าจะทำโดย AI ตัวไหนหรือคนไหน เป้าหมายคือให้ mockup จากคน 10 คน **ดูเหมือนออกมาจากทีมเดียวกัน**

> เรื่อง**พฤติกรรม/การโต้ตอบ**ของ UI (worklist, action, state, detail pattern) ย้ายไปอยู่ที่ [`ux-rules.md`](./ux-rules.md) แล้ว — ไฟล์นี้เน้นเฉพาะ**หน้าตา/ภาพ**

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

### 0.1 Premium HIS Product Character — Mandatory Additive Rules

กฎชุดนี้ **เพิ่มจาก Visual Audit เดิม ไม่ได้แทนที่กฎเดิมด้าน clinical safety / component / pattern**

Gorilla HIS ต้องให้ความรู้สึกเป็น **Professional Hospital Enterprise Application** ไม่ใช่ AI showcase, marketing dashboard, fintech dashboard หรือ consumer SaaS product

บุคลิกเป้าหมาย: **Clinical / Operational / Trustworthy / Dense / Calm / Professional**

1. **Enterprise HIS, not AI Dashboard** — ห้ามใช้ visual language แบบ futuristic AI, hero banner, marketing section, glowing/gradient decoration หรือองค์ประกอบที่มีไว้สร้างความว้าวมากกว่าช่วยงาน
2. **No Emoji UI** — ห้ามใช้ Emoji เป็น navigation icon, section icon, status icon หรือ decorative icon เช่น brain/chart/lightning/hospital/gear/sparkle emoji; ใช้ approved monochrome inline SVG/icon language แทน
3. **Locked Application Shell** — Desktop mockup ให้เริ่มจาก `components/application-shell.html` เว้นแต่มี approved shell อื่นที่ตรง use case; feature team/AI ปรับเฉพาะ module text, navigation labels, context และ Main Content โดยไม่สร้าง shell ใหม่
4. **Card is not the default container** — ห้าม Card Everywhere; operational screen ให้ตรวจ section, divider, table, split panel และ `operational-panel.html` ก่อน
5. **Operational KPI uses compact strip first** — Command Center / Operational Dashboard ให้ตรวจ `enterprise-kpi-strip.html` ก่อน `stat-card.html`; `stat-card.html` ยังใช้ได้ตาม Visual Audit สำหรับ Home/Executive summary ที่เหมาะสม
6. **Neutral-first color discipline** — พื้นที่ส่วนใหญ่ใช้ neutral surface/text/border; Brand Indigo ใช้ navigation/primary action; semantic clinical colors ยังคงอยู่ภายใต้กฎ §4 และห้ามใช้เพื่อตกแต่ง
7. **Compact operational density** — ที่ 1366×768 ควรเห็น page context + KPI/summary + alert + main operational information + primary action ใน first viewport เมื่อ requirement เอื้อ
8. **No oversized UI** — หลีกเลี่ยง KPI/heading/button/card แบบ poster/marketing scale; ใช้ typography token เดิม
9. **AI is a capability, not a visual theme** — AI/Prediction/Recommendation ต้องอยู่ใน Gorilla HIS visual language เดียวกับ function อื่น; ห้าม dark futuristic panel, sparkle decoration หรือ AI-specific theme
10. **Clarity over decoration** — shadow, radius, whitespace และ decoration ต้องช่วย hierarchy/scanability ไม่ใช่มีไว้เพื่อความสวยอย่างเดียว

## 1. หลักการออกแบบ (Design Principles)

1. **Patient Safety First** — ข้อมูลที่กระทบความปลอดภัยผู้ป่วย (แพ้ยา, ค่า Lab วิกฤต, Drug interaction) ต้อง**เด่นที่สุดในหน้าจอเสมอ** ห้ามให้จมไปกับ UI อื่น
2. **Clarity over decoration** — บุคลากรทางการแพทย์ใช้งานภายใต้ความกดดันเรื่องเวลา ห้ามใช้ลูกเล่นภาพที่ไม่ช่วยการอ่านข้อมูล (เงา/gradient ฉูดฉาด, font แฟนซี)
3. **Consistency ก่อน Creativity** — ความสม่ำเสมอข้าม module สำคัญกว่าความคิดสร้างสรรค์ส่วนบุคคล ถ้าจะเบี่ยงจาก pattern เดิมต้องมีเหตุผลทางธุรกิจรองรับ
4. **Information density ที่เหมาะสม** — จอ HIS ส่วนใหญ่แสดงข้อมูลจำนวนมาก (ตาราง, รายการ) ให้ออกแบบเพื่อการสแกนสายตาเร็ว ไม่ใช่จอโฆษณา
5. **Standard UI ก่อนเสมอ** — ทุก module ควรประกอบจาก Search, Filter, Worklist/Table, Patient Header, Tabs, Form, Modal/Drawer, Status Badge, Alert/Toast ที่มีอยู่แล้ว **ห้ามสร้าง Design System เฉพาะของ module ตัวเอง**

## 2. Layout & Grid

- **Baseline resolution:** ออกแบบสำหรับจอ desktop 1366×768 เป็นหลัก (เครื่อง PC ที่ใช้ในโรงพยาบาลส่วนใหญ่) รองรับการขยายได้ถึง 1920px แบบ fluid แต่ไม่ต้อง responsive ระดับ mobile เว้นแต่ระบุใน requirement
- **โครงหน้าจอมาตรฐาน:** Top bar (โลโก้ + ชื่อผู้ใช้ + module switcher) + Left sidebar navigation (แบบ collapsible) + Content area
- **Master shell:** สำหรับ desktop mockup ใหม่ ให้ใช้ `components/application-shell.html` เป็น structural reference; control ภายใน เช่น button/form/modal ยังต้อง reuse component เฉพาะของมัน
- **Spacing scale:** ใช้ค่าใน `tokens.css` (`--space-1` ถึง `--space-8`) เท่านั้น ห้ามใส่ px เอง
- **Grid:** เนื้อหาหลักใช้ 12-column grid, gutter = `--space-4`, max-width content = 1600px แล้ว center

## 3. Typography

- Font stack: `var(--font-family-base)` (รองรับภาษาไทยเป็นหลัก ดู `tokens.css`)
- ใช้ scale ที่กำหนดเท่านั้น: `--font-size-xs` ถึง `--font-size-2xl`
- หัวข้อหน้าจอ (page title) = `--font-size-xl` + `--font-weight-bold`
- ตัวเลขทางคลินิก (vitals, lab values) ใช้ `--font-family-mono` เพื่อให้ตัวเลขอ่านง่าย เรียงคอลัมน์ตรงกัน
- ห้ามใช้ display/marketing typography ใน operational screen

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
- Operational indicator ที่ไม่ใช่ clinical/patient-safety ห้ามยืมสีแดง/ส้ม/เขียวมาเพียงเพื่อเพิ่มความเด่น; ใช้ neutral/info เป็นค่าเริ่มต้น และใช้ warning/critical เฉพาะเมื่อมีความหมายความเสี่ยงจริงตาม requirement

## 5. Component Reuse Policy (กฎสำคัญที่สุด)

ก่อนสร้าง component ใหม่ ต้องตอบคำถามเหล่านี้ให้ได้ก่อน:

1. มี component ใน `design-system/components/` ที่ตรงกับ 80% ของ requirement หรือไม่? → ถ้ามี **ต้องใช้ตัวนั้นแล้วขยาย** (เพิ่ม prop/variant) ไม่ใช่สร้างใหม่ทั้งหมด
2. ถ้าไม่มีตัวที่ตรง ให้เช็คว่ามี pattern ระดับหน้าจอใน `design-system/patterns/` ที่ประกอบจาก component เดิมได้หรือไม่
3. ถ้าจำเป็นต้องสร้างใหม่จริง ๆ ต้องระบุเหตุผลใน Design Notes และ**เสนอเข้า design system กลาง**ผ่านที่ประชุม weekly sync (ดู `docs/TEAM_ONBOARDING.md`) ก่อนให้คนอื่นเอาไปใช้ต่อ — ห้ามต่างคนต่างสร้าง component ซ้ำซ้อนกันโดยไม่มีใครรู้
4. Operational/Command Center screen ต้องตรวจ `application-shell.html`, `enterprise-kpi-strip.html`, `operational-panel.html` ก่อนสร้าง shell/KPI/container ใหม่

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

## 10. Premium HIS Visual Anti-Patterns

ให้ Visual QA ระบุ deviation เมื่อพบโดยไม่มี approved exception:

- Emoji เป็น UI icon/navigation/section decoration
- Module-specific shell ที่ละเลย approved master shell
- AI/futuristic/marketing visual theme
- Card Everywhere หรือ oversized stat-card grid ใน operational screen ทั้งที่ compact component รองรับ
- Semantic clinical color ถูกใช้ตกแต่ง
- Oversized heading/KPI/button/card ที่ลด scanability
- Excessive whitespace จน key operational state ไม่อยู่ใน first viewport 1366×768 ทั้งที่จัดให้เห็นได้
- UI ดูเป็น generic SaaS template เพราะละเลย approved shell/components/patterns

## 11. Do / Don't สรุป

**Do:**
- ใช้ tokens.css ทุกครั้ง, reuse component เดิมก่อนเสมอ, ใส่ mock data ที่มี edge case, ใส่ header comment ทุกไฟล์
- สำหรับ desktop operational screen เริ่มจาก master shell และเลือก compact KPI/operational panel เมื่อเหมาะสม

**Don't:**
- ห้าม hardcode สี/spacing, ห้ามใช้ CDN ภายนอก, ห้ามใช้สีเชิงความหมายผิดความหมาย, ห้ามสร้าง component ซ้ำโดยไม่เช็คของเดิมก่อน, ห้ามใช้ข้อมูลผู้ป่วยจริง
- ห้ามสร้าง AI/SaaS visual identity ใหม่แทน Gorilla HIS
