### **Description**
Create a rectangle on UNIHIKER screen
### **Syntax**
**GUI.draw_rect(x, y, w, h, width, color , onclick)**
### **Parameters**
**x**: The x-coordinate where the rectangle is displayed on the UNIHIKER screen.  
**y**: The y-coordinate where the rectangle is displayed on the UNIHIKER screen.  
**w**: The width of the rectangle.  
**h**: The height of the rectangle.  
**width**: The thickness of the border.  
**color**: The colour of the border.  
**onclick**: The callback function triggered when the rectangle is clicked.  
### **Return**
**Rectangle object
### **Example Description**
In this simple example, we aim to display a blue rectangle at the centre of the UNIHIKER, bound to a click callback function. The rectangle's width is 80, its height is 60, and the border's thickness is 3.
### **Hardware Required**

- [UNIHIKER](https://www.dfrobot.com/product-2691.html)  

### **Example Code**
Instantiate an object of the GUI class within the UNIHIKER class, and call the draw_rect() function through this object to display the rectangle and set the parameters.  

```python
from unihiker import GUI   # Import the package
gui = GUI()  # Instantiate the GUI class

# Draw a rectangle on the GUI with the specified coordinates and parameters
# The rectangle is located at (x=80, y=110) with a width of 80 pixels and a height of 60 pixels
# The outline of the rectangle has a width of 3 pixels
# The color of the rectangle is specified as (0, 0, 255), representing an RGB color value (blue)
# When the rectangle is clicked, the lambda function is executed, which prints "rect clicked" to the console
gui.draw_rect(x=80, y=110, w=80, h=60, width=3, color=(0, 0, 255), onclick=lambda: print("rect clicked"))

import time
while True:
    # Add a delay to prevent the program from exiting and to observe the effects
    time.sleep(1)
```  

**Program Effect:**
![image.png](img/2.draw_rect()/1719481344876-d6f54a47-e9df-4656-8613-7fe45a16985d.png){width=300, style="display:block;margin: 0 auto"}  

--- 


