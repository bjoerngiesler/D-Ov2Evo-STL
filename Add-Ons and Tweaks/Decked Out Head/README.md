# Decked Out Head

This directory contains files for what we call the "Decked Out Head". It's a one-piece head with a separate eye tray and eye covers / "lenses" that can be used to add LED "eyes" to D-O. There is also a variant that allows mounting a FPV camera in the head cone.

This head absolutely needs a neck counterweight, it is too heavy otherwise. Even so, it should be printed in LW-PLA for weight reduction. D-O will drive with a decked out head in regular PLA but you will definitely notice the extra weight. At least for the version with the camera mount, it also will not print properly without supports. This definitely makes it a challenging print. Know what you're signing up for :-)


## Parts
* Headlight tint spray (I use https://www.amazon.de/dp/B0CTCSPR32)
* 3 WS2812 LED strips with 20 LEDs each (e.g. https://de.aliexpress.com/item/4000197861280.html)
* Optional FPV camera: Wyvern Link VTX 100mW transmitter (https://de.banggood.com/Emax-Wyvern-Link-AlphaOpenIPC-100mW-Video-Transmitter-VTX-for-RC-Drone-p-2022191.html)
* Optional FPV cam receiver (https://www.banggood.com/Emax-Wyvern-Link-AlphaOpenIPC-100mW-Video-Receiver-VRX-p-2022194.html)
* On the Qt Py in the head, solder the board with the Neopixel connector, not the one without.

## Printing and Assembly Instructions
1. Print the head variant of your choice, and the eye tray. 
2. Print the eye lens three times in regular white PLA.
3. Paint the eye lenses with a couple coats of headlight tint spray until they are as dark as you would like them.
4. Cut 3 LEDs off each of the LED strips, leaving 17 LEDs on each strip. Cut off the side without the cable, and make sure that you leave enough of the soldering pads intact that you can still solder cables to them.
5. Cut off the connectors on 2 of the strips.
6. Use double sided tape to mount the LED strips in the eye tray. The left eye gets the strip with the connector on it; push the connector through the hole at the top. The strip for the middle eye is mounted upside down; route the cable out the bottom and into the bottom hole on the left strip. The strip for the right eye is mounted with the cable pointing up; route it out the top and into the top hole on the middle strip.
7. Carefully connect the three strips by soldering the cables from the middle to the left and from the right to the middle strip, matching the colors of the cables coming out the other side. Lift the strip ends with the solder pads out of the eye tray for this so you don't heat up the eye tray's PLA.

## Connecting the Neopixel strips
This is a bit awkward for the current generation of boards. We are updating the board but at the moment you have to do some wiring and modification on the connector.

1. SMD solder the connector onto the board if it is not already on. Make sure that you also solder the side tabs, as they will take the mechanical strain from inserting the cable later - if you don't there is a good chance of breaking off the connector. Ask me how I know.
2. Solder a wire from the board's +5V input to the ESP32's +5V input.
3. Solder a wire from the ESP32's RX pin (it's the one farthest away from the +5V input on the same side) to the small hole on the board marked "NP" or "Neopixel".
4. Do not plug the Neopixel strip in yet. Plug the board into USB-C and measure the connection. It should have GND on the pin next to the "NP" hole, the connection to "NP" on the middle pin, and the connection to +5V on the pin closest to the ESP32 board. Make sure that your cable reflects that mapping - black wire is GND, red wire is +5V, and white wire is Data or "NP". You can rewire the cable by carefully lifting up the plastic tabs holding the pins with a needle and gently pulling the pins out and reinserting them into the correct holes.