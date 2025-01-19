# D-Ov2Evo HeadBox Instructions

## Print Files

```
HeadBoxA.stl
HeadBoxB.stl
HeadplateDynamixel.stl
NeckBottomDynamixel.stl
NeckTopDynamixel.stl
RubberGrommet.stl
TiltMountDynamixelUnified.stl
```

## Original Files

Use these files from MrBaddeley's original D-Ov2 OneDrive:

```
HeadBoxBar.stl
HeadGreeble.stl
HeadGreebleresin.stl
```

(`HeadGreebleresin.stl` is an optional variant of `HeadGreeble.stl`, don't need both.)

## Build Notes

We use a carbon tube (OD 15mm, ID 13mm, 1mm wall thickness) cut to 124mm length instead of the printed Barskin. It's lighter and very slightly more rigid. Not a big change so if you can't find one just use the original.

It's also a good idea to superglue the skin onto the bar after all the cabling has been done, again for extra rigidity. 

### Connectors

Servo mounts use M1.7x5mm self-tapping screws. You can use M2x5mm if you want but we find 1.7mm holds well. The head roll servo (the topmost one) connects to `HeadplateDynamixel.stl`, it is the only one that needs to be connected in the front and the back of the servo. For the back connection you need an idler, these come in Dynamixel's FPX330-H101 connector set.

### Orientation and supports

These parts are not oriented, your slicer's auto-orient feature will take care of that. No supports needed. **Exception:** `NeckTopDynamixel.stl` has a slightly recessed ring at the top that is not strictly needed but helps with registering the top servos to the bottom assembly. This doesn't come out properly if printed face down, so it's best to print with the two legs on the build plate and adding supports for the arc. 

### Material

Print these out of **LW-PLA** for weight reduction:

```
HeadBoxA.stl
HeadBoxB.stl
NeckBottomDynamixel.stl
```

Print these out of **ABS, ASA, or PLA+** for strength, but regular 2-wall profile works fine, strength profile with many walls would be too heavy:

```
HeadplateDynamixel.stl
HeadBoxBar.stl
NeckTopDynamixel.stl
TiltMountDynamixelUnified.stl
HeadGreeble.stl (or print HeadGreebleresin.stl out of resin)
```

Print this one out of **TPU** (black, paint tends to crack on TPU after a while due to its flexibility). We print this in 1-wall vase mode for weight reduction, which does cause problems with layer adhesion on our printers giving a bit of a "flayed" look. YMMV - try it out!

```
RubberGrommet.stl
```

