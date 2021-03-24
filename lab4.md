# การทดลองที่ 4 เรื่อง การเขียนโปรแกรมอินพุทสัญญาณดิจิทัล
# วัตถุประสงค์
1.รู้จักวิธีการนำสัญญาน input จากภายนอกมาใช้กับ microcontroller
2.สามารถดู input output ผ่านเซนเซอร์ของสภาพแวดล้อม
# อุปกรณ์ที่ใช้
1. ESP-01 (microcontrolor)
2. USB2Serial converter
3. adaptor port
4. เซนเซอร์รับแสง
5. สาย USB 
6. LED
# ศึกษาข้อมูลเบื้อต้น
* การใช้งาน platformio https://platformio.org/
* การเริ่มเขียนโปรแกรมภาษา C https://benzneststudios.com/blog/c-programming/c-programming-basic-1/
* เรียนรู้ ESP-01   https://docs.platformio.org/en/latest/boards/espressif8266/esp01_1m.html
* การต่อวงจร Microcontroller และการเขียนโปรแกรมควบคุมเบื้องต้น https://learninginventions.org/?page_id=2198
* การใช้เซนเซอร์ http://horizon.sti.or.th/node/53
# วิธีการทำการทดลอง
1.ต่อไมโครคอนโทรเลอร์ ESP-01 เข้ากับ Adapter port 0 และ 1 จากนั้นต่อทั้งหมดเข้ากับ Serial port แล้วต่อสาย USB เข้าคอมพิวเตอร์ และเตรียมโปรแกรมที่จะใช้ทดลอง แล้วเชื่อมต่อวงจรตาม source code 

![image](https://user-images.githubusercontent.com/80879968/112375191-947d4780-8d15-11eb-9c82-4b235bb75ef9.png)

3.พิมพ์คำสั่ง pio run -t upload เพื่ออัพโหลดโปรแกรมลง microcontroller และ กด ปุ่ม upload และ ปุ่ม reset บนตัว microcontroller เพื่อรับ code

![image](https://user-images.githubusercontent.com/80879968/112375514-f63db180-8d15-11eb-9f5c-3b2d5ae7107f.png)


4.รออัปโหลดโปรแกรมจนครบ แล้วพิมพ์ pio device mornitor เพื่อแสดงผลลัพธ์บนจอ

![image](https://user-images.githubusercontent.com/80879968/112376460-1326b480-8d17-11eb-9655-03073f582369.png)

5.นำเซนเซอร์รับแสงมาต่อกับ Adapter port และต่อสาย input ที่ port เดียวกับตัวรับสัญญาณเซนเซอร์แสง

![image](https://user-images.githubusercontent.com/80879968/112376686-56812300-8d17-11eb-8fd5-0cadc7d8fb5b.png)


# การบันทึกผลการทดลอง
เมื่อยังไม่ได้ทำการต่อเซนเซอร์แสง เมื่อทำการนำสาย input แตะไปที่ port 0 LED ก็จะสว่าง และเมื่อนำออก LED ก็จะดับ และเมื่อทำการต่อเซนเซอร์แสง ถ้าเรานำเซนเซอร์ถูกแสงสว่างไฟ LED ก็จะสว่าง ถ้าใช้มือปิดไฟ LED ก็จะดับ
# อภิปรายผลการทดลอง
จากการทดลอง การติดหรือดับของ LED ขึ้นอยู่กับการตั้งค่าไมโครคอนโทรเลอร์ว่าจะรับสัญญานจาก port ไหนเป็น input 
# คำถามหลังการทดลอง
  จงอธิบายความหมายของเซ็นเซอร์แสง และยกตัวอย่างประโยชน์
    
    -เป็นตัวต้านทานที่ค่าความต้านทาน ซึ่งค่าตัวต้านทานจะเปลี่ยนไปตามความเข้มของแสงที่ตกกระทบ ประโยชน์ที่เห็นได้ชัดเลยมักจะเอาไปใช้กับวงจร เปิด-ปิด ไฟอัตโนมัติ 
