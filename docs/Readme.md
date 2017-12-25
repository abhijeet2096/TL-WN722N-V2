# TL-WN722N-V2 Drivers clean ported to Kernel 4.8, 4.10 & 4.13(GNU/LINUX)

## TL-WN722N-V2

![TL-WN722N-V2](device_img.jpg?raw=true "TL-WN722N-V2")


## Installation Instruction

###### AS DKMS MODULE

1. Change directory to /usr/src
	```
	 $ cd /usr/src
	```
2. Clone the repository
	```
	 $ sudo git clone https://github.com/abhijeet2096/TL-WN722N-V2
	```
3. Add a Symbolic link for dkms to know where source is 
	```
	 $ sudo dkms add ./TL-WN722N-V2
	```
4. Build the source
	```
	 $ sudo dkms build -m 8188eu -v 1.2 
	```
5. Install the Build drivers
	```
	 $ sudo dkms install -m 8188eu -v 1.2 
	```
6. Modprobe it .
	```
	 $ sudo modprobe 8188eu
	```
6. Reboot system .
	```
	 $ sudo reboot
	```
	
###### NOT AS DKMS MODULE

1. Spawn terminal and clone the above repo by 
	```
	 $ git clone https://github.com/abhijeet2096/TL-WN722N-V2
	```
2. Change the working directory with
	```
	 $ cd TL-WN722N-V2
	``` 
3. Clean using `$ sudo make clean` .
4. Compile using `$ sudo make all` .
4. Install above driver as 
	```
	 $ sudo make install 
	```
5. Reboot your system !

P.S for uninstalling above driver 
	```
	 $ sudo make uninstall 
	```
## Activating Monitor Mode

 1. Plugin the device .
 2. Spwan terminal `$ iwconfig ` and notice the device name.
 3. `$ sudo ifconfig <device-name> down`
 4. `$ sudo iwconfig <device-name> mode Monitor`
 5. `$ sudo ifconfig <device-name> up`
 6. `$ iwconfig` output mode should be now "Auto"
 7. Go root `$ sudo -i`
 8. `airmon-ng start <device-name>`
 9. `airodump-ng <device-name>' 
 10 Monitor mode should start

## Activating/Deactivating LED

 1. Clone this Repository.
 2. Edit `include/autoconf.h` in your favourite editor
 3. go to line 173 and comment/uncomment `#define CONFIG_LED`
 4. Make again the drivers
 5. Reboot system


## Results
Results are displayed below in table.

| Drivers       				| Signal Strength  | 
| ------------- 				|:-------------:   | 
| lwfinger/rtl8188eu			|    0-10 %        | 
| mfruba/kernel   				|    65-75 % 	   | 
| abhijeet2096/TL-WN722N-V2   	|    85-95 %       |

NOTE: All results are tested from same distance from wifi router !

## Donate
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](http://www.paypal.me/abhijeet2096)

## Bugs
 I was not able to inject packets. If you want to help please ping me on Email.

## About
The Drivers are for TP-LINK TL-WN722N Version 2 . The drivers are ported to kernel 4.8 ,4.10 && Kernel 4.13 from source from [TP-LINK-WEBSITE](http://www.tp-link.com/us/download/TL-WN722N.html) which was intially made for kernel 4.3 .

## Contributors

[Abhijeet sharma](http://students.iitmandi.ac.in/~abhijeet_sharma)
1. Github: http://github.com/abhijeet2096
2. Email: sharma.abhijeet2096@gmail.com
3. Mobile: +91-8629015433

## References/Source

1. https://github.com/mfruba/kernel
2. http://www.tp-link.com/us/download/TL-WN722N.html
3. https://github.com/mfruba/kernel/pull/21/files
4. https://github.com/diederikdehaas/rtl8812AU/issues/75
5. https://www.raspberrypi.org/forums/viewtopic.php?p=342670
6. http://xmodulo.com/build-kernel-module-dkms-linux.html 
