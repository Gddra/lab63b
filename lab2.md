# การทดลองที่2. การเขียนโปรแกรมค้นหาไวไฟ

## วัตถุประสงค์
1. เพื่อใช้ในการค้นหาสัญญานไวไฟบริเวณรอบๆ และ บอกความแรงของสัญญาณไวไฟบริเวณนั้น

## อุปกรณ์ที่ใช้
1. อุปกรณต่อ USB
2. ESP-01 (microcontrolor)
3. USB2Serial converter
4. คอมพิวเตอร์

## ศึกษาข้อมูลเบื้อต้น
-> การใช้งาน platformio https://platformio.org/

-> การเริ่มเขียนโปรแกรมภาษา C https://benzneststudios.com/blog/c-programming/c-programming-basic-1/

-> เรียนรู้ ESP-01   https://docs.platformio.org/en/latest/boards/espressif8266/esp01_1m.html

-> การต่อวงจร Microcontroller และการเขียนโปรแกรมควบคุมเบื้องต้น https://learninginventions.org/?page_id=2198

## วิธีการทำการทดลอง
1. เตรียมโปรแกรมที่จะลง microcontrollor  มี2 ส่วน คือส่วน void set up เพื่อ set up ตัว wifi และส่วน void loop เพื่อการทำงานแบบวนไปเรื่อยๆ
2.พิมพ์ pio run -t upload เพื่ออัพโหลด source code ลงใน microcontroller และ กด ปุ่ม upload และ ปุ่ม reset บนตัว microcontroller เพื่อรับ code ![image](https://user-images.githubusercontent.com/80879968/112363557-39912380-8d08-11eb-82f6-3475404e3360.png)

3. รออัปโหลดโปรแกรมจนครบ แล้วพิมพ์ pio device mornitor  เพื่อแสดงผลการค้นหา wifi ที่เจอรอบๆ ขึ้นอยู่กับความแรงของสัญญาน ![image](https://user-images.githubusercontent.com/80879968/112363764-6fcea300-8d08-11eb-8149-2e58c8f018ac.png)
![image](https://user-images.githubusercontent.com/80879968/112365020-bbce1780-8d09-11eb-9424-56ebad54cce4.png)


## การบันทึกผลการทดลอง
การทดลองค้นหาไวไฟบริเวณรอบๆ microcontrollor ปรากฏว่าผลลัพธ์ wifi ทีเจอนั้น ขึ้นกับความแรงของสัญญาณที่ได้รับ จากที่ปราฏกให้เห็นจะมี MASTER BEDROOM 2.4GHz (-89),TEN (-80) , Homiebody(-90) เป็นต้น
## อภิปรายผลการทดลอง
การทดลองค้นหาสัญญาณไวไฟบริเวณรอบๆพบว่ามีข้อผิดพลาดในการต่อวงจรทำให้วงจรไม่สมบูรณ์ในตอนแรกจึงต้องทำการต่อให้และรันโปรแกรมใหม่ เพื่อให้ได้ผลลัพธ์ตามที่ต้องการ โดยโปรแกรมที่เขียนออกมาจะมี 2 part คือใช้ในการ void set up เพื่อ set ค่าต่างๆ และ void loop ใช้ในการสั่งงานค้นหาไวไฟไปเรื่อยๆ
## คำถามหลังการทดลอง
  จงอธิบายความหมายของสัญญาน wifi 
     
     -เครือข่ายไร้สาย มักใช้กับระบบเครือข่าย ไม่ว่าจะเป็นในองค์กรหรือในระบบเครือข่ายอินเตอร์เน็ต หรือพูดแบบง่ายๆก็คือWiFiก็คือคลื่นสัญญาณวิทยุ

