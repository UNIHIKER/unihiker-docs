

## **OS Image**
- To begin, download the OS img image file that needs to be flashed. 
- Once downloaded and extracted, you will have an img format image file.
**Download V0.4.0 System Image**
**Name:** unihiker_v0.4.0.md5.455cd88c55d5e5bf47b3588c3f9f9446.img

| **Download channel** |  |
| --- | --- |
| **Download:** | [Click to download](https://download3.dfrobot.com.cn/unihiker/img/unihiker_v0.4.0_20241129_2102.7z) |
| **Download from Google Drive:** | [Click to download](https://drive.google.com/drive/folders/1JU73SOyN5VmpB6ilbxVNvCB9qXfc-Qo-?usp=sharing) |

##  **Release Logs**
### **V0.4.0 :**

- Pinpong library upgraded to the latest V0.6.1 version (greatly improved stability, speed, and threading compatibility)
- The function of switching wireless hotspot has added the feature of switching security protocol
- unihiker library upgraded to the latest V0.0.27 version
- Several new Python libraries have been built in: torch,tensorflowjs,tf2onnx,xedu-hub
- The links of the Local Web Page have been updated and the function of switching between siot V1 and V2 has been added
- WiFi connection supports names with special symbols
- Block pip version update prompts

### **V0.3.6 :**

- The Local Web Page has been optimized to improve the WiFi connection process and reduce errors.
- The WiFi list on the Local Web Page can now be filtered to remove the self hotspot, improving the user experience.
- Modify some texts in Home Menu.
- The link for the "View Tutorial" page in the Home menu has been changed for better accessibility.
- The issue of non-existent files in the auto-startup process has been resolved.
- Increase CPU frequency setting.
- The tun driver has been updated with the latest version.
- Zip and 7z have been added to the built-in package for easier file compression and extraction.
- Update siot, pinpong, df-xfyun-speech libraries to the latest version.

### **V0.3.5 :**

- Added language switching function in Home menu, supports Chinese and English.
- The demo folder is added in the switching running program, which contains 7 demo programs.
- Add the mindplus folder in the switching program, so that it is convenient to quickly run the program transferred from Mind+.
- Added automatic reconnection after USB disconnection, improving the stability of USB connection.
- Increase the function of recording hotspot switch status.
- Increase the screen brightness adjustment command (brightness).
- The calibration page adds Chinese and English bilingual prompts.
- fix apt upgrade error.
- Update three built-in dedicated libraries (siot, pinpong, unihiker) to the latest version.
- Add a batch of built-in libraries:
   - webssh
   - opencv_contrib_python
-pyzbar
   - dominate
-pypinyin
   - lsusb
-onnxruntime
-graphviz