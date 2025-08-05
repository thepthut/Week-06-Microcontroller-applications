# Lab Exercise 1: สร้าง Basic ESP32 Project Structure

## วัตถุประสงค์
เรียนรู้การสร้างโครงสร้าง project ESP32 แบบ standard และเข้าใจการทำงานของ CMake build system

## ขั้นตอนการทำ Lab

### 1. การติดตั้ง ESP-IDF (ถ้ายังไม่ได้ติดตั้ง)

```bash
# Windows: ดาวน์โหลด ESP-IDF Installer
# หรือติดตั้งผ่าน command line

git clone --recursive https://github.com/espressif/esp-idf.git
cd esp-idf
./install.bat esp32
./export.bat
```

### 2. สร้าง Project ใหม่

```bash
# เปิด ESP-IDF Command Prompt
cd C:\your_workspace_path

# สร้าง project ใหม่
idf.py create-project lab1_basic_build

cd lab1_basic_build
```

### 3. ศึกษาโครงสร้าง Project ที่สร้างขึ้น

```
lab1_basic_build/
├── CMakeLists.txt          # Top-level CMake configuration
├── main/                   # Main application directory
│   ├── CMakeLists.txt     # Main component CMake file
│   └── lab1_basic_build.c # Main source file (auto-generated)
└── README.md              # Project documentation
```

### 4. แก้ไข main/lab1_basic_build.c

```c
#include <stdio.h>
#include "freertos/FreeRTOS.h"
#include "freertos/task.h"
#include "esp_system.h"
#include "esp_log.h"

static const char *TAG = "LAB1";

void app_main(void)
{
    ESP_LOGI(TAG, "Lab 1: Basic ESP32 Project Structure");
    ESP_LOGI(TAG, "ESP-IDF Version: %s", esp_get_idf_version());
    ESP_LOGI(TAG, "Free heap size: %d bytes", esp_get_free_heap_size());
    
    int counter = 0;
    
    while (1) {
        ESP_LOGI(TAG, "Build system test - Counter: %d", counter++);
        vTaskDelay(pdMS_TO_TICKS(2000)); // 2 seconds delay
    }
}
```

### 5. ศึกษาไฟล์ CMakeLists.txt

#### Top-level CMakeLists.txt
```cmake
# The following lines of boilerplate have to be in your project's
# CMakeLists.txt, at minimum.
cmake_minimum_required(VERSION 3.16)

include($ENV{IDF_PATH}/tools/cmake/project.cmake)
project(lab1_basic_build)
```

#### main/CMakeLists.txt
```cmake
idf_component_register(SRCS "lab1_basic_build.c"
                       INCLUDE_DIRS ".")
```

### 6. การ Build Project

```bash
# Configure project (first time only)
idf.py set-target esp32

# Build project
idf.py build

# Check build output
ls build/
```

### 7. การวิเคราะห์ Build Output

```bash
# ดูขนาด binary
idf.py size

# ดูรายละเอียดขนาดตาม component
idf.py size-components

# ดูรายละเอียดขนาดตาม source file
idf.py size-files
```

### 8. การ Flash และทดสอบ

```bash
# Flash ไปยัง ESP32 (เปลี่ยน COM3 เป็น port ที่ถูกต้อง)
idf.py -p COM3 flash

# Monitor output
idf.py -p COM3 monitor

# หรือ flash และ monitor พร้อมกัน
idf.py -p COM3 flash monitor
```

## การทดลองเพิ่มเติม

### 1. เพิ่ม Build Information

แก้ไข main/lab1_basic_build.c เพื่อแสดงข้อมูล build:

```c
#include <stdio.h>
#include "freertos/FreeRTOS.h"
#include "freertos/task.h"
#include "esp_system.h"
#include "esp_log.h"

static const char *TAG = "LAB1";

void print_build_info(void)
{
    ESP_LOGI(TAG, "=== Build Information ===");
    ESP_LOGI(TAG, "Project Name: lab1_basic_build");
    ESP_LOGI(TAG, "ESP-IDF Version: %s", esp_get_idf_version());
    ESP_LOGI(TAG, "Compile Date: %s", __DATE__);
    ESP_LOGI(TAG, "Compile Time: %s", __TIME__);
    ESP_LOGI(TAG, "Chip Model: %s", CONFIG_IDF_TARGET);
    ESP_LOGI(TAG, "Free Heap: %d bytes", esp_get_free_heap_size());
}

void app_main(void)
{
    print_build_info();
    
    int counter = 0;
    
    while (1) {
        ESP_LOGI(TAG, "Running... Counter: %d", counter++);
        
        // แสดงสถานะ memory ทุกๆ 10 ครั้ง
        if (counter % 10 == 0) {
            ESP_LOGI(TAG, "Current free heap: %d bytes", esp_get_free_heap_size());
        }
        
        vTaskDelay(pdMS_TO_TICKS(1000));
    }
}
```

### 2. เพิ่ม Preprocessor Definitions

แก้ไข main/CMakeLists.txt:

```cmake
idf_component_register(
    SRCS "lab1_basic_build.c"
    INCLUDE_DIRS "."
)

# เพิ่ม custom definitions
target_compile_definitions(${COMPONENT_LIB} PRIVATE
    PROJECT_VERSION_MAJOR=1
    PROJECT_VERSION_MINOR=0
    BUILD_NUMBER=1
)
```

แล้วใช้ใน source code:

```c
void print_version_info(void)
{
    ESP_LOGI(TAG, "Project Version: %d.%d.%d", 
             PROJECT_VERSION_MAJOR, PROJECT_VERSION_MINOR, BUILD_NUMBER);
}
```

## คำถามทบทวน

1. **Build Process**: อธิบายขั้นตอนการ build ของ ESP-IDF ตั้งแต่ source code จนได้ binary
2. **CMake Files**: บทบาทของไฟล์ CMakeLists.txt แต่ละไฟล์คืออะไร?
3. **Build Targets**: แต่ละ build target (build, flash, monitor) ทำหน้าที่อะไรบ้าง?
4. **Memory Analysis**: จากผลลัพธ์ของ `idf.py size` สามารถวิเคราะห์อะไรได้บ้าง?

## ผลลัพธ์ที่คาดหวัง

เมื่อทำ lab สำเร็จ นักเรียนจะ:
- เข้าใจโครงสร้าง project ESP32 standard
- สามารถใช้คำสั่ง idf.py เบื้องต้นได้
- เข้าใจ build process และสามารถวิเคราะห์ build output ได้
- สามารถแก้ไข CMakeLists.txt เพื่อปรับแต่ง build configuration

## การแก้ไขปัญหาที่พบบ่อย

### ปัญหา: CMake Error
```
CMake Error: CMAKE_C_COMPILER not set
```
**วิธีแก้**: ตรวจสอบว่าได้รัน export script แล้ว (`export.bat` หรือ `export.sh`)

### ปัญหา: Permission Denied
```
Permission denied: 'COM3'
```
**วิธีแก้**: ปิด Serial Monitor หรือโปรแกรมอื่นที่ใช้ COM port

### ปัญหา: Target not set
```
Target is not set, please run 'idf.py set-target <target>'
```
**วิธีแก้**: รันคำสั่ง `idf.py set-target esp32`
