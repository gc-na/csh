# [ระบบปฏิบัติการ] C Shell (csh) jobs การใช้งาน: แสดงรายการงานที่ทำงานอยู่

## Overview
คำสั่ง `jobs` ใน C Shell (csh) ใช้เพื่อแสดงรายการของงานที่กำลังทำงานอยู่ในเซสชันปัจจุบัน โดยจะแสดงสถานะของงานแต่ละงาน เช่น กำลังทำงานอยู่ รอการทำงาน หรือถูกหยุดชั่วคราว

## Usage
ไวยากรณ์พื้นฐานของคำสั่ง `jobs` คือ:

```
jobs [options] [arguments]
```

## Common Options
- `-l`: แสดงหมายเลขกระบวนการ (PID) ของงาน
- `-n`: แสดงเฉพาะงานที่มีการเปลี่ยนแปลงสถานะ
- `-p`: แสดงเฉพาะหมายเลขกระบวนการของงาน

## Common Examples
ตัวอย่างการใช้งานคำสั่ง `jobs` มีดังนี้:

1. แสดงรายการงานทั้งหมดที่กำลังทำงานอยู่:
   ```csh
   jobs
   ```

2. แสดงหมายเลขกระบวนการของงาน:
   ```csh
   jobs -l
   ```

3. แสดงเฉพาะงานที่มีการเปลี่ยนแปลงสถานะ:
   ```csh
   jobs -n
   ```

4. แสดงหมายเลขกระบวนการของงานเท่านั้น:
   ```csh
   jobs -p
   ```

## Tips
- ใช้คำสั่ง `bg` เพื่อส่งงานที่ถูกหยุดชั่วคราวกลับไปทำงานในพื้นหลังหลังจากที่ตรวจสอบสถานะด้วย `jobs`
- ใช้คำสั่ง `fg` เพื่อเรียกงานที่ทำงานอยู่ในพื้นหลังให้กลับมาทำงานในพื้นหน้า
- ตรวจสอบสถานะของงานบ่อย ๆ เพื่อให้แน่ใจว่างานของคุณทำงานตามที่คาดหวัง