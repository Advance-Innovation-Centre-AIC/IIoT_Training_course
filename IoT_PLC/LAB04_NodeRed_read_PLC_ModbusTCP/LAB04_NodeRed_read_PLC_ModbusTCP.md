# Lab04: การเขียนโปรแกรม Node-red เพื่ออ่านค่า PLC 

# **ตั้งค่า Node-red บน Windows**
1. Download และ ติดตั้ง Nodejs ที่เว็บไซต์ [Node.js](https://nodejs.org/en/)


![รูปภาพ: Website Node.js](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668742701228_file.png)

2. เปิด Command Promp โดยไปที่ Start>>พิมพ์ CMD ในช่องค้นหา
3. ตรวจสอบ version ของ node.js และ npm ที่ได้ติดตั้งไปก่อนหน้า โดยพิมพ์คำสั่ง ดังนี้


    node --version
    npm --version


![รูปภาพ: CMD แสดง  node.js และ npm version บน windows](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668744508638_file.png)

3. ติดตั้ง node-red โดย พิมพ์คำสั่ง ติดตั้งด้วย npm ดังนี้


     npm install -g --unsafe-perm node-red


4. เมื่อติดตั้ง node-red ให้ปิด หน้าต่าง Commade Promp แล้วเปิดใหม่ 
5. พิมพ์ คำสั่ง เปิดใช้งาน node-red ดังนี้


    node-red start 

หลังจาก Run Node-red แล้ว เราสามารถใช้งาน node-red  โดยไปที่หน้าเบราเซอร์ของคอมพิวเตอร์เรา พิมพ์ IP 127.0.0.1 หรือ คำว่า “localhost”  ตามด้วย port 1880 ดังตัวอย่าง ด้านล่าง


    http://127.0.0.1:1880
    or
    http://localhost:1880


![รูปภาพ: ตัวอย่าง Browser Node-red](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668745390560_file.png)



# **ตั้งค่า Node-red บน RaspberryPi**
1. สำหรับใช้งาน node-red บน Respberry Pi สามารถใช้ สคริปที่ node-red เตรียมให้ ดังนี้


    bash <(curl -sL https://raw.githubusercontent.com/node-red/linux-installers/master/deb/update-nodejs-and-nodered)


![รูปภาพ: terminal แสดงการติดตั้งโปรแกรมสำหรับใช้งาน Node-red](https://paper-attachments.dropboxusercontent.com/s_5931C85939E77FD48CAE3A71450F98024B4F088C5796C975D6067813D61AA140_1623228230189_Screenshot+from+2021-06-09+15-43-33.png)

2. ใส่คำสั่ง สำหรับ Run Node-red ดังนี้


    node-red start


3. หลังจาก Run Node-red แล้ว เราสามารถเข้าหน้าเบราเซอร์บนคอมพิวเตอร์ของเรา ผ่าน IP address  ของ Respberry Pi และ ตามด้วย port 1880


    http://<IP address of RespberryPi>:1880


# **ติดตั้ง Modbus modules Node-Red**
1. ไปที่ Manage palette >>Install>> search modules >> พิมพ์ “Modbus” >>node-red-contrib-modbus >> install


![รูปภาพ: Install node-red-contrib-modbus](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668745927148_file.png)

2. หลังจากติดตั้งเสร็จ สังเกต แถบทางซ้ายมือจะปรากฎ modbus node สำหรับใช้งาน


![รูปภาพ: modbus node](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668747265787_file.png)



# **LAB4-1: การทดลองเขียน Node-red อ่านค่า ผ่าน Modbus TCP/IP** 
## **วัตถุประสงค์**
1. เพื่อเรียนรู้วิธีเขียนโปรแกรม Node-red ใช้งาน Modbus TCP/IP อ่านข้อมูลได้
## **อุปกรณ์ประกอบการทดลอง**
1. คอมพิวเตอร์
2. PLC
3. Raspberry Pi

   ในการทดลองนี้เรากำหนดให้ค่า slave device มีการตั้งค่าให้ส่งข้อมูล ผ่าน Modbus protocol ดังนี้
Connection: Modbus TCP/IP
IP address: 127.0.0.1 
port: 502
Set-up
Slave ID: 1
Start Address: 1
Quantity: 2
function code: 01


![รูปภาพ: ตัวอย่างการใช้งาน โปรแกรม Sim Slave](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668748693706_image.png)



## **ขั้นตอนการทดลอง**

 จากที่เราได้ติดตั้ง modbus module เราสามารถใช้ Modbus-read node ในการอ่านค่า Modbus protocol โดยสามารถอ่านได้ทั้ง Modbus RTU และ Modbus TCP/IP ขึ้นอยู่กับการตั้งค่า ในที่นี้เราจะใช้ในการอ่านค่าแบบ modbus TCP/IP


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

