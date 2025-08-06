## 🔍 คำถามทบทวน

1. **Multiple Source Files**: เหตุใดต้องแยก source code เป็นหลายไฟล์?
2. **CMakeLists.txt Management**: การเพิ่มไฟล์ source ใหม่ต้องแก้ไขอะไรบ้าง?
3. **Header Files**: บทบาทของไฟล์ .h คืออะไร และทำไมต้องมี?
4. **Include Directories**: เหตุใด CMakeLists.txt ต้องระบุ INCLUDE_DIRS?
5. **Git Ignore**: ไฟล์ .gitignore ช่วยอะไรในการจัดการ ESP32 project?
6. **Task Management**: การใช้ FreeRTOS task ในโมดูล LED ช่วยอะไร?
7. **Code Organization**: ข้อดีของการแยกโมดูล sensor, display, led เป็นไฟล์แยกคืออะไร?

## 💡 บันทึกผลการทดลอง

**ขั้นตอนที่ 1 (เฉพาะ sensor.c):**
- จำนวนไฟล์ source: 4 ไฟล์
- ขนาด binary: 163041 bytes
- การทำงาน: _________________
<img width="562" height="213" alt="ภาพถ่ายหน้าจอ 2568-08-06 เวลา 10 49 39" src="https://github.com/user-attachments/assets/8266a57e-7cd6-49a0-8abb-34e39fc573cf" />


**ขั้นตอนที่ 2 (เพิ่ม display.c):**
- จำนวนไฟล์ source: 6 ไฟล์
- ขนาด binary: 163925 bytes
- การทำงาน: _________________
<img width="564" height="268" alt="ภาพถ่ายหน้าจอ 2568-08-06 เวลา 10 54 57" src="https://github.com/user-attachments/assets/dfca0bd5-44b5-4c75-b22f-2d0d6929ed18" />

**ขั้นตอนที่ 3 (เพิ่ม led.c):**
- จำนวนไฟล์ source: 8 ไฟล์
- ขนาด binary: 164873 bytes
- การทำงาน: _________________
<img width="562" height="368" alt="ภาพถ่ายหน้าจอ 2568-08-06 เวลา 10 57 19" src="https://github.com/user-attachments/assets/19e13f76-f894-42ec-95ae-8b43bff4b0db" />
