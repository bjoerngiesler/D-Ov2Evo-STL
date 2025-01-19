# D-Ov2Evo Head (Moveable Antennas) Instructions

## Modified Files

Use these modified files:

```
Head.stl
HeadplateDynamixel.stl
RearPanel.stl
RearPanelPlate.stl
ServoFramex3.stl
ServoLinkRodx3.stl
AerialArmx3.stl
AerialArmBracketx3.stl
```

`HeadPlateDynamixel.stl` replaces the one in the `HeadBox` directory.

## Original Files

Use these files from MrBaddeley's original D-Ov2 OneDrive:

```
Nose.stl
AerialBasex3.stl
AerialTipx3.stl
```

**Note** We use a carbon tube (OD 15mm, ID 13mm, 1mm wall thickness) cut to 124mm length instead of the printed Barskin. It's lighter and very slightly more rigid. It's also a good idea to superglue the skin onto the bar after all the cabling has been done, again for extra rigidity.

## Build Notes

This is a bit more involved.

### Caveats

Unfortunately the nano servos are often not OK out of the box. This is frustrating to say the least, and can cause at least two effects (probably more):

* Servos can become stuck in one extreme position, and not budge from there. Since at startup the servo connection pins output zero PWM the servos rush to their zero position, and if they get stuck there we can't move them unless someone moves them manually by turning the little gear. One remedy might be to add a circuit that only powers the servos when the Qt Py can output a sane PWM value. We haven't done that yet, sorry :-/ 
* Some servos just jitter. Some only in specific positions. Since we connect signal and power GND, this is not a GND issue, and we've not found a great way to quieten it.

At the moment the best bet is to swap servos until you've found three that work. They aren't exactly cheap either. Apologies.

### Orientation and Supports

Use your printer's auto-orient feature.

### Tools and hardware

In addition to the printed parts, you need 
* 3 lengths of 1.5mm carbon rod, 150mm each
* another 3 lengths of 1.5mm carbon rod, 12mm each (can also use 1.8mm, or 1.8mmx12mm steel registration pins)
* 3 nano linear servos, this sort: https://www.reichelt.de/de/de/micro-servo-ds15-links-master-ds15l-p258706.html
* an Adafruit Qt Py ESP32S2 microcontroller
* either the Bavarian Builders' D-O head servo adapter, or roll your own with a bit of stripboard (see below)
* some 2.54mm pin headers
* 12 M1.6x3mm or M1.7x3mm screws to hold the servos
* one M3x12mm thumb screw - something that you can tighten with your fingers
* one M3 square nut
* two M3x12mm socket head screws - I use Nylon ones for weight
* 6 M3x6mm socket head screws - I use Nylon ones for weight (and you can shorten them with a knife)
* 6 M1.4x3mm socket head screws
* Short Dynamixel TTL cable

### Material

Use LW-PLA (lightweight, the foaming kind) for `Head.stl`, `AerialArmBracketx3.stl`, `Nose.stl` and `AerialTipx3.stl`. Print the head and nose with a single wall, as lightweight as you possibly can. If you want you can also print `AerialBasex3.stl` in LW-PLA, unless you go to conventions, in which case it's probably a better idea to print it in TPU for flexibility should some kid grab your droid by the aerial.

Use TPU for `ServoFramex3.stl`, and print 3 of them. The reason for using TPU is to decouple the servo vibrations. If you can't print TPU you can also print these out of some other material, you'll hear a bit more servo noise, no big deal.

ASA or PLA+ for everything else.

## Assembly

### Rear Panel and Servos

* Tap 8 holes in `RearPanelPlate.stl` for M3: The 6 ones left and right to the rectangular aerial openings, and the two ones on the "legs" that will be used to screw the rear assembly to the head plate.
* Glue `RearPanelPlate.stl` to `RearPanel.stl`, so that the servo holes line up. There are four small holes around the periphery of both parts that you can use for registering the parts together with small screws (1.5mm). 
* Glue the three `ServoFramex3.stl` instances into the recesses in `RearPanelPlate.stl`, each next to an aerial opening.
* Screw the servos into the servo frames, with the nylon drive gear pointing towards the aerial openings. If the screws don't really grip that's no problem, they will hold by friction.
* Put the 12mm rods into the holes of the 3 aerial arms, and put the aerial arms into the holes. The horns are offset from the middle, orient them in such a way that they are on the other side of the corresponding servo's actuator horn.
* Add the aerial arm brackets and screw them down with short M3 socket head screws.
* Connect each servo horn to the corresponding aerial arm using M1.4 screws and the servo link rods.

### Head plate

The servos unfortunately use JST-1.0 connectors and not regular 2.54mm servo connectors like all other servos do. Therefore we need an adapter board or other connectors.

* Make sure that you have flashed the Qt Py with the Arduino sketch in `Arduino/Utilities/AntennaI2CServer`.
* If you use our servo head adapter, solder it to the Qt Py board using pin headers. The pin marked "-" on the servo head adapter connects to "GND" on the ESP32 board, and the first three pins (the ones at the other end of the "-") connect to SCK, MI, MO.
* If you don't use our servo head adapter:
  * Snip off the connectors at the end of the nano servo cables and crimp on regular 3 pin Dupont connectors. Ugly but works. Red cable (VCC) in the middle, black (GND) and white (PWM) on the sides. 
  * Build an adapter with a bit of stripboard. This adapter should have the following connections:
    * A 2-pin header for servo power, GND and +5V. This will come from the topmost Dynamixel.
    * Three 3-pin headers for the servos.
    * Connect GND from the 2-pin header to all 3 servo GNDs, and the Qt Py's GND.
    * Connect +5V from the 2-pin header to all 3 servo VCCs (middle pins), but not to the Qt Py.
    * Connect the servo connectors' PWM pins to SCK, MI, MO on the Qt Py.
  * Solder the adapter to the Qt Py so that Qt Py's GND connects to the adapter GND, and the three PWM pins to SCK, MI, MO.
* If you want to test things out, you can power the servos with an external +5V power supply and connect the Qt Py to your computer, opening a serial terminal to it. The servos should move to the center position. You can enter numbers from 0 to 180 in the serial terminal, and the servos should move to the corresponding position.
* Cut off one side of the Dynamixel TTL cable. Remove the TX cable, leaving only VCC (the middle one) and GND. If you're unsure which one is TX and which one is GND consult the neck wiring picture in https://github.com/bjoerngiesler/BBDroids/wiki/91-Individual-Droid:-D%E2%80%90Ov2Evo This is the power cable we will use for the aerial servos.
* Crimp a 2-pin Dupont connector onto the resulting power cable. Plug the side with the Dynamixel connector into the head roll Dynamixel.

### Aerials

* Glue the aerial tips onto the 1.5mmx150mm carbon rods.
* Glue the carbon roads into the aerial bases.

### Put everything together

* Glue the nose to the head cone.
* Add a M3 square nut into the pocket at the front of the head plate. There's a bit of plastic that covers the screw hole in lieu of support material. Push through this with a small screwdriver and make sure you can screw a thumbscrew into this from the top.
* Screw the servo adapter / Qt Py assembly to the head plate using the single hole in the middle at the back, so that the servo connectors point towards the rear.
* Screw the head plate onto the neck roll servo (front into the servo plate, back into the idler from the FPX330-H101 kit). M1.7 self tapping screws as usual.
* Push the head cone onto the head plate from the front, so that the head plate is underneath the plate inside the head cone.
* Fix the head cone with the thumbscrew at the front.
* Connect the servos to the adapter.
* Connect the Qt Py to the 4-pin i2c cable coming out of the neck, and to the power cable.
* Push the back head assembly into the head cone, first inserting the top latch into its slot at the top of the head, then screwing down head, head plate, and back assembly with two M3 screws from the bottom. For this you have to push the plastic aside on the bottom a bit, using hex socket screws and a hex driver with a rounded head helps.
* Push the aerials into the three aerial arms.

Presto!




