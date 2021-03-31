# การทดลองที่ 7 เรื่อง การออกแบบและประยุกต์ใช้โปรแกรมบน microcontroller
# วัตถุประสงค์
1.รู้จักการนำ microcontroller มาประยุกต์ใช้ในชีวิตประจำวัน
2.เรียนรู้ และฝึกทักษะการเขียน code
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
* source code สำหรับ lab7 ==>  https://github.com/Gddra/lab63b/blob/main/code%20lab7
# source code

    #include <Arduino.h>

    #include <ESP8266WiFi.h>

    int cnt = 0;

    void setup()

    {

      Serial.begin(115200);

      WiFi.mode(WIFI_STA);

      WiFi.disconnect();

      pinMode(0, INPUT);  //รับสัญญานจากตัวรับแสง

      pinMode(2, OUTPUT); //ต่อกับไฟ LED สีแดง

      delay(100);

      Serial.println("\n\n\n");

    }

    void loop()

    {

      int val = digitalRead(0);

      while(val==1) {

                  Serial.println("========== Searching for Wifi ===========");

                  int n = WiFi.scanNetworks();

                  if(n == 0) {

                    Serial.println(" NETWORK NOT FOUND (Please check your network) ");

                  } else {

                    for(int i=0; i<n; i++) {

                      Serial.print(i + 1);

                      Serial.print(": ");

                      Serial.print(WiFi.SSID(i));

                      Serial.print(" (");

                      Serial.print(WiFi.RSSI(i));

                      Serial.println(")");

                      Serial.print(WiFi.channel(i));

                      delay(10);

              }

            }

            Serial.println("\n\n");

            delay(5 * 1000);

         }

      digitalWrite(2, HIGH); //แสดงไฟสถานะ LED สีแดงเปิด

    }


# วิธีการทำการทดลอง
1.ต่อไมโครคอนโทรเลอร์ ESP-01 เข้ากับ Adapter port 0 และ 1 จากนั้นต่อทั้งหมดเข้ากับ Serial port แล้วต่อสาย USB เข้าคอมพิวเตอร์ และเตรียมโปรแกรมที่จะใช้ทดลอง แล้วเชื่อมต่อวงจรตาม source code 

2.พิมพ์คำสั่ง pio run -t upload เพื่ออัพโหลดโปรแกรมลง microcontroller และ กด ปุ่ม upload และ ปุ่ม reset บนตัว microcontroller เพื่อรับ code
![image](https://user-images.githubusercontent.com/80879968/112375514-f63db180-8d15-11eb-9f5c-3b2d5ae7107f.png)

3.รออัปโหลดโปรแกรมจนครบ แล้วพิมพ์ pio device mornitor เพื่อแสดงผลลัพธ์บนจอ


4.นำเซนเซอร์รับแสงมาต่อกับ Adapter port และต่อสาย input ที่ port เดียวกับตัวรับสัญญาณเซนเซอร์แสง

![image](https://user-images.githubusercontent.com/80879968/112376686-56812300-8d17-11eb-8fd5-0cadc7d8fb5b.png)


# การบันทึกผลการทดลอง
เมื่อห้องสว่างที่จอ mornitor จะมีการอ่านค้นหาสัญญาน wifi ไปเรื่อยๆ แต่เมื่อในห้องมืดจะหยุดการค้นหา wifi และขึ้นไฟสีแดงแสดงสถานะ
# อภิปรายผลการทดลอง
จากการทดลอง การติดหรือดับของ LED และการทำงานหาสัญญาน wifi ขึ้นอยู่กับสัญญาน inputที่ได้จากเซนเซอร์รับแสง
# คำถามหลังการทดลอง
  จงยกตัวอย่างประโยชน์ของระบบควบคุมอัตโนมัติ
    
    -เพิ่มความสะดวกสะบายให้แก่ผู้ใช้งาน
