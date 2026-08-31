# Gorilla HIS — Blueprint Quality Gate v1.0

Purpose: ตรวจว่า Application Blueprint พร้อมส่งเข้า UI Factory หรือยัง โดยไม่บังคับให้ Requirement ต้องสมบูรณ์ 100%

## Gate 1 — Source Truth
- [ ] ระบุข้อมูลจาก Hospital/User จริง
- [ ] แยกสิ่งที่ Confirm แล้วออกจาก TBD
- [ ] ไม่มี Requirement ที่ AI แต่งขึ้นเอง

**FAIL:** พบ invented business requirement

## Gate 2 — User & Permission
- [ ] ระบุผู้ใช้งานหลัก
- [ ] ระบุสิทธิ์/ข้อจำกัดสำคัญที่ทราบ
- [ ] Permission ที่ยังไม่ชัดถูกทำเครื่องหมาย TBD

## Gate 3 — Main Workflow
- [ ] มี Start และ End ของ Main Workflow
- [ ] Actor และ handoff สำคัญพอเข้าใจ
- [ ] จุด Approve/Reject/Confirm ที่ User ระบุถูกเก็บไว้

**FAIL:** ไม่สามารถอธิบาย Main Workflow ได้โดยไม่เดา

## Gate 4 — Business Rules
- [ ] กฎสำคัญถูกแยกจาก Function
- [ ] Calculation/Permission/Approval/Lock ที่ทราบถูกระบุ
- [ ] สูตรหรือ Threshold ที่ไม่ทราบไม่ถูก AI สร้างเอง

## Gate 5 — Functions & Information
- [ ] แตก Core Functions จาก Requirement ที่มี
- [ ] ระบุข้อมูลหลักที่ User ต้องเห็น/บันทึก
- [ ] ระบุ Integration ที่ User กล่าวถึง

## Gate 6 — States & Outcomes
- [ ] ระบุ State ที่ Source รองรับ
- [ ] State ที่จำเป็นแต่ไม่ทราบเป็น TBD
- [ ] Output/Report ที่ User ต้องการถูกระบุ

## Gate 7 — Gap Analysis
- [ ] ความขัดแย้งถูกชี้ออกมา
- [ ] Missing information ที่กระทบ Workflow/Business Rule ถูกระบุ
- [ ] คำถามกลับ Hospital สั้น ชัด และถามเฉพาะสิ่งจำเป็น
- [ ] ไม่ถามสิ่งที่ตอบได้จาก Raw Requirement อยู่แล้ว

## Gate 8 — Traceability
- [ ] มี FN-xx
- [ ] มี REQ-xx
- [ ] มี BR-xx เมื่อมี Business Rule
- [ ] มี AC-xx ที่ผูกกับ Requirement/Rule สำคัญ

## Readiness Decision

### DRAFT
ข้อมูลยังไม่พอสร้าง Main Workflow ที่น่าเชื่อถือ

### WAITING FOR CONFIRMATION
โครงสร้างหลักชัด แต่มี Blocking TBD ที่ต้องถาม Hospital ก่อนทำ Mockup

### READY FOR UI FACTORY
สามารถสร้าง Main Workflow และ Critical Workflow ใน Mockup ได้โดยไม่ invent Business Requirement

> READY ไม่ได้หมายถึง Requirement สมบูรณ์ 100% แต่หมายถึงสิ่งที่ยังไม่รู้ไม่ทำให้ AI ต้องเดาเรื่องสำคัญ

## Hard Reject
Blueprint ต้องไม่เข้า UI Factory เมื่อ:
1. Main Workflow ต้องอาศัยการเดา
2. Permission/Approval สำคัญขัดกันและยังไม่ Confirm
3. AI เติม clinical/business rule เพื่อทำให้ระบบดูสมบูรณ์
4. Critical requirement ไม่มี traceability
5. Blocking TBD ถูกซ่อนหรือเปลี่ยนเป็น assumption