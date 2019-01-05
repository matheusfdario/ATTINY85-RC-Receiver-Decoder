# ATTINY85 RC Receiver Signal Decoder

[![GitHub](https://img.shields.io/github/license/mashape/apistatus.svg)](https://en.wikipedia.org/wiki/MIT_License)

An RC receiver signal decoder using an [AVR ATTINY85 microcontroller](https://www.microchip.com/wwwproducts/en/ATtiny85). The decoder uses half of the 8-bit resolution for the 1ms between minimum (1ms) and maximum (2ms) RC receiver pulse.

## Features
  - An LED attached to LED_PORT indicates the servo center position (use a 200&Omega; resistor for the LED)
 - The pins for receiver and LED can be configured by the corresponding macros (RC_RECEIVER_PORT, LED_PORT). Do not use VCC, GND and RESET pins

## Example Breadboard Configuration

Obviously, before use, the code **main.c** needs to be programmed on the device via any ISP programmer.

![](images/Fritzing_Layout.png)

## Prerequisites
 - For the code to work the CPU needs to run at 8 MHz (this is NOT the factory default)
 - The fuse **CKDIV8** has to be unset, otherwise the CPU would run at 1 MHz
 - As an alternative the **CKDIV8** could be left as is (factory default), but then the prescaler for the *8-bit Timer/Counter1* has to be set to **4** (using the CS1x bits in the *8-bit Timer/Counter1* control register TCCR1). This alternative is untested.

<!--- HTML code used in order to be able to resize image -->
<img src="images/Fuse_Settings.png" alt="drawing" width="600"/>

**Setting of fuses in ATMEL Studio 7 - CKDIV8 unchecked for 8 MHz clock speed**

## Additional information
 - Official MICROCHIP [ATTINY85 datasheet](http://ww1.microchip.com/downloads/en/DeviceDoc/Atmel-2586-AVR-8-bit-Microcontroller-ATtiny25-ATtiny45-ATtiny85_Datasheet.pdf)

<br></br>

Distributed under the MIT license. See [LICENSE](https://github.com/chiefenne/ATTINY85-Servo-Control/blob/master/LICENSE) for more information.


