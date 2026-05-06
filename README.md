# DIY-mini-TDR
DIY Mini TDR – Time Domain Reflectometer

![image](https://github.com/nidalsaid04-ops/DIY-mini-TDR/blob/main/images/image.jpg)

### TDR (Time Domain Reflectometer) ?
TDR is An instrument that sends a signal down a transmission line and then analyzes the reflection. By measuring the reflection delay, the approximate cable length can be estimated and identify impedance mismatches, TDR systems can also be used to Find a cable fault underground ! Overhead, in the air, before you take it down! Is it damaged inside a wall? Has a staple penetrated it? Be the hero and go right to the trouble! 

### The goal of this project is :
make whether it is possible to build a low-cost  (TDR) using simple and the components that I have. 
While searching for a SCHMITT tringer, I found this to be my test gear. A searching through my electronics parts yielded SN74HCT14 hex inverter logic chips. They can be purchased new for 50 cents each if you must buy them :)
The first one sections form an oscillator with R1 and C1 setting the frequency to around 13KHz.This feeds five more sections to buffer and isolate the oscillator. Keeping the connections short and the components small allows the output rise times to be under 5 nanoseconds, faster than my 50 MHz oscilloscope can track.

### How build it:
The prototype was built on a small piece of copper-clad board slightly larger than the IC package and the BNC connector.
Pin 7 of the IC and the BNC ground connection were bent downward and soldered directly to the copper surface to create a solid ground plane and mechanically secure the components.
The BNC connector was mounted as close as possible to the IC in order to minimize lead inductance and transmission line discontinuities(you need to keep things very short).
However, the output impedance of the logic gate is not controlled. To better match the transmission line impedance, five inverter outputs were connected in parallel using 220 Ω series resistors to.
The equivalent output resistance is approximately:
Req ≈ 44 Ω
The battery can be just about anything you want to use from 2 to 5 volts. I just glued the board to the case. The circuit only draws 4 milliamps or so. Solder the negative of the supply to the ground pin. The positive of the supply goes to pin 14. Perhaps not necessary, but good practice, is to solder a .1 microfarad capacitor from pin 14 to ground as a bypass for the power.

![image](https://github.com/nidalsaid04-ops/DIY-mini-TDR/blob/main/images/Figure_1.jpg)
