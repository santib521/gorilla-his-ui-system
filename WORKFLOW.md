# WORKFLOW.md — Git & QA Process

## 1. Branch Naming

```
mockup/<module>-<feature>-<ชื่อย่อผู้ทำ>
```

ตัวอย่าง: `mockup/opd-patient-queue-checkin-ti`

## 2. ขั้นตอนทำงาน (ต่อ 1 feature)

1. `git checkout -b mockup/<module>-<feature>-<initials>`
2. Copy `modules/_feature-template/` → `modules/<module>/<feature>/`
3. กรอก `MOCKUP_PROMPT_TEMPLATE.md`, ส่งให้ AI, ได้ `index.html` มา
4. บันทึก prompt ที่ใช้จริงลงใน `prompt-used.md`
5. ทำ **Self-QA** ตาม `review/qa-checklist.md` ด้วยตัวเองก่อน
6. Commit: `git commit -m "mockup(<module>): add <feature> v1"`
7. Push + เปิด Pull Request เข้า `main`
   - PR description ต้องแปะ **Design Notes** ที่ AI สรุปมา
   - แนบ screenshot คร่าว ๆ ใน PR (ไม่ต้องรอ approve ก่อนถ่ายจริงจัง)

## 3. QA Gate (บังคับก่อน merge)

- Reviewer: Design QA Lead หรือเพื่อนร่วมทีมที่ได้รับมอบหมาย (หมุนเวียนกันในทีม 10 คน)
- ใช้ `modules/<module>/<feature>/review/qa-checklist.md` ตรวจทีละข้อ
- ถ้ามี AI ช่วยตรวจก่อน (Design QA Agent) ให้รันตาม prompt ท้าย `qa-checklist.md` แล้วให้คนยืนยันผลอีกที — **AI ตรวจอย่างเดียวไม่นับเป็น approve** ต้องมีคนเซ็นชื่อรับผิดชอบ
- ผลตรวจ 3 แบบ: **Approved** / **Rejected — ต้องแก้ไข** / **Approved with comments**

## 4. หลัง Approve

1. Merge PR เข้า `main`
2. คัดลอก `index.html` ไปที่ `approved-mockups/<module>/<feature>/index.html`
3. เปิดไฟล์ ถ่าย screenshot → บันทึกที่ `screenshots/approved-mockups/<module>-<feature>-YYYYMMDD.png`
4. เพิ่มแถวใหม่ใน `approved-mockups/INDEX.md`
5. Commit แยก: `git commit -m "approve(<module>): <feature> mockup v1"`

## 5. ถ้าอยากเสนอ Component/Pattern ใหม่เข้า Design System กลาง

ห้ามเพิ่มไฟล์ใน `design-system/components/` หรือ `design-system/patterns/` เองโดยไม่ผ่านทีม:

1. เปิด PR แยกต่างหาก แตะเฉพาะไฟล์ใน `design-system/`
2. อธิบายเหตุผลว่าทำไมของเดิมไม่พอ (อ้างอิงจาก mockup ไหนที่ต้องใช้)
3. นำเสนอในที่ประชุม weekly design sync ให้ทีมเห็นชอบก่อน merge
4. เมื่อ merge แล้ว อัปเดต `design-system/components/README.md` หรือ `design-system/patterns/README.md` ทันที

## 6. Branch Protection (แนะนำให้ตั้งค่าใน GitHub)

- `main` ต้อง require PR review อย่างน้อย 1 คนก่อน merge
- ห้าม push ตรงเข้า `main`
- เปิด CODEOWNERS ให้ path `design-system/**` ต้องผ่าน Design QA Lead เท่านั้น
