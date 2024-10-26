# ESP32 LEDC Fade Example - `ledc.fade`
โดย ledc_fade เป็นไลบรารีของ ESP32 เพื่อควบคุมการหรี่ไฟของ LED ที่เชื่อมต่ออยู่กับบอร์ด ESP32 โดยการเปลี่ยนแปลงความเข้มของแสง LED อย่างช้าๆ เพื่อให้เกิดเอฟเฟกต์การหรี่ไฟ ซึ่งสามารถทำได้โดยการปรับค่า Duty Cycle ของสัญญาณ PWM (Pulse Width Modulation) ที่ควบคุม LED
## ขั้นตอนการใช้งาน
1. เริ่มต้นโดยการเลือกตัวอย่าง `ledc.fade`
# ![Screenshot 2024-10-27 035741](https://github.com/user-attachments/assets/5848894c-f58f-4151-a076-5565a771822b)

# ![Screenshot 2024-10-27 040633](https://github.com/user-attachments/assets/9760fa84-4888-476f-93e0-9f3907bb83ae)

2. หลังจากเลือกตัวอย่างแล้ว ให้กดปุ่ม **Create**
# ![Screenshot 2024-10-27 040711](https://github.com/user-attachments/assets/60d18738-5351-4e98-a8a8-2bcdfc4e8342)

3. ตรวจสอบโค้ดในไฟล์ `main.c`
# ![Screenshot 2024-10-27 041002](https://github.com/user-attachments/assets/da5e51a0-5337-46d4-8bf6-fa10aca523df)
# ![Screenshot 2024-10-27 040840](https://github.com/user-attachments/assets/03e73f71-c5cd-43d8-bc5b-67abd907ea33)


### การต่อสายไฟ

ต่อ LED ตาม GPIO ดังนี้:

| GPIO Pin | LED  |
|----------|------|
| GPIO 18  | LED 1|
| GPIO 19  | LED 2|
| GPIO 4   | LED 3|
| GPIO 5   | LED 4|


## การรันโปรแกรม

กด Build และรันโปรแกรม จากนั้นเลือก **UART**

### ผลลัพธ์ที่ได้
ผลลัพธ์จากการรันจะมีลักษณะดังนี้:
# ![Screenshot 2024-10-27 041705](https://github.com/user-attachments/assets/12923357-dff6-4dac-af12-398f405b0723)
# ![Screenshot 2024-10-27 042331](https://github.com/user-attachments/assets/095dfcf1-4e6f-4a20-aaaa-15fb2bef9a47)

ตัวอย่างคลิปวิดีโอ
# https://drive.google.com/file/d/1NpNbqrlGodH6-1CDzuCmTdsoyTsczfeO/view?usp=sharing


### การเเก้ไขการปรับความเร็วในการหรี่ไฟ: สามารถปรับความเร็วของการค่อยๆสว่างค่อยๆดับได้
สามารถปรับความเร็วของการค่อย ๆ หรี่ไฟโดยเปลี่ยนค่าเวลาการหรี่ในโค้ด:
```
#define LEDC_TEST_FADE_TIME    (3000)
```
ค่าเริ่มต้นกำหนดไว้ที่ 3000 มิลลิวินาที (3 วินาที) หากต้องการให้ความเร็วในการหรี่ไฟเพิ่มขึ้น สามารถเปลี่ยนค่าเป็น 1000 มิลลิวินาที (1 วินาที) ดังนี้
```
#define LEDC_TEST_FADE_TIME    (1000)
```
# ตัวอย่างการปรับ define LEDC_TEST_FADE_TIME    (3000) เป็น (1000)
# https://drive.google.com/file/d/1iwikTHEop0ah5jd6wFmYZ89cIgCAVY-_/view?usp=sharing
### สรุปการทดลอง
ฟังก์ชัน ledc_fade บน ESP32 เป็นฟังก์ชันที่ช่วยให้คุณสามารถควบคุมการหรี่ไฟของ LED ได้อย่างราบรื่น โดยใช้หลักการของ Pulse Width Modulation (PWM) ซึ่งเป็นเทคนิคที่ช่วยสร้างสัญญาณเอาต์พุตที่สามารถปรับความเข้มของแสงไฟหรือควบคุมมอเตอร์ไฟฟ้าได้อย่างมีประสิทธิภาพและยืดหยุ่น การทำงานของ ledc_fade จะปรับค่า Duty Cycle ของ PWM แบบค่อยเป็นค่อยไปเพื่อให้เกิดการเปลี่ยนแปลงความเข้มแสงของ LED อย่างราบรื่นในระยะเวลาที่กำหนด
