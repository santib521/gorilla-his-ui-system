# screenshots/

โฟลเดอร์นี้แยกเป็น 2 จุดประสงค์ที่**ไม่เหมือนกัน** อย่าปนกัน:

| โฟลเดอร์ | เก็บอะไร | ใช้ทำอะไร |
|---|---|---|
| [`actual-gorilla-his/`](./actual-gorilla-his/) | ภาพหน้าจอ **ของจริง** จากระบบ Gorilla HIS ที่ใช้งานอยู่ (sanitized แล้ว) | สอน AI/ทีมให้รู้จักหน้าตาจริงของผลิตภัณฑ์ ก่อนออกแบบ — ใช้ทำ Visual Audit |
| `approved-mockups/` | ภาพหน้าจอของ **mockup ที่ผ่าน QA แล้ว** ใน `approved-mockups/` (repo root) | ดูภาพรวมเร็ว ๆ โดยไม่ต้องเปิดไฟล์ HTML ทีละไฟล์ (เช่น เอาไปแปะสรุปให้ผู้บริหาร) |

## Naming Convention (ใช้ทั้งสองโฟลเดอร์)

```
<module>-<feature หรือ ชื่อหน้าจอ>-<YYYYMMDD>.png
```

ตัวอย่าง: `opd-patient-queue-checkin-20260831.png`

## กฎ
- `approved-mockups/`: อัปเดตทุกครั้งที่ mockup เวอร์ชันนั้นถูกแก้ไข (ตั้งชื่อแยก version เช่น `-v2` ถ้าต้องการเก็บของเก่าไว้เทียบ) ถ่ายที่ความกว้างจอ 1366px เป็นมาตรฐาน
- `actual-gorilla-his/`: **ต้องเบลอ/ลบข้อมูลผู้ป่วยก่อน commit ทุกครั้ง** ดูกฎเต็มที่ `actual-gorilla-his/README.md`
