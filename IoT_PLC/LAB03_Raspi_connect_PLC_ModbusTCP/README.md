# **Lab03: Raspberry Pi connect to PLC via ModbusTCP**
Raspberry Pi เป็นบอร์ดที่ทำหน้าเหมือนคอมพิวเตอร์ขนาดเล็ก ซึ่งง่ายต่อการเพิ่มฟังก์ชันหรือพัฒนาต่อยอดให้กับระบบอุตสาหกรรมเดิมให้กลายเป็นระบบ IoT ได้ ซึ่งเราสามารถเชื่อมต่อ RaspberryPi กับ PLC ผ่าน Modbus protocol ได้

What is Modbus Protocol >> [link](https://github.com/Advance-Innovation-Centre-AIC/IIoT_Training_course/blob/main/IoT_PLC/LAB03_Raspi_connect_PLC_ModbusTCP/Modbus_Protocol.md#modbus-protocol) 

# **Key concept**
1. เพื่อเรียนรู้วิธีการตั้งค่าโปรแกรม Gxwork3 เพื่อตั้งค่า PLC Mitsubishi fx5u ใช้งาน Modbus TCP/IP 
2. เพื่อให้ผู้เรียนสามารถเข้าใช้งานบอร์ด RaspberryPi ผ่านการแสดงผลบนคอมพิวเตอร์ได้

# **Outline**
 
1. [ตั้งค่า PLC ใช้งาน Modbus TCP/IP Protocol](https://github.com/Advance-Innovation-Centre-AIC/IIoT_Training_course/tree/main/IoT_PLC/LAB03_Raspi_connect_PLC_ModbusTCP#%E0%B8%95%E0%B8%B1%E0%B9%89%E0%B8%87%E0%B8%84%E0%B9%88%E0%B8%B2-plc-%E0%B9%83%E0%B8%8A%E0%B9%89%E0%B8%87%E0%B8%B2%E0%B8%99-modbus-tcpip-protocol)
2. [การตั้งค่า Network ของ RaspberryPi]()


# **ตั้งค่า PLC ใช้งาน Modbus TCP/IP Protocol** 

1. ตั้งค่าโปรแกรมให้ PLC หน้าที่เป็น Modbus TCP/IP server
ไปที่ Navigation >>Parameter >>Module Parameter >> Ethernet Port 

![รูปภาพ: หน้า Navigation สำหรับตั้งค่าการใช้งาน modbus TCP](https://paper-attachments.dropboxusercontent.com/s_A23AB3C209E03A74945119EEB2B9EAE78A9F34C1CCEAAFE85B19F073E13F6BB0_1664258946167_image.png)

2. ไปที่หน้าต่าง Basic Settings >> Setting Item >> External Device Configuration >> ดับเบิ้ลคลิ๊กที่ >> Detailed Setting


![รูปภาพ: หน้า Setting Item](https://paper-attachments.dropboxusercontent.com/s_8A2B283F456F5748B1F6D485E5A2F0E26F88B0B4FB44EBE41B0D30BAABFF584D_1668480969556_file.png)



3. ไปที่แถบ Module List >>External Device (General)>>คลิ๊กที่ MODBUS/TCP Connection Module ค้างไว้แล้วลรากเข้าไปต่อหลัง Host Station >> กดออกจากหน้า Ethernet Configuration


![รูปภาพ: หน้า Module List](https://paper-attachments.dropboxusercontent.com/s_8A2B283F456F5748B1F6D485E5A2F0E26F88B0B4FB44EBE41B0D30BAABFF584D_1668481441587_file.png)


เราสามารถตั้งค่า Port No. และ IP ของ PLC ที่เราต้องการใช้ได้ ในที่นี้จะใช้ค่าเริ่มต้นที่กำหนดให้ Port No. คือ 502 
       

4. หลังจากเพิ่ม Modbus/TCP Connection Module สังเกตุที่หน้าต่าง Setting Item >> Modbus/TCP seting >> To Use or Not to Use MODBUS/ TCP Setting จะปรากฎคำว่า Used ที่แสดงว่า Modbus/TCP ได้เปิดใช้งานแล้ว

![รูปภาพ: หน้า Setting Item เปิดใช้งาน Modbus/TCP แล้ว](https://paper-attachments.dropboxusercontent.com/s_8A2B283F456F5748B1F6D485E5A2F0E26F88B0B4FB44EBE41B0D30BAABFF584D_1668482788219_image.png)

5. หลังจากกำหนดค่าเรียบร้อยให้ กด Apply เพื่อบันทึกการตั้งค่า


![รูปภาพ: ปุ่ม Apply หน้า Setting Item](https://paper-attachments.dropboxusercontent.com/s_8A2B283F456F5748B1F6D485E5A2F0E26F88B0B4FB44EBE41B0D30BAABFF584D_1668483716611_file.png)


       
เราสามารถดูค่า Allocation ที่ใช้สำหรับอ่านและเขียนข้อมูลจาก PLC ด้วย Modbus Protocol 

โดย ไปที่ Setting Item >> Modbus/TCP setting >> Device Assignment >> ดับเบิ้ลคลิ๊กที่ <Detailed Setting> 

![รูปภาพ: หน้า MODBUS device allocation parameter](https://paper-attachments.dropboxusercontent.com/s_8A2B283F456F5748B1F6D485E5A2F0E26F88B0B4FB44EBE41B0D30BAABFF584D_1668483390924_image.png)


[Ref. [MELSEC iQ-F FX5 User's Manual (MODBUS Communication)](https://www.mitsubishifa.co.th/files/dl/jy997d56101d_FX5(MODBUS%20Communication).pdf)]

----------
# **การตั้งค่า Network ของ RaspberryPi**
RaspberryPi จะสามารถเชื่อมต่อกับ PLC ได้จะต้องอยู่ในวง network เดียวกันและเราสามารถเข้าไปตั้งค่า RaspberryPi ได้ โดยการต่อจอและคีย์บอร์ดเข้ากับบอร์ด หรือไม่ต้องการต่อเพิ่มแต่ใช้วิธีที่เรียกว่าการ Remote เรายกตัวอย่างง่าย ๆ มี 2 วิธีดังนี้ 

## **วิธีที่1: ตั้งค่าการ Remote ผ่านวิธี Secure Shell (SSH) เข้าไปควบคุม Raspberry Pi**

1. ค้นหา IP Address ของ Raspberry Pi

หลังจากเปิด RaspberryPi และ เชื่อมต่อสายแลนด์กับ RaspberryPi ที่อยู่ในวงเดียวกันกับ PLC ของเรา เนื่องจาก Raspberry Pi OS ที่ใช้ได้ตั้งค่าเริ่มต้น รองรับ multicast Domain Name System (mDNS) โดยตั้งค่าเริ่มต้น hostname ว่า “raspberrypi” ไว้ก่อนที่ flash OS ลง SD card ดังนั้นเราสามารถ ทดสอบการเชื่อมต่อ network ระหว่าง PC กับ RaspberryPi ด้วยชื่อ hostneme ได้
 
จากแล็ปก่อนหน้านี้เราสามารถใช้โปรแกรม สแกน IP address ตามขั้นตอน ค้นหาค่า IP address ของ PLC ในก่อนหน้านี้ในการหา IP address ของ respberrypi ได้เช่นกัน
**On Linux/Windows**
คำสั่ง ทดสอบการเชื่อมต่อ network ระหว่าง PC กับ RaspberryPi
บน Linux ถ้าเราใช้ การ ping แบบใช้ hostname เราจะได้ ip address ของ Raspberry Pi มาด้วย 

```
    // hostname ของ raspberry Pi 
    ping raspberrypi.local
    // or ping <ip appdress of respberrypi>
    ping 192.168.3.101
```


![รูปภาพ: ตัวอย่างใช้ ping เพื่อทดสอบการเชื่อมต่อ  respberrypi ผ่านสายแลนด์ บน Windows](https://paper-attachments.dropboxusercontent.com/s_8A2B283F456F5748B1F6D485E5A2F0E26F88B0B4FB44EBE41B0D30BAABFF584D_1669185169812_image.png)



2. ทดลอง remote เข้า Raspberry Pi ด้วยวิธีการ Secure Shell (SSH) โดยพิมพ์คำสั่ง ssh ดังนี้

```
    // hostname ของ raspberry Pi 
    ssh pi@raspberrypi.local
    // or ping <ip appdress of respberrypi>
    ssh pi@192.168.3.101
```


3. ใส่ Password ของ Raspberry Pi คือ "raspberry"


![รูปภาพ: ตัวอย่างใช้ command line ssh to respberrypi on cmd](https://paper-attachments.dropboxusercontent.com/s_8A2B283F456F5748B1F6D485E5A2F0E26F88B0B4FB44EBE41B0D30BAABFF584D_1669186959452_image.png)



4. ทดสอบว่า Raspberry Pi เชื่อมต่อ PLC แลัว โดยพิมพ์คำสั่ง ping หา IP address ของ PLC ดังนี้

```
    ping 192.168.3.250 

```


เมื่อ ping ได้แล้วแสดงว่าเชื่อมต่อกับ PLC ได้สำเร็จแล้ว


----------
## **วิธีที่2: ตั้งค่าการ Remote ผ่านวิธี VNC Viewer เข้าไปควบคุม Raspberry Pi**

***สำหรับผู้ที่ใช้ respberry Pi ที่ไม่ต้องการต่อแป้นพิมพ์หรือจอเพิ่มต้องการแสดงหน้า Desktop  ของ RespberryPi 


1. ทำการ Remote โดยใช้วิธี SSH ก่อนหน้า
2. พิมพ์คำสั่ง สำหรับเปิดการใช้งาน VNC server บน respberry Pi ดังนี้

```
    sudo raspi-config
```

3. เมื่อปรากฎ หน้าต่างตั้งค่าแล้ว เลื่อนไป ตามภาพ a. >> Enter >>ตามภาพ b. >> Enter >>ตามภาพ c. >>  Enter
![a.](https://paper-attachments.dropboxusercontent.com/s_8A2B283F456F5748B1F6D485E5A2F0E26F88B0B4FB44EBE41B0D30BAABFF584D_1669187228353_image.png)
![b.](https://paper-attachments.dropboxusercontent.com/s_8A2B283F456F5748B1F6D485E5A2F0E26F88B0B4FB44EBE41B0D30BAABFF584D_1669187259622_image.png)

![c.](https://paper-attachments.dropboxusercontent.com/s_8A2B283F456F5748B1F6D485E5A2F0E26F88B0B4FB44EBE41B0D30BAABFF584D_1669187297365_image.png)


                                                                 *รูปภาพ: หน้า raspi-config*


4. ดาวน์โหลดและติดตั้งโปรแกรม [VNC viewer](https://www.realvnc.com/en/connect/download/viewer/) บนคอมพิวเตอร์
![รูปภาพ: Wedsite Download VNC Viewer](https://paper-attachments.dropboxusercontent.com/s_8A2B283F456F5748B1F6D485E5A2F0E26F88B0B4FB44EBE41B0D30BAABFF584D_1668489140116_image.png)



5. เปิดโปรแกรมที่ติดตั้ง


![รูปภาพ: หน้าโปรแกรม VNC Viewer](https://paper-attachments.dropboxusercontent.com/s_8A2B283F456F5748B1F6D485E5A2F0E26F88B0B4FB44EBE41B0D30BAABFF584D_1668489357686_image.png)

6. ใส่ IP address ของ RespberryPi ลงช่อง Enter a VNC Server address or search
7. เมื่อใส่รหัสผ่านของ raspberry Pi ถ้าเชื่อมต่อสำเร็จหน้า Desktop ของ raspberry pi จะแสดงขึ้นมาเราสามารถคลิ๊กเพื่อใช้งานได้เลย 


![a.](https://paper-attachments.dropboxusercontent.com/s_8A2B283F456F5748B1F6D485E5A2F0E26F88B0B4FB44EBE41B0D30BAABFF584D_1669188023123_image.png)
![b.](https://paper-attachments.dropboxusercontent.com/s_8A2B283F456F5748B1F6D485E5A2F0E26F88B0B4FB44EBE41B0D30BAABFF584D_1669187578955_image.png)
![c.](https://paper-attachments.dropboxusercontent.com/s_8A2B283F456F5748B1F6D485E5A2F0E26F88B0B4FB44EBE41B0D30BAABFF584D_1669188082753_image.png)


                                                  *รูปภาพ:การแสดงผลเชื่อมต่อ Rpi ผ่าน VNC viewer*
