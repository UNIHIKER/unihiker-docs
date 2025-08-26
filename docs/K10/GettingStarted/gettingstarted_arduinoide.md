## **UNIHIKER K10 with Arduino IDE**
The Arduino IDE is a software tool used for programming, compiling, and uploading code to microcontroller boards. It provides a simple and user-friendly interface that allows developers to write, edit, and debug code using the Arduino programming language (based on C/C++).
In this tutorial, we will guide you through the process of downloading Arduino IDE and installing UNIHIKER K10 sdk on your computer.<br/>
![Arduinnoide](img/gettingstarted_arduinoide/Arduino.png)

### **Download Arduino IDE**
Arduino IDE is an open source programming software which supports a large number of MCU dev boards. it provides an easy and fast C++ programming experience.

| **Download** |  |
| --- | --- |
| **Download from Arduino** | [Arduino IDE](https://www.arduino.cc/en/software/) |

!!! Note 
    UNIHIKER K10 is now fully support all versions of Arduino IDE since SDK version 0.0.2

### **Install Arduino IDE SDK**

SDK URL:
https://downloadcd.dfrobot.com.cn/UNIHIKER/package_unihiker_index.json<br/>
Open "File->Preference" in Arduino IDE<br/>
![image.png](img/gettingstarted_arduinoide/IDESDK1.png) 

Set "Compiler warnings" as none<br/>
![image.png](img/gettingstarted_arduinoide/IDESDK2.png) 

Click here to add SDK URL<br/>
![image.png](img/gettingstarted_arduinoide/IDESDK3.png) 

Copy and paste the URL in the box, then click OK to save<br/>
![image.png](img/gettingstarted_arduinoide/IDESDK4.png) 

Open "Tools->Board->Boards Manager"<br/>
![image.png](img/gettingstarted_arduinoide/IDESDK5.png)

Serach unihiker and install the SDK<br/>
![image.png](img/gettingstarted_arduinoide/IDESDK6.png)

UNIHIKER K10 will appear in your Arduino IDE<br/>
![image.png](img/gettingstarted_arduinoide/IDESDK7.png)

Note:The Arduino IDE SDK for UNIHIKER K10 is still in beta, there may be some bugs. if you find a bug, you can send an email to UNIHIKER team and we will fix it as soon as possible.<br/>
Email: unihiker@dfrobot.com<br/>
We will update to the official version in the near future.

## **Arduino Example**
Click to the [Arduino Example](../Examples/examples_arduinoide.md).