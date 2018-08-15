## [Purchase self-assembly kit](https://www.tindie.com/products/nerfhammer/hearty-badge-self-assembly-kit/).

## [Purchase pretty backlit badge (assembled)](https://www.tindie.com/products/nerfhammer/hearty-backlit-badge/).

# Materials

* 5mm LED
* 2n3904 BJT transitor, TO-92 package
* 1µF capacitor
* 100kΩ resistor
* Spring switch
* Coin cell battery

# Circuit

![alt text](https://github.com/grandinquisitor/lionheart/raw/master/src/trans_schematic.png)

When the spring switch is jangled, it charges up the capacitor, which slowly drains out through the transistor, lighting the LED. The capacitor's discharge curve give the LED a nice organic-looking fadeout effect.

This is essentially a switch controlled by an [RC filter](https://en.wikipedia.org/wiki/RC_circuit).

# Alternate designs

## Capacitor-only design

In this design, not even a transistor needs to be used!

In theory, C1 is not necessary, however, the coin cell battery power source has a high internal resistance, which means it is not able to charge up C2 quickly. With C1 in the circuit, the battery just keeps C1 charged up, and when the switch makes contact C1 quickly vents all of its current to C2.

The drawback to this design is the need for large capacitors. The capacitor needs to hold the entire current to keep the LED lit. With a transistor design only a tiny capacitor need be used as it only needs to hold enough current to keep the transistor active.

![alt text](https://github.com/grandinquisitor/lionheart/raw/master/src/cap_schematic.png)

## FET design

In this design, a mosfet is used instead of a BJT transistor.

This can potentially make the LED brighter since mosfets have a very low voltage drop, and can be kept switched on for a very long period of time depending on the values of C1 and R1.

R1 functions as both a bleeder for the capacitor and a pulldown for the mosfet gate.

This circuit assumes a coin cell battery is used as the power source. If lower resistance power source is used, a gate resistor should be added in series to the mosfet and a current limiting resistor should be added in series with the LED.


![alt text](https://github.com/grandinquisitor/lionheart/raw/master/src/fet_schematic.png)
