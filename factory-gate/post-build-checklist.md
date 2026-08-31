# Factory Gate — Post-Build Checklist

ตรวจ `index.html` หลัง Builder ส่งงาน ก่อนเข้า QA Agent

## A. Structure / Security
- [ ] Single `index.html`
- [ ] ไม่มี External CDN / external font / external JS/CSS
- [ ] ไม่มี Real API / ส่งข้อมูลออกภายนอก
- [ ] ไม่มีข้อมูลผู้ป่วยจริง

## B. Design Compliance
- [ ] ใช้ Gorilla HIS tokens
- [ ] Reuse Existing Components ตาม Pre-Build Plan
- [ ] Reuse Existing Patterns ตาม Pre-Build Plan
- [ ] ไม่สร้าง design language ใหม่
- [ ] New reusable UI ถูก Declare `Proposed New Pattern`
- [ ] อ้างอิง Gold Standard/Actual Screenshot ตามที่วางแผน

## C. Blueprint Coverage
สร้าง Traceability Table แล้วตรวจ:
- [ ] Workflow `WF-*` ครบ
- [ ] Requirements `REQ-*` ครบ
- [ ] Functions `FN-*` ครบ
- [ ] Business Rules `BR-*` ครบ
- [ ] States/Exceptions `ST-*` ครบตามความเกี่ยวข้อง

สถานะที่อนุญาต: `PASS / PARTIAL / FAIL / N/A`

## D. Functional
- [ ] Main Workflow click-through ได้
- [ ] Main buttons/actions ทำงาน
- [ ] Modal/Drawer/Tabs/Filter/Search ที่อยู่ใน scope ทำงาน
- [ ] ไม่มี Dead Button ใน Main Workflow
- [ ] Loading/Empty/Error/Success/Disabled/Validation state ครบตามบริบท

## E. Technical / Viewport
- [ ] ไม่มี Console Error ที่กระทบการใช้งาน
- [ ] 1366×768 ใช้งานได้
- [ ] 1920×1080 ใช้งานได้
- [ ] ไม่มี horizontal overflow ที่ไม่จำเป็น

## Result
- [ ] **PASS → SEND TO QA AGENT**
- [ ] **FAIL → RETURN TO BUILDER**

Critical Requirement หรือ Main Workflow ที่เป็น `FAIL` = Post-Build Gate FAIL อัตโนมัติ
