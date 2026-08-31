# Gorilla HIS Gold Standard

Gold Standard คือ Mockup ที่ผ่าน Factory Gate + QA + Human Approval แล้ว และอนุญาตให้ AI ใช้เป็น reference ระดับสูงสำหรับงานใหม่ที่มี UI archetype ใกล้เคียง

## สถานะ
`Candidate → QA Passed → Human Approved → Gold Standard`

ห้าม Promote จาก AI Builder หรือ QA Agent โดยอัตโนมัติ

## Minimum Package
Gold Standard แต่ละงานควรมี:
```
approved-mockups/<type-or-module>/<feature>/
├── index.html
├── screenshot.jpg
├── blueprint.txt
├── design-notes.md
└── qa-result.md
```

## Suggested Initial Gold Standards
1. Clinical Result Review — เช่น Lab Result
2. Worklist — เช่น OPD Worklist
3. Dashboard / Decision — เช่น Hospital Command Center

รายการข้างต้นเป็นเพียง Candidate category ยังไม่ถือว่า Approved

## Promotion Criteria
- Factory Pre/Post Gate PASS
- QA ไม่มี P0 และ Critical Requirement FAIL
- Main Workflow PASS
- Gorilla HIS design compliance PASS
- Human/Design QA ยืนยัน
- Proposed New Pattern ที่ต้องใช้ซ้ำได้รับการพิจารณาแล้ว
- เพิ่มรายการใน `approved-mockups/INDEX.md`

## Usage Rule
Builder ต้องเลือก Gold Standard ที่ใกล้กับ UI archetype ของงานเท่านั้น ห้ามอ่านทุก Gold Standard แล้วผสม pattern โดยไม่มีเหตุผล

Gold Standard เป็น reference ของ composition/interaction/quality ไม่ใช่สิทธิ์ให้ copy Business Rule หรือข้อมูลของ module อื่น
