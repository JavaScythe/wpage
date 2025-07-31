Total project time: 6 hours

7-29-25: Nothing 2 something

The entire creation of this project took place from about 10PM to 4AM. Prime time.

I started with what I had. ESP01, haptic, decent salvaged LiPo. 

I started to test putting the 3.7v on the ESP01. I held the wires against the battery but it was just too cumbersome to hold them on.

The clear next step would be attempt to solder some wires on the terminals of the battery (flat, copper). Despite excessive flux and flawless soldering skills it would simply not stick. The brilliant solution? Hold the wires on the battery with clay.

After applying 3.7V to the esp01 for a bit and seeing no light, I picked it up and was immediately informed of the esp's intolerance of such voltage because it was far too hot.

Good. A simple AMS1117 breakout solved this. While not perfect solution, I didn't measure voltage but it works. Amazing. Also provides a great indicator that it's on.

Unfortunately ESP01s, with their 2x3 pinout, don't work on breadboards.

Now I made the NPN to drive the motor. Seeing as either an NPN or MOSFET had been on almost all of my latest board this was quick work. No low ohm resistor? No problem. I'm using 4x 220ohms in parallel, so about 55 ohm resistance on gate pin. This is low enough to allow the weak ESP01 to saturate it.

Here's a schematic of the completed build

<img width="1734" height="935" alt="image" src="https://github.com/user-attachments/assets/265c50aa-22a3-4dbb-bd6f-8decb52243c5" />

A quick sketch to cycle IO0 0-255 verified the working of the amplifier and motor.

I then expanded the skwtch to include wifi, connect to wifi, and start TCP server to recieve bytes to directly feed to PWM motor control.

A nodejs script fed these bytes, either generated timely from itself, or from external trigger, over LAN and to the device.

<img width="786" height="623" alt="image" src="https://github.com/user-attachments/assets/2ed1bfb3-3920-489d-b3e4-663dafc949a7" />

That's all for this build.

6 hours
