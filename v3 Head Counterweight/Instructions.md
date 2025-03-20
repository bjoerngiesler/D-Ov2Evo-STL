# Why is a head counterweight significant?

In the original D-O files developed by Michael, the head weight is not balanced by its own counterweight. This means that every head motion changes the body weight distribution, especially if the neck tilts moving the head forward or backward. This causes the body to pitch forward or backward, influencing the body balance controller that is trying its very best to keep the body in equilibrium. Essentially this means that as you bring the head forward, the body pitches forward and starts to drive forward as the controller tries to compensate for that pitch. Not only the neck servo goes into this equation, but also the head motion on the neck itself. This makes the effect hard to compensate by software unless you know the exact weight distribution of all head and neck components and also the speed they are moving at and the torque their motors are enacting on the system.

These effects are the main reason why it is a very good idea to reduce head weight to an absolute minimum, but if we want to have movable aerials in the head for example there are limits to the weight reduction. Adding a counterweight to the head itself helps tremendously to decouple head from body motion, allowing for much more freedom in head materials and actuators.

The counterweight that James designed can add around 1kg of weight to balance out the head weight. Since the head lever is much longer, that additional kg is needed even though the head itself is only about 300g.

# Will the non-counterweight version be supported?

Only with static aerials unfortunately. If you know what you are doing you can certainly get a heavier head to control, all the parameters are there and an article describing how they interact is coming. But it is not easy to remove all residual drift, and remotely supporting this is far beyond the amount of time we can invest. We therefore heavily recommend making this change, even if it needs reprints.

# What do I need to change?

Unfortunately this requires a number of reprints - but it's really worth it!

You need a new main frame and top frame to make room for the counterweight, a new main axle to attach the counterweight to, and of course the counterweight pendulum itself. There is a new servo mount and servo main gear. There is also a new PCB base for the main board (which brings additional advantages and tweaks - e.g. you can now remove the PCB base and main board without unscrewing the top frame). You can find these files here: https://github.com/.../tree/main/v3%20Head%20Counterweight. The pendulum can be printed in one part, there is also a cut version that should be glued together with CA glue.

After printing, fill the main frame with 1-1.5kg of ballast and pour with epoxy. Fill the pendulum up to the brim with ballast, you should be able to get just short of 1kg of weight in there if you use lead. Make sure all the nooks and crannies are filled by shaking and pushing from the top. Epoxy is optional here, because the main bar will hold the ballast in place. If you want you can also fill the main bar with ballast, this is optional as it doesn't contribute a lot. The counterweight does not need to be exact - as you see from the video with just head and counterweight outside the body, the balance is not perfect with mine and it doesn't need to be; we still have the body counterweight and friction in the servo to take care of the delta. But it is a good idea to at least roughly try to assemble head,

Add square nuts to all the holes in main frame, top frame and pendulum, and secure with hot glue.

Set the pendulum aside, assemble servo and servo base, insert into main frame. Make sure the servo gear is at zero before you proceed.

Add the main bar and side panels with the large bearings. Now put the pendulum underneath the main bar into the cutout in the main frame and screw it on.

Add the top frame with power board and the PCB base with main board and cable everything up.
