## 🔍 คำถามทบทวน

1. **Multiple Source Files**: เหตุใดต้องแยก source code เป็นหลายไฟล์?

    ทำให้สามารถอ่าน code ได้ง่าย ไม่สับสน เเบ่ง code ของเต่ละ sensor ได้ชัดเจน

2. **CMakeLists.txt Management**: การเพิ่มไฟล์ source ใหม่ต้องแก้ไขอะไรบ้าง?

    เพิ่มไฟล์ sensor นั้นที่เป็น .c ลงใน SRCS

3. **Header Files**: บทบาทของไฟล์ .h คืออะไร และทำไมต้องมี?

    .h คือไฟล์หัวข้อที่ใช้บอกโครงสร้างหรือฟังก์ชันให้ไฟล์อื่นรู้ เพื่อให้โค้ดหลายส่วนทำงานร่วมกันได้.
    ใช้เพื่อ ประกาศฟังก์ชันและตัวแปร แชร์โครงสร้างข้อมูล (Structs, Enums, Macros) สนับสนุนการแยกไฟล์ 

4. **Include Directories**: เหตุใด CMakeLists.txt ต้องระบุ INCLUDE_DIRS?

    ให้คอมไพเลอร์รู้ว่าจะหาไฟล์  header จากที่ไหน ป้องกันข้อผิดพลาด 'file not found' พื่อให้คอมไพเลอร์สามารถรวมไฟล์ได้ถูกต้องตอน build.

5. **Git Ignore**: ไฟล์ .gitignore ช่วยอะไรในการจัดการ ESP32 project?

    เป็นการบังคับไม่ให้ไฟล์ต่างๆ ที่มีชื่อในไฟล์ .gitignore อัพโหลดไป git ซึ่งถ้าไม่ทำจะมีไฟล์ที่ไม่จำเป็นโหลดไปยัง git เยอะมาก

6. **Task Management**: การใช้ FreeRTOS task ในโมดูล LED ช่วยอะไร?
   
    แยกการกระพริบ LED ออกจากโค้ดหลัก ทำงานแบบต่อเนื่องใน background ใช้ประโยชน์จากระบบ multitasking ของ FreeRTOS

7. **Code Organization**: ข้อดีของการแยกโมดูล sensor, display, led เป็นไฟล์แยกคืออะไร?
    
    แยกหน้าเเต่ละตัวที่ชัดเจน code เป็นระเบียบ ดูแลและแก้ไขcodeง่าย ไม่ยุ่งยางซับซ้อน 

## 💡 บันทึกผลการทดลอง

**ขั้นตอนที่ 1 (เฉพาะ sensor.c):**
- จำนวนไฟล์ source: 4 ไฟล์
- ขนาด binary: 163041 bytes
- การทำงาน: จะโชว์อุณหภูมิเเละความชื้น
<img width="562" height="213" alt="ภาพถ่ายหน้าจอ 2568-08-06 เวลา 10 49 39" src="https://github.com/user-attachments/assets/8266a57e-7cd6-49a0-8abb-34e39fc573cf" />


**ขั้นตอนที่ 2 (เพิ่ม display.c):**
- จำนวนไฟล์ source: 6 ไฟล์
- ขนาด binary: 163925 bytes
- การทำงาน: จะเพิ่มข้อมูล value 1 เเละ 2 ซึ่งคือ อุณหภูมิเเละความชื้น
<img width="564" height="268" alt="ภาพถ่ายหน้าจอ 2568-08-06 เวลา 10 54 57" src="https://github.com/user-attachments/assets/dfca0bd5-44b5-4c75-b22f-2d0d6929ed18" />

**ขั้นตอนที่ 3 (เพิ่ม led.c):**
- จำนวนไฟล์ source: 8 ไฟล์
- ขนาด binary: 164873 bytes
- การทำงาน: จะเพิ่มสถาณะ LED เปิดปิด
<img width="562" height="368" alt="ภาพถ่ายหน้าจอ 2568-08-06 เวลา 10 57 19" src="https://github.com/user-attachments/assets/19e13f76-f894-42ec-95ae-8b43bff4b0db" />
