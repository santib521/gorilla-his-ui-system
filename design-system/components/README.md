# Components — Index

**อ่านไฟล์นี้ก่อนสร้าง component ใหม่เสมอ** ตามกฎ Reuse Policy ใน `../design-rules.md`

ทุกไฟล์เป็น HTML preview/reference สำหรับคัดลอกโครงสร้างเข้า single-file mockup โดยใช้ `tokens.css` และไม่มี external dependency

| ไฟล์ | ใช้ทำอะไร | ใช้ในโมดูล |
|---|---|---|
| `application-shell.html` | **Master desktop shell**: Topbar + Sidebar + Page Header + Content. ห้าม AI ออกแบบ shell ใหม่ต่อ module โดยไม่มี approved exception | ทุก desktop module |
| `enterprise-kpi-strip.html` | KPI summary แบบ compact scan-first; preferred สำหรับ operational/command-center dashboard | Command Center, Operations, Executive operational view |
| `operational-panel.html` | Panel/Table แบบข้อมูลหนาแน่น แทน Card Everywhere | ER, IPD, Bed Mgmt, Command Center, Operations |
| `buttons.html` | ปุ่ม primary / secondary / danger / icon-button พร้อม state | ทุก module |
| `form-controls.html` | Input/select/date/checkbox/radio/textarea พร้อม state | ทุก module |
| `status-badges.html` | Status badge ตาม semantic color | ทุก module |
| `alert-banner.html` | Alert banner สำหรับ clinical/operational attention | OPD, IPD, Pharmacy, Operations |
| `patient-banner.html` | Patient context header | Patient-context modules |
| `patient-search-bar.html` | Patient search + autocomplete mock | OPD, LAB, PHARMACY |
| `vitals-form.html` | Vitals form + validation | OPD, IPD |
| `lab-result-table.html` | Lab result table + flags | LAB |
| `modal-dialog.html` | Standard confirmation/form modal | ทุก module |
| `drawer.html` | Contextual short-task drawer | ทุก module |
| `worklist.html` | Operational work queue | Registration, ER, LAB, Radiology, Pharmacy |
| `tabs.html` | In-page category navigation | ทุก module |
| `notification-toast.html` | Temporary success/error/info feedback | ทุก module |
| `stat-card.html` | Home/Executive summary stat card; **ไม่ใช่ default สำหรับ operational dashboard** | Home/summary screens |
| `patient-summary-panel.html` | Detailed patient context panel | Pharmacy, IPD, clinical context |

## Selection Rule

- Desktop feature → เริ่มจาก `application-shell.html`
- Operational/Command Center KPI → ตรวจ `enterprise-kpi-strip.html` ก่อน `stat-card.html`
- Dense operational information → ตรวจ `operational-panel.html` / table / worklist ก่อนสร้าง card
- Emoji ห้ามใช้เป็น UI icon

## กฎการเพิ่มไฟล์ใหม่

1. ต้องผ่าน Design QA ก่อนเป็น shared standard
2. ตั้งชื่อ `kebab-case.html` และลงทะเบียนใน index
3. ใช้ `tokens.css`; ห้าม hardcode design values ที่ token ครอบคลุม
4. มี comment อธิบาย use case และข้อจำกัด
