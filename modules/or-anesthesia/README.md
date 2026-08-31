# Module: OR / ANESTHESIA (ห้องผ่าตัด/วิสัญญี)

เพิ่มเข้าระบบหลัง Visual Audit — ยืนยันว่าเป็น module จริงจากภาพหน้าจอ `21 OR Worklist.jpg`, `06-doctor-screen_Dashboard01.jpg` (OR Team Dashboard), `19 Anes record.jpg`, และ `17Graphic sheet.jpg` (Critical Care Flowsheet) ใน `../../screenshots/actual-gorilla-his/`

## บริบทธุรกิจ
จัดการคิวผ่าตัด ตั้งแต่รับคำขอผ่าตัด (OR Request) จัดตารางห้องผ่าตัด/ทีม บันทึกข้อมูลระหว่างดมยาสลบ (Anesthesia Record) จนถึงติดตามสัญญาณชีพผู้ป่วยวิกฤตหลังผ่าตัด (Critical Care Flowsheet)

## Flow หลักที่ต้องเข้าใจก่อนออกแบบ mockup
1. แพทย์เจ้าของไข้ส่ง **OR Request** (สั่งผ่าตัด) เข้าระบบ พร้อมระบุหัตถการ/ความเร่งด่วน
2. เจ้าหน้าที่ OR จัดคิวใน **Theatre WorkList** — เลือกห้องผ่าตัด, ทีมแพทย์/พยาบาล/วิสัญญีแพทย์, เวลา
3. หน้า **Team Dashboard** แสดงภาพรวมงานวันนี้ทั้งทีม (ใช้ stat-card row — ดู pattern `dashboard-home.md`)
4. วิสัญญีแพทย์บันทึก **Anesthesia Record** ระหว่างผ่าตัด — ชนิดยาสลบ, ปริมาณ, เวลาให้ยา, สัญญาณชีพระหว่างผ่าตัดแบบต่อเนื่อง
5. หลังผ่าตัด ติดตามผู้ป่วยด้วย **Critical Care Flowsheet** — กราฟ time-series ของสัญญาณชีพ (ยังไม่มี component รองรับ ดู `../../design-system/design-rules.md` § 0)

## ผู้ใช้งานหลัก
ศัลยแพทย์, วิสัญญีแพทย์, พยาบาลห้องผ่าตัด, เจ้าหน้าที่จัดตารางห้องผ่าตัด

## สิ่งที่ต้องระวังเป็นพิเศษ
- เวลาเป็นข้อมูลวิกฤต — ทุก event ใน Anesthesia Record ต้อง timestamp ชัดเจน ห้ามให้แก้ย้อนหลังแบบไม่มีร่องรอย (audit trail)
- สัญญาณชีพผิดปกติระหว่าง/หลังผ่าตัดต้องเด่นชัดทันที ใช้ `--color-status-critical` ไม่ปนกับสีอื่น
- ตารางห้องผ่าตัดชนกัน (double-booking) ต้องมี validation/warning ชัดเจนก่อนบันทึก
- กราฟ time-series ของสัญญาณชีพ (Critical Care Flowsheet) เป็น**ช่องว่าง component ที่ยังไม่มีของจริงให้ใช้** — ถ้าต้องทำ feature ที่ต้องใช้กราฟนี้ ให้ยกเข้าที่ประชุม weekly design sync ก่อนเริ่ม อย่าออกแบบเองโดยไม่ปรึกษา

## Pattern ที่มักใช้
- `dashboard-home.md` — หน้า Team Dashboard
- `order-entry.md` — OR Request
- `approval-confirmation.md` — ยืนยันตารางผ่าตัด/ยกเลิกคิว

## Feature ที่มีอยู่แล้ว
ดูรายการที่ approve แล้วที่ `../../approved-mockups/INDEX.md`
