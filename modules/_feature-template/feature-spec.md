# Feature Spec — <module>/<feature-name>

> ไฟล์นี้คือ**สเปกเชิงธุรกิจ/ฟังก์ชัน**ที่ควรกรอกโดย PM/BA/เจ้าของ module **ก่อน**ส่งงานให้ AI (คนละหน้าที่กับ `prompt-used.md` ซึ่งบันทึก prompt ที่ส่งจริง) — ถ้ายังไม่มี PM/BA แยก ผู้ทำ mockup กรอกเองได้ แต่แนะนำให้คิดให้ครบก่อนเริ่ม

## Module
[ชื่อ module]

## Users (ผู้ใช้งาน)
[บทบาทผู้ใช้ เช่น พยาบาลหน้าเคาน์เตอร์ OPD]

## Objective (วัตถุประสงค์ทางธุรกิจ)
[ทำไมต้องมี feature นี้ แก้ปัญหาอะไร]

## Main Workflow
```text
Step 1 → Step 2 → Step 3 → Result
```

## Functions (ฟังก์ชันที่ต้องมี)
1. [ฟังก์ชัน]
2. [ฟังก์ชัน]
3. [ฟังก์ชัน]

## Business Rules (กฎทางธุรกิจ/คลินิกที่ต้องยึด)
- [กฎ เช่น "ถ้าผู้ป่วยมีประวัติแพ้ยา ต้อง block การสั่งยากลุ่มนั้น"]

## Demo Scenarios (เคสที่ต้อง demo ได้)
- [เคสปกติ]
- [เคส edge case เช่น ค่าผิดปกติ/แพ้ยา/คิวเต็ม]

## Reused Components / Patterns
- [อ้างอิงไฟล์จาก design-system/components/ และ design-system/patterns/ ที่จะใช้]

## New Pattern Proposal (ถ้าจำเป็น)
เสนอเฉพาะกรณีที่ pattern/component เดิมแก้ปัญหานี้ไม่ได้จริง ๆ — อธิบายเหตุผล แล้วนำเข้าที่ประชุม weekly design sync ก่อน (ดู `WORKFLOW.md` § 5)

---

> กรอกไฟล์นี้เสร็จแล้ว ใช้เนื้อหาในนี้เป็น input หลักตอนกรอก `MOCKUP_PROMPT_TEMPLATE.md` (ที่ root ของ repo)
