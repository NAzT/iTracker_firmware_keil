# 1. Prepare development tools

## 1.1	Install keil IDE

## 1.2	Install segger for jlink

## 1.3	Install nRFgo Studio

## 1.4	Install nRF Connect(phone)

 
# 2. Download iTracker’s keil project

Download iTracker’s keil project from below link:
https://github.com/RAKWireless/iTracker_firmware_keil


# 3. Compile and burn the iTracker firmware

## 3.1	compile the project.
The project file is in below path:
…\tracker-firmware\project\tracker.uvprojx

## 3.2	burn softdevice
the softdevice is in below path, you can use the nRFgo Studio tool to burn it to iTracker.
…\nRF5_SDK\components\softdevice\s132\hex\s132_nrf52_5.0.0_softdevice.hex
![image](https://github.com/RAKWireless/iTracker_firmware_keil/blob/master/images/3.png) 

## 3.3	burn iTracker firmware
you can use keil ide or nRFgo Studio tool to burn the iTracker firmware.
### 3.3.1	burn iTracker firmware using keil IDE
![image](https://github.com/RAKWireless/iTracker_firmware_keil/blob/master/images/4.png) 
### 3.3.2	burn iTracker firmware use nRFgo tool
![image](https://github.com/RAKWireless/iTracker_firmware_keil/blob/master/images/5.png)
 

# 4. Test the iTracker
Use J-Link RTT Viewer to check the log print. Below is the J-Link RTT Viewer’s configuration.
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
 ![image](https://github.com/RAKWireless/iTracker_firmware_keil/blob/master/images/8.png)

