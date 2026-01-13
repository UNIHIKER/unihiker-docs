
## **Display - Camera Display**
````python title="Display_Camera"
from unihiker_k10 import screen
import time
from k10_base import Camera

camera = Camera() 

screen.init(dir=2)
camera.init()

screen.show_camera(camera)

while True:
    time.sleep(1)
````

## **Display - Screen icon Display**
````python title="Screen Display"
from unihiker_k10 import screen
import time
from k10_base import Camera

camera = Camera()
camera.init()
screen.init(dir=2)
screen.show_camera(camera)
screen.show_bg(color=0xFFFF00)
screen.set_width(width=5)
screen.draw_line(x0=0,y0=0,x1=80,y1=80,color=0x0000FF)
screen.draw_point(x=100,y=10,color=0xFF0000)
screen.draw_rect(x=120,y=100,w=80,h=120,bcolor=0xFF6666,fcolor=0x0000FF)
screen.draw_rect(x=120,y=100,w=40,h=60,bcolor=0x012345)
screen.draw_circle(x=80,y=80,r=40,bcolor=0x00FF00,fcolor=0x0000FF)
screen.draw_circle(x=80,y=80,r=20,bcolor=0xFF0000)
screen.draw_text(text="你好\n23",x=10,y=0,font_size=24,color=0xFF0000)
screen.draw_text(text="line\n456\nhgjh\n",line=2,font_size=24,color=0xFF0000)
screen.show_draw()
time.sleep(2)
screen.clear()

while True:
    time.sleep(1)
````

## **On board Sensor - button**
````python title="On board button"
from unihiker_k10 import button
import time
bt_a=button(button.a)
bt_b=button(button.b)

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
    print("button_a.status=",bt_a.status())
    print("button_b.status=",bt_b.status())
    time.sleep(0.1)
    pass

````

## **On board Sensor - Temperature & Humidity sensor**
````python title="Temperature & Humidity sensor"
from unihiker_k10 import button,temp_humi,screen
import time

screen.init(dir=2)
screen.show_bg(color=0xFFFF00)

while True:
    temp_c = temp_humi.read_temp()
    temp_f = temp_humi.read_temp_f()
    humi = temp_humi.read_humi()
    print(temp_c)
    print(temp_f)
    print(humi)
    screen.draw_text(text="温度: "+str(temp_c)+" C",x=10,y=0,font_size=24,color=0xFF0000)
    screen.draw_text(text="温度: "+str(temp_f)+" f",x=10,y=20,font_size=24,color=0xFF0000)
    screen.draw_text(text="湿度: "+str(humi)+" %RH",x=10,y=40,font_size=24,color=0xFF0000)
    screen.show_draw()
    time.sleep(1)

````

## **On board Sensor - Ambient Light Sensor**
````python title="Ambient Light Sensor"
from unihiker_k10 import light
import time
while True:
    print(light.read())
    time.sleep(0.1)
````

## **On board Sensor - On-board Accelerometer**
````python title="On-board Accelerometer"
from unihiker_k10 import acce
import time

while True:
    print("x=",acce.read_x())
    print("y=",acce.read_y())
    print("z=",acce.read_z())
    time.sleep(0.1)
````

## **On board Sensor - On board RGB LED**
````python title="On board RGB LED"
from unihiker_k10 import rgb
import time

rgb.write(num = 0,color=0x0000FF)

rgb.write(num = 0,R=255,G=0,B=0)

rgb.write(num = 0,color=0x000000)

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

## **On board Sensor - TF card**
````python title="TF card"
from k10_base import TF_card
import os
tf_card = TF_card()
files = os.listdir("/sd")
print("Files in /sd:",files)
````

## **On board Sensor - Record & Play**
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

## **Communication - Wifi**
````python title="Wifi"
from k10_base import WiFi,MqttClient
wifi = WiFi() 
wifi.connect(ssid="DFRobot-guest",psd="dfrobot@2017",timeout=50000) #Attempt to connect to a Wi-Fi network. Parameter names are optional. `timeout` is an optional parameter indicating the connection timeout duration, with a default timeout of 10,000 milliseconds.
wifi.status() #Returns the network connection status. True indicates connected, False indicates disconnected.
wifi.info() #Return a string containing the current IP address, subnet mask, gateway, and other information.
````

## **Communication - MQTT**
````python title="MQTT"
from k10_base import WiFi,MqttClient

import time

wifi.connect(ssid="DFRobot-guest",psd="dfrobot@2017",timeout=50000) #Attempt to connect to the Wi-Fi network. The parameter name is optional. `timeout` is an optional parameter indicating the connection timeout duration, with a default timeout of 10,000 milliseconds.
wifi.status() #Returns the network connection status. True indicates connected; False indicates disconnected.
wifi.info() #wifi.info() # Returns a string containing information such as the current IP address, subnet mask, and gateway.

def received_1ffdf0jpLa():
    msg=mqttclient.message(topic='siot/test')
    print(msg)

mqttclient.connect(server= "192.168.9.172",
                   port=1883, 
                   client_id="",
                   user= "siot" ,
                   psd= "dfrobot") #Blocked operation, default timeout is 3 seconds.
mqttclient.connected() #Return connection status

#msg=mqttclient.message(topic='1ffdf0jpLa') #Retrieve messages received for the specified topic. If no messages exist for that topic, return None.

mqttclient.received (topic='siot/test', #When a message is received for the corresponding topic, the callback function
                     callback=received_1ffdf0jpLa) #Specify a callback function via callback

while True: 
    mqttclient.publish(topic='siot/test',content= 'hello')#Send a message to the corresponding topic, with content as the message text.
    time.sleep(3)

````

## **Communication - Bluetooth HID**
````python title="Bluetooth HID"
from unihiker_k10 import screen, hid, keycode,button
import time
bt_a=button(button.a)
bt_b=button(button.b)

ble_hid = hid(name='mpy_hid') 
screen.init(dir = 2)
screen.show_bg(color=0xFFFF00)
screen.draw_text(text="ready",line=1,font_size=24,color=0xFF0000)
screen.show_draw()
while True:
    if ble_hid.isconnected():
        screen.draw_text(text="connect",line=1,font_size=24,color=0xFF0000)
        screen.show_draw()
    else:
        screen.draw_text(text="disconnect",line=1,font_size=24,color=0xFF0000)
        screen.show_draw()
    if bt_a.status() == 1:
        ble_hid.keyboard_send(keycode.SPACE) 
    if bt_b.status() == 1:
        ble_hid.keyboard_send([keycode.CTRL,keycode.a]) 
    time.sleep(0.1)
````

## **Peripheral Sensor - Servo**
````python title="Servo"
from unihiker_k10 import servo
import time
s1=servo(1) # Connect the servo to pin P1.
while True:
    s1.angle(value=170) #Set the servo to rotate to the 180° position, with an angle range of: 0 to 180 degrees.
    time.sleep(1)
    s1.angle(value=10)
    time.sleep(1)

````

## **Peripheral Sensor - RGB light strip**
````python title="WS2812"
from unihiker_k10 import neopixel
ws2812=neopixel(0,3) #Connect the light strip to pin 0, LED number is 3.
ws2812.brightness(9)#Set brightness 0-9

ws2812.write(0,1,0x00,0x00,0xFF) #Display colors on LEDs 0-1 based on their r, g, b values.

````

## **Peripheral Sensor - DHT11/DHT22**
````python title="DHT11/DHT22"
from unihiker_k10 import dht
import time

dhtsensor=dht(0)#Initialize the DHT sensor connected to port 0; it can automatically detect whether it is DHT11 or DHT22.
while True:
    temp,hum=dhtsensor.read()
    print(temp)
    print(hum)
    time.sleep(1)
````

## **Peripheral Sensor - DS18B20**
````python title="DS18B20"
from unihiker_k10 import ds18b20
import time
ds=ds18b20(1)
while True:
    temp=ds.read()
    print(temp)
    time.sleep(1)
````

## **Peripheral Sensor - TRIG-ECHO Ultrasonic sensor**
````python title="TRIG-ECHO"
from unihiker_k10 import ultrasonic
import time 
sonic=ultrasonic(trig=0,echo=0) #Connect the trig and echo pins. When assigning the same pin, use SEN0388.
while True:
    print(sonic.distance())
    time.sleep(0.1)
````

## **Peripheral Sensor - Weight sensor(KIT0176)**
````python title="Weight Sensor"
from unihiker_k10 import force
import time
fs=force()
fs.zero() #Weight Zeroing
while True:
    print(fs.read(mass=False)) #Returns the mass value in grams. # Returns the mass by default, and when parameter mass=False, returns the force in N (Newtons)
    time.sleep(0.5)
````

## **Peripheral Sensor - GPIO**
````python title="GPIO"
from unihiker_k10 import pin
import time

p0=pin(0)
p1=pin(1)

p2 = pin(2)
p2.write_digital(0)
p2.write_digital(1)

while True:
    print('read_digital:'+ str(p0.read_digital()))
    time.sleep(1)
    print('read_analog:'+ str(p0.read_analog()))
    time.sleep(1) 
    print('write_digital_1')
    p0.write_digital(value=1)
    time.sleep(1)
    print('write_digital_0')
    p0.write_digital(value=0)
    time.sleep(1)
    
    print('write_analog(value=0,freq=255)')
    p1.write_analog(value=0,freq=255)
    time.sleep(1)
    print('write_analog(value=500,freq=255)')
    p1.write_analog(value=500,freq=255)
    time.sleep(1)
    print('write_analog(value=1000,freq=255)')
    p1.write_analog(value=1000,freq=255)
    time.sleep(1)
````

## **AI - Movement detection**
````python title="Movement Detection"
import ai
import time
from unihiker_k10 import screen
import machine

#Init ai
ai.init_ai()

#Start camera
ai.camera_start()

#Start move detect
ai.move_detect()

screen.init()

try:
    while True:
        image_data = ai.camera_capture()
        screen.show_camera_img(image_data)
        if ai.is_ai_data_updated():
            data = ai.get_ai_data()
            print(f"Move: {data['move_flag']}")
            
        time.sleep_ms(1)
    
except KeyboardInterrupt:
    print("\nCapture Ctrl+C interrupt!")
    ai.deinit_ai()
````

## **AI - QR Code recognition**
````python title="QR Code recognition"
import ai
import time
from unihiker_k10 import screen
import machine

#Init AI
ai.init_ai()

#Start camera
ai.camera_start()

#Start QR code scanner
ai.code_scanner() 

screen.init()

try:
    while True:
        image_data = ai.camera_capture()
        screen.show_camera_img(image_data)
        if ai.is_ai_data_updated():
            data = ai.get_ai_data()
            if data['code_data']:
                print(f"QR Code: {data['code_data']}")
            else:
                print("No QR code detected")
            
        time.sleep_ms(1)
    
except KeyboardInterrupt:
    print("\nCapture Ctrl+C interrupt!")
    #screen.deinit()
    ai.deinit_ai()
````

## **AI - Cat/Dog recognition**
````python title="Cat/Dog recognition"
import ai
import time
from unihiker_k10 import screen
import machine

#Init AI
ai.init_ai()

#Start Camera
ai.camera_start()

#Start cat/dog detect
ai.cat_detect() 

screen.init()

try:
    while True:
        image_data = ai.camera_capture()
        screen.show_camera_img(image_data)
        if ai.is_ai_data_updated():
            data = ai.get_ai_data()
            print(f"Cat: {data['cat_flag']}")
            if data['cat_flag']:
                print(f"Cat Detect: {data['cat_detect']['frame_length']}")
                print(f"Cat Detect: {data['cat_detect']['frame_width']}")
            
        time.sleep_ms(1)
    
except KeyboardInterrupt:
    print("\nCapture Ctrl+C interrupt!")
    #screen.deinit()
    ai.deinit_ai()
````

## **AI - Face recognition**
````python title="Face recognition"
import ai
import time
from unihiker_k10 import screen
import machine

from unihiker_k10 import button
bt_a=button(button.a)#Init button A
bt_b=button(button.b)#Init button B

#Init AI
ai.init_ai()

#Start camera
ai.camera_start()

#Start face recognition
ai.face_recognize_start()

screen.init()

#When the button A/B pressed
def button_a_pressed ():
    print("button_a_pressed")
    ai.register_face()
    
def button_b_pressed():
    print("button_b_pressed")
    ai.recognize_face()
    
bt_a.event_pressed = button_a_pressed
bt_b.event_pressed = button_b_pressed

try:
    while True:
        image_data = ai.camera_capture()
        screen.show_camera_img(image_data)
        if ai.is_ai_data_updated():
            data = ai.get_ai_data()
            print(f"Face: {data['face_flag']}")
            if data['face_flag']:
                print(f"Face ID: {data['face_detect']['face_id']}")
                print(f"Left eye: {data['face_detect']['left_eye']}")
            
        time.sleep_ms(1)
    
except KeyboardInterrupt:
    print("\nCapture Ctrl+C interrupt!")
    #screen.deinit()
    ai.deinit_ai()
````