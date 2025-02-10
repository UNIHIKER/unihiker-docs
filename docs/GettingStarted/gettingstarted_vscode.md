## **Download and Install Visual Studio Code**

In this tutorial, we will demonstrate how to download and install VSCode (Visual Studio Code) on your Windows, Mac, or Linux computer.   

### **VSCode** 
VSCode is an elegant, free, and open-source code editor developed by Microsoft. It serves as a cross-platform solution, supporting numerous programming languages such as Python and C++. With features including syntax highlighting, code completion, and error detection, it empowers developers with a robust set of tools. Furthermore, its extension plugin system allows for customization and enhanced functionality, catering to diverse development requirements.   

### **Download the Editor**
[[Download VSCode]](https://code.visualstudio.com/download) .   

![image.png](img/VSCode - Python/1695025959912-55f4a8d7-c24e-4916-bcf3-0e3a510e5918.png)  

### **Installation and Open VSCode**
#### Windows 
Install VSCode on your computer.

![image.png](img/VSCode - Python/1695026309181-077ce5d0-0771-4e6f-afc5-7a6e4ec56e7d.png)  

#### macOS
Install VSCode on your computer.

![image.png](img/VSCode - Python/1695108244221-152e1447-b124-44fa-9419-d7fe6a8e1479.png)  

#### Linux
Install VSCode on your computer.

![070ee0f4c985d902b66e25775fddb0f.png](img/VSCode - Python/1695105735771-bc191987-6679-462e-9e77-64f485cf1375.png)  

## **Starting up the UNIHIKER**
### **Connect the UNIHIKER**
Connect the UNIHIKER to your computer using the Type-C to USB cable. Once connected and powered on, the UNIHIKER logo will appear on the screen.   
![](img/VSCode - Python/1691476703505-51223828-f994-438e-a0a5-f4577792ea1e.png)   

!!! note
    1. Please ensure that you plug the USB cable directly into the computer's USB port without using an extension cord or dock. If you experience any issues with the connection, refer to the FAQ for a solution.  
    2. When the UNIHIKER is connected to your PC via USB, the IP address is fixed at 10.1.2.3. You can find the IP address in the "Home" menu of the UNIHIKER.    

## **Run a simple example with VSCode**
The VSCode software supports programming the UNIHIKER through Python code, you can create a simple example as follows.  

(1) Launch the VSCode software, and you will see a screen similar to this.   

![image.png](img/VSCode - Python/1695035187001-88157a37-36a8-41c9-ba41-850b5e5214c5.png)  
  
(2) Install the "Python" extension from the VSCode Extensions marketplace.  

![image.png](img/VSCode - Python/1695033256764-669358ac-398f-46df-ab55-221ce974ee5f.png)  
  
(3) Search for the "remote" extension and install "Remote - SSH".  
SSH (Secure Shell) is a network protocol that enables secure remote access and data transfer between computers over unsecured networks. It establishes an encrypted channel to ensure the security and integrity of the data transmitted.  
The UNIHIKER has SSH service enabled by default, allowing you to use SSH tools such as PuTTY, MobaXterm, or Remote-SSH in VSCode to connect to it from another computer.  

![image.png](img/VSCode - Python/1695033186253-805b8884-c31e-44ef-b93e-2c2f7c8fc134.png)  
  
(4) Once the installation is complete, you will find the Remote Explorer in VSCode. To add a new connection, enter the SSH account as "root" and the password as "dfrobot". When connected via USB, the IP address is fixed as "10.1.2.3". Therefore, enter "root@10.1.2.3" and select "Linux". Enter the password when prompted.  

![image.png](img/VSCode - Python/1695036086258-d80531b8-ca91-4f60-a97c-ae21a63a213c.png)  

Input 'root@10.1.2.3' as host.  

![image.png](img/VSCode - Python/1695036155127-5a9dfc45-9599-4385-8f68-85c8ed5ed5e3.png)  

Select 'Linux' from the newly appeared pop-up window.    

![image.png](img/VSCode - Python/1695092403219-f9d79bb1-fb02-4271-b369-44145bf4e88f.png)  

Input the password 'dfrobot' and press Enter.    

![image.png](img/VSCode - Python/1695092654228-113e284a-109c-4248-85fb-47ed0e34a182.png)  

Note: If the connection fails, please retry multiple times.   
After successful connection, the status bar will display as follows.  

![image.png](img/VSCode - Python/1695093255059-6a4f405b-30a0-4f80-a988-37d009620eb4.png)  

Note: If you encounter any connection issues, please ensure that the USB cable is correctly plugged in.  


  
(5)  Once connected, you can select the UNIHIKER directory to open files and write programs for execution later.   

![image.png](img/VSCode - Python/1695093525215-09a569f0-84c3-41ab-99cb-6360b0254054.png)  

Input the password 'dfrobot' and press Enter.  

![image.png](img/VSCode - Python/1695093803806-5fdc2908-7d7e-47e9-aebe-d134e5c7edb4.png)  

After completing the previous step, you will see a screen like this. The first part corresponds to the sidebar, which serves as the file directory area of the board. The second part is the Panel Bar, which includes sections for problems, output, terminal, debug console, and ports.   

![image.png](img/VSCode - Python/1695105138963-80ab1cc4-4b6f-4b56-9c8f-365349e4d6ee.png)
  
(6) Then, we can click "+" option here to create a new file named "Hi_UNIHIKER.py" .  

![image.png](img/VSCode - Python/1695094508325-36a43f68-3438-4533-97c0-f0ef0d6f27fd.png)  
  
(7) After creating the file, we can double-click on the "Hi_UNIHIKER.py" file to program it in the code editing area of the program, as shown below.  

![image.png](img/VSCode - Python/1695095621927-8a849645-3c0b-48fa-be8f-976b56a2d0bd.png)  
  
（8）Please insert this code into the code editing area of the file "Hi_UNIHIKER.py". Here's a code snippet that will display "HI UNIHIKER" on the screen.  


```python
from unihiker import GUI
import time

gui = GUI()
#unihiker text
gui.draw_text(text="HI UNIHIKER",origin="center",x=120,y=160,color="#0066CC")

while True:
    time.sleep(1)
```
  
（9）Run the program on the UNIHIKER.
Right-click on the 'Hi_UNIHIKER.py' file, choose 'Open in Integrated Terminal', then input 'python Hi_UNIHIKER.py' and press Enter.   

![image.png](img/VSCode - Python/1715743166493-391327bf-296f-4cfe-a446-9a90494753d8.png)  

After running the code, the result will demonstrate on the screen.   

![image.png](img/VSCode - Python/1697096009301-82530852-4b48-45fd-87d7-a2ff5f0514fa.png)
  
---  
**Congratulations, you have successfully implemented programming control for the UNIHIKER. Now, you can explore exciting projects or understanding deeper of UNIHIKER.The possibilities are endless with UNIHIKER. Have fun exploring and learning!**  

**1. Discover more programming exercises: [Examples](../Examples/PythonCodingExamples/index.md)**  
**2. Explore Python libraries related to UNIHIKER: [Reference](../LanguageReference/UNIHIKER_Library/index.md)**  
**3. Gain insights into the built-in hardware of UNIHIKER: [Hardware ](../HardwareReference/hardware_reference_introduction.md)**    

---  
