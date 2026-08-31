# Gorilla HIS UI Factory Gate

Factory Gate เป็นด่านบังคับสำหรับ Mockup ทุกงาน เพื่อให้ผลลัพธ์จาก Claude, Gemini, GPT หรือ AI อื่นมีภาษา UI เดียวกัน โดย **Factory Gate ห้ามลดทอนกฎใน `AI_INSTRUCTIONS.md`** หากข้อความขัดกัน ให้ `AI_INSTRUCTIONS.md` มีอำนาจสูงสุดเสมอ

## Authority

### Business Authority
1. Application Blueprint (Business Source of Truth)
2. Workflow / Requirement / Function List / Business Rules ที่สกัดจาก Blueprint

> ถ้า Blueprint ไม่มีข้อมูลบางประเภท ให้ระบุ `N/A — not present in Blueprint` ห้าม AI แต่ง Business Rule ขึ้นเองเพื่อให้ checklist ครบ

### Design Authority
1. `AI_INSTRUCTIONS.md`
2. `design-system/design-rules.md`, `ux-rules.md`, `tokens.css`, `icon-rules.md`
3. Approved Components — สำหรับ desktop รวม locked structural reference `application-shell.html`
4. Approved Patterns
5. Gold Standard ใน `approved-mockups/`
6. `screenshots/actual-gorilla-his/`
7. Proposed New Pattern
8. AI design judgment

Blueprint บอกว่า "ระบบต้องทำอะไร" ส่วน Factory บอกว่า "Gorilla HIS ต้องแสดงและทำงานอย่างไร"

## Gate Flow

`Application Blueprint → Pre-Build Gate → Builder → Builder Self-QA → Post-Build Gate + Premium HIS Visual Gate → Independent QA Agent → Human Review → Approved → Gold Standard (เมื่อถูก Promote)`

- Pre-Build FAIL = STOP ห้าม Generate
- Builder Self-QA FAIL = Builder แก้ก่อนส่ง Post-Build Gate
- Post-Build FAIL = RETURN TO BUILDER
- Premium HIS Visual Gate FAIL ตามเกณฑ์ด้านล่าง = RETURN TO BUILDER
- QA FAIL = RETURN TO BUILDER
- Human Approved = Approved Mockup; **ยังไม่เป็น Gold Standard จนกว่าจะ Promote ตาม `approved-mockups/GOLD_STANDARD.md`**

## Hard Reject

ให้ Reject ทันทีเมื่อพบอย่างใดอย่างหนึ่ง:
- ไม่ได้อ่าน Application Blueprint ที่เป็น input ของงาน
- ไม่ได้อ่าน source ที่ `AI_INSTRUCTIONS.md` บังคับ
- External CDN / external font / external JS/CSS รวมถึง Font Awesome CDN/Kit ใน mockup
- สร้าง design language ใหม่แทน Gorilla HIS
- Hardcode **สี, spacing, font size, radius, shadow หรือ design value ที่ `tokens.css` ครอบคลุมอยู่แล้ว** แทนการใช้ token
- มี Main Workflow หรือ Critical Requirement จาก Blueprint หาย
- Dead button ใน Main Workflow
- JavaScript error ที่กระทบ Main Workflow
- ใช้ข้อมูลผู้ป่วยจริง
- New reusable UI pattern แต่ไม่ Declare `Proposed New Pattern`
- ไม่ทำ Builder Self-QA ตาม `modules/_feature-template/review/qa-checklist.md`
- Desktop module สร้าง application shell ใหม่แทน approved `application-shell.html` โดยไม่มี approved exception
- ใช้ Emoji เป็น UI icon/navigation/section decoration
- ใช้ custom SVG/icon ใหม่ทั้งที่มี approved Font Awesome semantic icon ตาม `design-system/icon-rules.md` โดยไม่มี approved exception
- Operational screen ใช้ AI/futuristic/marketing visual theme แทน Gorilla HIS visual language
- Semantic clinical colors ถูกใช้เป็น decoration หรือความหมายที่ขัดกับ `design-system/design-rules.md`

## Premium HIS Visual Gate — Mandatory

Visual Gate เป็น **ชั้นเพิ่มจาก Phase 1 Factory Gate** ไม่แทนที่ Hard Reject, Blueprint Traceability, Functional Gate หรือ Patient Safety rules เดิม

Builder Self-QA, Post-Build Gate และ Independent QA ต้องตรวจจาก rendered UI จริงเมื่อ tool รองรับ; ถ้า tool render ไม่ได้ ให้บันทึก limitation และส่ง Human/Visual QA ตรวจ ห้ามเดาว่า PASS จาก code อย่างเดียว

| Gate | Question | PASS condition |
|---|---|---|
| VG-01 Product Character | ดูเป็น Hospital Enterprise System หรือ generic SaaS/AI Dashboard? | Clinical / Operational / Trustworthy / Dense / Calm / Professional |
| VG-02 Application Shell | ใช้ approved shell หรือ approved exception? | Desktop shell structure consistent across modules |
| VG-03 Font Awesome Compliance | ใช้ icon language กลางหรือไม่? มี Emoji/custom icon/CDN หรือไม่? | Font Awesome semantic mapping ตาม `design-system/icon-rules.md`; default `fa-solid`; no Emoji UI; no custom SVG when approved FA icon exists; no external FA CDN/Kit in mockup |
| VG-04 Container Discipline | Card Everywhere หรือไม่? | Operational panels/tables/dividers/split layouts used as default when appropriate |
| VG-05 KPI Discipline | Operational KPI ใหญ่แบบ marketing/stat-card grid หรือไม่? | `enterprise-kpi-strip.html` considered/preferred for operational dashboard; stat-card remains valid for suitable Home/Executive summary |
| VG-06 Color Discipline | สีถูกใช้ตาม Design Rules หรือไม่? | Neutral-first; clinical semantic colors retain their strict meanings and are never decorative |
| VG-07 Density | 1366×768 เห็น key operational state เพียงพอหรือไม่? | Page context + summary + alert + main operational content + primary action visible when requirement/layout makes this feasible |
| VG-08 Typography/Scale | มี oversized heading/KPI/button หรือไม่? | Approved token scale; scan-first hierarchy |
| VG-09 AI Visual Theme | Feature AI ถูกทำเป็น futuristic theme หรือไม่? | AI presented as a capability inside Gorilla HIS visual language |

### Visual Gate Severity

- **VG-01, VG-02, VG-03, VG-06, VG-09 FAIL = P0 Design / Automatic FAIL** เมื่อเป็นการฝ่าฝืนชัดเจนและไม่มี approved exception
- **VG-04, VG-05, VG-07, VG-08 = P1** เมื่อทำให้ operational scanability หรือ Gorilla HIS consistency ลดลงอย่างมีนัยสำคัญ; QA ยกระดับเป็น P0 ได้เมื่อเป็น systematic design-language violation
- การไม่มี relevant operational KPI/panel ใน Blueprint ไม่ทำให้ VG-04/VG-05 FAIL; ใช้ `N/A` ได้พร้อมเหตุผล

## Reference Availability Rule

- `approved-mockups/` หรือ screenshot จริงอาจยังไม่มีตัวที่เกี่ยวข้องกับงานนั้นได้ ให้ระบุ `N/A — no relevant reference found`; **ไม่ถือว่า Pre-Build FAIL เพียงเพราะไม่มี reference**
- แต่ถ้ามี relevant approved pattern/component/reference แล้ว Builder ไม่ตรวจหรือเลือกละเลยโดยไม่มีเหตุผล ให้ FAIL
- ถ้า AI tool ดู binary screenshot ไม่ได้ แต่เข้าถึง metadata/path ได้ ให้ระบุ limitation และใช้ design rules + approved HTML/reference ที่อ่านได้แทน; ห้ามเดารายละเอียดในภาพ

## Gold Standard Rule

ไฟล์ที่ผ่าน Factory Gate หรือ Human Approved ยังไม่ถือเป็น Gold Standard อัตโนมัติ ต้องผ่าน Promotion Criteria ใน `approved-mockups/GOLD_STANDARD.md` และถูกบันทึกใน `approved-mockups/INDEX.md` พร้อม version/status/reference
