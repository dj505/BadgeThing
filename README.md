# Untitled
A small homebrew dev board, previously known as BadgeThing

# What is it?
Untitled is a software-focused development board, and an excuse for me to learn a bit more about some specific hardware I'd like to incorporate into future projects. The main focus is the integrated SSD1306 OLED display, which I've used in earlier projects as a separate module. This time around, I wanted to adapt the circuit into the project itself to make the whole thing more cohesive.

I figured since it was going to have a screen, I needed to be able to use the screen for something, so I included hardware I was already familiar with to interface with. There's the RP2040 I've used in other previous projects, and I've played with the ESP8266 before in the context of Arduino-like programming, so I thought I would try integrating that into this design so I could play with the AT firmware a little. I've used WS2812B LEDs a ton and thought they'd make a good set of indicators. And, since I wanted this to be versatile, it features some screw holes as well as slits along either side to mount using a wrist strap or some type of band to attach to other things without screws. It could even be wearable!

Oh, and it's called "Untitled" because I couldn't think of a witty name for this one. I originally wanted to call it the "no name development board with rp2040 and esp8266" with a logo and black/yellow colour scheme that parody the Canadian "no name" brand, but JLC doesn't offer black silkscreen on yellow solder mask, so I had to change it up.

# Features
- Built-in SSD1306 128*64 OLED display driven over SPI
- Raspberry Pi RP2040
- ESP-12 module for WiFi/Bluetooth
  - Compatible with ESP-12E, ESP-12F, and ESP-12S
- Piezo buzzer pins (though they can be repurposed for other parts that use 1 GPIO)
- Row of 4 addressable RGB LEDs
- 5 buttons for input and/or navigation
- Extra GPIO broken out, with access to additional SPI/UART/I2C busses if needed
- Wristband/wrist strap slots and mounting holes

# Custom SSD1306 footprint
I couldn't find an easy-to-place foorptint for the 30-pin SSD1306 display, so this project includes a custom KICAD footprint for the typical 12mm length/7mm pin pitch ribbon cable variant you can find for cheap on AliExpress. There are 4 variants, two meant for mounting the screen on the front of the board, and two for mounting it on the back. Both placements have variants including and excluding a cutout in the Edge.Cuts layer for the ribbon cable to pass through. **You are free to use these footprints in any project you want! I just ask that credit is provided.**

There is also a custom symbol in the schematic for the display, based off of Adafruit's schematic. I can't guarantee all the pins are labelled correctly. I have tested it, and it does work, but you should research and double check the correct pinouts for your own project.

# Parts
The majority of the parts are clearly labelled in the schematic and/or come with LCSC part numbers available through JLC. Not all of them are basic parts, unfortunately, but I used as many as I possibly could. You're also free to order part like the ESP-12 module separately and solder it yourself to save on assembly costs. However, it's important to keep in mind the following:
- The OLED diplay is made with a **0.7mm pin pitch in mind.** Some of the displays available have a 0.5mm pin pitch and will not fit.
- The display's ribbon cable should be **no longer than ~12mm** otherwise it will not fit the footprint without extra slack.
- Every ESP-12 model should fit this footprint, however I use the ESP-12S due to it supposedly having the best antenna efficiency. The missing pins along the bottom of the footprint are OK because this design does not use them, and they only serve to provide extra mechanical strength.
- The RGB LEDs are made with WS2812B-V5 LEDs in mind specifically, as they have built-in capacitors and such that I was not able to reliably fit on the PCB. Other pin-compatible and signal-compatible LEDs will work, and there is a footprint for one large capacitor. In my testing, LEDs that don't have a built in capacitor worked fine without one, but there may be cases where this does not hold true. Check the datasheet for the LEDs you plan to use to make sure they do not require an external capacitor.

# Ordering for assembly
As this project is meant to be mainly for personal use, I won't go into extensive detail here on how to order this board for assembly. However, a pre-made gerber zip is included in the "production" directory, and the BOM/CPL files can be generated through KiCAD. I recommend using the JLCPCB export plugin to do the heavy lifting for you - the LCSC part numbers I used for most components should be included in the schematic. Feel free to poke me with questions over Discord! You can reach me @dj505.
