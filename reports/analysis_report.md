## idf.py size
<img width="1006" height="586" alt="ภาพถ่ายหน้าจอ 2568-08-06 เวลา 09 53 11" src="https://github.com/user-attachments/assets/375d683d-277c-453a-bac1-0465fccef3a4" />

## ผลการ simulate
<img width="1440" height="900" alt="ภาพถ่ายหน้าจอ 2568-08-06 เวลา 10 06 09" src="https://github.com/user-attachments/assets/ee564bf1-a76b-4d7e-85a2-fa3f4cfae9d1" />
<img width="1440" height="900" alt="ภาพถ่ายหน้าจอ 2568-08-06 เวลา 10 06 16" src="https://github.com/user-attachments/assets/9c06e06c-0507-4e13-8775-b2901058369d" />

## 🔍 คำถามทบทวน

1. **Docker vs Native Setup**: อธิบายข้อดีของการใช้ Docker เปรียบเทียบกับการติดตั้ง ESP-IDF บน host system
2. **Build Process**: อธิบายขั้นตอนการ build ของ ESP-IDF ใน Docker container ตั้งแต่ source code จนได้ binary
3. **CMake Files**: บทบาทของไฟล์ CMakeLists.txt แต่ละไฟล์คืออะไร และทำงานอย่างไรใน Docker environment?
4. **Git Ignore**: ไฟล์ .gitignore มีความสำคัญอย่างไรสำหรับ ESP32 project development?
   เป็นการบังคับไม่ให้ไฟล์ต่างๆ ที่มีชื่อในไฟล์ .gitignore อัพโหลดไป git ซึ่งถ้าไม่ทำจะมีไฟล์ที่ไม่จำเป็นโหลดไปยัง git เยอะมาก 
5. **Container Persistence**: ข้อมูลใดบ้างที่จะหายไปเมื่อ restart container และข้อมูลใดที่จะอยู่ต่อ?
6. **Development Workflow**: เปรียบเทียบ workflow การพัฒนาระหว่างการใช้ Docker กับการทำงานบน native system
