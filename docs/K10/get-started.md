## **UNIHIKER K10**
UNIHIKER K10 is an ESP32 based development board designed for rapid experience and learning of artificial intelligence. The board integrates a 2.8-inch LCD color screen, WiFi, Bluetooth, camera, microphone, speaker, RGB indicator, multiple sensors and a rich set of expansion interfaces. With the highly integrated on-board resources, sensor control, IoT applications, and AI projects such as face recognition, voice recognition, and speech synthesis can be easily realized without the need to connect additional devices during the programming process.

### **Layout**
![image.png](img/get-started/getstarted1.png)

### **Quick Start**
Use a USB cable to connect the USB-C port of the UNIHIKER K10 to a computer USB port or 5V adapter, and wait for the K10's screen to display a logo, which means that K10 is ready to go. 
After successful boot-up, K10 runs the factory built-in program, you can quickly experience the most of the K10 features. (Note: K10 in the document is the abbreviation of K10 of the UNIHIKER K10)<br/>
![image.png](img/get-started/getstarted2.png)

!!! Note 
    Please make sure the USB cable is plugged directly into the USB port of your computer, do not use intermediate components such as extension cables or docking stations, and make sure the USB cable has a data transfer function.

-  Press button B to switch to the "Face Detection" mode, when a face appears in the picture taken by the camera, the recognition frame will automatically frame out the face.
![image.png](img/get-started/getstarted3.png)

- Press button B again to switch to “voice recognition” mode, you can wake up K10 by speak "Jarvis" or "Hi Telly", then speak command word like turn on the light, turn off the light, play animation, play a game or play music and other operations through the screen prompts, through voice control commands.<br/>
Note: To use play music function in the voice recognition mode. You need to prepare a 32G (or below) TF card, and then format it into FAT32 mode, and store a music file with the name of "music.wav" in it to play the music.

- Press button B again to switch to “Sensor” mode, at this mode the screen will display a plant. When blowing against the temperature and humidity sensor in the upper right corner of the board, it will simulate rain to water the plant; when it doesn't rain for a long time, the plant will wither; when irradiating the ambient light sensor in the upper right corner of the board with a strong light, the sun will become bigger to simulate sunlight; when it rains and there is enough light, the plant will bloom.<br/>
![image.png](img/get-started/getstarted4.png)

- Press the button B again to switch to “View Tutorial” mode, and scan the QR code through your cell phone to view the tutorial of K10.
To start programming on your own, please click on [MindPlus](https://www.unihiker.com/wiki/K10/GettingStarted/gettingstarted_mindplus/)

## **Working offline Power Supply**
After burning a programme for the K10 in Mind+ or other IDE, the programme will be stored in the board's Flash and will not be lost during a power failure, so when the K10 is re-powered it will run the programme that was uploaded last time.

## **Power Supply**
- Supports power supply via Type-C port, 5V DC.
- Supports power supply via on-board PH2.0 battery port, 3.0~6.0V DC. Recommend power source: 3.7V Lipo battery or three AA/AAA cells.
- Supports power supply via edge connector
- Supports power supply via expansion board

## **TF card**
We recommend using genuine SanDisk cards sold by DFRobot: [32GB Class 10](https://www.dfrobot.com/product-1715.html).
Using an unknown brand of memory card may cause problems such as card read/write failure and program crash.
If you use a 32GB or higher memory card, you need to format the card into FAT32 format.

