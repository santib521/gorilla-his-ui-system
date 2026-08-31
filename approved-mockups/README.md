# approved-mockups/ — Source of Truth ของ UI ที่ผ่าน QA แล้ว

โฟลเดอร์นี้เก็บเฉพาะ mockup ที่ผ่านขั้นตอน QA ใน `modules/<module>/<feature>/review/qa-checklist.md` แล้วเท่านั้น (สถานะ Approved)

## กฎสำคัญ
- **ห้าม**ก็อปไฟล์เข้ามาโดยตรงโดยไม่ผ่าน QA — ทุกไฟล์ในนี้คือ "ของจริง" ที่ทีม Dev และทีม Mockup คนอื่นจะอ้างอิงเป็น pattern
- โครงสร้างโฟลเดอร์เหมือน `modules/` คือ `approved-mockups/<module>/<feature>/index.html`
- ทุกครั้งที่ approve feature ใหม่ ต้องอัปเดต [`INDEX.md`](./INDEX.md) ด้วย

## ขั้นตอนการย้ายไฟล์เข้ามา (ทำโดยผู้ approve เท่านั้น)

1. คัดลอก `modules/<module>/<feature>/index.html` มาวางที่ `approved-mockups/<module>/<feature>/index.html`
2. เปิดไฟล์ด้วยเบราว์เซอร์ ถ่าย screenshot เต็มหน้าจอ → บันทึกที่ `../screenshots/approved-mockups/<module>-<feature>-YYYYMMDD.png`
3. เพิ่มแถวใหม่ใน `INDEX.md`
4. Commit message: `approve(<module>): <feature> mockup vX`
