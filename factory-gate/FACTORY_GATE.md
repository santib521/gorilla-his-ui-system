# Gorilla HIS UI Factory Gate

Factory Gate เป็นด่านบังคับสำหรับ Mockup ทุกงาน เพื่อให้ผลลัพธ์จาก AI ทุกตัวมีภาษา UI เดียวกัน โดย Factory Gate ห้ามลดทอน `AI_INSTRUCTIONS.md`; ถ้าขัดกันให้ `AI_INSTRUCTIONS.md` มีอำนาจสูงสุด

## Authority

### Business Authority
1. Application Blueprint
2. Workflow / Requirement / Function / Business Rules ที่สกัดจาก Blueprint

ถ้า Blueprint ไม่มีข้อมูล ให้ใช้ `N/A — not present in Blueprint`; ห้ามแต่ง Business Rule เพื่อให้ checklist ครบ

### Design Authority
1. `AI_INSTRUCTIONS.md`
2. `design-system/design-rules.md`, `ux-rules.md`, `tokens.css`
3. Approved Components — รวม locked `application-shell.html`
4. Approved Patterns
5. Gold Standard
6. Actual Gorilla HIS screenshots
7. Proposed New Pattern
8. AI design judgment

## Gate Flow

`Blueprint → Pre-Build Gate → Builder → Builder Self-QA → Post-Build Gate + Premium HIS Visual Gate → Independent QA → Human Review → Approved → Gold Standard Promotion`

## Hard Reject

Reject ทันทีเมื่อพบ:
- ไม่อ่าน Blueprint หรือ mandatory source
- External CDN/font/JS/CSS
- สร้าง design language ใหม่
- Hardcode design value ที่ token ครอบคลุม
- Main Workflow/Critical Requirement หาย
- Dead button หรือ JS error ใน Main Workflow
- ใช้ข้อมูลผู้ป่วยจริง
- New reusable UI ไม่ Declare Proposed New Pattern
- ไม่ทำ Builder Self-QA
- **Desktop module สร้าง application shell ใหม่แทน approved `application-shell.html` โดยไม่มี approved exception**
- **ใช้ Emoji เป็น UI icon/navigation/section decoration**
- **Operational screen ใช้ AI/futuristic/marketing visual theme**
- **Semantic clinical colors ถูกใช้เป็น decoration โดยไม่มี status meaning**

## Premium HIS Visual Gate — Mandatory

Independent QA ต้องตรวจจากหน้าจอจริง ไม่ใช่ดู code/checklist อย่างเดียว:

| Gate | Question | PASS condition |
|---|---|---|
| VG-01 Product Character | ดูเป็น Hospital Enterprise System หรือ generic SaaS/AI Dashboard? | Clinical / Operational / Trustworthy / Calm / Professional |
| VG-02 Application Shell | ใช้ approved shell หรือ approved exception? | Shell structure consistent across modules |
| VG-03 Icon Language | มี Emoji/decorative icon หรือไม่? | Monochrome approved icon language; no Emoji |
| VG-04 Container Discipline | Card Everywhere หรือไม่? | Operational panels/tables/dividers used as default |
| VG-05 KPI Discipline | KPI ใหญ่แบบ marketing/stat-card grid หรือไม่? | Compact KPI strip preferred for operational dashboard |
| VG-06 Color Discipline | สีใช้เพื่อความหมายหรือ decoration? | Neutral-first; semantic color only when meaningful |
| VG-07 Density | 1366×768 เห็น key operational state เพียงพอหรือไม่? | Page context + summary + alert + main operational content + primary action visible when feasible |
| VG-08 Typography/Scale | มี oversized heading/KPI/button หรือไม่? | Uses approved token scale; scan-first hierarchy |
| VG-09 AI Visual Theme | Feature AI ถูกทำเป็น futuristic theme หรือไม่? | AI presented as capability inside Gorilla HIS visual language |

**VG-01, VG-02, VG-03, VG-06 หรือ VG-09 FAIL = P0 Design / Automatic FAIL.**
VG-04, VG-05, VG-07, VG-08 = P1 หากทำให้หน้าจอดู generic SaaS หรือทำให้ operational scanability ลดลงอย่างมีนัยสำคัญ; QA อาจยกระดับ P0 เมื่อเป็น systematic design-language violation.

## Reference Availability Rule

ไม่มี relevant Gold Standard/screenshot ได้และใช้ N/A ได้ แต่ถ้ามี approved reference แล้วละเลยโดยไม่มีเหตุผลให้ FAIL. ถ้า AI ดู binary screenshot ไม่ได้ ให้บันทึก limitation และห้ามเดารายละเอียดภาพ

## Gold Standard Rule

Factory Gate PASS หรือ Human Approved ยังไม่เป็น Gold Standard อัตโนมัติ ต้องผ่าน `approved-mockups/GOLD_STANDARD.md` และลงทะเบียนใน INDEX
