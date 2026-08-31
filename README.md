# 🦍 Gorilla HIS UI Factory

Design System + Mockup Factory สำหรับระบบ Gorilla HIS (Hospital Information System)
ใช้โดยทีม Mockup 10 คน (ใช้ Claude และ Gemini เป็นเครื่องมือหลัก) เพื่อผลิต UI Mockup ที่:

- **สม่ำเสมอ** — หน้าตาเหมือนออกแบบโดยทีมเดียวกัน แม้ทำโดยคนละคน/คนละ AI
- **ตรวจสอบได้** — ทุก mockup ผ่าน QA ก่อนถูกอ้างอิงเป็นของจริง
- **ส่งต่อ Dev ได้ทันที** — ไฟล์ HTML เดียว รันได้จริง ไม่ต้องตีความใหม่

## เริ่มต้นใช้งานเร็ว (Quick Start)

1. อ่าน [`AI_INSTRUCTIONS.md`](./AI_INSTRUCTIONS.md) — กติกาทั้งหมด (อ่านครั้งแรกที่เข้าร่วมทีม)
2. Copy `modules/_feature-template/` ไปเริ่มงานใน `modules/<module>/<feature>/` แล้วกรอก `feature-spec.md` ก่อน
3. เปิด [`MOCKUP_PROMPT_TEMPLATE.md`](./MOCKUP_PROMPT_TEMPLATE.md) — copy พรอมป์นี้ไปใช้ทุกครั้งที่สร้าง feature ใหม่
4. ทำตาม [`WORKFLOW.md`](./WORKFLOW.md) — branch, PR, QA gate, merge

ทีมใหม่ดู [`docs/TEAM_ONBOARDING.md`](./docs/TEAM_ONBOARDING.md) สำหรับแผนสอนงานแบบ step-by-step

## โครงสร้าง Repository

```
gorilla-his-ui-system/
├── AI_INSTRUCTIONS.md          ← กติกาสำหรับ AI (อ่านก่อนเริ่มงานทุกครั้ง)
├── MOCKUP_PROMPT_TEMPLATE.md   ← Prompt กลางที่ทีมทั้ง 10 คนใช้เหมือนกัน
├── WORKFLOW.md                 ← Git branch / PR / QA gate process
├── docs/
│   └── TEAM_ONBOARDING.md      ← แผนสอนงานทีม Mockup
├── design-system/
│   ├── design-rules.md         ← หลักการออกแบบเชิงภาพ, กฎสี, accessibility
│   ├── ux-rules.md              ← หลักการเชิงพฤติกรรม/โต้ตอบ (action, worklist, state)
│   ├── tokens.css               ← Design tokens (สี/spacing/font) — ใช้เท่านั้น ห้าม hardcode
│   ├── components/              ← 13 component จริงที่ใช้งานได้ (copy ไปใช้ต่อ)
│   └── patterns/                 ← โครงหน้าจอระดับ pattern (list-detail, order-entry, approval, ฯลฯ)
├── screenshots/
│   ├── actual-gorilla-his/        ← ภาพหน้าจอของจริง (sanitized) สอน AI ให้รู้จักผลิตภัณฑ์จริง
│   └── approved-mockups/          ← ภาพหน้าจอของ mockup ที่ approved แล้ว
├── approved-mockups/              ← ⭐ Source of Truth — mockup ที่ผ่าน QA แล้ว
└── modules/                        ← 📁 ที่สร้าง mockup ใหม่ (9 module ธุรกิจ)
    ├── _feature-template/           ← Template สำหรับเริ่ม feature ใหม่ (copy ทั้งโฟลเดอร์)
    │   ├── feature-spec.md          ← สเปกเชิงธุรกิจ/ฟังก์ชัน (กรอกก่อนเริ่ม)
    │   └── review/qa-checklist.md   ← 📋 ที่ตรวจสอบ mockup ก่อน approve
    ├── registration/  ├── opd/      ├── ipd/
    ├── er/             ├── pharmacy/ ├── lab/
    ├── radiology/      ├── appointment/ └── patient-portal/
```

## สถาปัตยกรรมของระบบ

```
                     GORILLA HIS
                    DESIGN SYSTEM
                          │
            ┌─────────────┼─────────────┐
            │             │             │
          Rules       Components     Patterns
      (design-rules) (components/)  (patterns/)
            │             │             │
            └─────────────┼─────────────┘
                          │
                         Git  (source of truth)
                          │
            ┌─────────────┼─────────────┐
            ▼             ▼             ▼
          Claude         Gemini        Human
      (อ่าน repo         (ต้องแปะไฟล์    (อ่าน repo
       โดยตรง)            ก่อนเริ่ม)      โดยตรง)
            │             │             │
            ▼             ▼             ▼
        modules/A     modules/B     modules/C
            │             │             │
            └─────────────┼─────────────┘
                          ▼
              Design QA Agent / QA Lead
           (modules/<x>/review/qa-checklist.md)
                          │
                          ▼
                  approved-mockups/
                 (Source of Truth ที่ Dev ใช้)
```

## คำถามที่พบบ่อย

**ถ้า AI สร้าง component ใหม่ที่ซ้ำกับของเดิม ทำอย่างไร?**
QA reject กลับไปพร้อมชี้ว่ามีของเดิมใน `design-system/components/` ให้ใช้แทน — ดู `AI_INSTRUCTIONS.md` § 2 ข้อ 4

**ถ้าจำเป็นต้องมี component ใหม่จริง ๆ ทำอย่างไร?**
เสนอในที่ประชุม weekly design sync (ดู `docs/TEAM_ONBOARDING.md`) ก่อนเพิ่มเข้า `design-system/components/` — ห้ามต่างคนต่างสร้างเอง

**ทีมใช้ Gemini แล้วมันไม่เห็นไฟล์ใน repo ทำอย่างไร?**
ดู `MOCKUP_PROMPT_TEMPLATE.md` หมายเหตุสำหรับ Gemini — ต้องแปะเนื้อหาไฟล์ที่เกี่ยวข้องไว้ในพรอมป์ก่อนเสมอ
