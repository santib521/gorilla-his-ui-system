# modules/ — Directory สำหรับ "สร้าง Mockup" (1.1)

โฟลเดอร์นี้คือที่ที่ mockup ของ**ทุก feature ใหม่**ถูกสร้างขึ้น แยกตาม module ทางธุรกิจของ HIS (OPD, LAB, PHARMACY, ...)

## โครงสร้างมาตรฐานต่อ 1 feature

```
modules/<module>/<feature-kebab-case>/
├── feature-spec.md      ← สเปกเชิงธุรกิจ/ฟังก์ชัน (PM/BA กรอก หรือผู้ทำ mockup กรอกเอง)
├── prompt-used.md      ← พรอมป์ที่ใช้จริง (กรอกจาก MOCKUP_PROMPT_TEMPLATE.md)
├── index.html           ← mockup ไฟล์เดียว (HTML+CSS+JS+Mock Data)
└── review/              ← ที่นี่คือ Directory สำหรับ "ตรวจสอบ mockup" (1.2)
    └── qa-checklist.md  ← QA ติ๊กผลตรงนี้ก่อนจะถูก approve
```

## วิธีเริ่ม feature ใหม่ (สำหรับทีม Mockup ทั้ง 10 คน)

1. Copy โฟลเดอร์ `_feature-template/` ทั้งโฟลเดอร์ → เปลี่ยนชื่อเป็น `modules/<module>/<feature-kebab-case>/`
2. กรอก `feature-spec.md` ให้ครบก่อน (ถ้ามี PM/BA ให้ช่วยกรอก)
3. เปิด `MOCKUP_PROMPT_TEMPLATE.md` (ที่ root ของ repo) กรอกให้ครบโดยอ้างอิงจาก `feature-spec.md` แล้ว paste ผลลงใน `prompt-used.md` ของ feature นั้น
4. ส่ง prompt ให้ AI (Claude/Gemini) → ได้ `index.html` มาทับไฟล์ template
5. รัน self-QA ตาม `review/qa-checklist.md` ก่อนเปิด PR (ดู `../WORKFLOW.md`)

## กฎสำคัญ

**ห้ามสร้าง Design System เฉพาะของ module ตัวเอง** — ทุก module ใช้ `design-system/` ชุดเดียวกันทั้งหมด (สี, ฟอนต์, component, pattern) ต่างกันแค่ "ธุรกิจ/ข้อมูล/workflow" ที่อยู่ใน README ของแต่ละ module เท่านั้น

## Module ปัจจุบัน (11 module)

| Module | โฟลเดอร์ | บริบทธุรกิจ |
|---|---|---|
| เวชระเบียน/ลงทะเบียน | `registration/` | ลงทะเบียนผู้ป่วยใหม่/เก่า, สร้าง visit |
| ผู้ป่วยนอก | `opd/` | คิวตรวจ, ห้องตรวจแพทย์ |
| ผู้ป่วยใน | `ipd/` | ดูแลผู้ป่วย Admit ถึง Discharge |
| ห้องฉุกเฉิน | `er/` | Triage และรักษาเร่งด่วนตาม priority |
| เภสัชกรรม | `pharmacy/` | จ่ายยาตาม order, ตรวจสอบ drug interaction, คลังยา |
| ห้องปฏิบัติการ | `lab/` | รับ order ตรวจ, บันทึกผล, รายงานผล Lab |
| รังสีวิทยา | `radiology/` | รับ order ตรวจภาพ, นัดคิว, รังสีแพทย์อ่านผล |
| นัดหมาย | `appointment/` | จองนัด/เลื่อนนัด/จัดการตารางแพทย์ |
| ช่องทางผู้ป่วย | `patient-portal/` | ผู้ป่วยเข้าถึงข้อมูลตัวเอง (เว็บ/แอป) |
| ห้องผ่าตัด/วิสัญญี | `or-anesthesia/` | OR Request, Theatre WorkList, Anesthesia Record — เพิ่มหลัง Visual Audit |
| การเงิน/แคชเชียร์ | `billing/` | Billed WorkList, Cashier worklist, รับชำระเงิน — เพิ่มหลัง Visual Audit |

เพิ่ม module ใหม่: สร้างโฟลเดอร์ใหม่ใต้ `modules/`, เพิ่ม `README.md` อธิบายบริบทธุรกิจ, แจ้งทีมในที่ประชุม weekly sync
