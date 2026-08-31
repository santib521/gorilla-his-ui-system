# Gorilla HIS Mockup QA Checklist — v2.2

**Feature:** << module/feature >>  
**Blueprint:** << Application blueprint_*.txt >>  
**Reviewer Mode:** ⬜ Builder Self-QA ⬜ Independent QA Agent ⬜ Human  
**Overall:** ⬜ PASS ⬜ PASS WITH ISSUES ⬜ FAIL

Builder Self-QA ไม่มีสิทธิ์ตัดสิน READY FOR HUMAN REVIEW; Independent QA ต้องตรวจซ้ำจาก implementation และหน้าจอจริง

## 1. Blueprint Traceability — Mandatory
| ID | Blueprint Item | Expected | Evidence in index.html | Result | Issue/Fix |
|---|---|---|---|---|---|

Result = PASS / PARTIAL / FAIL / N/A
- [ ] Main Workflow click-through ครบ
- [ ] Critical Requirements ไม่มี FAIL/PARTIAL
- [ ] Function List ครบ
- [ ] Business Rules ถูก represent/enforce
- [ ] Required States/Exceptions ครบ

## 2. Factory Compliance
- [ ] Verify post-build-checklist ซ้ำ
- [ ] Single index.html
- [ ] No external CDN/font/CSS/JS
- [ ] No token-covered hardcode
- [ ] No Real API/data exfiltration
- [ ] No real patient data
- [ ] Metadata / Design Notes / prompt-used.md พร้อม

## 3. Component / Pattern / Reference
- [ ] Existing Components/Patterns reused
- [ ] Relevant Gold Standard/reference used or N/A
- [ ] New reusable UI Declare Proposed New Pattern
- [ ] ไม่มี hidden/module-specific design system

## 4. Premium HIS Visual Gate — Independent QA must inspect rendered UI
| ID | Check | Result | Evidence / Fix |
|---|---|---|---|
| VG-01 | Hospital Enterprise Product Character; not generic SaaS/AI dashboard | | |
| VG-02 | Approved Application Shell or approved exception | | |
| VG-03 | No Emoji/decorative UI icon; consistent monochrome icon language | | |
| VG-04 | No Card Everywhere; dense operational containers used appropriately | | |
| VG-05 | Compact KPI strip preferred on operational dashboard | | |
| VG-06 | Neutral-first; semantic colors only for meaning | | |
| VG-07 | 1366×768 operational density appropriate | | |
| VG-08 | No oversized heading/KPI/button/card | | |
| VG-09 | AI is capability, not futuristic visual theme | | |

**VG-01/VG-02/VG-03/VG-06/VG-09 FAIL = P0 / Automatic FAIL.**

QA ต้องตอบคำถามนี้ด้วยประโยคเดียว:
> “ถ้าเอาชื่อ Gorilla HIS ออกจากหน้าจอ หน้านี้ยังดูเป็นระบบ Hospital Enterprise ที่ออกแบบอย่างเป็นมืออาชีพ หรือดูเป็น generic AI/SaaS template?”

ถ้าคำตอบคือ generic AI/SaaS template → VG-01 FAIL.

## 5. Visual / UX / Patient Safety
- [ ] Semantic color ถูกความหมาย
- [ ] Critical alert มี icon/label + text ไม่พึ่งสีอย่างเดียว
- [ ] Action hierarchy ถูกต้อง
- [ ] Table/Form/Tabs/Modal/Drawer สอดคล้อง Gorilla HIS
- [ ] Clinical decision support ไม่ใช้ definitive diagnosis
- [ ] ไม่มี hidden chain-of-thought

## 6. Interaction QA
- [ ] Buttons
- [ ] Tabs/navigation
- [ ] Search/filter ถ้ามี
- [ ] Modal/Drawer/Confirmation ถ้ามี
- [ ] Status/Scenario/Task transitions ถ้ามี
- [ ] Validation/Disabled state
- [ ] ไม่มี Dead Button ใน Main Workflow

## 7. States / Mock Data
- [ ] Loading
- [ ] Empty
- [ ] Error
- [ ] Success/confirmation
- [ ] Edge case ตาม Blueprint
- [ ] Clinical mock values สมเหตุสมผลเมื่อเกี่ยวข้อง

## 8. Technical QA
- [ ] ไม่มี Console Error
- [ ] 1366×768 ใช้งานได้
- [ ] 1920×1080 ใช้งานได้
- [ ] ไม่มี overflow/overlay ขวาง action

## 9. Severity / Decision
- P0 Critical — Main workflow, patient safety, Hard Reject, mandatory Visual Gate
- P1 Major — function/compliance/visual hierarchy สำคัญไม่ครบ
- P2 Minor/Enhancement

Automatic FAIL: P0, Critical Requirement FAIL/PARTIAL, Main Workflow FAIL/PARTIAL, Hard Reject, mandatory Visual Gate FAIL, Console Error หรือ Post-Build Gate FAIL

### Decision
- Builder PASS → READY FOR POST-BUILD GATE / INDEPENDENT QA
- Independent QA FAIL → RETURN TO MOCKUP BUILDER
- Independent QA PASS → READY FOR HUMAN REVIEW
- Human Approved → Approved Mockup; Gold Standard promotion เป็นขั้นตอนแยก
