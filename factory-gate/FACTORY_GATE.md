# Gorilla HIS UI Factory Gate

Factory Gate เป็นด่านบังคับสำหรับ Mockup ทุกงาน เพื่อให้ผลลัพธ์จาก Claude, Gemini, GPT หรือ AI อื่นมีภาษา UI เดียวกัน

## Authority

### Business Authority
1. Application Blueprint
2. Workflow / Requirement / Function List / Business Rules ที่สกัดจาก Blueprint

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

`Application Blueprint → Pre-Build Gate → Builder → index.html → Post-Build Gate → QA Agent → Human Review → Approved/Gold Standard`

- Pre-Build FAIL = STOP ห้าม Generate
- Post-Build FAIL = RETURN TO BUILDER
- QA FAIL = RETURN TO BUILDER
- เฉพาะ Human Approved เท่านั้นจึง Promote เข้า `approved-mockups/`

## Hard Reject

ให้ Reject ทันทีเมื่อพบอย่างใดอย่างหนึ่ง:
- ไม่ได้อ่าน Application Blueprint
- ไม่ได้อ่านกฎกลางของ repo
- External CDN / external font / external JS/CSS
- สร้าง design language ใหม่แทน Gorilla HIS
- Hardcode design value โดยไม่มีเหตุผลและไม่ผ่าน token system
- มี Main Workflow หรือ Critical Requirement หาย
- Dead button ใน Main Workflow
- JavaScript error ที่กระทบ Main Workflow
- ใช้ข้อมูลผู้ป่วยจริง
- New reusable UI pattern แต่ไม่ Declare `Proposed New Pattern`

## Gold Standard Rule

ไฟล์ที่ผ่าน Factory Gate ยังไม่ถือเป็น Gold Standard อัตโนมัติ ต้องผ่าน QA และ Human Review ก่อน และต้องถูกบันทึกใน `approved-mockups/INDEX.md` พร้อม version/status/reference.
