### **Description**
SPI stands for Serial Peripheral Interface.
These SPIs are high-speed, full duplex, synchronous communication buses that only occupy four wires on the chip pins, saving chip pins and space for PCB layout, providing convenience.  
 It is mainly used in EEPROM, FLASH, real-time clock, AD converter, as well as between digital signal processors and digital signal decoders.  
SPI has two modes: master and slave. An SPI communication system needs to include one (and only one) master device and one or more slave devices. The master device provides the clock, and the slave device receives the clock. The read and write operations of the SPI interface are initiated by the master device. When there are multiple slave devices, they are managed through their respective chip selection signals.  

> Tips: The principle of SPI communication can be referred to in this video: [click here](https://www.youtube.com/watch?v=tBgfStp40qQ)

### **Common functions**

#### 1.1 SPI( )
| **Syntax**          | **Object = SPI(num, cs = Pin)**        |  
| :--------------     | :--------------------      |
| **Description**     | Define the initialization function for the SPI.      |  
| **Parameters**      | **num**: The device number of SPI.   |  
|                     | **cs = Pin**: Definition of CS chip pin selection. |
| **Return**          | **None    |  


#### 1.2 read( )
| **Syntax**          | **buf = Object.read(num)**        |  
| :--------------     | :--------------------      |
| **Description**     | Read bytes from the slave.      |  
| **Parameters**      | **num**: The number of bytes read.   |  
| **Return**          | Read data.    |  


#### 1.3 write( )
| **Syntax**          | **Object.write(buf)**        |  
| :--------------     | :--------------------      |
| **Description**     | Send the content from buf.      |  
| **Parameters**      | **buf:** User defined byte data group.   |  
| **Return**          | **None    |  






### **Example Description**
The following code is a commonly used code for controlling SPI devices through UNIHIKER. Assuming the user has an SPI device, connecting it to the SPI pin of UNIHIKER can perform data writing and sending operations.
### **Hardware Required**

- [UNIHIKER](https://www.dfrobot.com/product-2691.html)
- SPI devices used by users
### **Example Code**
```python
import time
from pinpong.board import Board, Pin, SPI

Board("UNIHIKER").begin()  # Initialize, select board type, and automatically recognize without inputting board type

# 0 represents SPI0 (P1 SCK, P10 MISO, P2 MOSI), 1 represents SPI1 (P13 SCK, P14 MISO, P15 MOSI)
# CS is a chip selection pin and can only be used as a host
spi0 = SPI(0, cs = Pin.P3)

w_buf = [0x00, 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07]

while True:
    # r_buf = spi0.read(8)    # Read 8 bytes from the slave
    # print(r_buf)
    spi0.write(w_buf)         # Spir0 sends buf
    time.sleep(1)
```


---
