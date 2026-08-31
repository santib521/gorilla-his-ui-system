# _feature-template/

**ห้ามลบโฟลเดอร์นี้ — นี่คือต้นแบบสำหรับทุก feature ใหม่**

## วิธีใช้
1. Copy ทั้งโฟลเดอร์นี้ → วางที่ `modules/<module>/<feature-kebab-case>/`
2. แก้ไข 4 ไฟล์ข้างในตามลำดับ:
   - `feature-spec.md` — (แนะนำให้ทำก่อน) สเปกเชิงธุรกิจ/ฟังก์ชัน — PM/BA หรือผู้ทำ mockup กรอกเองก็ได้
   - `prompt-used.md` — paste prompt ที่กรอกครบจาก `../../MOCKUP_PROMPT_TEMPLATE.md` (ใช้เนื้อหาจาก feature-spec.md เป็น input)
   - `index.html` — แทนที่ด้วย mockup จริงที่ AI สร้างให้
   - `review/qa-checklist.md` — ให้ผู้ตรวจ (peer/Design QA Lead) ติ๊กผลก่อน merge
3. ลบไฟล์ `README.md` นี้ออกจากโฟลเดอร์ feature จริง (ไม่ต้องเก็บไว้)
