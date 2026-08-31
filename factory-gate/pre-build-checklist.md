# Factory Gate — Pre-Build Checklist

**Application:** << name >>  
**Blueprint:** << Application blueprint_*.txt >>  
**AI/Builder:** << tool >>

> Pre-Build ตรวจว่า Builder มีข้อมูลและแผนพร้อมก่อน Coding ไม่ได้อ้างว่าฟังก์ชันทำงานแล้ว

## A. Source Readiness
- [ ] อ่าน Application Blueprint ครบ
- [ ] อ่าน source ตาม mandatory read order ใน `AI_INSTRUCTIONS.md`
- [ ] อ่าน `factory-gate/FACTORY_GATE.md`
- [ ] ตรวจ `approved-mockups/INDEX.md`
- [ ] ตรวจ relevant screenshot/reference เท่าที่ tool เข้าถึงได้

ทุกข้อให้ระบุ **Evidence/Path ที่อ่านจริง** ไม่ใช่เพียงติ๊ก checkbox

## B. Blueprint Extraction
สกัดเฉพาะสิ่งที่ Blueprint มี และคงสาระเดิม:
- [ ] Workflow: `WF-01...` หรือ `N/A — not present in Blueprint`
- [ ] Requirements: `REQ-01...` หรือ N/A
- [ ] Functions: `FN-01...` หรือ N/A
- [ ] Business Rules: `BR-01...` หรือ N/A
- [ ] Required States/Exceptions: `ST-01...` หรือ N/A
- [ ] ระบุ Critical Requirement/Main Workflow จากข้อความใน Blueprint; ถ้า Blueprint ไม่จัด Critical ห้าม AI เดาเอง

## C. Design Plan
- [ ] ระบุ Existing Components ที่จะ reuse พร้อม path
- [ ] ระบุ Existing Patterns ที่จะ reuse พร้อม path
- [ ] ระบุ Gold Standard ที่ใกล้เคียง หรือ `N/A — no relevant Gold Standard`
- [ ] ระบุ Actual Screenshot references หรือ limitation/N/A
- [ ] ระบุ Gap ที่ของเดิมรองรับไม่ได้
- [ ] ทุก reusable gap ถูก Declare เป็น `Proposed New Pattern`

## D. Screen & Flow Plan
- [ ] ระบุ Views/Screens ที่จะสร้าง
- [ ] Mapping `WF/REQ/FN/BR/ST` ที่มีอยู่ไปยัง View/Interaction ที่วางแผนรองรับ
- [ ] ระบุ Main Workflow ที่ **จะทำให้** click-through ได้หลัง Build

## Pre-Build Evidence Table
| Gate Item | Evidence / Repo Path / Blueprint Section | Result |
|---|---|---|
| Source readiness | | PASS/FAIL |
| Blueprint extraction | | PASS/FAIL |
| Design references | | PASS/N/A/FAIL |
| Screen/flow plan | | PASS/FAIL |

## Result
- [ ] **PASS — BUILD ALLOWED**
- [ ] **FAIL — STOP, DO NOT GENERATE**

FAIL เมื่อ source ที่บังคับเข้าถึงไม่ได้, Blueprint ไม่ได้ถูกอ่าน, หรือไม่สามารถสร้าง traceable plan ได้  
การไม่มี Gold Standard/screenshot ที่เกี่ยวข้อง **ไม่ใช่ FAIL อัตโนมัติ** ให้บันทึก N/A/limitation แทน
