## **Download and Install the Mindplus (Mind+)**
In this tutorial, we will guide you through the process of downloading and installing Mindplus on your Windows, MacOS or Linux.

### **Mindplus (Mind+)**
Mind+ is a software designed for teenagers that supports AI and IoT functions by integrating with popular mainboards and open-source hardware. It offers an easy programming experience through graphical building blocks and advanced languages like Python, C, and C++.
### **Download the Editor**
Download the Mind+ application that supports UNIHIKER **(V1.7.2 RC3.0 or above)**. [[Download Mind+ from the official website]](https://mindplus.cc/download-en.html)

![image.png](img/Mind+ - Python & Graphical Python/1691477041943-3a8c7375-2ba8-4dc3-a0df-15151648dbed.png)
### **Installation and open Mind+**
After downloading the software, install it normally by clicking "Next". After the installation is complete, launch MindPlus, click on the "Gear" button in the top right corner of the software to select the language.
#### Windows 
![image.png](img/Mind+ - Python & Graphical Python/1691567857184-0d8501f0-1ee5-4585-8575-f27d64077d7e.png)
#### Mac OS X
![5af433cc6654cbb0dec2b9598f4c75c.png](img/Mind+ - Python & Graphical Python/1694746212454-6e16de80-4fd4-4f74-a129-81abdae65c50.png)
#### Linux
![c0f598994ecf398275f2a3259fa1c0d.png](img/Mind+ - Python & Graphical Python/1694770829895-ee497990-961a-4708-83af-2abf29f82a1f.png)
## **Starting up the UNIHIKER**
### **Connect the UNIHIKER**
To begin, connect the UNIHIKER to your computer using the Type-C to USB cable. Once connected and powered on, the UNIHIKER logo will appear on the screen.
![](img/Mind+ - Python & Graphical Python/1691476703505-51223828-f994-438e-a0a5-f4577792ea1e.png){width=800, style="display:block;margin: 0 auto"}   

!!! note 
    For best results, please make sure to plug the USB cable directly into your computer's USB port without using an extension cord or dock. If you encounter any connection issues, please refer to the FAQ section for possible solutions.

## **Run a simple example with Python code**
Mind+ software offers programming support through Python code and provides a user-friendly graphical interface for programming the UNIHIKER. To access the graphical programming interface, simply click here to launch the Mind+ software on your computer.  

(1) To switch to code programming mode in the Mind+ software, click on the "Python" button in the upper right corner. This will allow you to write and execute Python code for your UNIHIKER.  

![image.png](img/Mind+ - Python & Graphical Python/1691562303403-8c6c9dc9-a3f3-401c-8d14-2cea8a79af65.png)  

(2) Once you have completed the previous step, you will see a screen like this. The right side is the file directory, where you can access and organize your saved projects. The left side consists of the code editing area, where you can write and edit your Python code, and the terminal area, where you can view the output of your code.  

![image.png](img/Mind+ - Python & Graphical Python/1691562337800-18250885-6d8d-4449-8bec-45ac414d85dc.png)  

(3) To create a new file in your project, click on the "+" option in the right catalog and select "File". Then, name the file "Hi UNIHIKER.py" and click "Create". This will create a new Python file in your project.  

![image.png](img/Mind+ - Python & Graphical Python/1691563557082-df071e64-2081-42ed-a745-e39a66594c8d.png)  

(4) To begin programming in the "Hi UNIHIKER.py" file, double-click on it in the file directory. This will open it in the code editing area, where you can write your Python code.  

![image.png](img/Mind+ - Python & Graphical Python/1691563867923-cd3b3558-ce1e-4826-bc2b-e76da95dd2b6.png)  

(5) Here is the code snippet to display "HI UNIHIKER" on the screen: print("HI UNIHIKER")
Copy and paste this into the code editing area of the "Hi UNIHIKER.py" file.  

```python
from unihiker import GUI
import time

gui = GUI()
#unihiker text
gui.draw_text(text="HI UNIHIKER",origin="center",x=120,y=160,color="#0066CC")

while True:
    time.sleep(1)
```
(6) To run your code on the UNIHIKER, you will first need to connect to it. Click on the icon preceding the Terminal, and select "Connect Remote Terminal" from the menu. This will establish a connection to a remote terminal on the UNIHIKER.  

![image.png](img/Mind+ - Python & Graphical Python/1691565537723-378d855e-3dc5-4fd0-a57f-8779e8df188e.png)  

To connect to the UNIHIKER, click on the IP address 10.1.2.3 in the remote terminal menu. This will establish a connection between your computer and the UNIHIKER.  

![image.png](img/Mind+ - Python & Graphical Python/1691565572761-bee204ac-e511-4091-a7b2-066654d2c217.png)  

!!! tip 
    If you experience any connection issues, make sure that the USB cable is properly plugged in and try troubleshooting according to the solutions provided in the document. If the issue persists, please refer to the FAQ or contact our technical support team for further assistance.  

Once you have established a successful connection, the file directory will display the files on the UNIHIKER, the terminal will switch to the remote terminal of the board, and the library management will switch to the board's library management. This will allow you to write and run Python code on the board.  

![image.png](img/Mind+ - Python & Graphical Python/1691565602804-4cedd0b5-6930-48dd-abf6-c26520a27436.png)  

To run your code on the UNIHIKER, click on the "Run" button in the toolbar. This will upload the code to the board and execute it, displaying the results on the board's screen.  

![image.png](img/Mind+ - Python & Graphical Python/1691565676393-fcff221c-5c0c-4514-93b3-503e604fb584.png)  

![image.png](img/Mind+ - Python & Graphical Python/1691567717568-d78f0d3e-111f-46d9-858a-b32a8aec528c.png){width=300, style="display:block;margin: 0 auto"}    

!!! note 
    As mentioned, the code you write in the Mind+ software resides on your computer. When you save your project, all the Python code, image resources, and other files included in the project will be packaged into a .mp file. This allows you to easily transfer and share your projects with others.  

![image.png](img/Mind+ - Python & Graphical Python/1691567282076-6dcd9453-9556-4de5-aaa8-5f96d952e5f9.png)  



---  
**Congratulations, you have successfully implemented programming control for the UNIHIKER. Now, you can explore exciting projects or understanding deeper of UNIHIKER.The possibilities are endless with UNIHIKER. Have fun exploring and learning!**  

**1. Discover more programming exercises: [Examples](../Examples/PythonCodingExamples/index.md)**  
**2. Explore Python libraries related to UNIHIKER: [Reference](../LanguageReference/UNIHIKER_Library/index.md)**  
**3. Gain insights into the built-in hardware of UNIHIKER: [Hardware ](../HardwareReference/hardware_reference_introduction.md)**    

---  




## **Run a simple example with Graphical Python**
(1) Click "Python" in the upper right corner.  

![image.png](img/Mind+ - Python & Graphical Python/1691568202401-010c63b2-e4ac-4ae0-9538-9e17c7fc364f.png)  

(2) To select the programming mode, click on the "Blocks" or "Code" button on the top left corner of the Mind+ software. For this project, we will choose "Blocks" as our programming mode. This will allow us to complete our  project using graphical building blocks.  

![image.png](img/Mind+ - Python & Graphical Python/1691568268467-85a753d6-b971-45f2-896e-ac66afae6755.png)  

(3) Once the programming mode is selected, you will be taken to the main programming interface in Mind+. From here, you can begin your project using the selected mode.  

![image.png](img/Mind+ - Python & Graphical Python/1691568705647-f697d0cf-f101-4f28-9ae1-3aec7b70e597.png)  

(4) To access "Expansions" in the Mind+ software, simply click on the button with the same name. This will allow you to explore and add different expansions or modules to your project.  

![image.png](img/Mind+ - Python & Graphical Python/1691568833609-7f8acdb9-1103-488d-b201-106ba25a68bf.png)  

(5) Locate the "UNIHIKER" module under the "Official Library" and click to add it.  

![image.png](img/Mind+ - Python & Graphical Python/1691568881425-7fbd9a0d-9d54-40db-a42c-cbac68e5c590.png)  

(6) Then go back, and you can see UNIHIKER in "Command Area", which means UNIHIKER is done loading.  

![image.png](img/Mind+ - Python & Graphical Python/1691568924735-7489f73e-2a25-4f11-8ce0-88a78ca57f3b.png)  

![image.png](img/Mind+ - Python & Graphical Python/1691568952672-02fa0f28-9a3d-4228-8c17-614e44d586f5.png)  

(7) Please note that after the "UNIHIKER" module is loaded, an additional option will appear in the menu bar for connecting to UNIHIKER, labeled "Connect Remote Terminal". Select 10.1.2.3 to connect to UNIHIKER.  

![image.png](img/Mind+ - Python & Graphical Python/1691569200726-66d8c4d7-f40f-49e8-93bb-a978b18405b9.png)  

!!! tips 
    If you encounter any connection issues, please ensure that the USB cable is correctly plugged in and refer to the troubleshooting section of this document for common solutions to the "unable to connect" problem.  

(8) Within the "UNIHIKER" Blocks library, locate the instruction for displaying text on the screen and drag it into the script area.  

![image.png](img/Mind+ - Python & Graphical Python/1691569553244-8d4d1014-9269-4a4f-b48f-b39a38b3d3a4.png)  

(9) Gently place the instruction beneath the "Python main program start" section, seamlessly connecting it below like a puzzle piece.  

![image.png](img/Mind+ - Python & Graphical Python/1691569483396-fcc3290e-63bb-4d38-9a7b-e2f1a282311c.png)  

Example:
![image.png](img/Mind+ - Python & Graphical Python/1691569625114-b87a1143-5702-4714-bee1-ec0f3fcab425.png){width=600, style="display:block;margin: 0 auto"}  

(10) Upon clicking the "Run" button, the screen will promptly display the text "UNIHIKER".  

![image.png](img/Mind+ - Python & Graphical Python/1691569738729-8b101abf-4ee0-49ac-80a7-76648679fca6.png)  
![image.png](img/Mind+ - Python & Graphical Python/1691569841550-a10cf46e-224e-4020-a1ad-0c0917483bbb.png){width=300, style="display:block;margin: 0 auto"}  
  
---  
**Congratulations, you have successfully implemented programming control for the UNIHIKER. Now, you can explore exciting projects or understanding deeper of UNIHIKER.The possibilities are endless with UNIHIKER. Have fun exploring and learning!**  

**1. Discover more programming exercises: [Examples](../Examples/PythonCodingExamples/index.md)**  
**2. Explore Python libraries related to UNIHIKER: [Reference](../LanguageReference/UNIHIKER_Library/index.md)**  
**3. Gain insights into the built-in hardware of UNIHIKER: [Hardware ](../HardwareReference/hardware_reference_introduction.md)**    

---  
