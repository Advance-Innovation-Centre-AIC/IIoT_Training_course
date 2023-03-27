
# **LAB1: ทดลองเขียนโปรแกรม PLC รับค่าอินพุตข้อมูลประเภท Digital**
ทดลองเขียน PLC เพื่ออ่านค่าสถานะการทำงานหรือหยุดทำงานของแขนกล

ตัวอย่าง LD page

----------
# **LAB2: ทดลองเขียนโปรแกรม PLC รับค่าอินพุตประเภท Analog**

## **ขั้นตอนการทดลอง**

ตัวอย่าง การอ่านค่าเซนเซอร์วัดอุณหภูมิ 

![](https://paper-attachments.dropboxusercontent.com/s_8548A7ADB4410E896D4B855B4D4106071ED1F17F3CC7C6E81DABC3E00A90EEEE_1666078443672_image.png)



----------
# **LAB3: ทดลองเขียนโปรแกรม PLC สำหรับควบคุมเอาต์พุตประเภท Digital**

*** PLC มี 2 แบบ คือ Output แบบ MR(Relay) และ MT(Transistor)*
      *Fx5u/fx5uc ควบคุมได้แค่แบบนี้  Output แบบ MR (Relay)* 

ตัวอย่าง การควบคุมโดยใช้ สวิตช์  on/off  [page 36-58](https://docs.google.com/document/d/1mfy1tqCErNVFj-Y-CQ-8FOzATdkFa578/edit?usp=sharing&ouid=112123354426746955459&rtpof=true&sd=true) 

![](https://lh4.googleusercontent.com/E4790ln9rjkGBbFRbWydU_rtZo_9YMS1ekCV7NxJ_bNoDjDG8NDGVCPXdo-kz9quzBp-vqHFJLmbvjTs8AJlUEwY_UO8nfuewb6DjnQ0oUBVYVxxdP9Kf_6oPV1hxX6aoc4FVCksraPsmkOmliHCyMw7k5HmA8dZ8SwNJce4CDiEWS2OkiJBZyxcOf4ReMl2fGxLxA)


ตัวอย่าง การทำงานสายพาน [page 61-62](https://docs.google.com/document/d/1mfy1tqCErNVFj-Y-CQ-8FOzATdkFa578/edit?usp=sharing&ouid=112123354426746955459&rtpof=true&sd=true)










----------
    
    
    
    PLC ควบคุมชุดทดลอง AIC  60%
        - อ่านค่า sensor
        - ควบคุม  M1 Robot 
    Ref. เอกสารการเขียน LD ของ 
    - [Auto Direc.](https://drive.google.com/file/d/1XGtkPk0SnKXdOdqEj90YgZ4AXmq33e9B/view?usp=sharing)  
    - ใบงาน m1 Gxword3
    
    (เรียบเรียงเป็น เอกสาร AIC)

** ยังไม่สอนการเขียน M1 แต่เน้น PLC รับ และส่งค่าไปยัง M1


































----------



Thsi lab will guide you to learn about basic PLC and PLC interfaces from ZERO to HERO, So what we have to serve you in this lesson? Let’s look around to gether. 

![SIMATIC S7-1200 | SIMATIC Controllers | Siemens Global](https://new.siemens.com/content/dam/internet/siemens-com/global/products-services/automation/systems/industrial/plc/simatic-s7-1200/application-pages-/8835_S7-1200-interactive_200729/static/img/bg.jpg)

# Things used in this project
## Hardware component
| **Figure**                                                                                                                            | **Name**                  | **Amount** |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------- | ---------- |
| ![](https://paper-attachments.dropbox.com/s_59625FBBC4D73C463D1FB0003439581FBA2A663DC1848F5B37B56CC9CCE0BB52_1655628651335_file.jpeg) | FX5UC 32MT Mitsubishi PLC | 1          |
| ![](https://cdn.mos.cms.futurecdn.net/sM6jQHKqVCAKk2pmdbiiJR.jpg)                                                                     | PC / Notebook RAM > 16GB  | 1          |

## Software component
| **Figure**                                                                                                                                                                                           | **Name**     | **Amount** |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | ---------- |
| ![](https://br.atsit.in/th/wp-content/uploads/2022/02/windows-11-e0b881e0b8b1e0b89a-windows-10-e0b8ade0b8b0e0b984e0b8a3e0b884e0b8b7e0b8ade0b884e0b8a7e0b8b2e0b8a1e0b981e0b895e0b881e0b895e0b988.jpg) | Window 10/11 | -          |
| ![](https://www.mitsubishielectric.com/fa/products/cnt/plceng/smerit/gx_works3/images/gxworks3_concept.jpg)                                                                                          | GXWork3      | -          |
| ![WinRAR (โหลดโปรแกรม WinRAR โปรแกรมบีบอัดไฟล์ แตกไฟล์ อันดับ 1 ของโลก) 6.10  ดาวน์โหลดโปรแกรมฟรี](https://i.ytimg.com/vi/r0Prw0NkTCo/mqdefault.jpg)                                                 | Winrar       | -          |

# **Story**
## **Introduction**

reference : [(226) PLC EP#1 First PLC with PLC MITSUBISHI by Program GX work2 - YouTube](https://www.youtube.com/watch?v=9ZZoVLbYTuA)

## Topic

*Basic knowhow plc and how to use it.
[(226) PLC EP#1 First PLC with PLC MITSUBISHI by Program GX work2 - YouTube](https://www.youtube.com/watch?v=9ZZoVLbYTuA)

    - Datasheet and focuspoint
    - Overview PLC
    - Input wiring skinning and sourcing
        - Lit LED Example 
    - Output wiring

May be guiding 02
*Interface bus on PLC (Knowledge)

    - TCP and UDP
    - Modbus
    - Canbus
    - …

**Optional**
*Read data from modbus and tcp or other interface port 

## BOM

[Search results for: 'Modbus' (seeedstudio.com)](https://www.seeedstudio.com/catalogsearch/result/?q=Modbus)
**Thing want to use on project** 
MOD, BUS TCP

- Industries Button industries grade 15B
- Pump water + gas and motor (servo or …) industries grade (Robot course)
- Sensor 
    - Check fluid 
    - RPM motor 
    - Camera High frame + Infared mode 
    - Sensor check High temp and pressure
    -  Sensor check [ESD](https://iopscience.iop.org/article/10.1088/1742-6596/646/1/012018)
    - Sensor check level fluid
    - [Sensor check viblation on industries](https://ifra.io/%E0%B9%80%E0%B8%8B%E0%B8%99%E0%B9%80%E0%B8%8B%E0%B8%AD%E0%B8%A3%E0%B9%8C%E0%B8%A7%E0%B8%B1%E0%B8%94%E0%B9%81%E0%B8%A3%E0%B8%87%E0%B8%AA%E0%B8%B1%E0%B9%88%E0%B8%99%E0%B8%AA%E0%B8%B0%E0%B9%80%E0%B8%97/)
    - Rotary encoder 
        - Data wire shotest you can do.
        - High resolution > Low resolution
        - Magnetic type will be immue with vibration (Absolute type)
        - (Extention) Brackets support vibration
    - Multimiter

*[Make BOM](https://www.geniuserp.com/blog/how-to-make-a-bill-of-materials-the-right-way)
Call to father or Check price from internet

