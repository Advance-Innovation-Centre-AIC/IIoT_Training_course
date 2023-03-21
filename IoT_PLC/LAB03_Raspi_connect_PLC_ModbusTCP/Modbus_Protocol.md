# **MODBUS Protocol**

 Modbus protocol เป็นโปรโตคอลสำหรับส่งข้อความที่อยู่ในชั้น Application layer ตามมาตาฐาน OSI model ซึ่งเป็นการสื่อสารระหว่าง client/server ของอุปกรณ์ที่ต้องการเชื่อมต่อบนบัส หรือ network ต่างประเภทกัน [Ref. [www.modbus.org](https://modbus.org/docs/Modbus_Application_Protocol_V1_1b3.pdf)]

 Modbus Protocol แบ่งการเรียกการสื่อสารตามรูปแบบมาตรฐานการสื่อสารเป็นกลุ่มใหญ่ได้ 2 แบบ คือ การสื่อสารผ่าน มาตรฐานการสื่อสาร  RS232 กับ RS485 ( EIA/TIA-232-E, TIA-485-A) เรียกว่า ModbusRTU/ASCII (Remote Terminal Unit) และ การสื่อสารผ่าน Ethernet หรือสายแลนด์ (มาตรฐานการสื่อสาร Ethernet/802.3) เรียกว่า Modbus TCP/IP 

## **รูปแบบการเก็บข้อมูล Modbus**

 การเก็บข้อมูลของ modbus มีการแบ่งประเภทข้อมูลเป็น 4 แบบดังตารางด้านล่าง โดย 2 แบบแรกจะใช้ในการเก็บค่าที่เป็น on/off หรือข้อมูลขนาด 1 บิต ส่วน 2 แบบท้ายจะเก็บข้อมูลแบบ 1 word หรือ 16 บิต ซึ่งในแต่ละแบบจะเก็บข้อมูลลงในช่วงตามช่วง Coil/Register Numbers ของตัวเอง เมื่อต้องการเรียกใช้งานข้อมูลสามารถเรียกตามตัวเลข Coil/Register Numbers ที่กำหนดไว้ได้

             
**Data stored in Standard Modbus table**

| **Coil/Register Numbers**<br>**(DEC)** | **Data Addresses**<br>**(HEX)** | **Type**   | **Table Name**                  |
| -------------------------------------- | ------------------------------- | ---------- | ------------------------------- |
| 1-9999                                 | 0000 to 270E                    | Read-Write | Discrete Output Coils           |
| 10001-19999                            | 0000 to 270E                    | Read-Only  | Discrete Input Contacts         |
| 30001-39999                            | 0000 to 270E                    | Read-Only  | Analog Input Registers          |
| 40001-49999                            | 0000 to 270E                    | Read-Write | Analog Output Holding Registers |

[Ref. [www.simplymodbus.ca](https://www.simplymodbus.ca/)]

## **Function code**

 function code เป็นตัวเลขที่ใช้สำหรับเข้าถึงข้อมูลของ slave โดยมีตัวเลขดังตารางด้านล่าง


| **Function Code** | **Action**     | **Table Name**                  |
| ----------------- | -------------- | ------------------------------- |
| 01 (01 hex)o      | Read           | Discrete Output Coils           |
| 05 (05 hex)       | Write single   | Discrete Output Coil            |
| 15 (0F hex)       | Write multiple | Discrete Output Coils           |
| 02 (02 hex)       | Read           | Discrete Input Contacts         |
| 04 (04 hex)       | Read           | Analog Input Registers          |
| 03 (03 hex)       | Read           | Analog Output Holding Registers |
| 06 (06 hex)       | Write single   | Analog Output Holding Register  |
| 16 (10 hex)       | Write multiple | Analog Output Holding Registers |

[Ref. [www.simplymodbus.ca](https://www.simplymodbus.ca/)]


## **การใช้งาน Modbus protocol**

 การสื่อสาร Modbus protocol ได้กำหนด frame ข้อมูลตามภาพด้านล่างดังนี้


![figure: Modbus Protocol Data section](https://paper-attachments.dropboxusercontent.com/s_67EE1652549C1B0192A8D98C8B3D52FDA6C5CDF699E58B031CADEB77267F2935_1669879567697_image.png)


[Ref. [mitsubishi](https://dl.mitsubishielectric.com/dl/fa/document/manual/plcf/jy997d56101/jy997d56101h.pdf)]

Address field: เป็นข้อมูลที่อยู่สำหรับให้อุปกรณ์ที่เป็น Master เรียกอุปกรณ์ที่เป็น Slave ในเครือข่ายสื่อสาร ซึ่งสามารถกำหนดตัวเลขให้กับ Slave ได้ตั้งแต่เลข 1 ถึง 247 หรือเรียกตัวเลขนี้ว่า Slave ID หรือ unit ID

Function code: เป็นข้อมูลของประเภทการเก็บข้อมูลของ modbus

Data: เป็นข้อความที่ต้องการส่ง
Error check: เป็นส่วนตรวจสอบความถูกต้องของข้อความจะทำงานอัตโนมัติเมื่อได้รับข้อความที่สื่อสารและจะทิ้งข้อความนั้นทันทีเมื่อตรวจสอบแล้วพบ error 


# **ตัวอย่างการใช้งาน Modbus TCP/IP** 
 ตัวอย่างการทดลองใช้ Modebus TCP/IP ในการอ่านข้อมูลประเภทดิจิตอลที่มีข้อมูลเป็นบิต 0 และ 1 เช่น Relay โดยใช้ โปรแกรม simmulator 

Download โปรแกรม [Modbus Poll และ Modbus slave](https://www.modbustools.com/download.html) 
หมายเหตุโปรแกรมมีอายุการใช้งานฟรี 30 วัน สำหรับคนที่ใช้ไม่ได้สามารถ download ได้จาก >> [link2](https://drive.google.com/drive/folders/1XdAiUCcNqe1Bkg2pbt6MFQ_ISRF8uysM?usp=share_link)

## **Setup Modbus slave tool (Slave)**
กำหนดให้ slave ดังนี้
- เป็นข้อมูล 0 1 และส่งข้อมูลที่อนุญาติให้อ่านได้
- Slave ID   เท่ากับ 1
- IP Address เท่ากับ 127.0.0.1 port 502

1. เปิดโปรแกรม Modbus slave 
2. ไปที่ setup >> Read/Write Definition 
                >> ตั้งค่า Slave ID เท่ากับ 1  
                >> Function code เลือก 01 Read Coils(0x)  
                >> ตั้งค่า Address เริ่มต้นที่ต้องการส่ง เท่ากับ 1 
                >> กำหนด Quantity หรือจำนวน address ที่ต้องการอ่าน เท่ากับ 2 และ คลิ๊ก OK 
                        
![Figure: setup data](https://paper-attachments.dropboxusercontent.com/s_67EE1652549C1B0192A8D98C8B3D52FDA6C5CDF699E58B031CADEB77267F2935_1669883773383_image.png)



3. ไปที่ Connection >> connect>>Connection>> เลือก Modbus TCP/IP 
4. ไปที่ TCP/IP server >> IP Address ตั้งค่า เป็น 127.0.0.1 port 502  คลิ๊ก OK


![Figure: setup Modbus connect](https://paper-attachments.dropboxusercontent.com/s_67EE1652549C1B0192A8D98C8B3D52FDA6C5CDF699E58B031CADEB77267F2935_1669883924208_image.png)



5. คลิ๊กที่ edit coil ให้เป็น Auto change เป็นการส่งข้อมูล 0 และ 1 สลับกันเรื่อย ๆ 


![Figure : Edit Coil](https://paper-attachments.dropboxusercontent.com/s_67EE1652549C1B0192A8D98C8B3D52FDA6C5CDF699E58B031CADEB77267F2935_1669884142399_image.png)


## **Setup Modbus Poll tool (Master)**

1. เปิดโปรแกรม Modbus Poll
2. ไปที่ setup >> Read/Write Definition
                  >> ตั้งค่า Slave ID เท่ากับ 1 
                  >> Function code เลือก 01 Read Coils(0x) 
                  >> ตั้งค่า Address เริ่มต้นที่ต้องการอ่าน เท่ากับ 1 
                  >> กำหนด Quantity หรือจำนวน address ที่ต้องการอ่าน เท่ากับ 2 และ คลิ๊ก OK
                
![Figure: setup data](https://paper-attachments.dropboxusercontent.com/s_67EE1652549C1B0192A8D98C8B3D52FDA6C5CDF699E58B031CADEB77267F2935_1669882717421_image.png)



3. ไปที่ Connection >> connect>>Connection>> เลือก Modbus TCP/IP 
4. ไปที่ Remote server >> IP Address ตั้งค่า เป็น 127.0.0.1 port 502  คลิ๊ก OK

**OUTPUT**

![Figure: Master read coil from the Slave](https://paper-attachments.dropboxusercontent.com/s_67EE1652549C1B0192A8D98C8B3D52FDA6C5CDF699E58B031CADEB77267F2935_1669884646325_image.png)



# **ตัวอย่างการใช้งาน Modbus RTU**
 ตัวอย่างการทดลองใช้ Modbus RTU ในการอ่านข้อมูล sensor วัดอุณหภูมิและความชื้น ซึ่งจัดอยู่ในข้อมูลประเภท Analog โดยใช้ โปรแกรม simmulator 

**ข้อมูล Sensor (Slave)**
Temperature and humidity transmitter SHT20 sensor Modbus RS485 Datasheet →[link](https://drive.google.com/file/d/17E3FKH77xNIqxdpTzDWW65fY6L36x7PP/view?usp=share_link) 


**Setup Modbus Poll tool(Master)**  

1. เปิดโปรแกรม Modbus Poll
2. ไปที่ setup >> Read/Write Definition
                  >> ตั้งค่า Slave ID เท่ากับ 1 
                  >> Function code เลือก 03 Read Holding Registers(4x) 
                  >> ตั้งค่า Address เริ่มต้นที่ต้องการอ่าน เท่ากับ 1 
                  >> กำหนด Quantity หรือจำนวน address ที่ต้องการอ่าน เท่ากับ 2 และ คลิ๊ก OK


![Figure: setup data](https://paper-attachments.dropboxusercontent.com/s_67EE1652549C1B0192A8D98C8B3D52FDA6C5CDF699E58B031CADEB77267F2935_1669885479143_image.png)




https://www.youtube.com/watch?v=W85ZBtQ-t-8&&list=WL&index=2

https://www.nectec.or.th/news/news-public-document/modbus-protocol.html





