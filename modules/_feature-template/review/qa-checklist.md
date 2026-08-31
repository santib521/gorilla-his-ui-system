# QA Checklist — Directory สำหรับ "ตรวจสอบ Mockup" (1.2)

**Feature:** << module/feature-name >>
**ผู้ตรวจ (Design QA Agent หรือ Design QA Lead/Human):** << ชื่อ >>
**วันที่ตรวจ:** << YYYY-MM-DD >>
**ผลตรวจโดยรวม:** ⬜ Approved ⬜ Rejected — ต้องแก้ไข ⬜ Approved with comments

> ใช้ checklist นี้ทั้งแบบ **Human review** และแบบ **AI Design QA Agent** (ป้อน prompt ด้านล่างสุดของไฟล์นี้ให้ AI ตรวจแทนคน แล้วให้คนยืนยันผลอีกที)

## 1. Compliance กับกฎเหล็ก (AI_INSTRUCTIONS.md § 2)

- [ ] เป็นไฟล์ `index.html` ไฟล์เดียว ไม่มีไฟล์ `.css`/`.js` แยก
- [ ] ไม่มีการเรียก CDN ภายนอกใด ๆ (เปิดแบบ offline/ตัดเน็ตแล้วยังใช้งานได้ครบ)
- [ ] ไม่มีค่าสี/spacing hardcode ที่ไม่ได้มาจาก `tokens.css` (ตรวจแบบสุ่ม inspect element)
- [ ] มี header comment ครบตามรูปแบบ (module, feature, author, date, based-on, version)
- [ ] ไม่เชื่อมต่อ API จริงหรือส่งข้อมูลออกภายนอก

## 2. Component & Pattern Reuse (design-rules.md § 5)

- [ ] Component ที่มีอยู่แล้วถูกนำมาใช้จริง (เทียบกับ `Design Notes` ที่แนบมา)
- [ ] ถ้ามี component ใหม่ที่สร้างขึ้น → มีเหตุผลชัดเจนว่าทำไมของเดิมไม่พอ
- [ ] หน้าตา/พฤติกรรมของ component ที่ reuse มา**ตรงกับต้นแบบ**ใน `design-system/components/` ไม่ถูกปรับจนเพี้ยน

## 3. Semantic Color & Patient Safety (design-rules.md § 4, § 8)

- [ ] สีแดง (critical) ใช้เฉพาะกรณีความเสี่ยงถึงชีวิต/แพ้ยา/ค่าวิกฤตเท่านั้น
- [ ] Alert banner แพ้ยา/critical (ถ้ามีในบริบท) อยู่ตำแหน่งบนสุดของหน้าจอ
- [ ] ไม่มีการสื่อความหมายด้วยสีอย่างเดียว (มี icon + label ข้อความประกอบเสมอ)

## 4. Mock Data (design-rules.md § 7)

- [ ] ไม่มีข้อมูลผู้ป่วยจริงปะปนอยู่
- [ ] มีอย่างน้อย 1 record ที่เป็นค่าผิดปกติ/edge case ตามที่ requirement ระบุ
- [ ] ค่าทางคลินิก (vitals/lab) อยู่ในช่วงอ้างอิงที่สมเหตุสมผลตามมาตรฐาน

## 5. States ครบถ้วน (design-rules.md § 8)

- [ ] Loading state (ถ้าเกี่ยวข้องกับการดึงข้อมูล)
- [ ] Empty state (ถ้ารายการอาจว่างเปล่าได้)
- [ ] Error state (ถ้ามี action ที่อาจล้มเหลว)

## 6. Functional QA

- [ ] เปิดไฟล์ใน browser แล้วไม่มี error ใน Console (เช็คด้วย DevTools)
- [ ] ปุ่ม/ลิงก์/interaction หลักทำงานได้จริง ไม่ใช่แค่ตกแต่งเฉย ๆ
- [ ] ทดสอบที่ความกว้างจอ 1366px และ 1920px แล้วเลย์เอาต์ไม่แตก
- [ ] ตรวจตาม `ux-rules.md` § 2-4 (action/worklist/detail pattern เลือกใช้ถูกบริบท) และ § 5 (state ครบ 6 แบบตามที่เกี่ยวข้อง)
- [ ] ถ้ามีเนื้อหาเชิงคลินิก/decision support: ไม่มีข้อความฟันธงวินิจฉัยโรค (ดู `AI_INSTRUCTIONS.md` § 2 ข้อ 11) และไม่มี chain-of-thought ของ AI หลุดปนมาในไฟล์/Design Notes (ข้อ 10)

## 7. ผลสรุปและ Action

**ปัญหาที่พบ (ถ้ามี):**
```
1. ...
2. ...
```

**Action ถัดไป:**
- ⬜ ส่งกลับให้ผู้สร้าง mockup แก้ไขตามข้อ (ระบุเลข) ด้านบน
- ⬜ Approved → ย้ายไฟล์ไปที่ `approved-mockups/<module>/<feature>/`, ถ่าย screenshot ใส่ `screenshots/`, เพิ่มแถวใน `approved-mockups/INDEX.md`

---

## Prompt สำหรับใช้กับ "Design QA Agent" (AI ตรวจแทนคนขั้นแรก)

```
คุณคือ Design QA Agent ของระบบ Gorilla HIS
ตรวจสอบไฟล์ index.html ที่แนบมา โดยเทียบกับกฎใน AI_INSTRUCTIONS.md, design-system/design-rules.md,
และไฟล์ component ต้นแบบใน design-system/components/ ที่เกี่ยวข้อง

ให้ตรวจตาม checklist นี้ทีละข้อ (คัดลอก 6 หัวข้อด้านบนของไฟล์นี้) และตอบกลับเป็น:
1. ตาราง ผ่าน/ไม่ผ่าน ทีละข้อ พร้อมเหตุผลสั้น ๆ
2. รายการปัญหาที่ต้องแก้ (ถ้ามี) เรียงตามความรุนแรง
3. สรุปผล: Approved / Rejected / Approved with comments
```
