# PinPong Library - Introduction
UNIHIKER is equipped with a microcontroller coprocessor, whose duty is to control the onboard components and GPIO interface pins. In order to achieve hardware control, we utilize the PinPong library in Python to communicate with the coprocessor and write Python code to control the hardware.

The PinPong library is a collection of Python code for controlling open-source hardware mainboards. allowing you to quickly and easily control open-source hardware using Python within just five minutes.

The name of the PinPong library is composed of "Pin" and "Pong". "Pin" refers to the pin, and "PinPong" is a homophone of "ping-pong", indicating the reciprocation of signals.

With the assistance of the PinPong library, you can directly program various common open-source hardware using Python code. The underlying principle involves flashing a specific firmware onto the open-source hardware, enabling it to communicate with the computer via a serial port and execute various commands.


## Installing the PinPong Library

The PinPong library can be installed and updated using the pip tool.

> Note: The PinPong library is already integrated into the factory firmware of UNIHIKER, so this step can be skipped. 

!!! note
    Starting from PinPong library version 0.6.0, the communication method of UNIHIKER's coprocessor has been changed from firmata to Linux peripherals, thereby improving communication speed, stability, multi-threading capability, and Linux compatibility. User-level code is basically compatible. If the PinPong version on your UNIHIKER is lower than 0.6.0, please upgrade.

**Installation：**

```bash
pip install pinpong
```

**Update：**

```bash
pip install -U pinpong
```

## Importing the PinPong Library
- As the PinPong library supports various types of microcontroller boards and open-source hardware, it is divided into three packages: "board", "extension", and "libs". The "board" package comprises the commonly used libraries and functions supported by microcontroller boards, the "extension" package contains the customized libraries related to specific microcontroller boards, while the "libs" package includes expansion libraries for other sensors.
- As the PinPong library aims to support multiple microcontrollers, corresponding objects can be generated based on specified board types and port numbers when using the library. However, as the coprocessor and port numbers on the UNIHIKER are already fixed, object initialization can be performed directly when using the UNIHIKER , without the need to specify these parameters.

```python
from pinpong.board import xxx   # Importing the xxx library from the board package
from pinpong.libs.xxx    # Importing the xxx library from the libs package
from pinpong.extension.xxx    # Importing the xxx module from the extension package

Board().begin()    # Initializing the Board: connecting the coprocessor and checking firmware. If the firmware is empty or the version is incorrect, automatic burning will be performed.

```

> **Note: Please replace `xxx` with the actual names of the libraries or modules you are using.**


---  

