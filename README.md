SPI65
=====

This is a fork of André Fachat's SPI65/B (http://www.6502.org/users/andre/spi65b/index.html).
It has been slightly modified for my COLE-2 65816 SBC.

This version contains the following differences from SPI65/B:

- I removed the multiple MISO input as I didn't need them
- The clock divisor is 4 bits again as I was able to fit it again
- The /IRQ output is is now a totem pole output instead of open collector, so that I
  didn't have to add another pullup resistor to my design
- The VHDL code uses PHI2 directly instead of an inverted copy. This should not have
  made any difference, but without these I could not reliably read or write to the chip.
- The pins have been rearranged, in order to make it easier wire it up in place of
  the second VIA on my breadboard prototype build.

I have successfully built and programmed this design into a Xilinx XC9572XL and used
it to communicate with an ATmega328p acting as an SPI slave.
