# การทดลองที่ 1 เรื่อง การเขียนโปรแกรมเพื่อรันบนไมโครคอนโทรเลอร์

# วัตถุประสงค์ 
  1.เพื่อให้รู้จัก microcontroller 
  
  2.เพื่อศึกษาการเขียนโปรแกรมเพื่อใช้งาน microcontroller 
  
  3.เพื่อศึกษาให้เข้าใจหลักการติดตั้ง Firmware ลงในไมโครคอนโทรล์เลอร์ผ่าน Hardware Programmer และผ่าน Bootloader 

# อุปกรณ์ที่ใช้
1.microcontroller ESP-01

2.serial port

3.สาย USB เชื่อมต่อ

4.คอมพิวเตอร์

# ศึกษาข้อมูลเบื้องต้น
  -> การใช้งาน platformio https://platformio.org/
  
  -> การเริ่มเขียนโปรแกรมภาษา C https://benzneststudios.com/blog/c-programming/c-programming-basic-1/
  
  -> เรียนรู้ ESP-01   https://docs.platformio.org/en/latest/boards/espressif8266/esp01_1m.html
  
  -> การต่อวงจร Microcontroller และการเขียนโปรแกรมควบคุมเบื้องต้น https://learninginventions.org/?page_id=2198
 
 # วิธีการทำการทดลอง
  1.ต่อmicrocontrollor กับ USB เชื่อมเข้ากับคอมพิวเตอร์เพิ่เขียนโปรแกรมรันบน ESP-01 ![image](https://user-images.githubusercontent.com/80879968/112357621-490d6e00-8d02-11eb-927a-38bb4ff79fa3.png)

  2.เปิด source code ที่จะอัพโหลดลง microcontroller แล้ว พิมพ์ pio run -t upload เพื่ออัพโหลด source code ลงใน microcontroller ![image](https://user-images.githubusercontent.com/80879968/112359942-62afb500-8d04-11eb-8e38-59a4077bc917.png)
  
  3.กด ปุ่ม upload และ ปุ่ม reset บนตัว microcontroller เพื่อรับ code 

  4.เมื่อ upload เสร็จแล้ว พิมพ์ pio divice monitor เพื่อแสดงผล ![image](https://user-images.githubusercontent.com/80879968/112360748-39435900-8d05-11eb-893c-a8e2e994bc44.png)

# การบันทึกผลการทดลอง
    ค่าที่รันออกมาจาก ESP-01 จะเป็นค่าcount ที่นับไปเรื่อยๆโดยมีระยะห่างที่1 วินาที เมื่อกดปุ่มรีเซ็ตก็จะมีการเริ่มนับ 1ใหม่
    
# อภิปรายผลการทดลอง
     ค่าที่ได้จากโปรแกรมที่แสดงผลออกมาจะเป็นโปรแกรมที่ถูกเขียนขึ้นจากคอมพิวเตอร์แล้วนำมา upload ลงใน microcontrollor(ESP-01) แล้วนำมาประมวลผลได้ผลลัพธ์ออกมา
     
# คำถามหลังการทดลอง
   จงอธิบายความหมายของ microcontroller 
       
     - เป็นอุปกรณ์ควบคุมขนาดเล็ก ซึ่งบรรจุความสามารถที่คล้ายคลึงกับระบบคอมพิวเตอร์
