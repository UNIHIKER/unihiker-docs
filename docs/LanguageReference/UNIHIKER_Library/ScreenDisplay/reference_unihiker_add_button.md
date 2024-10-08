### **Description**
Create a button on the UNIHIKER screen.

### **Syntax**
**GUI.add_button(x, y, w, h, text, origin, state,onclick)**
### **Parameters**
- **x**:  The x-coordinate where the button is displayed on the UNIHIKER screen.  
- **y**:  The y-coordinate where the button is displayed on the UNIHIKER screen.  
- **w**:  The width of the button displayed on the UNIHIKER screen.  
- **h**:  The height of the button displayed on the UNIHIKER screen.  
- **text**:  The text displayed on the button.  
- **origin**:  The origin point position of the entire object. Default position is the top-left.  
- **State：** The button's enable/disable state. Set to "disabled" to make the button unclickable, or "normal" to restore its normal clickable state.  
**onclick**:  The callback function triggered when the button is clicked.  
### **Return**
**Button object
### **Example Description**
In this simple example, our main goal is to display three buttons on the UNIHIKER, each bound to a click callback function. After clicking the three buttons in sequence, the numbers 1, 2, and 3 will be displayed at the top of the screen one after another.
### **Hardware Required**

- [UNIHIKER](https://www.dfrobot.com/product-2691.html)  

### **Example Code**
Instantiate an object of the GUI class within the UNIHIKER class and define a callback function to display text on the screen. Then, call the add_button() function through this object to display the button and set the parameters, binding the callback function to the button to enable it to trigger upon being pressed.  

```python
from unihiker import GUI   # Import the package
gui=GUI()  # Instantiate the GUI class

def btclick(data):
    print(data)
    txt.config(text=str(data))

txt = gui.draw_text(text="0", x=120, y=10, font_size=20, origin="center", color="#0000FF")

# Add three buttons at different positions
# Each button calls the btclick function with a different parameter when clicked
gui.add_button(x=120, y=100, w=100, h=30, text="Button1", origin='center', onclick=lambda: btclick(1))
gui.add_button(x=120, y=150, w=100, h=30, text="Button2", origin='center', onclick=lambda: btclick(2))
gui.add_button(x=120, y=200, w=100, h=30, text="Button3", origin='center', onclick=lambda: btclick(3))

import time
while True:
    # Add a delay to prevent the program from exiting and to observe the effects
    time.sleep(1)
```    
  
**Program Effect:**  
![image.png](img/8.add_button()/1718951390448-04c2a276-1eb6-42d4-b9c8-109a1da512b1.png){width=300, style="display:block;margin: 0 auto"}  

### **Notes and Warnings**
- In the onclick callback function, the GUI does not refresh, and only refreshes after the GUI ends. If you need to refresh in the function, you should start a thread with the lambda:gui.start_thread(function_name) in onclick.
- Since draw_image also has onclick, if you need a more aesthetically pleasing button, you can implement it using draw_image.

---  


