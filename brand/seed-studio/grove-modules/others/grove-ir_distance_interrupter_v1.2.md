---
oldwikiname: Grove_-_IR_Distance_Interrupter_v1.2
bzprodimageurl: 'http://statics3.seeedstudio.com/images/101020040 1.jpg'
prodimagename: Grove_-_IR_Distance_Interrupter_v1.2.jpg
surveyurl: 'https://www.research.net/r/Grove-IR_Distance_Interrupter_v1_2'
bzurl: 'https://seeedstudio.com/Grove-IR-Distance-Interrupter-p-1278.html'
title: Grove - IR Distance Interrupter v1.2
tags: 'grove_digital, io_3v3, io_5v, plat_duino, plat_bbg, plat_wio'
sku: 101020040
category: Sensor
---

# Grove IR Distance Interrupter v1.2

![](https://raw.githubusercontent.com/SeeedDocument/Grove-IR_Distance_Interrupter_v1.2/master/img/Grove_-_IR_Distance_Interrupter_v1.2.jpg)

**Grove - IR Distance Interrupter** is used to detect any object blocking the path of light. The module consists of an IR LED and a photosensor \(phototransistor\) pair. The light emitted by the IR LED gets reflected by any object placed in front of the sensor and this reflection is detected by the photosensor\(phototransistor\). Any white \(or lighter\) colored surface reflects more than black \(or darker\) colored surface.

When the reflected light is detected, it produces **Digital HIGH** \(or Binary **1**\) output on the **SIG** pin. The on-board LED indicator will also glow. If no reflection is detected or if the object is too far from the sensor, the output on the **SIG** pin stays at **Digital LOW** \(Binary **0**\). The on-board LED indicator will be off as well. The detectable range of this sensor is 7.5–40 cm. The module incorporates a Rail-to-Rail Operational Amplifier to amplify the output of phototransistor. There is a potentiometer which can be used to adjust the gain of the amplifier, that is, sensitivity of detection.

With this sensor, you can build the following \(but not limited to\) applications: **line following robots, optical encoders** and **object counting applications**.

Note This product is mildly sensitive to non-IR radiations also and hence any bright light on photosensor impairs or disturbs IR light detection.

Tip The instructions to use this product are same as Grove - Infrared Reflective Sensor's. You can use this product directly if you have used Grove - Infrared Reflective Sensor.

## Version Tracker

| Product version | Release date | Support status |
| :--- | :--- | :--- |
| Versions older than v1.2 | June 2012‎ | Not supported |
| Grove - IR Distance Interrupter v1.2\(current version\) | April 2016 | Supported |

## Features

* Grove compatible and easy to use
* Highly sensitive and reliable
* Longer detectable distance
* Adjustable sensitivity for various occasions
* More durable

!!!Tip More details about Grove modules please refer to [Grove System](http://wiki.seeed.cc/Grove_System/)

## Specifications

| Parameter | Value |
| :--- | :--- |
| Operating voltage\(V\) | 3.3 or 5 Volts |
| Operating current\(mA\) | Maximum: 20 mA |
| Effective detectable distance | 7.5–40 cm |
| Reflective photosensor | [datasheet](https://raw.githubusercontent.com/SeeedDocument/Grove-IR_Distance_Interrupter_v1.2/master/res/Reflective_photosensor.pdf) |
| Output operational amplifiers | [datasheet](https://raw.githubusercontent.com/SeeedDocument/Grove-IR_Distance_Interrupter_v1.2/master/res/LM393.pdf) |
| Weight | 2.5 g\(for the module\), 8.5 g\(for all single package\) |

## Platforms Supported

Note If no version number is mentioned for a specific platform, it means this product supports all versions within this platform. But, you will need additional Grove Shield like Grove - Base shield v2 board.

## Hardware Overview

![](https://raw.githubusercontent.com/SeeedDocument/Grove-IR_Distance_Interrupter_v1.2/master/img/Grove-IR_Distance_Interrupter_v1.2_hardware_overview_1200.jpg)

* **RPR-359F Reflective photosensor**, Highly sensitive reflective photosensor.
* **LM393 operational amplifier**, rail-to-rail operational amplifier.
* **LED Indicator**, The LED will turn on when the received infrared light intensity exceeds a preset level.
* **Light sensitivity adjusting potentiometer** , adjust the sensitivity of reflective photosensor to light.

### **Package includes**

| Parts name | Quantity |
| :--- | :--- |
| Grove - Infrared Reflective Sensor | 1 piece |
| [Grove cable](http://www.seeedstudio.com/depot/Grove-Universal-4-Pin-Buckled-5cm-Cable-5-PCs-Pack-p-925.html?cPath=98_106_57) | 1 piece |

## Getting Started

Let us see how to implement few basic applications with this module:

### With Arduino

#### Material required

* Grove - IR Distance Interrupter v1.2 × 1
* Arduino UNO \(other models also are fine\) × 1
* [Grove cable](http://www.seeedstudio.com/depot/Grove-Universal-4-Pin-Buckled-5cm-Cable-5-PCs-Pack-p-925.html?cPath=98_106_57) × 1
* [Grove - Base Shield](/Base_Shield_V2) × 1

#### Connections

1.Connect Grove - IR Distance Interrupter v1.2 to Arduino UNO with Grove cable.

2.Place and hold the Reflective photosensor towards white\(or light\) colored surface.

![](https://raw.githubusercontent.com/SeeedDocument/Grove-IR_Distance_Interrupter_v1.2/master/img/Reflective_photosensor3.jpg)

3.Adjust the potentiometer with a screwdriver to change the sensitivity of reflective photosensor, until the LED indicator glows. As your rotate clockwise, the reflective photosensor will be more sensitive to light.

Note Use a proper screw-driver to adjust the tiny potentiometer. Applying heavy pressure or frequent adjustments might damage the wiper of the potentiometer.

![](https://raw.githubusercontent.com/SeeedDocument/Grove-IR_Distance_Interrupter_v1.2/master/img/Reflective_photosensor2.jpg)

![](https://raw.githubusercontent.com/SeeedDocument/Grove-IR_Distance_Interrupter_v1.2/master/img/Reflective_photosensor1.jpg)

4.Create an Arduino sketch and copy the below code into it.

```text
void setup()  {
    Serial.begin(9600);
    pinMode(6,INPUT);
}
void loop()  {
    while(1)  {
        delay(500);
        if(digitalRead(6)==LOW)  {
            Serial.println("Somebody is here.");
        }
        else  {
            Serial.println("Nobody.");
        }
    }
}
```

5.Upload the code. If you do not know how to upload a Arduino sketch, please visit [https://www.arduino.cc/en/Guide/Windows](https://www.arduino.cc/en/Guide/Windows) for Windows user or [https://www.arduino.cc/en/Guide/MacOSX](https://www.arduino.cc/en/Guide/MacOSX) for Mac user. You can see the result as below.

6.When the path of light is blocked by some object, you would see "Somebody is here." in Serial Terminal else you will see "Nobody."

### With Raspberry Pi

#### Material required

* Raspberry Pi \(other models also are fine\) × 1
* [GrovePi](http://www.seeedstudio.com/depot/GrovePi-p-1672.html?cPath=73) or [Grovepi+](http://www.seeedstudio.com/depot/GrovePi-p-2241.html?cPath=122_154_158) × 1
* [Grove cable](http://www.seeedstudio.com/depot/Grove-Universal-4-Pin-Buckled-5cm-Cable-5-PCs-Pack-p-925.html?cPath=98_106_57) × 1

#### Hardware Connections and Software Work

1.You should have a Raspberry Pi and a GrovePi or GrovePi+. In this demo, we use GrovePi.

2.We assume you have built the development environment successful. If not, follow [this tutorial](/GrovePiPlus).

3.Connection:

Plug Grove - IR Distance Interrupter into port D4 on GrovePi with [Grove cable](http://www.seeedstudio.com/depot/Grove-Universal-4-Pin-Buckled-5cm-Cable-5-PCs-Pack-p-925.html?cPath=98_106_57).

4.Navigate to the demos' directory, run the following command in a terminal.

```text
    cd yourpath/GrovePi/Software/Python/
```

Run the command in a terminal:

```text
    nano grove\_infrared\_distance\_interrupt.py
```

Copy and save the following code into it.

```text
import time
import grovepi

# Connect the Grove Infrared Distance Interrupt Sensor to digital port D4
# SIG,NC,VCC,GND
sensor = 4

grovepi.pinMode(sensor,"INPUT")

while True:
    try:
        # Sensor returns LOW and onboard LED lights up when the
        # received infrared light intensity exceeds the calibrated level
        if grovepi.digitalRead(sensor) == 0:
            print "found something"
        else:
            print "nothing"

        time.sleep(.5)

    except IOError:
        print "Error"
```

5.Run the demo, run following command in terminal.

```text
    sudo python grove\_infrared\_distance\_interrupt.py
```

## Resources

* [Grove - IR Distance Interrupter v1.2 Eagle file](https://raw.githubusercontent.com/SeeedDocument/Grove-IR_Distance_Interrupter_v1.2/master/res/Eagle_files.zip)
* [Reflective Photosensor Datasheet](https://raw.githubusercontent.com/SeeedDocument/Grove-IR_Distance_Interrupter_v1.2/master/res/Reflective_photosensor.pdf)
* [LM393 Datasheet](https://raw.githubusercontent.com/SeeedDocument/Grove-IR_Distance_Interrupter_v1.2/master/res/LM393.pdf)
* [LMV358 Datasheet](https://raw.githubusercontent.com/SeeedDocument/Grove-IR_Distance_Interrupter_v1.2/master/res/LMV358_datasheet.pdf)
* [Infrared Reflective Sensor Source Files](https://raw.githubusercontent.com/SeeedDocument/Grove-IR_Distance_Interrupter_v1.2/master/res/Grove-Infrared_Reflective_Sensor_v1.0_SourceFile.zip)

