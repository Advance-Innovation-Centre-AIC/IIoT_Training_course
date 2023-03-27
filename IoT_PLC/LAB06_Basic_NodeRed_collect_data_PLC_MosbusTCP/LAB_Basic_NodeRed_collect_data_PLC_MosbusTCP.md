

# **LAB1: ทดลองเขียน node-red  เก็บข้อมูลที่ได้จาก modbus TCP/IP ลงไฟล์ .csv ไฟล์**

จากการทดลองเขียนโปรแกรม node-red อ่านค่า Modbus เราสามารถนำค่าที่อ่านได้ไปลงไฟล์ csv เพื่อทำข้อมูลไปใช้งานต่อได้ โดยเพิ่ม write file node และ csv node ในการแปลงข้อมูลลงไฟล์ csv  และตั้งค่าที่ลงพื้นที่ที่ต้องการเก็บข้อมูล
      
      

![รูปภาพ: write file node](https://paper-attachments.dropboxusercontent.com/s_658EA92A6511F4A6D9DBC5C18FA68E122C12026AE7FD8BD469980BE09BFF5730_1668764340477_image.png)



![รูปภาพ: csv file node](https://paper-attachments.dropboxusercontent.com/s_658EA92A6511F4A6D9DBC5C18FA68E122C12026AE7FD8BD469980BE09BFF5730_1668764371282_image.png)



1. สร้าง modbus read node และ debus node ตามขั้นตอนการทดลองก่อนหน้า สำหรับอ่านข้อมูลจาก modbus TCP/IP
2. ไปที่แถบซ้ายมือ >> funtion >> เลือก function node
3. ไปที่แถบซ้ายมือ >> parser >> เลือก csv node
4. ไปที่แถบซ้ายมือ >> storage >> เลือก write file node
5. เชื่อม modbus read node ต่อ function node  ตามด้วย write file node และต่อด้วย csv node 


![รูปภาพ: Basic-write-csv file flow](https://paper-attachments.dropboxusercontent.com/s_658EA92A6511F4A6D9DBC5C18FA68E122C12026AE7FD8BD469980BE09BFF5730_1668767808542_image.png)

6. ตั้งค่า node write file   ตามภาพด้านล่าง เพื่อกำหนด path เก็บข้อมูลที่ต้องการเขียนลงไฟล์


![รูปภาพ: ตัวอย่าง ตั้งค่า Edit write node บน RaspberryPi](https://paper-attachments.dropboxusercontent.com/s_2356CDFF764A5B2E96B9FFE02AB5E39D5A33DDABAC28B1747354F8FB32E63A7C_1665116821484_image.png)
![รูปภาพ: ตัวอย่าง ตั้งค่า Edit write node บน Windows](https://paper-attachments.dropboxusercontent.com/s_658EA92A6511F4A6D9DBC5C18FA68E122C12026AE7FD8BD469980BE09BFF5730_1668768258279_image.png)

6. ตั้งค่า csv node ตามภาพด้านล่าง


![รูปภาพ: Edit csv node](https://paper-attachments.dropboxusercontent.com/s_658EA92A6511F4A6D9DBC5C18FA68E122C12026AE7FD8BD469980BE09BFF5730_1668768662457_image.png)



5. คลิ๊กที่ Deploy เพื่อให้ Node-red ทำงานตามโปรแกรมที่ได้ตั้งค่าไว้


## **บันทึกผลการทดลอง**

…
…
…


# **แบบฝึกหัด**
1. **ทดลองเขียน funcion node  ให้เก็บ มี timestamp พร้อมกับ ข้อมูลที่ได้จาก modbus TCP/IP  ลงไฟล์ csv** 



