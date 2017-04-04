# pio-blink

A `platform.io` project that builds `blink.ino` for multiple boards.

## Usage

### Requirements

* [PlatformIO Core](http://docs.platformio.org/en/latest/core.html)
* [Arduino IDE](http://www.arduino.org/learning/getting-started)

### Building

```sh
pio run
```

### Uploading

#### attiny boards

The target AVR ISP is `ArduinoISP`. See "Circuit (targeting an AVR on a
breadboard)" in [Using an Arduino as an AVR ISP (In-System
Programmer)](https://www.arduino.cc/en/Tutorial/ArduinoISP) for hookup.

```sh
pio run -t program -e attiny13
```

### Writing fuses

```sh
pio run -t fuses -e bootloader_attiny13
```

For `fusebits`, see:

* https://embedderslife.wordpress.com/2012/08/20/fuse-bits-arent-that-scary/
* http://www.pocketmagic.net/how-to-set-the-avr-fusebits/
* http://www.engbedded.com/fusecalc

## Hooking up

### ATtiny85 and ATtiny13a

```
LED_BUILTIN is 1, pin 6 or PB 1
                 +-\/-+
Ain0 (D 5) PB5  1|    |8  Vcc
Ain3 (D 3) PB3  2|    |7  PB2 (D 2)  Ain1
Ain2 (D 4) PB4  3|    |6  PB1 (D 1) pwm1 --> LED + Registor --> GND
           GND  4|    |5  PB0 (D 0) pwm0
                 +----+
```
