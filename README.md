# Arduino_vBus

I was working to Build up a System, which shows me Time, Temperature and Solar/Heating Datas.

- Arduino Due
- Arduino WiFi Shield
- Adafruit BME280 Humidity + Barometric Pressure + Temperature Sensor Breakout over IC2
- Nextion Enhanced 7" Display NX8048K070_011R 
- Resol DL2

Time:
Nextion Enhanced is running with an RTC Clock. The Clock will be synced with NTP.

Temperature:
Temperature is pushed over IC2 from the BME280 to the Arduino

Resol vBus :
The Communication is established over HTTP with the Resol Datenlogger DL2. The Datas are convertet from a JSON Table.

Display:
The Display has an own HMI. It gots only the Signals over UART from the Arduino DUE (Serial2).

Libarys:
<SPI.h>
<Wire.h>
<WiFi.h>
<WiFiUdp.h>
<TimeLib.h>
https://github.com/PaulStoffregen/Time
<ArduinoJson.h>      
https://github.com/bblanchon/ArduinoJson
<Adafruit_Sensor.h>  
https://github.com/adafruit/Adafruit_Sensor
<Adafruit_BME280.h>  
https://github.com/adafruit/Adafruit_BME280_Library
"Nextion.h"          
https://github.com/itead/ITEADLIB_Arduino_Nextion
<avr/dtostrf.h>
<stdlib.h>

The Libary Nextion needs the latest Pull request (29) to Update the RTC-Commands.
On File "NexUpload.cpp" of the Libary you have to disable line 17 (//#include <SoftwareSerial.h>)
