# Factory Gate — Pre-Build Checklist

**Application:** << name >>  
**Blueprint:** << Application blueprint_*.txt >>  
**AI/Builder:** << tool >>

## A. Source Readiness
- [ ] อ่าน Application Blueprint ครบ
- [ ] อ่าน `AI_INSTRUCTIONS.md`
- [ ] อ่าน `design-system/design-rules.md`
- [ ] อ่าน `design-system/ux-rules.md`
- [ ] อ่าน `design-system/tokens.css`
- [ ] ตรวจ `design-system/components/`
- [ ] ตรวจ `design-system/patterns/`
- [ ] ตรวจ `approved-mockups/INDEX.md`
- [ ] ตรวจ screenshot จริงที่เกี่ยวข้อง

## B. Blueprint Extraction
ก่อน Generate ต้องสรุปเป็น ID ที่ trace ได้:
- [ ] Workflow: `WF-01...`
- [ ] Requirements: `REQ-01...`
- [ ] Functions: `FN-01...`
- [ ] Business Rules: `BR-01...`
- [ ] Required States/Exceptions: `ST-01...`

## C. Design Plan
- [ ] ระบุ Existing Components ที่จะ reuse
- [ ] ระบุ Existing Patterns ที่จะ reuse
- [ ] ระบุ Gold Standard ที่ใกล้เคียง (ถ้ามี)
- [ ] ระบุ Actual Screenshot references
- [ ] ระบุ Gap ที่ของเดิมรองรับไม่ได้
- [ ] ทุก reusable gap ถูก Declare เป็น `Proposed New Pattern`

## D. Screen & Flow Plan
- [ ] ระบุ Views/Screens ที่จะสร้าง
- [ ] Mapping `WF/REQ/FN/BR` ไปยัง View/Interaction แล้ว
- [ ] Main Workflow สามารถ click-through ได้ตั้งแต่ต้นจนจบ

## Result
- [ ] **PASS — BUILD ALLOWED**
- [ ] **FAIL — STOP, DO NOT GENERATE**

ถ้ามีข้อบังคับข้อใดไม่ผ่าน ห้าม Generate `index.html` และต้องรายงานสิ่งที่ขาดก่อน
