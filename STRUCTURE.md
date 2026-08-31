# STRUCTURE.md — คำอธิบายโครงสร้างทั้งหมดของ Repository

เอกสารนี้รวมคำอธิบาย**ทุกไฟล์ ทุกโฟลเดอร์**ใน `gorilla-his-ui-system/` ไว้ที่เดียว สำหรับคนที่เพิ่งเข้าโปรเจกต์และอยากเห็นภาพรวมเร็ว ๆ โดยไม่ต้องไล่เปิดทีละไฟล์ (README ย่อยในแต่ละโฟลเดอร์ยังคงอยู่ตามเดิม สำหรับรายละเอียดเชิงลึกของจุดนั้น ๆ)

---

## ผังโครงสร้างเต็ม

```
gorilla-his-ui-system/
│
├── AI_INSTRUCTIONS.md              ★ กติกาสำหรับ AI — อ่านก่อนเริ่มงานทุกครั้ง
├── MOCKUP_PROMPT_TEMPLATE.md       ★ Prompt กลางที่ทีมทั้ง 10 คนใช้เหมือนกัน
├── WORKFLOW.md                       Git branch / PR / QA gate process
├── README.md                         ภาพรวมโปรเจกต์ + quick start
├── STRUCTURE.md                      ไฟล์นี้ — คำอธิบายโครงสร้างทั้งหมด
├── .gitignore                        ไฟล์ที่ไม่ต้อง track ใน git
│
├── docs/
│   └── TEAM_ONBOARDING.md            แผนสอนงานทีม Mockup 10 คน (workshop + buddy system)
│
├── design-system/                  ★★ หัวใจของระบบ — กติกา + ชิ้นส่วน UI ที่ใช้ซ้ำได้
│   ├── design-rules.md               กฎเชิง "หน้าตา" (สี, layout, typography, accessibility)
│   ├── ux-rules.md                   กฎเชิง "พฤติกรรม" (action, worklist, drawer/modal, state)
│   ├── tokens.css                    ตัวแปร design ทั้งหมด (สี/spacing/font) — ใช้เท่านั้น ห้าม hardcode
│   ├── components/                   13 component พร้อมใช้งานจริง (เปิดดูได้ในเบราว์เซอร์)
│   │   ├── README.md                   ดัชนี + กฎการเพิ่ม component ใหม่
│   │   ├── buttons.html
│   │   ├── form-controls.html
│   │   ├── status-badges.html
│   │   ├── alert-banner.html
│   │   ├── patient-banner.html
│   │   ├── patient-search-bar.html
│   │   ├── vitals-form.html
│   │   ├── lab-result-table.html
│   │   ├── modal-dialog.html
│   │   ├── drawer.html
│   │   ├── worklist.html
│   │   ├── tabs.html
│   │   └── notification-toast.html
│   └── patterns/                     7 pattern ระดับหน้าจอ (โครง wireframe เชิงข้อความ)
│       ├── README.md                   ดัชนี + กฎการเพิ่ม pattern ใหม่
│       ├── list-detail-page.md
│       ├── search-and-table.md
│       ├── form-wizard.md
│       ├── order-entry.md
│       ├── result-review.md
│       ├── approval-confirmation.md
│       └── error-handling.md
│
├── screenshots/                     ภาพหน้าจอ 2 ประเภท (คนละจุดประสงค์กัน)
│   ├── README.md                      อธิบายความต่างของ 2 โฟลเดอร์ด้านล่าง
│   ├── actual-gorilla-his/            ภาพจอ "ของจริง" จากโปรดักชัน (sanitized) — สอน AI ให้รู้จักของจริง
│   │   └── README.md                    กฎการเบลอข้อมูลผู้ป่วย + ขั้นตอน Visual Audit
│   └── approved-mockups/              ภาพจอของ mockup ที่ผ่าน QA แล้ว (ยังว่าง รอ mockup แรก)
│
├── approved-mockups/                ★★ Source of Truth — mockup ที่ผ่าน QA แล้วเท่านั้น
│   ├── README.md                      ขั้นตอนย้ายไฟล์เข้ามาหลัง approve
│   ├── INDEX.md                       ตาราง registry: มี mockup อะไร approve ไปแล้วบ้าง
│   └── <module>/                      โฟลเดอร์ว่างของทั้ง 9 module รอ mockup แรกที่ approve
│       (registration, opd, ipd, er, pharmacy, lab, radiology, appointment, patient-portal)
│
└── modules/                         ★★ ที่ "สร้าง" mockup ใหม่ (แยกตาม module ธุรกิจ)
    ├── README.md                      ดัชนี 9 module + กฎ "ห้ามสร้าง design system เฉพาะ module"
    ├── _feature-template/             ต้นแบบสำหรับเริ่ม feature ใหม่ — copy ทั้งโฟลเดอร์นี้
    │   ├── README.md                    วิธีใช้ template นี้
    │   ├── feature-spec.md              สเปกเชิงธุรกิจ/ฟังก์ชัน (กรอกก่อนเริ่ม)
    │   ├── prompt-used.md               บันทึก prompt จริงที่ส่งให้ AI + Design Notes ที่ได้กลับมา
    │   ├── index.html                   Mockup ไฟล์เดียว (placeholder รอถูกแทนที่)
    │   └── review/
    │       └── qa-checklist.md          ★ จุดตรวจสอบ mockup ก่อน approve (มี prompt สำหรับ Design QA Agent ด้วย)
    ├── registration/README.md          บริบทธุรกิจ: ลงทะเบียนผู้ป่วยใหม่/เก่า
    ├── opd/README.md                   บริบทธุรกิจ: ผู้ป่วยนอก
    ├── ipd/README.md                   บริบทธุรกิจ: ผู้ป่วยใน
    ├── er/README.md                    บริบทธุรกิจ: ห้องฉุกเฉิน
    ├── pharmacy/README.md              บริบทธุรกิจ: เภสัชกรรม
    ├── lab/README.md                   บริบทธุรกิจ: ห้องปฏิบัติการ
    ├── radiology/README.md             บริบทธุรกิจ: รังสีวิทยา
    ├── appointment/README.md           บริบทธุรกิจ: นัดหมาย
    └── patient-portal/README.md        บริบทธุรกิจ: ช่องทางผู้ป่วย
```

---

## 1. ไฟล์ระดับ Root (5 ไฟล์)

| ไฟล์ | คืออะไร | ใครอ่าน/ใช้ | อ่านตอนไหน |
|---|---|---|---|
| `AI_INSTRUCTIONS.md` | "รัฐธรรมนูญ" ของระบบ — ลำดับการอ่านไฟล์บังคับ, กฎเหล็ก 11 ข้อ, ขั้นตอนการทำงาน, รูปแบบ Design Notes, Definition of Done | AI (Claude/Gemini) + คนในทีม | ครั้งแรกที่เข้าร่วมทีม และให้ AI อ่านทุกครั้งก่อนเริ่มงาน |
| `MOCKUP_PROMPT_TEMPLATE.md` | Prompt สำเร็จรูปที่กรอกช่องว่างแล้วส่งให้ AI ได้เลย | ทีม Mockup ทั้ง 10 คน | ทุกครั้งที่เริ่ม feature ใหม่ |
| `WORKFLOW.md` | ขั้นตอน Git จริง: ตั้งชื่อ branch, เปิด PR, QA gate, merge, การเสนอ component/pattern ใหม่ | ทีม Mockup + Design QA Lead | ตอนเปิด branch/PR |
| `README.md` | หน้าแรกของ repo — ภาพรวม, สถาปัตยกรรม, quick start, FAQ | ทุกคน | จุดแรกที่เปิด repo |
| `STRUCTURE.md` | ไฟล์นี้ — สรุปทุกไฟล์ทุกโฟลเดอร์ไว้ที่เดียว | คนใหม่ที่อยากเห็นภาพรวมเร็ว | ตอนปฐมนิเทศ |

---

## 2. `docs/` — เอกสารสำหรับทีม

| ไฟล์ | คืออะไร |
|---|---|
| `TEAM_ONBOARDING.md` | แผนสอนงานแบบ step-by-step: workshop ครึ่งวัน 5 session, buddy system 2 สัปดาห์แรก, weekly design sync, checklist ความพร้อมของคนใหม่ |

---

## 3. `design-system/` — หัวใจของระบบ (ห้ามให้ module ไหนสร้างของตัวเอง)

### 3.1 ไฟล์กติกา 2 ไฟล์ (แยกเรื่องภาพ vs พฤติกรรม)

| ไฟล์ | ครอบคลุมเรื่องอะไร |
|---|---|
| `design-rules.md` | Product character, layout/grid, typography, **semantic color** (สีไหนหมายถึงอะไร ห้ามใช้ผิด), accessibility, clinical data rules (ช่วงค่าปกติทางการแพทย์), naming convention, Do/Don't |
| `ux-rules.md` | Core UX principles (แสดง context/state/next-action เสมอ), กฎเรื่อง action (primary เดียว/destructive ต้องยืนยัน), worklist, เมื่อไหร่ใช้ drawer vs modal vs เต็มหน้า, 6 states (Normal/Loading/Empty/Error/Success/Disabled), consistency |

### 3.2 `tokens.css` — ตัวแปร design ทั้งหมด

ไฟล์ CSS เดียวที่มี design tokens ทุกตัว: สี (primitive + semantic เช่น `--color-status-critical`), typography scale, spacing scale, radius/shadow, z-index, breakpoint — **ต้อง copy ทั้งไฟล์ไปฝังใน `<style>` ของทุก mockup**

### 3.3 `components/` — 13 component ใช้งานได้จริง

แต่ละไฟล์เปิดในเบราว์เซอร์ได้ตรง ๆ เพื่อดู preview จริง (ไม่ใช่แค่ภาพนิ่ง)

| Component | ใช้ทำอะไร |
|---|---|
| `buttons.html` | ปุ่ม primary/secondary/danger/critical/icon พร้อม state |
| `form-controls.html` | input/select/checkbox/radio/textarea พร้อม state error/disabled |
| `status-badges.html` | ป้ายสถานะ (นัดหมาย, lab flag, priority) ตาม semantic color |
| `alert-banner.html` | แบนเนอร์เตือนเต็มความกว้าง สงวนไว้สำหรับ patient-safety critical เท่านั้น |
| `patient-banner.html` | แถบข้อมูลผู้ป่วยด้านบนจอ (HN/ชื่อ/อายุ/เตียง) |
| `patient-search-bar.html` | ค้นหาผู้ป่วยด้วย HN/ชื่อ พร้อม autocomplete แบบ mock |
| `vitals-form.html` | ฟอร์มสัญญาณชีพ ไฮไลต์ค่าผิดปกติอัตโนมัติตามช่วงอ้างอิง |
| `lab-result-table.html` | ตารางผล Lab พร้อม flag สูง/ต่ำ/วิกฤต, sort/filter แบบ mock |
| `modal-dialog.html` | หน้าต่างยืนยัน action / ฟอร์มสั้น ๆ |
| `drawer.html` | แผงเลื่อนจากขอบจอ สำหรับงานสั้นที่มีบริบทเดียว |
| `worklist.html` | คิวงานที่ต้องดำเนินการต่อ พร้อม action ต่อแถว (ต่างจากตารางแสดงผลอย่างเดียว) |
| `tabs.html` | สลับดูเนื้อหาหลายหมวดในหน้าเดียว |
| `notification-toast.html` | แจ้งผล action ชั่วคราว (Success/Error/Info ทั่วไป) |

`README.md` ในโฟลเดอร์นี้คือดัชนีตารางเดียวกันนี้ + กฎว่าจะเพิ่ม component ใหม่ต้องผ่านที่ประชุม weekly sync ก่อน

### 3.4 `patterns/` — 7 pattern ระดับหน้าจอ

โครง wireframe เชิงข้อความที่ประกอบจากหลาย component (ไม่ใช่ไฟล์ HTML รันได้)

| Pattern | ใช้เมื่อไหร่ |
|---|---|
| `list-detail-page.md` | รายการทางซ้าย + รายละเอียดทางขวา |
| `search-and-table.md` | ค้นหา/กรอง แล้วแสดงผลเป็นตาราง |
| `form-wizard.md` | กรอกข้อมูลหลายขั้นตอนต่อเนื่อง |
| `order-entry.md` | สั่งบางอย่างเข้าระบบให้ module อื่นดำเนินการต่อ |
| `result-review.md` | ตรวจทานผลก่อนรับรอง/ส่งต่ออย่างเป็นทางการ |
| `approval-confirmation.md` | ยืนยัน action ที่มีผลกระทบสำคัญ (3 ระดับความเข้ม) |
| `error-handling.md` | ออกแบบ error/failure state ให้ครบทุกจุด |

---

## 4. `screenshots/` — ภาพ 2 ประเภท อย่าปนกัน

| โฟลเดอร์ | เก็บอะไร | สถานะตอนนี้ |
|---|---|---|
| `actual-gorilla-his/` | ภาพหน้าจอ**ของจริง**จากระบบที่ใช้งานอยู่ในโรงพยาบาล (ต้องเบลอข้อมูลผู้ป่วยก่อน) ใช้สอน AI ให้รู้จักหน้าตาจริงของผลิตภัณฑ์ | ยังว่าง — รอภาพจริงจากทีม |
| `approved-mockups/` | ภาพหน้าจอของ mockup ที่ approve แล้ว ใช้ดูภาพรวมเร็ว ๆ ไม่ต้องเปิดไฟล์ HTML | ยังว่าง — รอ mockup แรกที่ approve |

---

## 5. `approved-mockups/` — Source of Truth (⭐ สำคัญที่สุด)

โฟลเดอร์นี้เก็บเฉพาะ mockup ที่ผ่าน QA แล้วเท่านั้น มีโฟลเดอร์ย่อยของทั้ง 9 module รอไว้ (ตอนนี้ว่างเปล่า เพราะยังไม่มี mockup ไหน approve) พร้อม:

- `README.md` — ขั้นตอนย้ายไฟล์เข้ามาหลัง approve (copy → ถ่าย screenshot → อัปเดต INDEX.md)
- `INDEX.md` — ตาราง registry ว่ามี mockup อะไร approve ไปแล้วบ้าง module/feature ไหน ใครอนุมัติ วันที่เท่าไหร่ — **AI ต้องเช็คไฟล์นี้ก่อนเริ่มงานใหม่ทุกครั้ง**

---

## 6. `modules/` — ที่ "สร้าง" mockup ใหม่ทั้งหมด

`README.md` เป็นดัชนีของทั้ง 9 module พร้อมกฎ **"ห้ามสร้าง Design System เฉพาะของ module ตัวเอง"**

### 6.1 `_feature-template/` — ต้นแบบที่ต้อง copy ทุกครั้งที่เริ่ม feature ใหม่

| ไฟล์ | ใช้ทำอะไร | ใครกรอก |
|---|---|---|
| `README.md` | อธิบายวิธีใช้ template (ลบทิ้งได้เมื่อเริ่มงานจริง) | - |
| `feature-spec.md` | สเปกเชิงธุรกิจ/ฟังก์ชัน: users, objective, workflow, business rules, demo scenarios | PM/BA หรือผู้ทำ mockup เอง (กรอกก่อนสุด) |
| `prompt-used.md` | บันทึก prompt จริงที่ส่งให้ AI + Design Notes ที่ AI ตอบกลับมา (traceability) | ผู้ทำ mockup |
| `index.html` | Mockup ไฟล์เดียว — placeholder ที่รอ AI แทนที่ด้วยของจริง | AI (Claude/Gemini) |
| `review/qa-checklist.md` | จุดตรวจสอบก่อน approve — 6 หมวด + prompt สำหรับ "Design QA Agent" | Peer/Design QA Lead |

### 6.2 โฟลเดอร์ทั้ง 9 module (แต่ละอันมีแค่ README.md บริบทธุรกิจ รอ feature จริง)

| Module | บริบทธุรกิจโดยย่อ |
|---|---|
| `registration/` | ลงทะเบียนผู้ป่วยใหม่/เก่า, สร้าง visit |
| `opd/` | ผู้ป่วยนอก: คิวตรวจ, ห้องตรวจแพทย์ |
| `ipd/` | ผู้ป่วยใน: Admission ถึง Discharge |
| `er/` | ห้องฉุกเฉิน: Triage และรักษาตาม priority |
| `pharmacy/` | จ่ายยา, ตรวจสอบ drug interaction, คลังยา |
| `lab/` | รับ order ตรวจ, บันทึก/รายงานผล Lab |
| `radiology/` | รับ order ตรวจภาพ, นัดคิว, อ่านผล |
| `appointment/` | จองนัด/เลื่อนนัด/จัดการตารางแพทย์ |
| `patient-portal/` | ช่องทางที่ผู้ป่วยเข้าถึงข้อมูลตัวเอง |

เมื่อจะเริ่มงานจริงในแต่ละ module: **copy `_feature-template/` ทั้งโฟลเดอร์ไปวางเป็น `modules/<module>/<feature-kebab-case>/`**

---

## 7. เส้นทางของ mockup หนึ่งชิ้น (สรุปทุกไฟล์ที่เกี่ยวข้องตามลำดับ)

```
1. อ่าน AI_INSTRUCTIONS.md, design-rules.md, ux-rules.md, tokens.css,
   design-system/components/, design-system/patterns/, modules/<module>/README.md,
   approved-mockups/INDEX.md
        ↓
2. Copy modules/_feature-template/ → modules/<module>/<feature>/
        ↓
3. กรอก feature-spec.md
        ↓
4. กรอก MOCKUP_PROMPT_TEMPLATE.md (อ้างอิง feature-spec.md) → ส่งให้ AI
        ↓
5. ได้ index.html + Design Notes → บันทึกลง prompt-used.md
        ↓
6. Self-QA ตาม modules/<module>/<feature>/review/qa-checklist.md
        ↓
7. เปิด PR ตาม WORKFLOW.md → Design QA Lead ตรวจด้วย checklist เดียวกัน
        ↓
8. Approved → copy index.html ไป approved-mockups/<module>/<feature>/
   → ถ่าย screenshot ไป screenshots/approved-mockups/
   → เพิ่มแถวใน approved-mockups/INDEX.md
```

---

## 8. สรุปตัวเลข

- ไฟล์ทั้งหมด: **60 ไฟล์**
- Component พร้อมใช้: **13**
- Pattern: **7**
- Module: **9**
- เอกสารกติกาหลัก: **2** (design-rules.md แยกจาก ux-rules.md)
