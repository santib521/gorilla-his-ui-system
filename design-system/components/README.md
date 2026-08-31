# Components — Index

**อ่านไฟล์นี้ก่อนสร้าง component ใหม่เสมอ** ตามกฎ Reuse Policy ใน `../design-rules.md` § 5

ทุกไฟล์ในโฟลเดอร์นี้เป็น **HTML แบบเปิดดูได้จริงในเบราว์เซอร์** (โหลด `../tokens.css` ผ่าน `<link>` เพื่อ preview) ใช้เป็น**ตัวอย่างต้นแบบให้คัดลอกโครงสร้าง HTML + CSS ไปวางใน mockup ของคุณ** (แล้ว inline ให้เป็นไฟล์เดียวตามกฎใน `AI_INSTRUCTIONS.md`)

> เปิดดูทั้งหมดพร้อมกันได้ง่าย ๆ ด้วย local server เช่น `npx serve design-system/components` แล้วเปิดแต่ละไฟล์ในเบราว์เซอร์

| ไฟล์ | ใช้ทำอะไร | ใช้ในโมดูล |
|---|---|---|
| `buttons.html` | ปุ่ม primary / secondary / danger / icon-button พร้อม state (default, hover, disabled, loading) | ทุก module |
| `form-controls.html` | Input text, select, date picker style, checkbox, radio, textarea พร้อม state error/disabled | ทุก module |
| `status-badges.html` | ป้ายสถานะ (badge) สำหรับ appointment status, priority, lab flag ตาม semantic color | ทุก module |
| `alert-banner.html` | แบนเนอร์เตือนแบบเต็มความกว้าง สำหรับแพ้ยา/ความเสี่ยง critical | OPD, IPD, Pharmacy |
| `patient-banner.html` | แถบข้อมูลผู้ป่วยด้านบนหน้าจอ (HN, ชื่อ, อายุ, เตียง) ใช้ซ้ำแทบทุกหน้าที่เกี่ยวกับผู้ป่วยรายคน | ทุก module ที่แสดงข้อมูลผู้ป่วยรายคน |
| `patient-search-bar.html` | ช่องค้นหาผู้ป่วยด้วย HN/ชื่อ พร้อม autocomplete แบบ mock | OPD, LAB, PHARMACY |
| `vitals-form.html` | ฟอร์มบันทึกสัญญาณชีพ พร้อม validation ไฮไลต์ค่าผิดปกติอัตโนมัติ | OPD, IPD |
| `lab-result-table.html` | ตารางแสดงผล Lab พร้อม flag สูง/ต่ำ/วิกฤต และ sort/filter แบบ mock | LAB |
| `modal-dialog.html` | หน้าต่าง modal มาตรฐาน (confirm action, form ใน modal) | ทุก module |
| `drawer.html` | แผงเลื่อนจากขอบจอ สำหรับงานสั้น ๆ ที่มีบริบทเดียว โดยไม่ต้องออกจากหน้าหลัก (ดู `ux-rules.md` § 4) | ทุก module |
| `worklist.html` | คิวงานที่ต้องดำเนินการต่อ พร้อม action ต่อแถว (ต่างจาก data table ที่แสดงผลอย่างเดียว) | Registration, ER, LAB, Radiology, Pharmacy |
| `tabs.html` | สลับดูเนื้อหาหลายหมวดในหน้าเดียวกัน (เช่น ประวัติผู้ป่วย: Vitals/Lab/Medication/Notes) | ทุก module |
| `notification-toast.html` | แจ้งผลลัพธ์ action แบบชั่วคราว (Success/Error/Info ทั่วไป — ไม่ใช่ patient-safety critical) | ทุก module |
| `stat-card.html` | ตัวเลขสรุปภาพรวม (ไอคอนวงกลมสี + ตัวเลข + label) — พบจริงใน Visual Audit | หน้า Dashboard/Home ของทุก module **เท่านั้น** (ห้ามใช้กับหน้าปฏิบัติการ ดู § 0.5.3 ใน `design-rules.md`) |
| `enterprise-kpi-strip.html` | KPI แถวเดียว compact สำหรับหน้าจอปฏิบัติการที่มีตัวเลขสรุปหลายตัว (ไม่ใช่ Home Dashboard) — ใช้ก่อน `stat-card.html` เสมอตาม `design-rules.md` § 0.5.3 | Command Center, ER Flow, Bed Management และหน้าปฏิบัติการอื่นที่มี KPI แถวบน |
| `application-shell.html` | **Master Application Shell ที่ล็อกตายตัว** (Top bar + Left sidebar + Content) — ทุก feature ต้องใช้โครงนี้ ห้ามออกแบบ Shell เอง (ดู `design-rules.md` § 0.5.5) | ทุก module/feature |
| `patient-summary-panel.html` | แผงข้อมูลผู้ป่วยแบบละเอียด (vitals + allergy + underlying + social history) — พบจริงใน Visual Audit | Pharmacy, IPD, หน้าที่ต้องดู context ผู้ป่วยตลอดเวลา |

## กฎการเพิ่มไฟล์ใหม่ในโฟลเดอร์นี้

1. ต้องผ่านการ approve จาก Design QA Lead ในที่ประชุม weekly design sync ก่อน (ไม่ใช่ต่างคนต่างเพิ่มเอง)
2. ตั้งชื่อไฟล์ `kebab-case.html`, เพิ่มแถวในตารางด้านบนทันที
3. ต้องใช้ tokens.css ทั้งหมด ห้าม hardcode ค่า
4. ต้องมี comment อธิบายวิธีใช้งาน/ตัวแปรสำคัญไว้บนสุดของไฟล์
