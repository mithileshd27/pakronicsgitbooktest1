---
title: Grove - Button
category: Actuator
bzurl: 'https://www.seeedstudio.com/Grove-Button-p-766.html'
oldwikiname: Grove - Button
prodimagename: Button.jpg
surveyurl: 'https://www.surveymonkey.com/r/grove-button'
sku: 101020003
---

# Grove Button

![](https://github.com/SeeedDocument/Grove_Button/raw/master/image/Button.jpg)

**Grove - Button** is a momentary push button. It contains one independent "momentary on/off" button. “Momentary” means that the button rebounds on its own after it is released. The button outputs a HIGH signal when pressed, and LOW when released. The button signals the SIG Pin of the Grove Interface while NC is not used at all. There are two versions of this button available as showed in the pictures. The only difference between them is the direction of the Grove socket.

## Features

* Easy to use momentary ON/OFF button
* Uses Standard 4-pin Grove Cables to connect to other Grove modules such as Grove Power Modules and Grove - Base Shield

## Usage

**Standalone**

Follow these steps to build a sample circuit using this module but without using any microcontroller:

* Connect the button module to the input side of your circuit \(to the left of the power module\). On the output side of the circuit, you may use a range of User [Interface modules](/Grove/Grove_System/) \(Grove - Red LED, Grove - LED String Light, Grove - Mini Fan, Grove - Buzzer, Grove - Recorder etc.\)
* Power up the circuit when complete.
* The button module can now be used to trigger an output. For example:
  * When used in conjunction with a Grove - Red LED output module, observe that the LED turns ON when you press the button and turns OFF when you stop pressing it.

![](https://github.com/SeeedDocument/Grove_Button/raw/master/image/Grove-momentarySwitch-RedLED.jpg)

In terms of power modules, use either the Grove - USB Power module or the Grove - DC Jack Power module for the Grove circuit.

**With Arduino**

Follow these simple steps to build a Grove circuit using the momentary ON/OFF button:

When using the module in conjunction with an Arduino or a Seeeduino, use the Grove - Base Shield and connect the Grove - Button module to the shield using a designated Grove interface. Also attach an output module such as a Grove - Red LED which will get triggered based on input received from the button. Upload the following sample sketch to make the LED turn ON and OFF based on input from Grove - Button:

```c
//Turns on and off a light emitting diode(LED) connected to digital pin 13, when pressing a pushbutton attached to pin 2.

/*
 The circuit:
 * LED attached from pin 13 to ground
 * pushbutton attached to pin 2 from +5V
 * 10K resistor attached to pin 2 from ground

 * Note: on most Arduinos there is already an LED on the board
 attached to pin 13.


 This example code is in the public domain.

 http://www.arduino.cc/en/Tutorial/Button
 */

// constants won't change. They're used here to
// set pin numbers:
const int buttonPin = 2;     // the number of the pushbutton pin
const int ledPin =  13;      // the number of the LED pin

// variables will change:
int buttonState = 0;         // variable for reading the pushbutton status

void setup() {
    // initialize the LED pin as an output:
    pinMode(ledPin, OUTPUT);
    // initialize the pushbutton pin as an input:
    pinMode(buttonPin, INPUT);
}

void loop(){
    // read the state of the pushbutton value:
    buttonState = digitalRead(buttonPin);

    // check if the pushbutton is pressed.
    // if it is, the buttonState is HIGH:
    if (buttonState == HIGH) {
        // turn LED on:
        digitalWrite(ledPin, HIGH);
    }
    else {
        // turn LED off:
        digitalWrite(ledPin, LOW);
    }
}
```

**With Raspberry Pi**

This is a simple example of Raspberry Pi. Run Program and press button, it will print 1 on the terminal, else print 0. Such as the picture below.

![](https://github.com/SeeedDocument/Grove_Button/raw/master/image/GrovePi%2B_grove_button.jpg)

![](https://github.com/SeeedDocument/Grove_Button/raw/master/image/Grovepi%2B_grove_button_terminal.jpg)

```python
# http://www.seeedstudio.com/wiki/Grove_-_Button

import time
import grovepi

# Connect the Grove Button to digital port D3
# SIG,NC,VCC,GND
button = 3

grovepi.pinMode(button,"INPUT")

while True:
    try:
        print grovepi.digitalRead(button)
        time.sleep(.5)

    except IOError:
        print "Error"
```

**Run The Program**

* Find the path to the file\(According to your own path\)

  ```text
  cd GrovePi/Software/Python/
  ```

* Run Progrom

  ```text
  sudo python grove_button.py
  ```

## Project

![](https://raw.githubusercontent.com/SeeedDocument/Grove_Button/master/img/gun.jpg)

Inspired by OVERWATCH, we have made a very cool Wooden Laser Gun toy for fun these day!

The Wooden Laser Gun and the Gun Target are all based on an Arduino board called Seeeduino Lotus. The laser emitter on the Laser Gun is controlled to fire laser pulse to "activate" the Gun Target. And there are 3 light sensors on the Gun Target to detect the laser pulse. It seems very simple right? If you are interested in our project, please make one for yourself or your child! It's worth to spend one day DIY it as a Xmas present.

## Resources

* [Schematic at Easyeda](https://easyeda.com/Seeed/Grove_Button_v1_2-f0f9f212fcee460ebe3703dab813e5c4)
* [Grove-Button Eagle Files](https://github.com/SeeedDocument/Grove_Button/raw/master/resources/Grove_-_Button_v1.0_Source_File.zip).
* [How to upload code](http://wiki.seeedstudio.com/wiki/Upload_Code)

