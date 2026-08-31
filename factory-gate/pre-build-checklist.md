# Factory Gate — Pre-Build Checklist

**Application:** << name >>  
**Blueprint:** << Application blueprint_*.txt >>  
**AI/Builder:** << tool >>

> Pre-Build ตรวจว่า Builder มีข้อมูลและแผนพร้อมก่อน Coding ไม่ได้อ้างว่าฟังก์ชันทำงานแล้ว

## A. Source Readiness
- [ ] อ่าน Application Blueprint ครบ
- [ ] อ่าน source ตาม mandatory read order ใน `AI_INSTRUCTIONS.md`
- [ ] อ่าน `factory-gate/FACTORY_GATE.md`
- [ ] อ่าน `design-system/tokens.css` และบันทึก approved token names ที่จะใช้
- [ ] อ่าน `design-system/icon-rules.md`
- [ ] อ่าน `design-system/components/application-shell.html` สำหรับ desktop module
- [ ] ถ้าเป็น Command Center / Mission Control / Operations / Flow / Capacity page ให้อ่าน `design-system/components/premium-operational-layout.html`
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

## C. Binding Reuse Contract — Mandatory

> **Read/Reference ≠ Reuse.** Builder ต้องประกาศ source ที่จะนำไปใช้จริงก่อน Coding และ Post-Build ต้องพิสูจน์ implementation ย้อนกลับได้

กรอกตารางนี้ก่อน PASS:

| UI Role | Approved Source / Repo Path | Exact Reuse Plan | Exception Requested? | Result |
|---|---|---|---|---|
| Application Shell | `design-system/components/application-shell.html` | ระบุว่าจะคง structure ส่วนใด | No / Requested | PASS/FAIL |
| Premium Operational Layout | `design-system/components/premium-operational-layout.html` หรือ N/A | สำหรับ Command Center/Operations ให้ระบุ compact header/context/KPI/alert/2:1 workspace/action rail | No / Requested / N/A | PASS/N/A/FAIL |
| Design Tokens | `design-system/tokens.css` | ระบุ token groups/names ที่จะใช้โดยตรง | No / Requested | PASS/FAIL |
| Icons | `design-system/icon-rules.md` | ระบุ semantic mapping หลัก | No / Requested | PASS/FAIL |
| KPI | `design-system/components/enterprise-kpi-strip.html` หรือ N/A | ระบุว่าจะ reuse อย่างไร | No / Requested / N/A | PASS/N/A/FAIL |
| Operational Container | `design-system/components/operational-panel.html` หรือ N/A | ระบุ panel/table/divider reuse | No / Requested / N/A | PASS/N/A/FAIL |
| Other Components | relevant approved paths | ระบุ component → view/function | No / Requested / N/A | PASS/N/A/FAIL |
| Patterns | relevant approved paths | ระบุ pattern → workflow | No / Requested / N/A | PASS/N/A/FAIL |

Binding rules:
- [ ] Desktop module จะเริ่มจาก approved `application-shell.html` ไม่สร้าง header/nav/shell ใหม่
- [ ] Command Center / Mission Control / Operations / Flow / Capacity page จะ derive composition จาก `premium-operational-layout.html`
- [ ] จะไม่มี Hero Banner / dark AI hero / developer-terminal feed / 3-column equal-card showcase เป็น primary operational composition เว้นแต่ Blueprint + approved exception ระบุ
- [ ] Main operational workspace จะเน้น table/worklist/queue/trend/exception/action และใช้ 2/3 evidence + 1/3 decision/action rail เมื่อเหมาะสม
- [ ] จะใช้ approved token names **โดยตรง** ไม่สร้าง local palette/token aliases เช่น `--primary-color`, `--success-color`, `--danger-color`, `--card-bg`, `--bg-main` เมื่อ token เดิมรองรับ
- [ ] Operational dashboard ตรวจ `enterprise-kpi-strip.html` และจะ reuse ถ้ารองรับ requirement
- [ ] Operational content ตรวจ `operational-panel.html`; card จะไม่เป็น default container
- [ ] Font Awesome mapping ใช้ตาม `icon-rules.md`; no Emoji/custom SVG/CDN/Kit
- [ ] หากไม่ใช้ required source ต้อง Declare `Approved Exception Requested` พร้อมเหตุผลก่อน Coding; Builder ห้าม approve เอง

**ข้อใด Required และไม่สามารถ commit reuse ได้ = PRE-BUILD FAIL.**

## D. Design Plan
- [ ] ระบุ Existing Components ที่จะ reuse พร้อม path
- [ ] ระบุ Existing Patterns ที่จะ reuse พร้อม path
- [ ] ระบุ Gold Standard ที่ใกล้เคียง หรือ `N/A — no relevant Gold Standard`
- [ ] ระบุ Actual Screenshot references หรือ limitation/N/A
- [ ] ระบุ Gap ที่ของเดิมรองรับไม่ได้
- [ ] ทุก reusable gap ถูก Declare เป็น `Proposed New Pattern`

## E. Screen & Flow Plan
- [ ] ระบุ Views/Screens ที่จะสร้าง
- [ ] Mapping `WF/REQ/FN/BR/ST` ที่มีอยู่ไปยัง View/Interaction ที่วางแผนรองรับ
- [ ] ระบุ Main Workflow ที่ **จะทำให้** click-through ได้หลัง Build
- [ ] สำหรับ operational page ระบุ first viewport composition ที่ 1366×768 ว่าจะเห็น KPI + alert + main evidence + action rail อย่างไร

## Pre-Build Evidence Table
| Gate Item | Evidence / Repo Path / Blueprint Section | Result |
|---|---|---|
| Source readiness | | PASS/FAIL |
| Blueprint extraction | | PASS/FAIL |
| Binding Reuse Contract | | PASS/FAIL |
| Premium Operational Master (if applicable) | | PASS/N/A/FAIL |
| Design references | | PASS/N/A/FAIL |
| Screen/flow plan | | PASS/FAIL |

## Result
- [ ] **PASS — BUILD ALLOWED**
- [ ] **FAIL — STOP, DO NOT GENERATE**

FAIL เมื่อ source ที่บังคับเข้าถึงไม่ได้, Blueprint ไม่ได้ถูกอ่าน, ไม่สามารถสร้าง traceable plan ได้, หรือไม่สามารถ commit Binding Reuse Contract สำหรับ required source ได้  
การไม่มี Gold Standard/screenshot ที่เกี่ยวข้อง **ไม่ใช่ FAIL อัตโนมัติ** ให้บันทึก N/A/limitation แทน
