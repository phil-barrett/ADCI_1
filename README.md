# THC ADCI_1

THC ADCI_1 is an isolated Analog to Digital converter for CNC Plasma CNC designs to implement Torch Height Control (THC) in grblHAL.  It uses the standard grblHAL I2C interface available on a number of breakout boards.

Technical specifications.

* Digital Interface: I2C
* Bit resolution: 12 Bit
* Channels: 1
* Isolated power input: 8-24VDC
* Arc voltage divider
  - On board lower divider resistor: 4.7K
  - User supplied upper divider resistor (see below).

## External Resistor
ADCI_1 uses a voltage divider to drop the Plasma Cutter's Arc Voltage output to a usable level.  This uses 2 resistors.  One, the lower resistor, is on the ADCI board and the other, the upper resistor, must be supplied by the user.  This allows support any Arc Voltage value. The user supplied resistor should be in series with the signal cable running from the Plasma Cutter to the ADCI board. It should be outside the electronics box where the ADCI is mounted so that high voltage does not enter.  To find the right value of the user supplied resistor, refer to the following table or use the formula after the table.

| Arc Voltage | Resistor Value | Resistor Wattage |
|---|---|---|
|100V|183.3K|1/2W|
|50V|89.3K|1/2W|
|20V|32.9K|1/2W|
|10V|14.1K|1/2W|
|5V|4.7K|1/2W|

R_value = 10000 * ( Arc_V / 2.5) - 1)
>
Where Arc_V is the arc voltage value output by the Plasma Cutter.
###
The resistor power rating should be 1/2W.
