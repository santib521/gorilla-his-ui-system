# TEAM_ONBOARDING.md — แผนสอนงานทีม Mockup (10 คน)

เป้าหมาย: ให้ทั้ง 10 คนใช้ระบบ Gorilla HIS UI Factory ได้เหมือนกันทุกคน ภายใน **1 วัน (workshop) + 2 สัปดาห์แรกแบบ buddy**

---

## Workshop วันแรก (ครึ่งวัน ~ 4 ชั่วโมง)

### Session 1 — ทำไมต้องมีระบบนี้ (30 นาที)
- ปัญหาที่เจอตอนนี้: mockup แต่ละคนหน้าตาไม่เหมือนกัน, ลูกค้าสับสน, Dev ตีความ UI ผิด
- เดโมเปรียบเทียบ: mockup แบบเก่า (ต่างคนต่างทำ) vs mockup ที่ผ่านระบบใหม่
- เป้าหมาย: ความเร็ว + ความสม่ำเสมอ + ตรวจสอบย้อนกลับได้

### Session 2 — เดินดู Repository จริง (45 นาที)
ให้ทุกคนเปิด repo พร้อมกัน เดินไล่ตามลำดับนี้:
1. `README.md` — ภาพรวม
2. `AI_INSTRUCTIONS.md` — กติกา (เน้นย้ำ § 2 กฎเหล็ก และ § 5 QA)
3. `design-system/tokens.css` — ตัวแปรที่ต้องใช้
4. `design-system/components/` — เปิดไฟล์จริงในเบราว์เซอร์ทีละไฟล์ (patient-search-bar, vitals-form, lab-result-table) ให้เห็นว่า "ใช้งานได้จริง" ไม่ใช่แค่ภาพ
5. `design-system/patterns/` — อธิบายว่า pattern ต่างจาก component ยังไง
6. `modules/` และ `approved-mockups/` — อธิบาย flow สร้าง → QA → approve

### Session 3 — ลงมือทำจริงพร้อมกัน (Hands-on) (90 นาที)
โจทย์ฝึก: **"สร้าง mockup หน้าค้นหาผู้ป่วยแบบง่าย ๆ สำหรับ module OPD"**

ทุกคนทำตามขั้นตอนจริงพร้อมกัน:
1. Copy `modules/_feature-template/` → `modules/opd/practice-search-<ชื่อตัวเอง>/`
2. เปิด `MOCKUP_PROMPT_TEMPLATE.md` กรอกโจทย์ฝึกให้ครบ
3. ครึ่งห้องใช้ Claude, ครึ่งห้องใช้ Gemini — ส่ง prompt เดียวกัน เปรียบเทียบผลลัพธ์ท้าย session
4. บันทึกผลใน `prompt-used.md`
5. **สังเกตร่วมกัน:** ผลจาก Claude กับ Gemini ต่างกันตรงไหน ทำไมถึงต้องมีขั้นตอน "แปะไฟล์" สำหรับ Gemini

### Session 4 — Git Workflow + QA Checklist (45 นาที)
- สาธิตขั้นตอนเต็มใน `WORKFLOW.md`: branch → PR → QA → merge → approved-mockups
- จับคู่ 2 คน ให้คนหนึ่งเป็นผู้สร้าง อีกคนเป็นผู้ QA ไฟล์จาก Session 3 โดยใช้ `qa-checklist.md` จริง
- สรุปข้อผิดพลาดที่พบบ่อยร่วมกันทั้งห้อง

### Session 5 — Q&A + มอบหมายงานจริงชิ้นแรก (30 นาที)
- ตอบคำถามค้างคาใจ
- มอบหมาย feature จริงชิ้นแรกให้แต่ละคน (จับคู่กับ buddy ตามด้านล่าง)

---

## 2 สัปดาห์แรก — Buddy System

- จับคู่คนใหม่กับคนที่ช่ำชอง (หรือ Design QA Lead) 1:1
- feature จริง 2 ชิ้นแรกของแต่ละคน ต้องให้ buddy ช่วยรีวิว prompt **ก่อน**ส่งให้ AI (ไม่ใช่แค่รีวิว output)
- หลัง feature ที่ 2 ผ่าน QA แบบไม่มีปัญหาใหญ่ → ทำงานเดี่ยวได้เต็มตัว

## Weekly Design Sync (ต่อเนื่องตลอดไป)

- ประชุมสั้น 30 นาที/สัปดาห์
- วาระ: มี component/pattern ใหม่เสนอเข้า design system กลางไหม, ปัญหาที่เจอซ้ำ ๆ ใน QA, อัปเดต `tokens.css` (ถ้ามี)
- **กฎ:** ห้ามเพิ่ม component/pattern ใหม่เข้า `design-system/` โดยไม่ผ่านที่ประชุมนี้ (ดู `WORKFLOW.md` § 5)

## Checklist ความพร้อมของคนใหม่ (ให้ Design QA Lead เซ็นรับรอง)

- [ ] อ่าน `AI_INSTRUCTIONS.md` และ `design-rules.md` จบแล้ว
- [ ] ทำโจทย์ฝึก Session 3 สำเร็จ และผ่าน QA checklist ได้ด้วยตัวเอง
- [ ] เข้าใจว่าเมื่อไหร่ต้อง "เสนอ component ใหม่" แทนที่จะสร้างเอง
- [ ] รู้ขั้นตอน branch/PR/merge ใน `WORKFLOW.md`
- [ ] ผ่าน feature จริง 2 ชิ้นแรกพร้อม buddy แล้ว

## ข้อผิดพลาดที่พบบ่อย (อัปเดตหลังทุก sync — เริ่มต้นว่างไว้ก่อน)

| ปัญหาที่พบ | สาเหตุ | วิธีป้องกัน |
|---|---|---|
| _ตัวอย่าง_ AI สร้างปุ่มสีแดงเพื่อ "เตะตา" ไม่ใช่ critical จริง | ไม่ได้อ่าน design-rules.md § 4 ก่อน | ย้ำใน prompt ว่าใช้ semantic color ตามกฎเท่านั้น |
