# DIY-mini-TDR
DIY Mini TDR – Time Domain Reflectometer

![image](https://github.com/nidalsaid04-ops/DIY-mini-TDR/blob/main/images/image.jpg)

### TDR (Time Domain Reflectometer) ?
TDR is An instrument that sends a signal down a transmission line and then analyzes the reflection. By measuring the reflection delay, the approximate cable length can be estimated and identify impedance mismatches, TDR systems can also be used to Find a cable fault underground ! Overhead, in the air, before you take it down! Is it damaged inside a wall? Has a staple penetrated it? Be the hero and go right to the trouble! 

### The goal of this project is :
The goal of this project is to explore whether it is possible to build a low-cost TDR using simple components and basic laboratory tools.
While searching for a SCHMITT tringer, I found this to be my test gear. A after searching through my electronics parts inventory, I found several SN74HCT14 hex inverter logic ICs. They can be purchased new for 50 cents each if you must buy them :)
The first inverter sections form an oscillator with R1 and C1 setting the frequency to around 13KHz.This feeds five more sections to buffer and isolate the oscillator. Keeping the connections short and the components small allows the output rise times to be under 5 nanoseconds, faster than my 50 MHz oscilloscope can track.

### How build it:
The prototype was built on a small piece of copper-clad board slightly larger than the IC package and the BNC connector.
Pin 7 of the IC and the BNC ground connection were bent downward and soldered directly to the copper surface to create a solid ground plane and mechanically secure the components.
The BNC connector was mounted as close as possible to the IC in order to minimize lead inductance and transmission line discontinuities(you need to keep things very short).
The output from terminal 3 was then distributed to the remaining five inverter gates.Terminals 5, 9, 11, and 13 were connected directly to terminal 3.
Each of these inverter gate outputs - pins 4, 6, 8, 10 and 12 - is connected to a common output node through individual 220 Ω series resistors.
However, the output impedance of the logic gate is not controlled. To better match the transmission line impedance, five inverter outputs were connected in parallel using 220 Ω series resistors to.
The equivalent output resistance is approximately:
Req ≈ 44 Ω
The battery can be just about anything you want to use from 2 to 5 volts. I just glued the board to the case. The circuit only draws 4 milliamps or so. Solder the negative of the supply to the ground pin. The positive of the supply goes to pin 14. Perhaps not necessary, but good practice, is to solder a 1 microfarad capacitor from pin 14 to ground as a bypass for the power.

![image](https://github.com/nidalsaid04-ops/DIY-mini-TDR/blob/main/images/Figure_1.jpg)


### Basic TDR Principle
The mathematical foundation of TDR measurements is elementary but important.TDR measurements are primarily based on the integration delay of the reflected waveform.
Most TDR meters will perform the necessary calculations internally and display a numerical result.
The cable length can be estimated using:

$$
L = \frac{\Delta t \cdot c \cdot VF}{2}
$$

Where :
  - L = cable length
  - Δt = round-trip propagation delay
  - c = speed of light typically 0.2998m/ns
  - VF = velocity factor of the cable

The division by 2 is required because the signal travels to the end of the cable and then reflects back toward the source. Typical velocity factor values:
- Coaxial cable: 66% to 85%
- Twisted pair cable: 64% to 74%
### The Reflection Coefficient 
TDR measurements are described in terms of a Reflection Coefficient, ρ (rho). The coefficient ρ is the ratio of the reflected pulse amplitude to the incident pulse amplitude:

$$
\rho = {V_{reflected} \over V_{incident}}
$$

For a fixed termination ZL, ρ can also be expressed in terms of the transmission line characteristic impedance, ZO and the load impedance ZL.


$$
\rho = {Z_L - Z_0 \over Z_L + Z_0}
$$

Now that we have the formulas, we can see that when we input the numbers that represent the identical load, the short circuit, and the open load, we can see that ρ has a range of values ​​from +1 to -1, where 0 represents the matched impedance.

Where : 
  - ρ is 0 the load is matched. There are no reflections. 
  - ρ is +1 is infinite, an open circuit is implied. the reflected wave adds constructively to the incident wave.
  - ρ is -1 implies a short circuit. the reflected wave is inverted relative to the incident wave.

Calculating the Impedance of the Transmission Line and the Load The characteristic impedance Z0, or the load impedance ZL, can be calculated with the value of ρ :

$$
Z_L = Z_0 \cdot {1+\rho \over 1-\rho}
$$

## Experimental Results

> [!NOTE]
> Due to limited available equipment, testing was performed using a short 60 cm BNC-to-SMA coaxial cable.  
> Although the cable length is relatively short for traditional TDR applications, it is still sufficient to demonstrate:
>
> - Transmission line reflections
> - Impedance mismatch behavior
> - Open-circuit and short-circuit reflections
> - Basic propagation delay effects
>
> The primary purpose of this setup is educational experimentation and validation of the TDR operating principle rather than precise long-distance cable fault measurement.

