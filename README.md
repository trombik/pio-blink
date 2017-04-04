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

## LICENSE

```
Copyright (c) 2017 Tomoyuki Sakurai <tomoyukis@reallyenglish.com>

Permission to use, copy, modify, and distribute this software for any
purpose with or without fee is hereby granted, provided that the above
copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
```
