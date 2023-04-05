# **Outline**
- [LAB: Node-red read data from ModbusTCP Slave tool](https://github.com/Advance-Innovation-Centre-AIC/IIoT_Training_course/blob/main/IoT_PLC/LAB04_NodeRed_read_PLC_ModbusTCP/LAB_NodeRed_read_PLC_ModbusTCP.md#lab-node-red-read-data-from-modbustcp-slave-tool)
- [LAB: Node-red read data from PLC via ModbusTCP](https://github.com/Advance-Innovation-Centre-AIC/IIoT_Training_course/blob/main/IoT_PLC/LAB04_NodeRed_read_PLC_ModbusTCP/LAB_NodeRed_read_PLC_ModbusTCP.md#lab-node-red-read-data-from-plc-via-modbustcp)

# **LAB: Node-red read data from ModbusTCP Slave tool**
ในการทดลองนี้เรากำหนดให้ค่า slave device มีการตั้งค่าให้ส่งข้อมูล ผ่าน Modbus protocol ดังนี้
Master ส่งคำสั่งสำหรับอ่านข้อมูลประเภท coil จาก slave ที่ ID เท่ากับ 1 และ ip address 127.0.0.1 port 502

## **Setup Modbus slave tool (Slave)**
กำหนดให้ slave ดังนี้
- เป็นข้อมูล 0 1 และส่งข้อมูลที่อนุญาติให้อ่านได้
- Slave ID   เท่ากับ 1
- IP Address เท่ากับ 127.0.0.1 port 502

1. เปิดโปรแกรม Modbus slave 
2. ไปที่ setup >> Read/Write Definition

      - ตั้งค่า Slave ID เท่ากับ 1 

      - Function code เลือก 01 Read Coils(0x)

      - ตั้งค่า Address เริ่มต้นที่ต้องการส่ง เท่ากับ 1

      - กำหนด Quantity หรือจำนวน address ที่ต้องการอ่าน เท่ากับ 2 และ คลิ๊ก OK 

![รูปภาพ: ตัวอย่างการใช้งาน โปรแกรม Sim Slave](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668748693706_image.png)



## **Setup ModbusTCP in Node-red (Master)**
 
 จากที่เราได้ติดตั้ง modbus module เราสามารถใช้ Modbus-read node ในการอ่านค่า Modbus protocol โดยสามารถอ่านได้ทั้ง Modbus RTU และ Modbus TCP/IP ขึ้นอยู่กับการตั้งค่า ในที่นี้เราจะใช้ในการอ่านค่าแบบ modbus TCP/IP

1. ติดตั้ง Modbus modules Node-Red
 - ไปที่ Manage palette >> Install >> พิมพ์ “Modbus” >> เลือก node-red-contrib-modbus >> คลิ๊ก install


![รูปภาพ: Install node-red-contrib-modbus](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668745927148_file.png)

2. หลังจากติดตั้งเสร็จ สังเกต แถบทางซ้ายมือจะปรากฎ modbus node สำหรับใช้งาน


![รูปภาพ: modbus node](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668747265787_file.png)


![รูปภาพ: Modbus-Read node](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668765590553_image.png)



3. ไปที่ แถบซ้ายมือ >> Modbus >> คลิ๊กค้างที่ modbus Read และรากลงบนพื้นที่ว่าง
4. คลิ๊กที่ node ที่ได้รากมา แล้วตั้งค่าสำหรับ อ่านค่า Slave Modbus TCP/IP  Function code แบบ 01 read coil ดังภาพด้านล่าง


![รูปภาพ: Edit Modbus-read node](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668747754621_file.png)
![รูปภาพ: connection config node](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668749400675_image.png)



5. ไปที่แถบซ้ายมือ comom >> เลือก debug node 
6. เชื่อม node debug และ modbus read ต่อกัน


![รูปภาพ: Basic-read Modbus TCP/IP flow](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668765859002_image.png)



7. ตั้งค่า node debug ตามภาพด้านล่าง เพื่อ debug ข้อมูลที่ modbus Read node อ่านได้


![](https://paper-attachments.dropboxusercontent.com/s_EAE347BCB7B527CA2156619BD46DF2D9708CD446BDA75189903AABB7E89CF529_1668749237323_image.png)

8. คลิ๊กที่ Deploy เพื่อให้ Node-red ทำงานตามโปรแกรมที่ได้ตั้งค่าไว้


**บันทึกผลการทดลอง**



# **LAB: Node-red read data from PLC via ModbusTCP**
หลังจากทดลองเขียนโปรแกรม Node-red สื่อสารด้วย ModbusTCP กับโปรแกรม Simmulator จำลองเป็น Slave ได้แล้ว เราสามารถใช้โปรแกรม Node-red นี้ไป

## **Setup PLC ModbusTCP (Slave)**
1. ตั้งค่า PLC ใช้งาน Modbus TCP/IP Protocol ตามขั้นตอน > [ตั้งค่า PLC ใช้งาน Modbus TCP/IP Protocol](https://github.com/Advance-Innovation-Centre-AIC/IIoT_Training_course/blob/main/IoT_PLC/LAB03_Raspi_connect_PLC_ModbusTCP/Lab03_RasberryPi_connect_PLC_ModbusTCP.md#%E0%B8%95%E0%B8%B1%E0%B9%89%E0%B8%87%E0%B8%84%E0%B9%88%E0%B8%B2-plc-%E0%B9%83%E0%B8%8A%E0%B9%89%E0%B8%87%E0%B8%B2%E0%B8%99-modbus-tcpip-protocol)

2. เขียนโปรแกรม Ledder ตามภาพด้านล่าง ลง PLC 

![ladder_ex](https://github.com/Advance-Innovation-Centre-AIC/IIoT_Training_course/blob/15c64790f1e96be5e1fc8a4df1e6c5d4ee33341e/IoT_PLC/LAB04_NodeRed_read_PLC_ModbusTCP/picture/ladder_ex.png)


3. หลังจาก Run โปรแกรม PLC แล้ว 
   - ไปที่แถบเครื่องมือของโปรแกรม GxWork3 ที่ Online > Monitor > Device/Buffer Memory Batch Monitor 

![image_program_plc](https://github.com/Advance-Innovation-Centre-AIC/IIoT_Training_course/blob/15c64790f1e96be5e1fc8a4df1e6c5d4ee33341e/IoT_PLC/LAB04_NodeRed_read_PLC_ModbusTCP/picture/image_program_plc.png)

4. Device name > ใส่ X0 กด Enter เราสามารถควบคุม X0 โดยเป็น 0 เป็น 1 ผ่านหน้าต่างนี้ได้เช่นกัน 

![plc_control](https://github.com/Advance-Innovation-Centre-AIC/IIoT_Training_course/blob/15c64790f1e96be5e1fc8a4df1e6c5d4ee33341e/IoT_PLC/LAB04_NodeRed_read_PLC_ModbusTCP/picture/plc_control.png)


## **Setup ModbusTCP in Node-red (Master)**
สามารถทดลองโดยการเขียนโปรแกรม Node-red ขั้นตอนแบบเดียวกันกับการทดลองก่อนหน้านี้->[link](https://github.com/Advance-Innovation-Centre-AIC/IIoT_Training_course/blob/main/IoT_PLC/LAB04_NodeRed_read_PLC_ModbusTCP/LAB_NodeRed_read_PLC_ModbusTCP.md#setup-modbustcp-in-node-red-master) ทดลองอ่านค่าจาก PLC ที่ X0 และสังเกต การเปลี่ยนแปลงที่หน้าต่าง Device/Buffer Memory Batch Monitor ของโปรแกรม Gxwork3 กับค่าที่ node-red อ่านได้

**บันทึกผลการทดลอง**






----------

Ref. [Running Node-RED locally](https://nodered.org/docs/getting-started/local)

Ref. [Running on Raspberry Pi](https://nodered.org/docs/getting-started/raspberrypi)

Ref. [Running on Windows](https://nodered.org/docs/getting-started/windows)

