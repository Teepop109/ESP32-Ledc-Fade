# ESP32-Ledc-Fade
# โปรเจค ESP32-Ledc-Fade Example จะมีชื่อว่า ledc.fade
โดย ledc_fade เป็นไลบรารีของ ESP32 เพื่อควบคุมการหรี่ไฟของ LED ที่เชื่อมต่ออยู่กับบอร์ด ESP32 โดยการเปลี่ยนแปลงความเข้มของแสง LED อย่างช้าๆ เพื่อให้เกิดเอฟเฟกต์การหรี่ไฟ ซึ่งสามารถทำได้โดยการปรับค่า Duty Cycle ของสัญญาณ PWM (Pulse Width Modulation) ที่ควบคุม LED
ขั้นตอนแรกเลือก Example
1. เริ่มต้นโดยการเลือกตัวอย่าง `ledc.fade`
# ![image](https://github.com/user-attachments/assets/e9db595c-d29e-463a-8d17-4dd28ab9ef3c)
# ![Screenshot 2024-10-27 035741](https://github.com/user-attachments/assets/ce3593b0-db3f-4ec4-9540-3dcc5620d17b)
2. หลังจากเลือกตัวอย่างแล้ว ให้กดปุ่ม **Create**
# ![image](https://github.com/user-attachments/assets/1ab90257-cabd-4ac8-ba58-56bba0423c7b)
3. ตรวจสอบโค้ดในไฟล์ `main.c`
# ![image](https://github.com/user-attachments/assets/2b0e952b-1147-4b34-ab33-554ed76545cd)
### การต่อสายไฟ

ต่อ LED ตาม GPIO ดังนี้:

| GPIO Pin | LED  |
|----------|------|
| GPIO 18  | LED 1|
| GPIO 19  | LED 2|
| GPIO 4   | LED 3|
| GPIO 5   | LED 4|
# ![Screenshot 2024-10-27 040840](https://github.com/user-attachments/assets/d7e76d43-de68-4659-9ff6-dc1b77f7b511)

## การรันโปรแกรม

กด Build และรันโปรแกรม จากนั้นเลือก **UART**
# ![image](https://github.com/user-attachments/assets/fa92b29f-64da-4891-89c2-ec5d61988e47)


### ผลลัพธ์ที่ได้
# ![image](https://github.com/user-attachments/assets/0c98c72a-96a0-4ad2-a47e-d964bb2be0e0)
ตัวอย่างคลิปวิดีโอ
# https://drive.google.com/file/d/1NpNbqrlGodH6-1CDzuCmTdsoyTsczfeO/view?usp=sharing


# สามารถปรับความเร็วของการค่อยๆสว่างค่อยๆดับได้

# ![image](https://github.com/user-attachments/assets/e6ad513a-d5f4-457a-825c-b40d7b506662)
# ![image](https://github.com/user-attachments/assets/f6299fd5-79fb-4771-82fb-f18d32fa65dd)

```
#define LEDC_TEST_FADE_TIME    (3000)
```
สามารถเปลี่ยนเป็นค่าที่ต้องการได้โดยการปรับเเต่งที่ให้มา คือ 3000 เเสดงว่า 3 วินาที ถ้าหากเราต้องการปรับเเต่งก็สามารถทำได้ เช่น ต้องการให้เร็วขึ้นก็เปลี่ยนจาก 3000 เป็น 1000 
# ตัวอย่างการปรับ define LEDC_TEST_FADE_TIME    (3000) เป็น (1000)
# https://drive.google.com/file/d/1iwikTHEop0ah5jd6wFmYZ89cIgCAVY-_/view?usp=sharing
# สรุปการทดลอง
ฟังก์ชัน ledc_fade บน ESP32 เป็นฟังก์ชันที่ช่วยให้คุณสามารถควบคุมการหรี่ไฟของ LED ได้อย่างราบรื่น โดยใช้หลักการของ Pulse Width Modulation (PWM) ซึ่งเป็นเทคนิคที่ช่วยสร้างสัญญาณเอาต์พุตที่สามารถปรับความเข้มของแสงไฟหรือควบคุมมอเตอร์ไฟฟ้าได้อย่างมีประสิทธิภาพและยืดหยุ่น การทำงานของ ledc_fade จะปรับค่า Duty Cycle ของ PWM แบบค่อยเป็นค่อยไปเพื่อให้เกิดการเปลี่ยนแปลงความเข้มแสงของ LED อย่างราบรื่นในระยะเวลาที่กำหนด
