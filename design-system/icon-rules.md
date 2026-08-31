# Gorilla HIS Icon Rules — Font Awesome Standard

เอกสารนี้เป็น Design Authority สำหรับการเลือกและใช้งาน icon ใน Gorilla HIS Mockup และเป็น semantic contract สำหรับ Dev ที่นำ mockup ไปพัฒนาต่อ

## 1. Official Icon Source

**Gorilla HIS Official Icon Library = Font Awesome**

- ทุก UI icon ต้องค้นหาและเลือกจาก Font Awesome ก่อนเสมอ
- Default style family = `fa-solid` เพื่อความชัดเจนบนหน้าจอ HIS ที่มี information density สูง
- `fa-regular` ใช้ได้เมื่อมีเหตุผลด้าน hierarchy และยังคง consistency กับหน้าจอรอบข้าง
- ห้ามใช้ Emoji เป็น UI icon, navigation icon, status icon หรือ section decoration
- ห้าม AI วาด custom SVG icon ใหม่ หากมี Font Awesome icon ที่สื่อความหมายเดียวกันอยู่แล้ว
- Custom icon ใช้ได้เฉพาะกรณีไม่มี Font Awesome ที่เหมาะสม และต้อง Declare ใน Design Notes เพื่อ Design QA

## 2. Mockup vs Production Rule

### Mockup Factory

Factory ยังคงกฎ **NO external CDN / external font / external JS/CSS**

ดังนั้น mockup ห้ามใส่ Font Awesome Kit/CDN URL เช่น external `<script>` หรือ `<link>` เพื่อให้ icon แสดงผล

Mockup ต้องระบุ Font Awesome semantic name/class ให้ Dev trace ต่อได้ เช่น:

```html
<i class="fa-solid fa-magnifying-glass" aria-hidden="true"></i>
```

หาก environment ของ Builder ไม่มี Font Awesome asset แบบ local/self-contained ให้เก็บ semantic class/data mapping ไว้และห้ามโหลดจาก Internet เพื่อแก้ปัญหา preview

### Production HIS

Dev ใช้ Font Awesome ผ่าน package/local/self-hosted asset ตามมาตรฐานของ Gorilla HIS application repository โดยไม่เปลี่ยน semantic icon ที่ได้รับการอนุมัติจาก Mockup/Design System

## 3. Semantic Icon Mapping — Approved Baseline

ใช้ mapping นี้เป็น default เพื่อป้องกัน AI/ทีมเลือก icon คนละตัวสำหรับความหมายเดียวกัน

| Meaning | Font Awesome semantic icon | Default style |
|---|---|---|
| Home / Main | `fa-house` | `fa-solid` |
| Dashboard / Trend | `fa-chart-line` | `fa-solid` |
| Worklist / Task | `fa-list-check` | `fa-solid` |
| Search | `fa-magnifying-glass` | `fa-solid` |
| Patient | `fa-user` | `fa-solid` |
| Doctor | `fa-user-doctor` | `fa-solid` |
| Hospital / Facility | `fa-hospital` | `fa-solid` |
| Appointment | `fa-calendar-check` | `fa-solid` |
| Bed / Admission | `fa-bed` | `fa-solid` |
| Lab | `fa-flask` | `fa-solid` |
| Medication / Pharmacy | `fa-pills` | `fa-solid` |
| Save | `fa-floppy-disk` | `fa-solid` |
| Edit | `fa-pen` | `fa-solid` |
| Delete | `fa-trash` | `fa-solid` |
| Settings | `fa-gear` | `fa-solid` |
| Filter | `fa-filter` | `fa-solid` |
| Refresh | `fa-rotate` | `fa-solid` |
| Warning | `fa-triangle-exclamation` | `fa-solid` |
| Critical / Error | `fa-circle-exclamation` | `fa-solid` |
| Information | `fa-circle-info` | `fa-solid` |
| Success / Complete | `fa-circle-check` | `fa-solid` |
| Notification | `fa-bell` | `fa-solid` |
| User / Profile | `fa-circle-user` | `fa-solid` |

ถ้า feature ต้องใช้ความหมายที่ไม่มีในตาราง ให้เลือก Font Awesome icon ที่ใกล้ที่สุดและบันทึกเพิ่มใน Design Notes ก่อนเสนอเข้า mapping กลาง

## 4. Usage Rules

1. **Meaning before decoration** — icon ต้องช่วยให้ผู้ใช้ scan/recognize action หรือ status เร็วขึ้น ไม่ใช้เพื่อเติมพื้นที่ว่าง
2. **One meaning, one icon** — ความหมายเดียวกันควรใช้ semantic icon เดียวกันข้าม module
3. **Icon + text for important actions** — Primary/critical workflow ห้ามใช้ icon-only หากความหมายอาจกำกวม
4. **Patient safety never color-only** — Warning/Critical ต้องมี icon + text/label ตาม patient-safety rules
5. **No decorative color** — icon inherit สีจาก context; semantic red/orange/green ใช้ตาม `design-rules.md` เท่านั้น
6. **No arbitrary animation** — spin/pulse/bounce ใช้เฉพาะมี functional meaning เช่น loading และต้องเป็น approved behavior
7. **Consistent sizing** — ขนาด icon ต้องมาจาก component/token scale ไม่กำหนดขนาดใหม่ต่อหน้า
8. **Accessibility** — decorative icon ใช้ `aria-hidden="true"`; icon-only control ต้องมี accessible label

## 5. Design Notes Requirement

เมื่อ mockup มี icon ที่เกี่ยวข้องกับ Main Workflow ให้ Design Notes ระบุอย่างน้อย:

```text
Icon Mapping
- Search → Font Awesome: fa-solid fa-magnifying-glass
- Worklist → Font Awesome: fa-solid fa-list-check
- Warning → Font Awesome: fa-solid fa-triangle-exclamation
```

## 6. Factory / QA Failure Conditions

ให้ถือว่า Icon Compliance FAIL เมื่อพบโดยไม่มี approved exception:

- ใช้ Emoji เป็น UI icon
- ใช้ custom SVG/icon ใหม่ทั้งที่ Font Awesome มี icon ที่เหมาะสม
- ความหมายเดียวกันใช้ Font Awesome หลาย icon แบบไม่มีเหตุผล
- ผสม style family จน visual language ไม่สม่ำเสมอ
- ใช้ icon เพื่อตกแต่งจนทำให้หน้าจอดูเป็น generic SaaS/AI dashboard
- เรียก Font Awesome ผ่าน external CDN/Kit ใน mockup
