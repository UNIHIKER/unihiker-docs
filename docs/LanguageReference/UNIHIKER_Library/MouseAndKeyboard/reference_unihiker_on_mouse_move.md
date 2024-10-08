### **Description**
Listen for mouse position movement (touch screen click) events.

### **Syntax**
**GUI.on_mouse_move(Name of the callback function)**
### **Parameters**
Name of the callback function
### **Return**
**None
### **Example Description**
In this simple example, our main goal is to display mouse coordinates at the bottom of UNIHIKER. As the mouse moves to different positions on the screen, the displayed coordinate information will update accordingly.
### **Hardware Required**

- [UNIHIKER](https://www.dfrobot.com/product-2691.html)  

### **Example Code**
Instantiate an object of the GUI class within the UNIHIKER class. Define a callback function to display text on the screen. Then, use the object to call the on_mouse_move() function to capture mouse coordinates (touch screen click) and bind the callback function for displaying them on the screen.    

```python
from unihiker import GUI   # Import the package
gui = GUI()  # Instantiate the GUI class

# Draw a text element on the GUI with the specified coordinates and text
# The text element displays the mouse coordinates
# The origin is set to 'bottom', which means the text will be anchored at the bottom-left corner
info_text = gui.draw_text(x=120, y=320, text='Mouse coordinates', origin='bottom')

# Define a callback function that is triggered when the mouse moves
def mouse_move(x, y):
    # Update the text of the info_text element to display the current mouse coordinates
    info_text.config(text="coordinate: x={}, y={}".format(x, y))
    # Print the mouse coordinates to the console
    print(x, y)

# Register the mouse_move function as the callback for the mouse move event
gui.on_mouse_move(mouse_move)

import time
while True:
    # Add a delay to prevent the program from exiting and to observe the effects
    time.sleep(1)
```
**Program Effect:**
![mouse.gif](img/1.on_mouse_move()/1720666634292-09279399-19c8-465a-8740-9f4b41d5a52f.gif){width=300, style="display:block;margin: 0 auto"}  


---  


