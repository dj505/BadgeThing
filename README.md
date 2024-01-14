# Untitled
A small homebrew dev board, previously known as BadgeThing

# What is it?
Untitled is a software-focused development board, and an excuse for me to learn a bit more about some specific hardware I'd like to incorporate into future projects. The main focus is the integrated SSD1306 OLED display, which I've used in earlier projects as a separate module. This time around, I wanted to adapt the circuit into the project itself to make the whole thing more cohesive.

I figured since it was going to have a screen, I needed to be able to use the screen for something, so I thought about the hardware I was already familiar with. There's the RP2040 I've used in other previous projects, and I've played with the ESP8266 before in the context of Arduino-like programming, so I thought I would try integrating that into this design so I could play with the AT firmware a little. I've used WS2812B LEDs a ton and thought they'd make a good set of indicators. And, since I wanted this to be versatile, it features some screw holes as well as slits along either side to mount using a wrist strap or some type of band to attach to other things without screws. It could even be wearable!

Oh, and it's called "Untitled" because I couldn't think of a witty name for this one. I originally wanted to call it the "no name development board with rp2040 and esp8266" with a logo and black/yellow colour scheme that parody the Canadian "no name" brand, but JLC doesn't offer black silkscreen on yellow solder mask, so I had to change it up.

# Features
- Built-in SSD1306 128*64 OLED display driver over SPI
  - Features jumpers to switch display to I2C mode if necessary. Some bodge wires required.
- Raspberry Pi RP2040
- ESP-12 module for WiFi/Bluetooth
  - Compatible with ESP-12E, ESP-12F, and ESP-12S
- Piezo buzzer pins (though they can be repurposed for other parts that use 1 GPIO)
- Row of 4 addressable RGB LEDs
- 5 buttons for input and/or navigation

# Ordering for assembly
As this project is meant to be mainly for personal use, I won't go into extensive detail here on how to order this board for assembly. However, a pre-made gerber zip is included in the "production" directory, and the BOM/CPL files can be generated through KiCAD. I recommend using the JLCPCB export plugin to do the heavy lifting for you - the LCSC part numbers I used for most components should be included in the schematic. Feel free to poke me with questions over Discord! You can reach me @dj505.
