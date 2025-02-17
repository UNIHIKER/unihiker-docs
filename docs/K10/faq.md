## **High frequency problem**
Q: Can't find K10 after downloading the public beta version of Mind+
A: The K10 is a microcontroller dev board and needs to be programmed in Mind+ upload mode.

Q: I can't find the port number of K10 in offline mode, do I need to install the driver?
A: The Windows 10 or Windows 11 does not need to install the driver, if the computer of Win10/11 can not recognize the port, please make sure whether you are using the USB-C cable which come with the K10. And try to connect the K10 to the computer's native USB port on your PC instead of pass through the USB hub.
Windows7 computers need to install the serial driver manually: install [zadig](https://zadig.akeo.ie/) and set it up as follows:
![image.png](img/faq/faq3.png) 
![image.png](img/faq/faq4.png) 

Q: After Select the K10 board to upload the program, prompting the error message: spawn ENAMETOOLONG.<br/>
![image.png](img/faq/faq1.png) 
A: The public beta version of Mind+ is manually unzipped by users, so it may cause the unzipped path of Mind file is not correct or the file name is wrong. Please follow the steps below to solve the problem:
- Completely delete the Mind+ unzipped this time
- Then put the newly downloaded zip in the root directory of C drive.
![image.png](img/faq/faq2.png) 
- Quit all antivirus software before unzipping, and make sure that the entire folder path is all English characters. Copying the zip archive is likely to automatically generate Chinese characters in ‘)’ or ‘(’ brackets.

Q: K10 continues to reboot and crash after uploading a program.
A: Please select K10 in Mind+ offline mode and click “Restore device initialization settings”.
![image.png](img/faq/faq5.png) 

## **How to download K10 supported Mind+**
- Please view this [page](https://www.unihiker.com/wiki/K10/GettingStarted/gettingstarted_mindplus/)

## **K10 abnormal reboot**
Q: Board restarts abnormally when using MQTT, pin interrupts, multithreading.
A: In MQTT, pin interrupt, multi-threading and other functions of the callback function / thread and other hat-type blocks, can not use the screen display related blocks, you need to assign a value to the variable in the callback function / thread, and then in the main program will be displayed, the specific use of the following chart (on-board AB button hat-type blocks under the use of the screen display blocks can be run normally, but also pay attention to not a large number of use)<br/>

Reason: Due to the large size of the K10 screen, it takes up a large amount of memory when updating the screen content, and it is not suitable to run a program that takes up a large amount of memory under the hat blocks such as callback functions/threads.
![image.png](img/faq/faq6.png)

Q: The board restarts abnormally when using multi-threaded, sub-threaded related blocks.
A: Any of the blocks in the "screen" section can not be used under the “ hat block in the sub-thread, and any of the blocks in the “Artificial Intelligence” section except for the blocks related to voice recognition. You cannot use any of the blocks in the “Screen Display” section, and you cannot use any of the blocks in the "AI" section can also not be used, except for the voice recognition blocks.

Q: When using a TF card with AI-related blocks, the board restarts abnormally.
A: TF card abnormality, when K10 initializes some poor quality TF card it will generate an unknown error causing the program to crash when used in combination with the AI function. It is recommended to use 16G/32G memory card from DFRobot official store. You can delete all the blocks related to the TF card first, and then test if the reboot problem still exists, in order to quickly troubleshoot whether it is a TF card problem.

Q: The board reboots abnormally when using only the AI-related functions integrated on the motherboard and not using any other extended functions.
A: The built-in model file of the board is damaged, click “Restore Device Initial Settings” to burn the preset model for the board again.
![image.png](img/faq/faq5.png) 

## **Program got stucked**
Q: When using the AI function, the screen image gets stuck and does not move.
A: The two blocks "Enable/Disable show camera" and "switch detection mode" should be avoided to be called at high frequency, and should be called at initialization time or through conditional judgment. This problem is easy to appear in the project of multiple recognition mode switching, as follows:
![image.png](img/faq/faq7.png) 
![image.png](img/faq/faq8.png) 


## **Audio**
Q: When playing wav files from a TF card, the playback sound has a noticeable speedup or the playback sound is garbled.
A: Wav file exception, the wav audio need to be uncompressed dual-channel files.
WAV files can be exported as stereo channels at this [website](https://cloudconvert.com/mp3-to-wav)

Q: When used in conjunction with multi-threading, note playback/audio playback cannot be started again after the thread is stopped.
A: When playing notes/audio in a subthread, the subthread cannot be stopped during playback, otherwise the notes will not be played when the thread is started again.

## **WiFi**
Q: K10 unable to connect to the hotspot on the UNIHIKER M10.
A: UNIHIKER M10 must be install the OS of version 0.3.7 and above, and then switch the mode to WPA2 in "5-Switch Wireless Hotspot Mode".
[UNIHIKER M10 install OS tutorial](https://www.unihiker.com/wiki/SystemAndConfiguration/UnihikerOS/)

