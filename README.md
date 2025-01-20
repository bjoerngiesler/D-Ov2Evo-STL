# D-Ov2Evo
Bavarian Builders: Felix Beyer, Björn Giesler

## This is an ADD-ON to Michael Baddeley's files!

This GitHub contains modified print files that are to be used as add-ons and partial replacements of Michael Baddeley's D-Ov2. This GitHub does not contain all the files to print a functional droid, you still need parts from [Michael's Patreon](https://www.patreon.com/c/mrbaddeley). We have Michael's express permission to post our modifications on GitHub to better handle file changes, upgrades etc., but will never post all files for a functional droid here.

## What is D-Ov2Evo?

D-Ov2Evo is an extension of Michael Baddeley’s great D-Ov2 design for the D-O Astromech Droid from The Rise of Skywalker. 

D-Ov2 in itself is an extension and improvement of Michael’s original D-Ov1 design. Where D-Ov1 had a central drive axis for the main wheels, D-Ov2 has an excentric Lazy Susan design, which allows fixing the wheels all around the body, giving tremendously higher stability and longevity. Where D-Ov1 had the main neck and head nod servos in the body, D-Ov2 has the head nod servo in the headbox, which greatly improves play in the head assembly.

D-Ov2Evo improves D-O in the following respects.

* All analog servos have been replaced by Dynamixel digital servos, which are serially controlled. This reduces servo play, jitter, and noise. It removes 3 out of 4 servo cables routed through the neck. It also allows much tighter control and diagnostics.
* The motors have been replaced by the same model fitted with quadrature encoders, allowing for individual wheel speed control as part of a more stable control concept. They are also actively cooled so they will never overheat.
* The whole droid is controlled by a central more powerful Arduino, and uses a modern IMU, for tighter control and the opportunity to run free head animation (e.g. turning/leaning the head automatically as the droid drives a curve).
* Power is provided by two easily removable 18650 battery packs, which yield a bit less runtime than the original LiPos but can be changed in seconds without disassembly (and are safer).
* The body takes 5W speakers instead of the original 3W ones, giving much louder sound for conventions.
* A central power supply and distribution board includes a fuse, a voltage monitor, and means much less cabling.
* The head has moving antennas run from their own microcontroller.
* The software is fully open source and published at https://github.com/bjoerngiesler/BBDroids. 

## How to Build!

**Note:** This is not a beginner project. You should have a well working printer, soldering experience, and understanding and alertness to question our instructions. We are not perfect, and there may be bugs.

You will find the print files for D-Ov2Evo in this directory and its subdirectories. The directory structure mirrors the original D-Ov2 directory structure. Each folder underneath here only contains our modified files, not copies of the original print files, so please use the D-Ov2 originals for everything not in here. Each folder also contains an Instructions file, that contains the list of original and modified files for the part, printing and materials advice, and some instructions on assembly.

You will find the systems and wiring diagram, the electronics BOM, and other documentation, in the BBDroids Wiki: https://github.com/bjoerngiesler/BBDroids/wiki/91-Individual-Droid:-D%E2%80%90Ov2Evo If something is not clear, please check the Wiki first, and if you still have questions there is a discussion board at https://github.com/bjoerngiesler/BBDroids/discussions that you can use for questions. Please search before you ask, maybe someone already answered your question!

**Note:** The head with the movable aerials is optional. It is fancy, and we will add more antenna animation as things progress; but it also adds quite some weight to the head and work and cost to your list. You can also simply build the head assembly from the original D-Ov2 plans, with static antennas. Print `HeadStaticAerialsDynamixelCutout.stl` instead of the original head cone, because the roll Dynamixel sticks out at the top and this one has a cutout for it.

## Work in Progress! (But almost done)

D-Ov2Evo has been in development for more than a year. It started with taking a lot of inspiration from Matt Denton’s Dynamixel/Lynxmotion modification of the original D-Ov1.

Over time, we learned, added and modified many things. Björn’s original D-Ov2Evo ran great at a convention for a day, and on the second day one motor burned up… we need active cooling. Getting the batteries out and back in is a huge hassle… we need to modify for removable batteries. The thing is much too silent… we need bigger speakers. You can’t get at the grub screws for the motor gears. The cabling is a mess. And so on and so on. 

We are actively stopping ourselves now from doing any more modifications, it’s time the thing gets tested by other people. But as we publish, we are building two droids as test kits, and making how-to videos. As this slowly progresses, we are going to publish the files to Michael Baddeley’s OneDrive, and we are also going to publish extensive (and hopefully correct :-)) videos that guide through physical build, electronics, control system tuning, and software.

Please bear with us, we’ll arrive at the head eventually.

If you have any questions or suggestions, you can find Felix and Björn in MrBaddeley’s Facebook group, please ping us there in posts or send us PMs.