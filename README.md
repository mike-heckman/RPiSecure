
Welcome!

This board is designed to "glue" parts to a Raspberry Pi for an RFID door lock.

It attaches on top of the the Pi using the stacking header and uses an L293D
half-H motor driver and an MCP23017 digital IO expander so the other (optional)
components don't take up all the Raspbery Pi's GPIO pins.

If the board is fully populated, it provides the following:

   Two bi-directional motor drivers with either coupled or independent power.
   Connections for two switches, intended for door position (hall-effect sensor) and deadbolt position (tactile momentary switch depressed by the deadbolt).
   Connections for one or two DHT-22 temperature and humidity sensors.
   Connections for up to four LEDs (one is hardwired for power, the other three are on IO ports).
   A connection for a speaker.
   8 additional IO ports addressed through the MCP23017.

The board is designed to use the minimum number of pins on the Raspberry Pi.
To use the second motor driver you have to jumper the MTR2 pins, or tie them
to other pins on the Raspberry Pi breakout.

Also the INTB pins can be jumpered if you want interrupt access to the second
bank of GPIO on the MCP23017 - you don't have to unless you want the interrupt
to go to GPIO pin 4.

You also need to set three jumpers for the MCP23017 3 low id bits.

The board intentionally doesn't draw power from the Pi as it will be powered by
DC/DC power converters from a common 12v source.  There's a pin header near the
upper left corner that provides a +5V and GND power to optionally power the Pi.

The board should work for either the model B or B+ Raspberry Pis.

Datasheets are available for most parts:

L293D Motor Driver:  http://www.farnell.com/datasheets/1804890.pdf
MCP21037 Digital IO: http://www.farnell.com/datasheets/12179.pdf

Standard Traces are 10 mil with 12 mil isolation, the traces for the motor
power in out and to the L293D are larger as it can switch motors up to 36V.
The top and bottom ground planes have been maximized around the chips to allow
them to sink heat into the board.
