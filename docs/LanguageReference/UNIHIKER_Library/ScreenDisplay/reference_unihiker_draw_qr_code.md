### **Description**
Create a QR code on the UNIHIKER screen.

### **Syntax**
**GUI.draw_qr_code(x, y, w, text, origin, onclick)**
### **Parameters**
- **x**:  The x-coordinate where the QR code is displayed on the UNIHIKER screen.  
- **y**:  The y-coordinate where the QR code is displayed on the UNIHIKER screen.  
- **w**:  The side length of the QR code.  
- **text**:  The content obtained after scanning the QR code.  
- **origin**:  The alignment position. Default is the top-left corner. 
- **onclick**:  The callback function triggered when the QR code is clicked.  
### **Return**
**QR code object
### **Example Description**
In this simple example, our main goal is to display a QR code at the centre of the UNIHIKER, bound to a click callback function. The content of the QR code is "[https://unihiker.com](https://unihiker.com)," which will be displayed after scanning.
### **Hardware Required**

- [UNIHIKER](https://www.dfrobot.com/product-2691.html)  

### **Example Code**
Instantiate an object of the GUI class within the UNIHIKER class, and call the draw_qr_code() function through this object to display the QR code and set the parameters.  

```python
from unihiker import GUI   # Import the package
gui = GUI()  # Instantiate the GUI class

# Draw a QR code at the specified position with the given parameters
# The QR code will have a size of 100x100 pixels
# The QR code will encode the provided text "https://unihiker.com"
# The origin of the QR code is set to "center"
# When the QR code is clicked, the lambda function is executed, which prints "qr clicked" to the console
gui.draw_qr_code(x=115, y=140, w=100, text="https://unihiker.com", origin="center", onclick=lambda: print("qr clicked"))

import time
while True:
    # Add a delay to prevent the program from exiting and to observe the effects
    time.sleep(1)

```  

**Program Effect:**
![image.png](img/7.draw_qr_code()/1718941218661-d7460bb9-46c3-41d1-9e1f-70dca2c4a75e.png){width=300, style="display:block;margin: 0 auto"}  

---  


