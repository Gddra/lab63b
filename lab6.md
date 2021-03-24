# การทดลองที่ 6 เรื่อง การเขียนโปรแกรมสร้างไวไฟแอคเซสพอยต์ (Wifi AP)

# วัตถุประสงค์
1. ศึกษาการเขียนโปรแกรมสร้างไวไฟ 
2. สามารถต่อไวไฟที่เราสร้างขึ้นมาเองได้จากโทรศัพท์มือถือ 
3. ศึกษาความหมายของแอคเซสพอยต์
# อุปกรณ์ที่ใช้
1. ESP-01 (microcontrolor)
2. USB2Serial converter
3. สาย USB
4. คอมพิวเตอร์
5. โทรศัพท์มือถือ
# ศึกษาข้อมูลเบื้อต้น
1. การใช้งาน platformio https://platformio.org/
2. การเริ่มเขียนโปรแกรมภาษา C https://benzneststudios.com/blog/c-programming/c-programming-basic-1/
3. เรียนรู้ ESP-01 https://docs.platformio.org/en/latest/boards/espressif8266/esp01_1m.html
4. การต่อวงจร Microcontroller และการเขียนโปรแกรมควบคุมเบื้องต้น https://learninginventions.org/?page_id=2198
5. 06 run wiri AP https://www.youtube.com/watch?v=T26DVHePlTs
# วิธีการทำการทดลอง
1. ต่อไมโครคอนโทรเลอร์ ESP-01 เข้ากับ Adapter port 0 และ 1 จากนั้นต่อทั้งหมดเข้ากับ Serial port แล้วต่อสาย USB เข้าคอมพิวเตอร์ และเตรียมโปรแกรมที่จะใช้ทดลองตามนี้

![image](https://user-images.githubusercontent.com/80879968/112381764-8b907400-8d1d-11eb-9f41-68d48508fa02.png)

![image](https://user-images.githubusercontent.com/80879968/112381909-bc70a900-8d1d-11eb-9082-a312ebc4496b.png)

2. พิมพ์คำสั่ง pio run -t upload เพื่ออัพโหลดโปรแกรมลง microcontroller และ กด ปุ่ม upload และ ปุ่ม reset บนตัว microcontroller เพื่อรับ code

![image](https://user-images.githubusercontent.com/80879968/112382024-e5913980-8d1d-11eb-82f2-c3408d0ecaf6.png)

3. รออัปโหลดโปรแกรมจนครบ แล้วพิมพ์ pio device mornitor เพื่อแสดงผลลัพธ์บนจอ

![image](https://user-images.githubusercontent.com/80879968/112382110-06f22580-8d1e-11eb-942d-fdee92b43501.png)

4.ใช้โทรศัพท์มือถือค้นหาสัญญาณไวไฟ

![image](https://user-images.githubusercontent.com/80879968/112382237-3143e300-8d1e-11eb-9297-68bc81feaeb7.png)



# การบันทึกผลการทดลอง
การทดลองพบว่า microcontroller สามารถสร้าง wifi ขึ้นมาได้ และสามารถเชื่อมต่อ wifi ทางโทรศัพท์ โดยทำการใส่รหัสผ่าน
# อภิปรายผลการทดลอง
การเขียนโปรแกรมสร้างไวไฟแอคเซสพอยต์ (Wifi AP) โดยเราทำการสร้างไวไฟจาก ESP-01 โดยเปลื่อยชื่อเป็นชื่อที่ต้องการและกำหนดรหัสผ่านตามที่กำหนด โดยเราจะกำหนด IP Address และ สร้าง access point 
การทดสอบโดยการเชื่อต่อไวไฟทางโทรศัพท์ ทำการใส่รหัสผ่านและเข้าใช้งานอินเตอร์เน็ตได้
# คำถามหลังการทดลอง
จงอธิบายความหมายของไวไฟแอคเซสพอยต์ (Wifi AP)

  - อุปกรณ์ในเครือข่ายคอมพิวเตอร์ ที่ช่วยให้อุปกรณ์ไร้สายสามารถเชื่อมต่อกับเครือข่ายแบบมีสายได้โดยการใช้เทคโนโลยีของแลนไร้สาย หรือ มาตรฐานอื่นๆที่เกี่ยวข้อง

