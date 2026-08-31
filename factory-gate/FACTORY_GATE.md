# Gorilla HIS UI Factory Gate

Factory Gate เป็นด่านบังคับสำหรับ Mockup ทุกงาน เพื่อให้ผลลัพธ์จาก Claude, Gemini, GPT หรือ AI อื่นมีภาษา UI เดียวกัน โดย **Factory Gate ห้ามลดทอนกฎใน `AI_INSTRUCTIONS.md`** หากข้อความขัดกัน ให้ `AI_INSTRUCTIONS.md` มีอำนาจสูงสุดเสมอ

## Authority

### Business Authority
1. Application Blueprint (Business Source of Truth)
2. Workflow / Requirement / Function List / Business Rules ที่สกัดจาก Blueprint

> ถ้า Blueprint ไม่มีข้อมูลบางประเภท ให้ระบุ `N/A — not present in Blueprint` ห้าม AI แต่ง Business Rule ขึ้นเองเพื่อให้ checklist ครบ

### Design Authority
1. `AI_INSTRUCTIONS.md`
2. `design-system/design-rules.md`, `ux-rules.md`, `tokens.css`
3. Approved Components
4. Approved Patterns
5. Gold Standard ใน `approved-mockups/`
6. `screenshots/actual-gorilla-his/`
7. Proposed New Pattern
8. AI design judgment

Blueprint บอกว่า "ระบบต้องทำอะไร" ส่วน Factory บอกว่า "Gorilla HIS ต้องแสดงและทำงานอย่างไร"

## Gate Flow

`Application Blueprint → Pre-Build Gate → Builder → Builder Self-QA → Post-Build Gate → Independent QA Agent → Human Review → Approved → Gold Standard (เมื่อถูก Promote)`

- Pre-Build FAIL = STOP ห้าม Generate
- Builder Self-QA FAIL = Builder แก้ก่อนส่ง Post-Build Gate
- Post-Build FAIL = RETURN TO BUILDER
- QA FAIL = RETURN TO BUILDER
- Human Approved = Approved Mockup; **ยังไม่เป็น Gold Standard จนกว่าจะ Promote ตาม `approved-mockups/GOLD_STANDARD.md`**

## Hard Reject

ให้ Reject ทันทีเมื่อพบอย่างใดอย่างหนึ่ง:
- ไม่ได้อ่าน Application Blueprint ที่เป็น input ของงาน
- ไม่ได้อ่าน source ที่ `AI_INSTRUCTIONS.md` บังคับ
- External CDN / external font / external JS/CSS
- สร้าง design language ใหม่แทน Gorilla HIS
- Hardcode **สี, spacing, font size, radius, shadow หรือ design value ที่ `tokens.css` ครอบคลุมอยู่แล้ว** แทนการใช้ token
- มี Main Workflow หรือ Critical Requirement จาก Blueprint หาย
- Dead button ใน Main Workflow
- JavaScript error ที่กระทบ Main Workflow
- ใช้ข้อมูลผู้ป่วยจริง
- New reusable UI pattern แต่ไม่ Declare `Proposed New Pattern`
- ไม่ทำ Builder Self-QA ตาม `modules/_feature-template/review/qa-checklist.md`

## Reference Availability Rule

- `approved-mockups/` หรือ screenshot จริงอาจยังไม่มีตัวที่เกี่ยวข้องกับงานนั้นได้ ให้ระบุ `N/A — no relevant reference found`; **ไม่ถือว่า Pre-Build FAIL เพียงเพราะไม่มี reference**
- แต่ถ้ามี relevant approved pattern/component/reference แล้ว Builder ไม่ตรวจหรือเลือกละเลยโดยไม่มีเหตุผล ให้ FAIL
- ถ้า AI tool ดู binary screenshot ไม่ได้ แต่เข้าถึง metadata/path ได้ ให้ระบุ limitation และใช้ design rules + approved HTML/reference ที่อ่านได้แทน; ห้ามเดารายละเอียดในภาพ

## Gold Standard Rule

ไฟล์ที่ผ่าน Factory Gate หรือ Human Approved ยังไม่ถือเป็น Gold Standard อัตโนมัติ ต้องผ่าน Promotion Criteria ใน `approved-mockups/GOLD_STANDARD.md` และถูกบันทึกใน `approved-mockups/INDEX.md` พร้อม version/status/reference
