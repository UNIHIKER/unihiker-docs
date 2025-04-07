## **Examples of all on-board resources**
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

## **Screen Display**
````python title="Screen Display"
from unihiker_k10 import screen
import time
screen.init(dir=2)
screen.show_bg(color=0xFFFF00)
screen.set_width(width=5)
screen.draw_line(x0=0,y0=0,x1=80,y1=80,color=0x0000FF)
screen.draw_point(x=100,y=10,color=0xFF0000)
screen.draw_rect(x=120,y=100,w=80,h=120,bcolor=0xFF6666,fcolor=0x0000FF)
screen.draw_rect(x=120,y=100,w=40,h=60,bcolor=0x012345)
screen.draw_circle(x=80,y=80,r=40,bcolor=0x00FF00,fcolor=0x0000FF)
screen.draw_circle(x=80,y=80,r=20,bcolor=0xFF0000)
screen.draw_text(text="hello\n123",x=10,y=0,font_size=24,color=0xFF0000)
screen.draw_text(text="line\n456\nhgjh\n",line=2,font_size=24,color=0xFF0000)
screen.show_draw()
time.sleep(2)
screen.clear()
while True:
    pass
````

## **On board button**
````python title="On board button"
from unihiker_k10 import button
import time
bt_a=button(button.a)#Init button A
bt_b=button(button.b)#Init button B

#When button A/B is pressed/release
def button_a_pressed():
    print("button_a_pressed")
    
def button_a_released():
    print("button_a_released")
    
def button_b_pressed():
    print("button_b_pressed")
    
def button_b_released():
    print("button_b_released")

bt_a.event_pressed = button_a_pressed
bt_a.event_released = button_a_released
bt_b.event_pressed = button_b_pressed
bt_b.event_released = button_b_released

while True:
    #print("button_a.status=",bt_a.status())
    #print("button_b.status=",bt_b.status())
    time.sleep(0.1)
    pass
````

## **Temperature & Humidity sensor**
````python title="Temperature & Humidity sensor"
from unihiker_k10 import button,temp_humi
#Read (temp ℃/temp ℉/humi)
print(temp_humi.read_temp())#℃
print(temp_humi.read_temp_f())#℉
print(temp_humi.read_humi())
while True:
    pass
````

## **Ambient Light Sensor**
````python title="Ambient Light Sensor"
from unihiker_k10 import light
import time
while True:
    print(light.read())
    time.sleep(0.1)
````

## **On board RGB LED**
````python title="On board RGB LED"
from unihiker_k10 import rgb
import time
#LED number (0,1,2,ALL) show color
rgb.write(num = 0,color=0x0000FF)#num=-1 or not assigne any value to num is select all LED

#LED number (0,1,2,ALL) show RGB color
rgb.write(num = 0,R=255,G=0,B=0)

#switch off LED number (0,1,2,ALL)
rgb.write(num = 0,color=0x000000)

#set RGB LED brightness
rgb.brightness(9)
while True:
    rgb.write(color=0xFF00FF)
    time.sleep(1)
    rgb.write(num = 0, R=255,G=0,B=0)
    rgb.write(num = 1, R=0,G=255,B=0)
    rgb.write(num = 2, R=0,G=0,B=255)
    time.sleep(1)
    rgb.clear()
    time.sleep(1)
    rgb.write(num = 2, R=0,G=0,B=255)
    time.sleep(1)
    rgb.write(color=0x0000)
    time.sleep(1)
````

## **TF card**
````python title="TF card"
from unihiker_k10 import tf_card
import os
files = os.listdir("/sd")
print("Files in /sd:",files)
````

## **Record & Play**
````python title="Record & Play"
from unihiker_k10 import mic,speaker
import time
print("begin sys recode")
mic.recode_sys(name="sound.wav",time=5)
print("recode sys done")
time.sleep(1)
print("begin sys play")
speaker.play_sys_music("sound.wav")
print("end sys play")
time.sleep(1)
print("begin tf recode")
mic.recode_tf(name="sound.wav",time=5)
print("recode tf done")
time.sleep(1)
print("begin tf play")
speaker.play_tf_music("sound.wav")
print("end tf play")
while True:
    pass
````

## **Wifi**
````python title="Wifi"
from unihiker_k10 import wifi
#try to connect wifi.The parameter name can be omitted. timeout is an optional parameter that indicates the connection timeout duration, the default timeout is 10000 milliseconds.
wifi.connect(ssid="dfrobotOffice",psd="dfrobot2011",timeout=50000) 
#Return network connection status, True means connected, False means not connected
wifi.status() 
# Returns a string containing the current IP address, subnet mask, gateway and other information
wifi.info()
````

## **MQTT**
````python title="MQTT_EASYIOT"
# EASYIOT 
from unihiker_k10 import wifi
from unihiker_k10 import mqttclient
import time

#Connect WiFi
wifi.connect(ssid="Redm",psd="aijine12345",timeout=50000)
wifi.status()
wifi.info()

def received_1ffdf0jpLa():
    msg=mqttclient.message(topic='AwErylzNg')
    print(msg)

mqttclient.connect(server= "iot.dfrobot.com",
                   port=1883, 
                   client_id="",
                   user= "VB3Xs_kHg" ,
                   psd= "VB3Xy_zNgz") #Blocking runs with a default timeout of 3 seconds
mqttclient.connected() #Return to Connection Status
mqttclient.publish(topic='AwErylzNg',content= 'hello')#Send a message to the corresponding topic, content is the content of the message.
#msg=mqttclient.message(topic='1ffdf0jpLa') #Get the messages received by the corresponding topic, if there are no messages for the topic, then return None.

mqttclient.received (topic='AwErylzNg', #When the corresponding topic receives a message, the callback function
                     callback=received_1ffdf0jpLa) #Specify the callback function via callback

while True:
    time.sleep(0.1)
    pass
````


````python title="MQTT_SIOTV1"
# SIOT V1
from unihiker_k10 import wifi
from unihiker_k10 import mqttclient
import time

wifi.connect(ssid="DFRobot-guest",psd="dfrobot@2017",timeout=50000)
wifi.status()
wifi.info()

def received_1ffdf0jpLa():
    msg=mqttclient.message(topic='siot/Speed')
    print(msg)

mqttclient.connect(server= "192.168.7.141",
                   port=1883, 
                   client_id="",
                   user= "siot" ,
                   psd= "dfrobot") 
mqttclient.connected() 
mqttclient.publish(topic='siot/Speed',content= 'hello')
#msg=mqttclient.message(topic='1ffdf0jpLa') 

mqttclient.received (topic='siot/Speed', 
                     callback=received_1ffdf0jpLa) 
while True:
    time.sleep(0.1)
    pass
````

````python title="MQTT_SIOTV1"
# SIOT V2   mqttclient.publishs should be added "->"
from unihiker_k10 import wifi
from unihiker_k10 import mqttclient
import time

wifi.connect(ssid="Redm",psd="aijine12345",timeout=50000) 
wifi.status() 
wifi.info() 

def received_1ffdf0jpLa():
    msg=mqttclient.message(topic='siot/Speed')
    print(msg)

mqttclient.connect(server= "192.168.45.146",
                   port=1883, 
                   client_id="",
                   user= "siot" ,
                   psd= "dfrobot") 
mqttclient.connected() 
mqttclient.publish(topic='siot/Speed',content= '->hello')
#msg=mqttclient.message(topic='1ffdf0jpLa')

mqttclient.received (topic='siot/Speed', 
                     callback=received_1ffdf0jpLa) 

while True:
    time.sleep(0.1)
    pass
````


## **Bluetooth HID**
````python title="Bluetooth HID"
from unihiker_k10 import screen, hid, keycode,button
import time
bt_a=button(button.a)#Init button A
bt_b=button(button.b)#Init button B

ble_hid = hid(name='mpy_hid') #Init bluetooth HID and name the device as mpy_hid
screen.init(dir = 2)
screen.show_bg(color=0xFFFF00)
screen.draw_text(text="ready",line=1,font_size=24,color=0xFF0000)
screen.show_draw()
while True:
    if ble_hid.isconnected():#Determine whether the connection has been made, True is connected, False is not connected Non-blocking
        screen.draw_text(text="connect",line=1,font_size=24,color=0xFF0000)
        screen.show_draw()
    else:
        screen.draw_text(text="disconnect",line=1,font_size=24,color=0xFF0000)
        screen.show_draw()
    if bt_a.status() == 1:
        ble_hid.keyboard_send(keycode.SPACE) #keyboard pressing space
    if bt_b.status() == 1:
        ble_hid.keyboard_send([keycode.CTRL,keycode.a]) #Keyboard pressing CTRL+a
    time.sleep(0.1)
````

## **Servo**
````python title="Servo"
from unihiker_k10 import servo
import time
s1=servo(1) # Connect servo to P1
while True:
    s1.angle(value=170) #Set the servo to 170°(0~180°)
    time.sleep(1)
    s1.angle(value=10)
    time.sleep(1)
````

## **WS2812**
````python title="WS2812"
from unihiker_k10 import neopixel
ws2812=neopixel(P1,3) #Connect the LED strip to p1, the LED strip has 3 WS2812
ws2812.brightness(9)#Set brightness

ws2812.write(0,1,0x00,0x00,0xFF) #Set WS2812 0-2 to display colours based on r, g, b values.
````

## **DHT11/DHT22**
````python title="DHT11/DHT22"
from unihiker_k10 import dht
import time

dhtsensor=dht(P0)#Initialising the DHT sensor connected to port 0, 
#which automatically recognises whether it is a DHT11 or a DHT22.

while True:
    temp,hum=dhtsensor.read()
    print(temp)
    print(hum)
    time.sleep(1)
````

## **DS18B20**
````python title="DHT11/DHT22"
from unihiker_k10 import ds18b20
import time
ds=ds18b20(1)
while True:
    temp=ds.read()
    print(temp)
    time.sleep(1)
````

## **TRIG-ECHO Ultrasonic sensor**
````python title="TRIG-ECHO"
from unihiker_k10 import ultrasonic
import time 
sonic=ultrasonic(trig=0,echo=0) #To connect the trig and echo pins, the DFRobot SEN0388 is used to fill in the same pins.
while True:
    print(sonic.distance())
    time.sleep(0.1)
````

## **Weight sensor(KIT0176)**
````python title="TRIG-ECHO"
from unihiker_k10 import force
import time
fs=force()
fs.zero() #Weight Zeroing
while True:
    print(fs.read(mass=False)) #Returns the mass value in grams. # Returns the mass by default, and when parameter mass=False, returns the force in N (Newtons)
    time.sleep(0.5)
````