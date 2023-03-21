# LAB01-Pre: Setup PLC workspace 

# **Outline**

[Step1: Install GXWork3](https://github.com/Advance-Innovation-Centre-AIC/IIoT_Training_course/tree/main/IoT_PLC/LAB01_Pre_Setup#step-1-%E0%B8%95%E0%B8%B4%E0%B8%94%E0%B8%95%E0%B8%B1%E0%B9%89%E0%B8%87%E0%B9%82%E0%B8%9B%E0%B8%A3%E0%B9%81%E0%B8%81%E0%B8%A3%E0%B8%A1-gx-work3)

[Step2: Connect PLC with GXwork3](https://github.com/Advance-Innovation-Centre-AIC/IIoT_Training_course/tree/main/IoT_PLC/LAB01_Pre_Setup#step-1-%E0%B8%95%E0%B8%B4%E0%B8%94%E0%B8%95%E0%B8%B1%E0%B9%89%E0%B8%87%E0%B9%82%E0%B8%9B%E0%B8%A3%E0%B9%81%E0%B8%81%E0%B8%A3%E0%B8%A1-gx-work3) 


# **Step1: ติดตั้งโปรแกรม GXWork3**
1. Download Gxwork3 >> [link](https://drive.google.com/file/d/1olgX69E1S-ZEzhd0WcJog4AseTfC6inn/view?usp=share_link)
2. เข้าไปที่ โฟเดอร์ Disk1 
3. คลิ๊กไฟล์  setup.exe 


![Fig: setup.exe file](https://github.com/Advance-Innovation-Centre-AIC/IIoT_Training_course/tree/main/IoT_PLC/LAB01_Pre_Setup/pictures/image1.png)



2. เลือก GX-Works3
3. คลิ๊ก  **Next**


![Fig: GXWork3 Setup](https://github.com/Advance-Innovation-Centre-AIC/IIoT_Training_course/tree/main/IoT_PLC/LAB01_Pre_Setup/pictures/image2.png)



4. ใช่ข้อมูลลงในช่อง Name และ Company ตามต้องการ 
5. ใส่ตัวเลข Product ID ของ AIC 

```
    861-945946269
```

6. เมื่อใส่ข้อมูลครบแล้วให้คลิ๊ก  **Next**


![Fig: User Information](https://github.com/Advance-Innovation-Centre-AIC/IIoT_Training_course/tree/main/IoT_PLC/LAB01_Pre_Setup/pictures/image3.png)



7. เลือกโปรแกรม GX-Works3 และ คลิ๊ก  **Next**


![Fig: Sotfware Selection](https://paper-attachments.dropboxusercontent.com/s_1E2F6E44CDC583AF61E8EF2E284ED2600A5427B68F401AE7B32CFF12E3C7F5E9_1674802297581_Screenshot+2023-01-27+135111.png)



9. เลือกที่อยุ่ในการติดตั้งโปรแกรมในคอมพิวเตอร์ของคุณ ในที่นี้ใช้ตำแหน่งตามที่โปรแกรมเลือกให้ 
10. คลิ๊ก **Next** 



![fig: Selection of install destination](https://paper-attachments.dropboxusercontent.com/s_1E2F6E44CDC583AF61E8EF2E284ED2600A5427B68F401AE7B32CFF12E3C7F5E9_1674805473177_Screenshot+2023-01-27+144322.png)




11. คลิ๊ก **Next**  อีกครั้ง



![Fig: Start Copying files](https://paper-attachments.dropboxusercontent.com/s_1E2F6E44CDC583AF61E8EF2E284ED2600A5427B68F401AE7B32CFF12E3C7F5E9_1674803593162_Screenshot+2023-01-27+141139.png)



12. คลิ๊ก **Install** เมื่อหน้าต่างถามว่าต้องการติดตั้ง device software


13. คลิ๊กที่ หน้า GX-Works3 สำหรับเลือกให้สร้าง shortcut ไว้ที่หน้า dasktop หลังจากนั้นไปทำในขั้นตอนต่อไปสำหรับเริ่มต้นใช้งาน


# **Step2: Connect PLC with GXwork3**


1. เปิดโปรแกรม GXwork3
 
![](https://paper-attachments.dropbox.com/s_59625FBBC4D73C463D1FB0003439581FBA2A663DC1848F5B37B56CC9CCE0BB52_1655634627188_image.png)


2. เริ่มต้นสร้างโปรเจคใหม่โดยไปที่ : Project → New


![](https://paper-attachments.dropbox.com/s_59625FBBC4D73C463D1FB0003439581FBA2A663DC1848F5B37B56CC9CCE0BB52_1655634610270_image.png)


3. ตั้งค่าโปรเจคตามภาพด้านล่างแล้วคลิ๊ก OK
- Series เลือก FX5CPU
- Type เลือก FX5U
- Program Language เลือก Ladder


![](https://paper-attachments.dropbox.com/s_59625FBBC4D73C463D1FB0003439581FBA2A663DC1848F5B37B56CC9CCE0BB52_1655634699042_image.png)


**Method 2-1 : LAN Directly mode** 

1. เชื่อมต่อคอมพิวเตอร์เข้ากับพอร์ตสายLAN ของ PLC 
2. ไปที่ : Online เลือก Current Conection destination…


![](https://paper-attachments.dropbox.com/s_59625FBBC4D73C463D1FB0003439581FBA2A663DC1848F5B37B56CC9CCE0BB52_1655635299089_image.png)



3. เลือก "Directly Connect to CPU"

![](https://paper-attachments.dropbox.com/s_59625FBBC4D73C463D1FB0003439581FBA2A663DC1848F5B37B56CC9CCE0BB52_1655635665693_image.png)

4. ไปที่ช่องค้นหาบน Windows พิมพ์ CMD และ คลิ๊ก“Open” ที่ Command Prompt App


![](https://paper-attachments.dropbox.com/s_1E2F6E44CDC583AF61E8EF2E284ED2600A5427B68F401AE7B32CFF12E3C7F5E9_1663314177597_Screenshot+9_16_2022+2_38_57+PM.png)



 5. พิมพ์ command ตามคำสั่งด้านล่างเพื่อตรวจสอบ IP address ของคอมพิวเตอร์ว่า Ethernet port IP อะไร 

```
    ipconfig
```

![fig. CMD for show your IP address](https://paper-attachments.dropbox.com/s_59625FBBC4D73C463D1FB0003439581FBA2A663DC1848F5B37B56CC9CCE0BB52_1655637259851_image.png)


จากภาพให้ดูเลข IP ที่ IPv4  "Ethernet ip address" ในตัวอย่าง IP คือ "169.254.107.86"
6. เมื่อรู้เลข IP แล้ว ไปที่โปรแกรม GXwork3 
7. ที่หน้าต่างโปรแกรมให้ไปที่ “Adapter” เลือกชื่อพอร์ต LAN Adapter ตามตัวอย่างภาพด้านล่าง
8. สังเกตุที่ช่อง IP Address of Adapter ต้องเป็นเลข IP เดียวกันกับขั้นตอนก่อนหน้าที่เป็นเลข IP address ของเครื่องคอมพิวเตอร์ของคุณ
9. คลิ๊ก OK


![](https://paper-attachments.dropbox.com/s_59625FBBC4D73C463D1FB0003439581FBA2A663DC1848F5B37B56CC9CCE0BB52_1655637436520_image.png)



10. โปรแกรมจะทดสอบการเชื่อมต่อระหว่างคอมพิวเตอร์กับ PLC ถ้าเชื่อมต่อสำเร็จจะแสดงผลดังภาพด้านล่าง


![Successfully connected with PLC](https://paper-attachments.dropbox.com/s_59625FBBC4D73C463D1FB0003439581FBA2A663DC1848F5B37B56CC9CCE0BB52_1655637683678_image.png)


**Method 2-2 : WiFi Directly mode** **at AIC Room**

1. เชื่อมต่อคอมพิวเตอร์เข้ากับ Wifi ชื่อ "BCG_workshop_#1_5G" 

![](https://paper-attachments.dropbox.com/s_59625FBBC4D73C463D1FB0003439581FBA2A663DC1848F5B37B56CC9CCE0BB52_1655640750094_image.png)




2. ไปที่ : Online เลือก Current Conection destination…


![](https://paper-attachments.dropbox.com/s_59625FBBC4D73C463D1FB0003439581FBA2A663DC1848F5B37B56CC9CCE0BB52_1655635299089_image.png)



3. เลือก "Directly Connect to CPU"
![](https://paper-attachments.dropbox.com/s_59625FBBC4D73C463D1FB0003439581FBA2A663DC1848F5B37B56CC9CCE0BB52_1655635665693_image.png)

4. ไปที่ช่องค้นหาบน Windows พิมพ์ CMD และ คลิ๊ก“Open” ที่ Command Prompt App


![](https://paper-attachments.dropbox.com/s_1E2F6E44CDC583AF61E8EF2E284ED2600A5427B68F401AE7B32CFF12E3C7F5E9_1663314177597_Screenshot+9_16_2022+2_38_57+PM.png)


 5. พิมพ์ command ตามคำสั่งด้านล่างเพื่อตรวจสอบ IP address ของคอมพิวเตอร์ว่า Wireless LAN adapter WiFi ของคุณ IP อะไร 

```
    ipconfig
```

![](https://paper-attachments.dropbox.com/s_59625FBBC4D73C463D1FB0003439581FBA2A663DC1848F5B37B56CC9CCE0BB52_1655640965798_image.png)


6. เมื่อรู้เลข IP แล้วไปที่โปรแกรม GXwork3 
7. ที่หน้าต่างโปรแกรมให้ไปที่ “Adapter” เลือกชื่อพอร์ต Wireless Adapter ตามตัวอย่างภาพด้านล่าง
8. สังเกตุที่ช่อง “IP Address of Adapter” ต้องเป็นเลข IP เดียวกันกับขั้นตอนก่อนหน้าที่เป็นเลข IP address ของเครื่องคอมพิวเตอร์ของคุณ
9. คลิ๊ก OK


![](https://paper-attachments.dropbox.com/s_59625FBBC4D73C463D1FB0003439581FBA2A663DC1848F5B37B56CC9CCE0BB52_1655641092087_image.png)



10. โปรแกรมจะทดสอบการเชื่อมต่อระหว่างคอมพิวเตอร์กับ PLC ถ้าเชื่อมต่อสำเร็จจะแสดงผลดังภาพด้านล่าง


![](https://paper-attachments.dropbox.com/s_59625FBBC4D73C463D1FB0003439581FBA2A663DC1848F5B37B56CC9CCE0BB52_1655641116316_image.png)

----------

