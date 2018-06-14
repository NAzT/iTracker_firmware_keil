# 1. Prepare development tools

```Note: to compile this app you would require to have the full version of Keil uVision as the evaluation version doesnt allow programs to be compiled larger than 35kbytes.```

## 1.1	Install Keil IDE
Signup and Download MDK-ARM
https://www.keil.com/demo/eval/arm.htm
Add you licence once installed.

## 1.2	Install Segger for J-Link
You would need a segger jlink device:
https://www.segger.com/downloads/jlink/
download the J-link software and Documentation pack

## 1.3	Install nRFgo Studio
press the download tab and get the appropriate version for your setup:
https://www.nordicsemi.com/eng/Products/2.4GHz-RF/nRFgo-Studio

## 1.4	Install nRF Connect for mobile (optional)
 
# 2. Download iTracker’s keil project
Clone/Download iTracker’s keil project from below link:
https://github.com/ajurcevic/iTracker_firmware_keil


# 3. Compile the Project 
## 3.1	Build in Keil
Open Keil uVision and Import project file:
…\tracker-firmware\project\tracker.uvprojx

Press F7 or the build button to build a hex file which you will deploy to your device.

the output file will be located:
…\tracker-firmware\project\_build\<project name>.hex

## 3.2 Softdevice 
This project uses nRFK52 v14, so we would require the S132 5.x
get the file from here:
https://www.nordicsemi.com/eng/nordic/download_resource/58987/13/97029009/116068

Use the nRFgo Studio to program device with this softdevice:
1: Erase all to clear the device 
2: Select the 'Program SoftDevice' tab in nRF5x Programming.
3: Find the S132 5.x hex softdevice file you just downloaded
4: Press the program button to program your device
![image](https://github.com/ajurcevic/iTracker_firmware_keil/blob/master/images/softdevice_install.png) 

## 3.3	Program Device
There is an option to deploy with Keil IDE using the Load/download(F8) function. However i have not been successful in performing this.
(If anyone has let me know cheers)

Other option is nRFgo Studio.

nRFgo Studio:
1: Select the 'Program Application' tab in nRF5x Programming.
2: Find the hex file that was built in 3.1
3: Press the program button to program your device
![image](https://github.com/ajurcevic/iTracker_firmware_keil/blob/master/images/program_install.png) 

 
# 4. Testing
Use J-Link RTT Viewer to check the log print. Below is the J-Link RTT Viewer’s configuration.
if you installed it to the default location it should be here: C:\Program Files (x86)\SEGGER\JLink_V632f
![image](https://github.com/RAKWireless/iTracker_firmware_keil/blob/master/images/6.png)![image](https://github.com/RAKWireless/iTracker_firmware_keil/blob/master/images/7.png)        

## 4.1	sensors & gps test 
0> [39] [DEBUG]: {<br>
 0> "temp" : 22.85,<br>
 0> "humi" : 37.64,<br>
 0> "press" : 102525.88,<br>
 0> "light" : 28.58,<br>
 0> "lati" : 31.10,<br>
 0> "longi" : 121.43,<br>
 0> "X" : 13616,<br>
 0> "Y" : 4000,<br>
 0> "Z" : -6720,<br>
 0> "m_x" : 178.50,<br>
 0> "m_y" : 199.50,<br>
 0> "m_z" : 489.00<br>
 0> }<br>

## 4.2	M35 test 
 0> [0] [INFO]: iTracker Start V1.0.0!<br>
 0> [2] [INFO]: check auto baud<br>
 0> [3] [INFO]: set echo<br>
 0> [3] [INFO]: check sim card<br>
 0> [6] [INFO]: check network<br>
 0> [12] [INFO]: check GPRS<br>
 0> [15] [INFO]: set context 0<br>
 0> [15] [INFO]: check GSM Network ok!!<br>
 0> [15] [INFO]: rssi=63<br>


## 4.3	BC95 test
 [INFO]: iTracker Start V1.0.0<br>
 0> [0] [INFO]: check network<br>
 0> [21] [INFO]: check GPRS<br>
 0> [22] [INFO]: check con status<br>
 0> [22] [INFO]: BC95 Connected<br>
 0> [22] [INFO]: rssi=79<br>

## 4.4	BLE test
Download and install the mobile application nRF Connect and search bluetooth devices:
 ![image](https://github.com/RAKWireless/iTracker_firmware_keil/blob/master/images/8.png)

