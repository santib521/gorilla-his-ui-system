# Design Rules — Gorilla HIS Design System

กฎเหล่านี้ผูกพันกับทุก mockup ที่สร้างในระบบ ไม่ว่าจะทำโดย AI ตัวไหนหรือคนไหน เป้าหมายคือให้ mockup จากคน 10 คน **ดูเหมือนออกมาจากทีมเดียวกัน**

> เรื่องพฤติกรรม/การโต้ตอบของ UI ให้ยึด `ux-rules.md`; ไฟล์นี้เป็น Design Authority ด้านหน้าตาและ Product Character

## 0. Product Character — Premium Hospital Enterprise System

Gorilla HIS ต้องดูเป็น **Professional Hospital Enterprise Application** ไม่ใช่ AI showcase, marketing dashboard, fintech dashboard หรือ consumer SaaS product

บุคลิกหลัก: **Clinical / Operational / Trustworthy / Dense / Calm / Professional**

### Premium HIS Visual Rules — Mandatory

1. **Enterprise HIS, not AI Dashboard** — ห้ามใช้ visual language แบบ futuristic AI, hero banner, marketing section, glowing/gradient decoration หรือองค์ประกอบที่มีไว้สร้างความว้าวมากกว่าช่วยงาน
2. **No Emoji UI** — ห้ามใช้ Emoji เป็น navigation icon, section icon, status icon หรือ decorative icon เช่น brain/chart/lightning/hospital/gear/sparkle emoji ให้ใช้ approved monochrome inline SVG/icon language แทน
3. **Locked Application Shell** — Desktop mockup ต้องเริ่มจาก `components/application-shell.html` เว้นแต่มี approved shell อื่นที่ตรง use case; feature team/AI ปรับได้เฉพาะข้อความ navigation/context และ Main Content ห้ามออกแบบ shell ใหม่ต่อ module
4. **Card is not the default container** — ห้ามทำ Card Everywhere. ให้ใช้ section, divider, table, split panel และ `operational-panel.html` เป็นค่าเริ่มต้นสำหรับ operational screen. Card ใช้เมื่อข้อมูลเป็น independent summary จริง
5. **Operational KPI uses compact strip first** — หน้า Command Center / Operational Dashboard ให้ใช้ `enterprise-kpi-strip.html` ก่อน `stat-card.html`; stat card เหมาะกับ Home/Executive summary ที่มีเหตุผลรองรับ
6. **90% Neutral / 10% Meaning** — พื้นที่ส่วนใหญ่ใช้ neutral surface/text/border. Brand Indigo ใช้ navigation/primary action. Green/Orange/Red ใช้เมื่อมี semantic meaning เท่านั้น ห้ามใช้สีเพื่อทำให้ card หรือปุ่มดูโดดเด่นโดยไม่มีความหมาย
7. **Compact operational density** — ที่ 1366×768 ผู้ใช้ควรเห็น page context + KPI/summary + alert + main operational information + primary action โดยไม่ต้อง scroll ใน main workflow ถ้า requirement เอื้อ
8. **No oversized UI** — หลีกเลี่ยง KPI/heading/button/card ที่ใหญ่เกินความจำเป็น. Page title ใช้ token scale ที่กำหนด; operational number ต้อง scan ได้เร็วโดยไม่กลายเป็น poster typography
9. **AI is a capability, not a visual theme** — Feature AI ใช้ภาษาเดียวกับ Gorilla HIS. ใช้คำ Operational Intelligence / Recommendation / Prediction ตาม business context; ห้ามสร้าง dark futuristic AI panel, sparkle decoration หรือ AI-specific theme
10. **Clarity over decoration** — shadow, radius, whitespace และ decoration ต้องมีเหตุผลด้าน hierarchy/scanability ไม่ใช่เพื่อความสวยอย่างเดียว

## 1. Design Principles

1. **Patient Safety First** — ข้อมูลที่กระทบความปลอดภัยผู้ป่วยต้องเด่นที่สุดในหน้าจอ
2. **Clarity over decoration** — บุคลากรทางการแพทย์ใช้งานภายใต้แรงกดดันด้านเวลา
3. **Consistency ก่อน Creativity** — ความสม่ำเสมอข้าม module สำคัญกว่าความคิดสร้างสรรค์ส่วนบุคคล
4. **Information density ที่เหมาะสม** — ออกแบบเพื่อการสแกนสายตาเร็ว ไม่ใช่จอโฆษณา
5. **Standard UI ก่อนเสมอ** — approved components/patterns มาก่อนการสร้างใหม่

## 2. Layout & Grid

- Baseline resolution: 1366×768; fluid ถึง 1920×1080
- Standard shell: **ใช้ `components/application-shell.html` เป็น master** — Top bar + Left sidebar + Page Header + Content area
- Main content ใช้ 12-column grid เมื่อเหมาะสม, gutter = `--space-4`, max-width = `--layout-content-max-width`
- ใช้ spacing token เท่านั้น ห้ามใส่ค่า spacing เองเมื่อ token รองรับ
- Operational screen ควร prioritize vertical efficiency; whitespace มากไม่ถือว่า premium โดยอัตโนมัติ

## 3. Typography

- Font: `var(--font-family-base)`
- ใช้ token scale `--font-size-xs` ถึง `--font-size-2xl`
- Page title = `--font-size-xl` + `--font-weight-bold`
- Clinical numeric data ใช้ `--font-family-mono` เมื่อช่วยการอ่าน/จัดแนว
- ห้ามใช้ display/marketing typography ในหน้าระบบงาน

## 4. Semantic Color — Mandatory

Semantic color สงวนไว้สำหรับความหมายของสถานะ ห้ามใช้ตกแต่ง

| Token | Meaning |
|---|---|
| `--color-status-critical` | วิกฤต / patient-safety critical |
| `--color-status-warning` | ต้องระวัง / ผิดปกติ / operational warning |
| `--color-status-normal` | ปกติ / สำเร็จ |
| `--color-status-info` | ข้อมูลทั่วไป / in-progress |
| `--color-status-inactive` | ไม่ใช้งาน / ปิด |

- Critical ต้องมีสี + icon/label/text ไม่พึ่งสีอย่างเดียว
- Brand mark teal ใช้เฉพาะ brand/logo context
- ปุ่ม destructive ทั่วไปใช้ action token ไม่แย่งความหมาย clinical critical

## 5. Component Reuse Policy

1. ถ้ามี component ตรง requirement ≥80% ต้อง reuse/extend
2. ถ้าไม่มี ให้ตรวจ approved pattern ก่อนสร้างใหม่
3. New reusable component/pattern ต้อง Declare ใน Design Notes และเสนอ Design QA ก่อนเป็น shared standard
4. Operational dashboard ต้องตรวจ `application-shell.html`, `enterprise-kpi-strip.html`, `operational-panel.html` ก่อนสร้าง container/KPI/navigation ใหม่

## 6. Accessibility

- Contrast ≥ WCAG AA
- Interactive target อย่างน้อย 44×44px ตาม approved component implementation
- Keyboard/focus state ต้องมองเห็น
- ห้ามใช้สีอย่างเดียวสื่อความหมาย

## 7. Mock Clinical Data

- ใช้ข้อมูลสมมติเท่านั้น
- ค่าทางคลินิกต้องสมเหตุสมผลกับบริบท
- เมื่อ feature มี Lab/Vitals/Alert ให้มีกรณี abnormal/attention ตาม Blueprint/QA need โดยไม่ใช้ข้อมูลผู้ป่วยจริง

## 8. Premium HIS Anti-Patterns — Automatic Design QA Failure

ให้ถือว่า Visual Gate FAIL เมื่อพบโดยไม่มี approved exception:

- Emoji เป็น UI icon
- Module-specific shell ที่ไม่ใช้ approved shell
- AI/futuristic/marketing visual theme
- Card Everywhere หรือ oversized stat-card grid ใน operational screen ทั้งที่ compact component ใช้ได้
- Semantic clinical color ถูกใช้ตกแต่ง
- Oversized heading/KPI/button ทำให้ information density ลดลงอย่างชัดเจน
- Excessive whitespace จน key operational state ไม่อยู่ใน first viewport 1366×768 ทั้งที่จัดให้เห็นได้
- UI ดูเป็น generic SaaS template มากกว่า Gorilla HIS เนื่องจากละเลย approved shell/components/patterns
