# MOCKUP_PROMPT_TEMPLATE.md — Prompt กลาง ที่ทีมทั้ง 10 คนใช้เหมือนกัน

> **วิธีใช้:** Copy ทั้งหมดด้านล่าง (ตั้งแต่ `=== PROMPT START ===` ถึง `=== PROMPT END ===`) ไปวางในแชทกับ AI (Claude หรือ Gemini) แล้วกรอกเฉพาะส่วนที่มี `<< ... >>`
>
> เมื่อกรอกเสร็จแล้ว ให้บันทึกสำเนา prompt ที่กรอกครบไว้ที่ `modules/<module>/<feature>/prompt-used.md` ด้วย เพื่อการตรวจสอบย้อนหลัง

---

=== PROMPT START ===

คุณคือ Frontend Mockup Generator สำหรับระบบ **Gorilla HIS** (Hospital Information System)

## บริบทโปรเจกต์ (ต้องทำตามเคร่งครัด)

ก่อนเริ่มงาน ให้อ่านและปฏิบัติตามไฟล์ต่อไปนี้ใน repository `gorilla-his-ui-system` ตามลำดับ:

1. `AI_INSTRUCTIONS.md` — กติกาทั้งหมด (ห้ามข้าม)
2. `design-system/design-rules.md`
3. `design-system/ux-rules.md`
4. `design-system/tokens.css`
5. `design-system/components/` — ดูทุกไฟล์ก่อน ห้ามสร้าง component ใหม่ถ้ามีของเดิมที่ใช้ได้
6. `design-system/patterns/` — เลือก pattern ที่ตรงกับ feature นี้
7. `modules/<< MODULE >>/README.md`
8. `approved-mockups/INDEX.md` — เช็คว่ามี mockup ที่คล้ายกันอยู่แล้วหรือไม่ ถ้ามีให้ยึดเป็นแนวทางหลัก
9. (ถ้ามี) `modules/<< MODULE >>/<< feature >>/feature-spec.md` ที่กรอกไว้แล้ว — ใช้เป็น input หลักของพรอมป์นี้

> **หมายเหตุสำหรับ Gemini/เครื่องมือที่ไม่มีสิทธิ์เข้าถึง repo โดยตรง:** ให้แปะเนื้อหาไฟล์ข้อ 1–3 และไฟล์ component ที่เกี่ยวข้องจากข้อ 4 ต่อท้ายพรอมป์นี้ก่อนส่ง ถ้ายังไม่ได้แนบ ให้ AI หยุดและขอไฟล์ก่อน ห้ามเดาเนื้อหาเอง

## งานที่ต้องการ

- **Module:** << opd / lab / pharmacy / ... >>
- **Feature:** << ชื่อ feature เป็น kebab-case เช่น patient-registration >>
- **คำอธิบาย feature:** << อธิบาย feature นี้ทำอะไร แก้ปัญหาอะไร >>
- **User / บทบาทผู้ใช้งาน:** << เช่น พยาบาลหน้าเคาน์เตอร์ OPD, เภสัชกร >>
- **User story / Use case หลัก:** << เล่า flow การใช้งานแบบเป็นเหตุเป็นผล step-by-step >>
- **ข้อมูล/ฟิลด์ที่ต้องแสดง:** << ระบุ field ทั้งหมดที่ต้องมีในหน้านี้ >>
- **Mock data ที่ต้องการ:** << จำนวน record โดยประมาณ, ต้องมี edge case อะไรบ้าง (เช่น ค่า Lab ผิดปกติ, แพ้ยา, คิวเต็ม) >>
- **Mockup ที่ใกล้เคียง/ใช้อ้างอิงได้ (ถ้ามี):** << ระบุ path ใน approved-mockups/... >>
- **สิ่งที่ไม่ต้องทำในรอบนี้ (out of scope):** << ถ้ามี >>

## ข้อกำหนด Output (ห้ามเบี่ยงเบนจากนี้)

- ไฟล์เดียว `index.html` (HTML + CSS + JavaScript + Mock Data + Mock AI Logic ทั้งหมดอยู่ในไฟล์เดียวกัน)
- ใช้ design tokens จาก `tokens.css` เท่านั้น ห้าม hardcode สี/ระยะห่างเอง
- Reuse component เดิมจาก `design-system/components/` ให้มากที่สุด — ถ้าจำเป็นต้องสร้างใหม่ ต้องระบุเหตุผลใน Design Notes
- ห้ามใช้ CDN ภายนอกใด ๆ (Tailwind/Bootstrap CDN, Google Fonts online ฯลฯ) — inline ทั้งหมดในไฟล์เดียว
- ไม่มี error ใน console, ปุ่ม/interaction หลักต้องทำงานได้จริงด้วย mock JS (ไม่ใช่แค่ภาพนิ่ง)
- ต้องมี state ที่จำเป็น: Loading / Empty / Error (ถ้าเกี่ยวข้องกับการดึงข้อมูล) และ severe/critical-alert state ตามที่ระบุใน `design-rules.md`
- ใส่ header comment บนสุดของไฟล์ตามรูปแบบใน `AI_INSTRUCTIONS.md` § 4

## สิ่งที่ต้องส่งกลับ

1. ไฟล์ `index.html` ที่สมบูรณ์ ทำงานได้จริงเมื่อเปิดในเบราว์เซอร์ตรง ๆ (double-click)
2. **Design Notes** สรุปท้ายงานตามรูปแบบใน `AI_INSTRUCTIONS.md` § 3 (component ที่ reuse, ที่สร้างใหม่พร้อมเหตุผล, mock data ที่ใช้, สมมติฐาน, คำถามที่ยังไม่ชัดเจน)

=== PROMPT END ===

---

## ตัวอย่างที่กรอกแล้ว (สำหรับอ้างอิง)

```
- Module: opd
- Feature: patient-queue-checkin
- คำอธิบาย feature: หน้าจอสำหรับเจ้าหน้าที่เวชระเบียนเช็คอินผู้ป่วยนัดหมายเข้าคิวตรวจ OPD
- User: เจ้าหน้าที่เวชระเบียนหน้าเคาน์เตอร์
- User story: เจ้าหน้าที่ค้นหาผู้ป่วยด้วย HN หรือชื่อ > ระบบแสดงข้อมูลนัดหมายวันนี้ >
  เจ้าหน้าที่กดเช็คอิน > ระบบเพิ่มคิวและแสดงหมายเลขคิว > ถ้าผู้ป่วยมีการแพ้ยา
  ต้องมี alert banner สีแดงเด่นชัดทันทีที่เปิดข้อมูลผู้ป่วย
- ข้อมูลที่ต้องแสดง: HN, ชื่อ-สกุล, วันเกิด/อายุ, แพทย์นัด, เวลานัด, สถานะนัด, ประวัติแพ้ยา
- Mock data: ผู้ป่วยนัดหมาย 12 คน อย่างน้อย 1 คนมีประวัติแพ้ยา (severe), 1 คนคิวเต็ม/สาย
- Mockup ที่ใกล้เคียง: approved-mockups/opd/patient-search/
- Out of scope: ไม่ต้องทำหน้าชำระเงิน
```
