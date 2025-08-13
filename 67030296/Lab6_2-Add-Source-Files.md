~~~1. Multiple Source Files: เหตุใดต้องแยก source code เป็นหลายไฟล์?
ข้อดีของการแยกไฟล์:

จัดระเบียบโค้ด: แยกหน้าที่ตามโมดูล (sensor, display, LED) ทำให้อ่านและเข้าใจง่าย
การบำรุงรักษา: แก้ไขหรือเพิ่มฟีเจอร์ในโมดูลเดียวโดยไม่กระทบส่วนอื่น
การทำงานร่วมกัน: หลายคนสามารถพัฒนาโมดูลต่างกันพร้อมกันได้
Compilation Time: เมื่อแก้ไขโค้ดเพียงไฟล์เดียว ระบบจะ compile เฉพาะไฟล์ที่เปลี่ยน
Code Reusability: สามารถนำโมดูลไปใช้ในโปรเจคอื่นได้
Testing: ทำ Unit Testing แต่ละโมดูลได้ง่ายขึ้น


2. CMakeLists.txt Management: การเพิ่มไฟล์ source ใหม่ต้องแก้ไขอะไรบ้าง?
idf_component_register(
    SRCS 
        "main_file.c"
        "new_source_file.c"    # เพิ่มไฟล์ใหม่ที่นี่
    INCLUDE_DIRS 
        "."                    # ระบุตำแหน่ง header files
)

3. Header Files: บทบาทของไฟล์ .h คืออะไร และทำไมต้องมี?
บทบาทของ Header Files:

Function Declarations: ประกาศฟังก์ชันให้ไฟล์อื่นรู้จัก
Interface Definition: กำหนด interface ของโมดุล
Type Definitions: ประกาศ struct, enum, typedef
Include Guards: ป้องกันการ include ซ้ำ (#ifndef, #define, #endif)
Documentation: เป็นที่เก็บ comment อธิบายการใช้งาน

เหตุผลที่ต้องมี:

Compilation: Compiler ต้องรู้ function signature ก่อน compile
Linking: Linker ใช้ข้อมูลจาก header เพื่อเชื่อมโยงฟังก์ชัน
Code Organization: แยก declaration และ implementation

4. Include Directories: เหตุใด CMakeLists.txt ต้องระบุ INCLUDE_DIRS?
Search Path: บอก compiler ว่าต้องหา header files ที่ไหน
Relative Path: ใช้ "." หมายถึงโฟลเดอร์เดียวกับ CMakeLists.txt
Multiple Directories: สามารถระบุหลาย path ได้

5. Git Ignore: ไฟล์ .gitignore ช่วยอะไรในการจัดการ ESP32 project?
Repository Size: ลดขนาด repository
Collaboration: หลีกเลี่ยงการ conflict ในไฟล์ที่ generate อัตโนมัติ
Security: ป้องกันการอัปโหลดไฟล์ sensitive (*.key, *.pem)

6. Task Management: การใช้ FreeRTOS task ในโมดูล LED ช่วยอะไร?
Parallel Execution: LED สามารถกะพริบพร้อมกับงานอื่น
Independent Timing: LED มีจังหวะเวลาของตัวเอง (3 วินาที)
Non-blocking: Main loop ไม่ต้องรอ LED
Resource Management: RTOS จัดการ CPU time sharing

7. Code Organization: ข้อดีของการแยกโมดูล sensor, display, led เป็นไฟล์แยกคืออะไร?
ข้อดี:

Single Responsibility: แต่ละโมดูลมีหน้าที่เดียว
Maintainability: แก้ไข LED ไม่กระทบ sensor
Testability: ทดสอบแต่ละโมดูลแยกกันได้
Scalability: เพิ่มโมดูลใหม่ได้ง่าย
Code Reuse: นำโมดูลไปใช้ในโปรเจคอื่นได้


---------------------------------------------
บันทึกผลการทดลอง
ขั้นตอนที่ 1 (เฉพาะ sensor.c):

จำนวนไฟล์ source: 2 ไฟล์ (main + sensor.c)
ขนาด binary: ~150-200 KB
การทำงาน: Main loop + Sensor reading ทุก 2 วินาที, Status check ทุก 6 วินาที

ขั้นตอนที่ 2 (เพิ่ม display.c):

จำนวนไฟล์ source: 3 ไฟล์ (main + sensor.c + display.c)
ขนาด binary: ~155-210 KB
การทำงาน: เพิ่ม Display messages, Clear screen ทุก loop, Show data

ขั้นตอนที่ 3 (เพิ่ม led.c):

จำนวนไฟล์ source: 4 ไฟล์ (main + sensor.c + display.c + led.c)
ขนาด binary: ~160-220 KB
การทำงาน: เพิ่ม LED blinking task (3 วินาที), LED status display ~~~

