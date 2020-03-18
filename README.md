This Tutorial is for people that know at least a bit of c++
In this tutorial we are going to use the HTD sensor library (Version 1.3.8) so you must install it [(link for how to download and setup a library in arduino IDE).](https://www.arduino.cc/en/Guide/Libraries)

Things used for this project:
- Arduino uno
- DHT11 Sensor 
- 3 Male Wires 
- Breadboard

### 1. Connections 

![DHT11Sensor_bb](https://user-images.githubusercontent.com/47701859/72470889-448a2300-37ea-11ea-9a7b-710a3f139ca5.png)
![DHT11_Pins](https://user-images.githubusercontent.com/47701859/72471055-8fa43600-37ea-11ea-8fd7-b0235d26b6de.png)

You connect the first wire to the VCC pin in the breadboard the end of the the wire goes in the 3v3 pin of your Arduino.
You connect the second wire on the Data pin in the breadboard the end of the wire goes in the A1
And the third is GRD(Ground) so you connect the wire on that pin and the end of it in any GND in your Arduino.
(The fourth pin in not used so dont worry about it)

### 2. CODE

`#include <DHT.h>`

`#define DHTPIN A1`

`#define DHTTYPE DHT11`

`DHT dht(DHTPIN, DHTTYPE);`

`void setup(){`

`  Serial.begin(9600);`

`}`

`void loop()`

`{`

`  int d = dht.read(DHTPIN);`

`  Serial.print("Temperature = ");`

`  Serial.print(dht.readTemperature());`

`  Serial.println("C ");`

`  Serial.print("Humidity = ");`

`  Serial.print(dht.readHumidity());`

`  Serial.println("% ");`

`  Serial.print("============================================= \n");`

`  delay(4000);`

`}`


First you import the library, after that you define the pin that you connected the data pin of the sensor and then you define the type of the sensor now we are using the DHT11, then we call a function from the library using the values we defined (i'm not gonna get in details about the coding part, see on top). `Serial.begin(9600);` is gonna start a session where we can later print our values on (like a debugger) as we can see in the loop.
After you upload the code to the Arduino, to see the outputs you have to click on the top right of the IDE, there is something like magnifying lens 

![learn_arduino_ide_serial_moniotor_button](https://user-images.githubusercontent.com/47701859/72473678-e3654e00-37ef-11ea-874f-69a95c7943c5.jpg)
click and wait a few seconds


# The key words are:

###########################################
# Syntax Coloring Map For DHT-sensor-library
###########################################

###########################################
# Datatypes (KEYWORD1)
###########################################

DHT	KEYWORD1

###########################################
# Methods and Functions (KEYWORD2)
###########################################

begin	KEYWORD2

readTemperature	KEYWORD2

convertCtoF	KEYWORD2

convertFtoC	KEYWORD2

computeHeatIndex	KEYWORD2

readHumidity	KEYWORD2

read	KEYWORD2

If you go where you installed the library and go through the files you can see another example and a keywords.txt
Read the Keywords bcs other tutorials use older versions and the code is not compatible with the new 
See how the sensor [works](http://www.micro4you.com/files/sensor/DHT11.pdf)

Sorry for my english
If you want share this tut and folow me
