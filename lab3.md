# การทดลองที่3. การเขียนโปรแกรมเอ้าพุทสัญญาณดิจิทัล

# วัตถุประสงค์
1.การเขียนโปรแกรมเอ้าพุทสัญญาณดิจิทัลเพื่อสั่งทำงานบนไมโครคอนโทรเลอร์
2.การใช้ Adapter port

# อุปกรณ์ที่ใช้
1. สาย USB เชื่อมต่อ
2. ESP-01 (microcontrolor)
3. USB2Serial converter
4. adaptor port 
5. relay 
6. LED
# ศึกษาข้อมูลเบื้อต้น
-> การใช้งาน platformio https://platformio.org/

-> การเริ่มเขียนโปรแกรมภาษา C https://benzneststudios.com/blog/c-programming/c-programming-basic-1/

-> เรียนรู้ ESP-01   https://docs.platformio.org/en/latest/boards/espressif8266/esp01_1m.html

-> การต่อวงจร Microcontroller และการเขียนโปรแกรมควบคุมเบื้องต้น https://learninginventions.org/?page_id=2198
# วิธีการทำการทดลอง
1.ต่อไมโครคอนโทรเลอร์ ESP-01 เข้ากับ Adapter port 0 และ 1 จากนั้นต่อทั้งหมดเข้ากับ Serial port แล้วต่อสาย USB เข้าคอมพิวเตอร์ ![image](https://user-images.githubusercontent.com/80879968/112371332-13bc4c80-8d11-11eb-9d6a-10705204c8ba.png)

2.เตรียมโปรแกรมของตัวอย่างที่3 ที่จะลง microcontrollor 

![image](https://user-images.githubusercontent.com/80879968/112371925-bc6aac00-8d11-11eb-8057-0638374c2d25.png)

3.พิมพ์คำสั่ง pio run -t upload เพื่ออัพโหลดโปรแกรมลง microcontroller และ กด ปุ่ม upload และ ปุ่ม reset บนตัว microcontroller เพื่อรับ code ![image](https://user-images.githubusercontent.com/80879968/112372215-179c9e80-8d12-11eb-9c8c-30eee2a95e35.png)

# การบันทึกผลการทดลอง
 out put LED ที่ต่อเข้ากับ port 0 จะสว่างทุกการนับcount เลขคี่(on) หรือหลอดไฟสีเขียวจะติดไฟ และ ทุกการนับcount เลขคู่(off) หรือหลอดไฟสีเขียวจะดับ โดยผลลัพธ์ทั้งสองจะสลับกับทุกๆ1 วินาที สังเกตได้ว่าหลอดไปสีน้ำเงินไม่มีแสดงผลเนื่องจาก โปรแกรมที่เขียนสั่งให้แสดงผลแค่ port 0 เท่านั้นคือ หลอดไฟสีเขียว สามารถดูผลลัพธ์ได้ทางจอ 
 
 ![image](https://user-images.githubusercontent.com/80879968/112373512-9e05b000-8d13-11eb-8116-b7547695ca12.png)

# อภิปรายผลการทดลอง
 จากการทดลองจะเห็นได้ว่าไมโครคอนโทรเลอร์ ESP-01 สามารถส่งสัญญาญ output ไปที่ Port ต่างๆที่เชื่อมต่อได้
# คำถามหลังการทดลอง
  จงอธิบายความหมายของสัญญานดิจิทัล
    
     -เป็นสัญญาณแบบไม่ต่อเนื่อง อยู่ในรูปแบบของระดับแรงดันไฟฟ้าที่มี

      รูปคลื่นเป็นสี่เหลี่ยม สามารถแทนเลขฐานสอง “0” และ “1” ได้ สัญญาณดิจิตอลเป็น

      สัญญาณที่คอมพิวเตอร์ใช้ในการติดต่อสื่อสารกัน
