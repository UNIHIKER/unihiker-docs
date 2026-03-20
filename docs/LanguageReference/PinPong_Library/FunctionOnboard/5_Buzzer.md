### **Description**
The UNIHIKER main controllers come equipped with an integrated buzzer, which can emit pre-set tones.
### **Syntax**
**buzzer.play(buzzer.DADADADUM, buzzer.Once)**
### **Parameters**
- **buzzer.DADADADUM:** The music played by the buzzer.
- **buzzer.Once:** The playback mode of the buzzer.

> Note:   
    - Music includes: DADADADUM ENTERTAINER PRELUDE ODE NYAN RINGTONE FUNK BLUES BIRTHDAY WEDDING FUNERAL PUNCHLINE BADDY CHASE BA_DING WAWAWAWAA JUMP_UP JUMP_DOWN POWER_UP POWER_DOWN  
    - The playback modes include: Once (play once) Forever (play continuously) OnceInBackground (play once in the background) ForeverInBackground (play continuously in the background)   buzzer.play(buzzer.DADADADUM, buzzer.Once)  

### **Return**
**None  
### **Example Description**
The code below uses the buzzer.play() function to play music on the buzzer. With different functions such as buzzer.pitch(), buzzer.stop(), buzzer.pitch(), and buzzer.redirect(), one can modify the tone, start and pause playback, and redirect the buzzer to a specific pin.
### **Hardware Required**

- [UNIHIKER](https://www.dfrobot.com/product-2691.html)
### **Example Code**
```python
# -*- coding: utf-8 -*-

import time
from pinpong.board import Board, Pin
from pinpong.extension.unihiker import *

Board().begin()  # Initialize the UNIHIKER

# Music: DADADADUM ENTERTAINER PRELUDE ODE NYAN RINGTONE FUNK BLUES BIRTHDAY WEDDING FUNERAL PUNCHLINE
# Music: BADDY CHASE BA_DING WAWAWAWAA JUMP_UP JUMP_DOWN POWER_UP POWER_DOWN
# Play mode: Once (play once) Forever (play continuously) OnceInBackground (play once in the background) ForeverInBackground (play continuously in the background)
buzzer.play(buzzer.DADADADUM, buzzer.Once)  # Play music once
# buzzer.set_tempo(4, 60)  # Set the number of notes per beat and the beats per minute
buzzer.pitch(494, 4)  # Play a pitch/note
# buzzer.pitch(494)  # Play a pitch/note in the background
# time.sleep(10)
# buzzer.stop()  # Stop playing in the background
# buzzer.redirect(Pin.P0)  # Redirect the buzzer to a specific pin, only supports PWM pins
# buzzer.play(buzzer.ENTERTAINER, buzzer.ForeverInBackground)  # Play music continuously in the background
while True:
    time.sleep(1)  # Wait for 1 second to maintain the state
```
**Program Effect:**  

![image.png](img/5_Buzzer/1722825855482-4f0c353a-efd8-493f-85f6-a2c1ccb68027.png)


---
