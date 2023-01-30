# โครงสร้างหลักสูตร IIoT Gateway courses

    
หลักสูตรนี้สร้างขึ้นเพื่อเพิ่มความเข้าใจหลักการพื้นฐานการนำข้อมูลจาก PLC และจัดเตรียมข้อมูล
สำหรับนำไปใช้กับการทำ Data Analytics เพื่อวิเคราะห์ข้อมูลเมื่อเกิดเหตุผิดปกติให้มีการแจ้งเตือน

## **จุดประสงค์**

1. เข้าใจการพื้นฐานการอ่านข้อมูลจาก PLC
2. สามารถเขียนโปรแกรมเพื่ออ่านข้อมูลจาก PLC 
3. สามารถดึงข้อมูลจาก PLC นำไปวิเคราะห์ความผิดปกติและแจ้งเตือน สำหรับชุดจำลองการทำงานอุตสาหกรรมได้
4. สร้างแรงบัลดาลใจให้ผู้เข้าร่วมอบรมนำความรู้ไปประยุกต์ใช้งานในโรงงานหรือ แนวคิดในการต่อยอดธุรกิจ

## **อุปกรณ์ที่เกี่ยวข้อง**

**ทางเราจัดเตรียมให้**

- ชุด Demo Robot และ PLC ของศูนย์ AIC  จำนวน 1 ชุด ประกอบด้วย
    - Mitsubishi PLC รุ่น Fx5u 
    - M1 Robot  
    - ชุดสายพานจำลองโรงงานแยกประเภทวัตถุด้วยเซนเซอร์
    - Raspberry Pi 

**ทางผู้เรียนต้องเตรียมมาเอง**

- คอมพิวเตอร์สำหรับอบรมสเปค แรม 8 GB ขึ้นไป ติดตั้ง windows 10 ขึ้นไป
## **โปรแกรมที่เกี่ยวข้อง**
- โปรแกรม GX-Word3 สำหรับ PLC
- โปรแกรมสำหรับ Remote เข้า Raspberry Pi 
- VSCode 
## **เหมาะกับกลุ่มผู้เรียน**
1. นิสิต หรือบุคคลทั่วไปที่สนใจแต่ไม่มีความรู้พื้นฐาน
2. บุคคลที่สนใจเกี่ยวกับการดึงข้อมูลจาก PLC ไปประยุกต์ใช้
3. บริษัทที่สนใจเกี่ยวกับการดึงข้อมูลจาก PLC ไปประยุกต์ใช้
## **ระยะเวลาการอบรม**

ทั้งหมด 12 ชั่วโมง สำหรับ นิสิตหรือผู้ไม่มีความรู้พื้นฐาน PLC
      และ 9 ชั่วโมง สำหรับ ผู้มีความรู้พื้นฐาน PLC

## **จำนวนผู้เข้าร่วมอบรม**

รองรับผู้สนใจอบรมได้ 12-20 คน ต่อ รอบการอบรม
(ชุดอุปกรณ์ Raspberry Pi  1/5 คน)

## **ราคา course**

~~1500 บาท ต่อ คน~~


## Course **ที่ 1:** **IoT and PLC**

**ตารางเวลาและรายละเอียดของหลักสูตร** 

| **หัวข้อการอบรม**                                               | **รายละเอียด**                                                                                                                                                                            | **เวลาทั้งหมด** | **ทฤษฎี** | **ปฏิบัติ**   |
| --------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------- | --------- | ------------- |
| พิ้นฐาน PLC <br>(สำหรับ นิสิตหรือผู้ไม่มีความรู้พื้นฐาน PLC)    | - PLC คืออะไร<br>- วิธีการใช้ PLC เบื้องต้น<br>- การเขียนโปรแกรม PLC เบื้องต้นสำหรับควบคุมชุด<br><br>จำลองการทำงานแขนกลกับเซนเซอร์ควบคุมสายพานอุตสากรรมและชุดเซนเซอร์แยกวัตถุของศูนย์อบรม | 3 ชม.           | 15 นาที   | 2 ชม. 45 นาที |
| การเชื่อมต่อ PLC กับ rapberrypi ผ่าน modbus TCP/IP              | - การเชื่อมต่อ PLC แบบ modbus TCP/IP<br>- การตั้งค่า rapberrypi สำหรับเชื่อมต่อกับ PLC                                                                                                    | 1 ชม.           | -         | 1 ชม.         |
| การเขียนโปรแกรม Node-red เพื่ออ่านค่า PLC และแสดงผลบน Dashboard | - การเขียนโปรแกรม Node-red บน rapberrypi เบื้อง<br><br>ต้นสำหรับอ่านค่า PLC ผ่าน modbus TCP/IP<br><br>- การเขียนโปรแกรม Node-red แสดงค่าที่อ่านจาก PLC แสดงบน<br><br>Dashboard            | 3 ชม.           | -         | 3 ชม.         |
| การเก็บค่า PLC ลง data logger                                   | - การเขียน node-red  เก็บข้อมูลเป็นไฟล์ .csv ไฟล์<br><br>เพื่อเตรียมสำหรับการนำไปใช้งานกับการทำ Analytics                                                                                 | 2 ชม.           | -         | 2 ชม.         |



## Course **2:**  **PLC’s data analytics** ****

**ตารางเวลาและรายละเอียดของหลักสูตร**

| **หัวข้อการอบรม**        | **รายละเอียด**                                                                                                  | **เวลาทั้งหมด** | **ทฤษฎี** | **ปฏิบัติ** |
| ------------------------ | --------------------------------------------------------------------------------------------------------------- | --------------- | --------- | ----------- |
| การเตรียม Dataset        | - การจัดรูปแบบของข้อมูล<br>    - การจัดข้อมูล PLC ในรูปแบบ time series<br>- การ label <br>- การแบ่ง window size | 1 ชม.           | 30 นาที   | 30 นาที     |
| basic ML สำหรับ Industry | - การนำ Dataset มาใช้ training<br>    - สัดส่วนการแบ่ง Train/test<br>- การแสดงผลลัพธ์ ML                        | 2 ชม.           | 30 นาที   | 90 นาที     |
| การแสดงผล Analytics      | - การแสดงค่า Raw data ในรูปแบบต่างๆ<br>- การออกแบบระบบแจ้งเตือนอย่างง่าย                                        | 1 ชม.           | -         | 1 ชม.       |



----------


## **REVIEW THE COURSE SUMMARY BELOW**
| **GENERAL INFORMATION** |                          |
| ----------------------- | ------------------------ |
| **VENDOR :**            | Internet of Thing        |
| **LEARNING METHOD :**   | Instructor-Led           |
| **TRACK:**              | Internet of Thing Course |
| **DESCRIPTION :**       | IoT in industry          |
| **REMARK :**            | -                        |
| **CODE :**              |                          |
| **LANGUAGE :**          | Thai                     |



| **PRICING INFORMATION** |           |
| ----------------------- | --------- |
| **USUAL :**             | 1500 Baht |
| **SPECIAL :**           | Pls. Call |
| **REMARK :**            | -         |



[+IIoT Training (info. Promotion follow Vnohow)](https://paper.dropbox.com/doc/IIoT-Training-info.-Promotion-follow-Vnohow-rXl1ExtBbFSEhatorEGZw) 

