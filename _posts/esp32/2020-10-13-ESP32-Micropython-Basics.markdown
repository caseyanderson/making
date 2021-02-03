---
layout: post
title:  "Micropython Basics"
date:   2020-10-13 07:00:00 -0700
categories: "esp32"
week: "5"
published: false
---

# Digital Output
## Materials

* laptop
* internet access
* [Adafruit HUZZAH32](https://www.adafruit.com/product/3591)
* [USB cable - USB A to Micro-B - 3 foot long](https://www.adafruit.com/product/592) (or similar)
* 1x Breadboard
* 1x Resistor (220, 270, or 330 Ohms)
* 1x LED


## blink.py (internal LED)

```python
'''
blink.py (internal led)
'''

from machine import Pin
from time import sleep

led = Pin(13, Pin.OUT)

while True:
    led.value(1)
    sleep(0.5)
    led.value(0)
    sleep(0.5)

```


## blink.py (external LED)

### Hookup Pattern

![]({{site.url}}/assets/imgs/fritzing/blink_external_led.png)


## update blink.py (for external LED)

1. On your laptop open `blink.py` in Jupyter Notebook and change the pin number from `13` to `27`: `jupyter notebook blink.py`
2. Delete the previous version of `blink.py` from the ESP32: `ampy -p /dev/tty.SLAB_USBtoUART rm blink.py`
3. Write the new version of `blink.py` to the ESP32: `ampy -p /dev/tty.SLAB_USBtoUART put blink.py`
4. Connect to ESP32 Command Prompt
5. Run `blink.py`: `import blink.py`
6. Ctrl-C to stop `blink.py`
7. Ctrl-D to reboot
7. Exit the ESP32 Command Prompt


## blink_if.py (external LED + if statement)

Another way to blink an LED is to use [Boolean logic](https://en.wikipedia.org/wiki/Boolean_algebra). In the example below we check to see if the `led.value` is `0` (or off). If the LED is off we turn it back on (`led.value(1)`), otherwise, we turn the led off (`led.value(0)`). We repeatedly check `led.value()` by wrapping this `if` statement in a `while` loop, which will run forever.

```python
'''
blink w/ if statement
'''

from machine import Pin
from time import sleep

led = Pin(13, Pin.OUT)

while True:
    if led.value() == 0:
        led.value(1)
    else:
        led.value(0)
    sleep(0.5)
```


# Digital Input / Digital Output
## Materials

* laptop
* internet access
* [Adafruit HUZZAH32](https://www.adafruit.com/product/3591)
* [USB cable - USB A to Micro-B - 3 foot long](https://www.adafruit.com/product/592) (or similar)
* 1x Breadboard
* 1x Resistor (220, 270, or 330 Ohms)
* 1x LED
* 1x SPST button


## Digital Input

### button.py

```python
'''
button.py
'''

from machine import Pin
from time import sleep_ms

button = Pin(12, Pin.IN, Pin.PULL_UP)

while True:
    if not button.value():
        print('Button pressed!')
    sleep_ms(20)

```

### Hookup Pattern

![]({{site.url}}/assets/imgs/fritzing/button.png)


## Digital Input / Digital Output

### button_led.py

```python
'''
button_led.py
'''

from machine import Pin
from time import sleep_ms

button = Pin(12, Pin.IN, Pin.PULL_UP)
led = Pin(27, Pin.OUT)

while True:
    if not button.value():
        led.value(1)
    else:
        led.value(0)
    sleep_ms(20)
```

### Hookup Pattern

![]({{site.url}}/assets/imgs/fritzing/button_led.png)

# Analog Read
## Materials

* laptop
* internet access
* [Adafruit HUZZAH32](https://www.adafruit.com/product/3591)
* [USB cable - USB A to Micro-B - 3 foot long](https://www.adafruit.com/product/592) (or similar)
* 1x Breadboard
* 1x Potentiometer
* 1x LED (w/ 1x Resistor [220, 270, 330])

## analog_read.py

```python
# analog read

from machine import ADC, Pin
from time import sleep_ms

adc = ADC(Pin(34))
adc.atten(ADC.ATTN_11DB)

while True:
  print(adc.read())
  sleep_ms(20)
```

### Hookup Pattern

![]({{site.url}}/assets/imgs/fritzing/analog_read.png)
