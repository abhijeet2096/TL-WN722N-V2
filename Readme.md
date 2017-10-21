# TL-WN722N-V2 Drivers clean ported to Kernel 4.10 (GNU/LINUX)

## TL-WN722N-V2

![TL-WN722N-V2](device_img.jpg?raw=true "TL-WN722N-V2")


## Installation Instruction

1. Clone the above repo by 
	```
	 $ git clone https://github.com/abhijeet2096/TL-WN722N-V2
	```
2. Spawn terminal in cloned folder.
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
 8. `airmon-ng <device-name>`
 9. `airodump-ng <device-name>' 
 10 Monitor mode should start

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
The Drivers are for TP-LINK TL-WN722N Version 2 . The drivers are ported to kernel 4.10 from source from [TP-LINK-WEBSITE](http://www.tp-link.com/us/download/TL-WN722N.html) which was intially made for kernel 4.3 .

## Contributors

[Abhijeet sharma](http://students.iitmandi.ac.in/~abhijeet_sharma)
1. Github: http://github.com/abhijeet2096
2. Email: sharma.abhijeet2096@gmail.com
3. Mobile: +91-8629015433

## References/Source

1. https://github.com/mfruba/kernel
2. http://www.tp-link.com/us/download/TL-WN722N.html
