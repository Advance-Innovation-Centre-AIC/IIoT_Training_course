
ในการทดลองนี้เรากำหนดให้ค่า slave device มีการตั้งค่าให้ส่งข้อมูล ผ่าน Modbus protocol ดังนี้
Master ส่งคำสั่งสำหรับอ่านข้อมูลประเภท coil จาก slave ที่ ID เท่ากับ 1 และ ip address 127.0.0.1 port 502

# **ขั้นตอนการทดลอง**

## **Setup Modbus slave (server) tool**
1. เปิดโปรแกรม Modbus slave

2. ไปที่ setup >> Read/Write Definition
                  
                  >> ตั้งค่า Slave ID เท่ากับ 1 
                  
                  >> Function code เลือก 01 
                  
                  >> ตั้งค่า Address เริ่มต้นที่ต้องการอ่าน เท่ากับ 1 
                  
                  >> กำหนด Quantity หรือจำนวน address ที่ต้องการอ่าน เท่ากับ 2 
                  
                  และ คลิ๊ก OK

![รูปภาพ: ตัวอย่างการใช้งาน โปรแกรม Sim Slave](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668748693706_image.png)




 จากที่เราได้ติดตั้ง modbus module เราสามารถใช้ Modbus-read node ในการอ่านค่า Modbus protocol โดยสามารถอ่านได้ทั้ง Modbus RTU และ Modbus TCP/IP ขึ้นอยู่กับการตั้งค่า ในที่นี้เราจะใช้ในการอ่านค่าแบบ modbus TCP/IP






1. ติดตั้ง Modbus modules Node-Red
 - ไปที่ Manage palette >>Install>> search modules >> พิมพ์ “Modbus” >>node-red-contrib-modbus >> install


![รูปภาพ: Install node-red-contrib-modbus](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668745927148_file.png)

2. หลังจากติดตั้งเสร็จ สังเกต แถบทางซ้ายมือจะปรากฎ modbus node สำหรับใช้งาน


![รูปภาพ: modbus node](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668747265787_file.png)


![รูปภาพ: Modbus-Read node](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668765590553_image.png)



1. ไปที่ แถบซ้ายมือ >> Modbus >> คลิ๊กค้างที่ modbus Read และรากลงบนพื้นที่ว่าง
2. คลิ๊กที่ node ที่ได้รากมา แล้วตั้งค่าสำหรับ อ่านค่า Slave Modbus TCP/IP  Function code แบบ 01 read coil ดังภาพด้านล่าง


![รูปภาพ: Edit Modbus-read node](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668747754621_file.png)
![รูปภาพ: connection config node](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668749400675_image.png)



2. ไปที่แถบซ้ายมือ comom >> เลือก debug node 
3. เชื่อม node debug และ modbus read ต่อกัน


![รูปภาพ: Basic-read Modbus TCP/IP flow](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668765859002_image.png)



4. ตั้งค่า node debug ตามภาพด้านล่าง เพื่อ debug ข้อมูลที่ modbus Read node อ่านได้


![](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668749237323_image.png)

5. คลิ๊กที่ Deploy เพื่อให้ Node-red ทำงานตามโปรแกรมที่ได้ตั้งค่าไว้


## **บันทึกผลการทดลอง**

…
…
…


# **แบบฝึกหัด**
1. **ทดลองเขียน Node-red อ่านค่าผ่าน Modbus TCP/IP แบบ function code 3**
2. **ทดลองใช้ โปรแกรม Node-red ที่เขียนก่อนหน้า อ่านค่า PLC function code แบบ 01 read coil  ผ่าน Modbus TCP/IP** 


----------

Ref. [Running Node-RED locally](https://nodered.org/docs/getting-started/local)
Ref. [Running on Raspberry Pi](https://nodered.org/docs/getting-started/raspberrypi)
Ref. [Running on Windows](https://nodered.org/docs/getting-started/windows)

