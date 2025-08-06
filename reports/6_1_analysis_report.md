## idf.py size
<img width="1006" height="586" alt="ภาพถ่ายหน้าจอ 2568-08-06 เวลา 09 53 11" src="https://github.com/user-attachments/assets/375d683d-277c-453a-bac1-0465fccef3a4" />

## ผลการ simulate
<img width="1440" height="900" alt="ภาพถ่ายหน้าจอ 2568-08-06 เวลา 10 06 09" src="https://github.com/user-attachments/assets/ee564bf1-a76b-4d7e-85a2-fa3f4cfae9d1" />
<img width="1440" height="900" alt="ภาพถ่ายหน้าจอ 2568-08-06 เวลา 10 06 16" src="https://github.com/user-attachments/assets/9c06e06c-0507-4e13-8775-b2901058369d" />

## 🔍 คำถามทบทวน

1. **Docker vs Native Setup**: อธิบายข้อดีของการใช้ Docker เปรียบเทียบกับการติดตั้ง ESP-IDF บน host system
   
   ไม่ต้องติดตั้งเครื่องมือเอง มี ESP-IDF และ dependencies พร้อมใช้งาน ใช้หลายเวอร์ชันได้ง่าย สลับ ESP-IDF version โดยไม่ชนกัน เหมาะกับการทำงานเป็นทีม รองรับหลายระบบปฏิบัติการ
   
2. **Build Process**: อธิบายขั้นตอนการ build ของ ESP-IDF ใน Docker container ตั้งแต่ source code จนได้ binary

   1.เตรียม Source Code 

      นำโปรเจกต์ ESP-IDF ที่มี CMakeLists.txt และ main/ พร้อม source code เข้าไปใน container

   2.เข้าสู่ Docker Container ใช้คำสั่ง docker-compose exec esp32-dev

   3.ตั้งค่า Environment ใช้คำสั่ง . $IDF_PATH/export.sh

   4.Build Project ใช้คำสั่ง idf.py build

   5.จะได้ Binary 
   
3. **CMake Files**: บทบาทของไฟล์ CMakeLists.txt แต่ละไฟล์คืออะไร และทำงานอย่างไรใน Docker environment?
   
   CMakeLists.txt นอก main บอกว่าใช้ CMake เวอร์ชันขั้นต่ำเท่าไหร่ สั่งให้ CMake โหลดระบบ build ของ ESP-IDF เชื่อมระบบกับ ESP-IDF SDK บังคับใช้ component build systemตั้งชื่อโปรเจกต์ lab6_2_multiple_files

   CMakeLists.txt ใน main  ลงทะเบียน component กับระบบ build บอกว่า component นี้มี source files  อะไรบ้าง ที่ต้องนำไป compile บอกว่าไฟล์ header ของ component นี้อยู่ที่ไหนเป็นจุดเริ่มต้นที่สำคัญที่สุดของระบบ build

4. **Git Ignore**: ไฟล์ .gitignore มีความสำคัญอย่างไรสำหรับ ESP32 project development?

   เป็นการบังคับไม่ให้ไฟล์ต่างๆ ที่มีชื่อในไฟล์ .gitignore อัพโหลดไป git ซึ่งถ้าไม่ทำจะมีไฟล์ที่ไม่จำเป็นโหลดไปยัง git เยอะมาก 

5. **Container Persistence**: ข้อมูลใดบ้างที่จะหายไปเมื่อ restart container และข้อมูลใดที่จะอยู่ต่อ?

    ข้อมูลที่อยู่ใน Docker volume หรือ bind mount  Image ของ container Dockerfile settings / ENV / IDF_PATH

6. **Development Workflow**: เปรียบเทียบ workflow การพัฒนาระหว่างการใช้ Docker กับการทำงานบน native system

   Docker เหมาะกับทีมพัฒนาที่ต้องการ environment เหมือนกันทุกเครื่องและจัดการ dependency ง่าย เน้นความร่วมมือในทีมและต้องการความเสถียรของ environment 

   Native system เหมาะกับงานที่ต้องการประสิทธิภาพสูงหรือเข้าถึงฮาร์ดแวร์โดยตรง เน้นประสิทธิภาพสูง
