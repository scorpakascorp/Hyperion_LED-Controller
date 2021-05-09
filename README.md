# Hyperion LED Controller for ESP8266/ESP32

Original GIT [SciLor/Hyperion_LED-Controller](https://github.com/SciLor/Hyperion_LED-Controller)

This code allows you to use a ESP8266 with a fitting led strip as extension for [hyperion](https://github.com/hyperion-project) (ambilight clone).
You need to configure hyperion to stream the leds as UDP to the esp.

English Tutorial: https://hyperion-project.org/threads/tutorial-wireless-led-extension-with-esp8266-esp32-for-hyperion.3004/

French Tutorial: https://ambimod.jimdo.com/2017/01/12/tuto-faire-de-l-ambilight-sans-fil-avec-un-esp8266-nodemcu-et-la-biblioth%C3%A8que-fastled/

German Tutorial: https://forum-raspberrypi.de/forum/thread/25242-tutorial-esp8266-nodemcu-addon-wifi-led-controller-udp/

Tested with following following libraries (other versions may work):
# IDE
a) VS Code + PlatformIO

# Libraries
a) ArduinoThread @ >2.1.1

b) ArduinoJSON @ >5.12.0

c) LinkedList @ >1.2.3

d) FastLED @ >3.1.6

e) Logging https://github.com/SciLor/Arduino-logging-library 


# Installation

# Configuration of the board
1. Go to the `HyperionRGB` folder and create a copy of `ConfigStatic.h.example`. Remove the `.example` suffix
2. Configure the `ConfigStatic.h` for your needs:
   - Select your LED chip type. All LEDs of the [FastLed](https://github.com/FastLED/FastLED) libraries are supported
   - Configure the used LED pins. You can also change the Pin Order. The NodeMCU order doesn't work sometimes to please also try the `RAW_PIN_ORDER``
   - Define the number of used LEDs
   - Define one of the standard modes which are active when your light is idle. Choose one from: OFF, HYPERION_UDP, STATIC_COLOR, RAINBOW, FIRE2012
   - You maydefine Wifi configuration but you can also change it from the Webinterface
3. Open the project folder in VS Code
4. Compile and upload to your board

# Configuration of Hyperion NG


Go to **Confiruration -> General**, select Controller type: **udpraw** set Target IP (your ESP IP addr) and Port (**19446**).


There's a detailed instruction page for [controlling multiple devices](https://hyperion-project.org/wiki/Controlling-Multiple-Devices).

