
## Geekcon buttplug project

During geekcon 2016 we made a buttplug with wifi access capability.
Two models were built.
The first is a es8266 Adafruit Huzzah board with a pressure sensor (we recommend to add an mp6050 for next time). 
The Second is a Linkit 7688 with a torrent server, an accelerometer mp6050, and a webcam.

## Esp8266

The ESP model has Firmware Over-The-Air (FOTA) capability, and uses an esp8266 Huzzah. We also used a NodeMCU 0.9, which also works (you might need to change the LED pin).

Simply set your ssid and password, flash an upload the code. Connect a pressure sensor to the I2C pins, and an LED to the led pin.
Once conncted, you will have a webserver with the pressure and tempreture readings.


## Linkit Instructions

the linkit 7688 dev boards have a good 3v3 regulator, the [XC6220](http://media.digikey.com/pdf/Data%20Sheets/Torex/XC6220.pdf) 

http://www.cnx-software.com/2015/12/01/mediatek-linkit-smart-7688-and-smart-7688-duo-boards-run-openwrt-for-iot-applications/

### low dropout

![]http://i.imgur.com/Kw4ZbtX.jpg

the linkit power draw even under peeks will not surpass the 400mA
and at idle can stablise on 

### 1A max current
this effects the dropout, and temprature. 



#### fails
the  MP1583 Step-Down convertor cant hepl as its "4.75V to 23V Operating Input Range", the 


## sensors
### BMP180 pressure sensors
https://cdn-shop.adafruit.com/datasheets/BST-BMP180-DS000-09.pdf

i2c 
Pressure range: 300 ... 1100hPa (+9000m ... -500m relating to sea level)
Supply voltage: 1.8 ... 3.6V (VDD)


###MPU6050
python soruce for reading data:
https://github.com/intel-iot-devkit/upm/blob/master/examples/python/mpu60x0.py
*Note: did not work on the duo because of the arduino pins

### lols
http://www.penguin.cz/~utx/hardware/Creatic_18650_Power_Bank/CT6201_v1.0.pdf

#### charging
no worries, just hook both battary and load on the same line [ladyada](https://learn.adafruit.com/li-ion-and-lipoly-batteries/proper-charging)

[TP4056 1A Linear Li-lon Battery Charger with Thermal](https://dlnmh9ip6v2uc.cloudfront.net/datasheets/Prototyping/TP4056.pdf)

##video streaming
https://iamblue.gitbooks.io/linkit-smart-nodejs/content/en/basic/video_streaming.html

Bus 001 Device 002: ID 1e4e:0110 Cubeternet
https://github.com/foosel/OctoPrint/wiki/Webcams-known-to-work


https://github.com/intel-iot-devkit/mraa
