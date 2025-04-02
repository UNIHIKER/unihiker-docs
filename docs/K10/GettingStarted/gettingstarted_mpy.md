## **UNIHIKER K10 with MicroPython**

## **Download**
- Micropython firmware<br/>
Before using micropython to program the UNIHIKER K10, the Micropython firmware has to be uploaded into the UNIHIKER K10.

| **Download channel** |  |
| --- | --- |
| **Download from Google Drive:** | [Google Drive](https://drive.google.com/file/d/1gKTtFghDu0V-vSi19ahH7bor5WSaBbDE/view?usp=drive_link) |


- Flash Download Tool<br/>
Flash Download Tool released by Espressif is the tool to upload the Micropython firmware into the UNIHIKER K10.<br/>[Click to download](https://www.espressif.com.cn/en/support/download/other-tools) Flash Download Tool.
<br/>

- Thonny<br/>
Thonny is one of the most common Micropython editor.<br/>[Click to download](https://thonny.org/) Thonny.

## **Flash MicroPython Firmware**
Click to open the Flash Download Tool, then choose the ESP32-S3
![image.png](img/gettingstarted_mpy/flashdownload1.png)

Select the firmware and fill up the address with 0x00, then click on √.
![image.png](img/gettingstarted_mpy/flashdownload2.png)

Press and hold the BOOT button on the back of K10, connect the board to the computer and select the corresponding port in the software.<br/>
First click "ERASE" to clear the flsh, and then click "START" to flash the firmware after ERASE step is successful.<br/>
Press the RST reset button on the K10 board after the flash is completed.<br/>


## **Coding**
Open up Thonny as the MicroPython Editor.<br/>
Select the ESP32 device in Thonny.<br/>
![image.png](img/gettingstarted_mpy/Thonny1.png)

Creat a new file and enter the code.<br/>
![image.png](img/gettingstarted_mpy/Thonny2.png)

````python title="hello_unihiker"
from unihiker_k10 import screen,camera,tf_card,
from unihiker_k10 import temp_humi,light,acce
from unihiker_k10 import rgb,button
from unihiker_k10 import mic,speaker
import time

#Init display and set the display direction(0~3)
screen.init(dir=2)#direction default to be 2
camera.init()#Init camera


#On board LED
rgb.write(num = 0, R=255,G=0,B=0)
rgb.write(num = 1, R=0,G=255,B=0)
rgb.write(num = 2, R=0,G=0,B=255)
time.sleep(1)
rgb.clear()

#Start record voice, save the audio file into the ESP32 file system then play the audio
screen.draw_text(text="begin sys recode",line=0)
screen.show_draw()
mic.recode_sys(name="sound.wav",time=5)
screen.draw_text(text="recode sys done",line=0)
screen.show_draw()
time.sleep(1)
screen.draw_text(text="begin sys play",line=0)
screen.show_draw()
speaker.play_sys_music("sound.wav")
screen.draw_text(text="end sys play",line=0)
screen.show_draw()
time.sleep(1)

#Display the camera image onto the screen
screen.show_camera(camera)

bt_a=button(button.a)#Init on board button A
bt_b=button(button.b)#Init on board button B
def button_a_pressed():
    screen.draw_text(text="btn_a:pressed",line=5)
    screen.show_draw()
    
def button_a_released():
    screen.draw_text(text="btn_a:released",line=5)
    screen.show_draw()
    
def button_b_pressed():
    screen.draw_text(text="btn_b:pressed",line=6)
    screen.show_draw()
    
def button_b_released():
    screen.draw_text(text="btn_b:released",line=6)
    screen.show_draw()
bt_a.event_pressed = button_a_pressed
bt_a.event_released = button_a_released
bt_b.event_pressed = button_b_pressed
bt_b.event_released = button_b_released

while True:
    screen.draw_text(text="temp=" + str(temp_humi.read_temp()) + " humi=" + str(temp_humi.read_humi()),line=0)
    screen.show_draw()
    screen.draw_text(text="light=" + str(light.read()) ,line=1)
    screen.show_draw()
    screen.draw_text(text="ax=" + str(acce.read_x()),line=2)
    screen.show_draw()
    screen.draw_text(text="ay=" + str(acce.read_y()),line=3)
    screen.show_draw()
    screen.draw_text(text="az=" + str(acce.read_z()),line=4)
    screen.show_draw()
    time.sleep(0.1)
````

CTRL+S to save to micropython device. Choose to save to This computer is also fine, but if the program save to local computer, the program will be lost after K10 was reboot, it is more suitable for saving to the computer when debugging.<br/>
![image.png](img/gettingstarted_mpy/Thonny3.png)

save the code and name as main.py
![image.png](img/gettingstarted_mpy/Thonny4.png)

Click to run the code
![image.png](img/gettingstarted_mpy/Thonny5.png)


## **Flash back to Arduino C firmware**
Restore the device to the factory Arduino firmware in Mind+.
![image.png](img/gettingstarted_mpy/Restore1.png)