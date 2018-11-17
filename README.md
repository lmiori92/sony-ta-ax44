# sony-ta-ax44
Retrieve the magic bits from the ancient NEC 4-bit MCUs

# Introduction

Information on D553C dumps and a dump rig can be found here: http://blog.kevtris.org/blogfiles/Handhelds/

Information on how the factory test mode roughly works: http://www.handheldmuseum.com/forum/viewtopic.php?p=11039&sid=d6908cd18eb085e3694a217f15b6a7e4#11039

Additionally, I have contact the author of the above sites to get some information about power supply. So, I would like to thank him too.

# Assumptions and definitions

The D553C is a P-MOS device requiring negative supply. We won't use any negative supply, we just feed the +10V at pin 21 and GND at pin 41.

The microcontroller that is going to run the factory test will instead be feed by the same power rail, just normally and regulated down to +5V.

All voltages are referring to these voltages i.e. not the inverted ones!

# Factory Test Mode

The Factory Test Mode is enabled when pin TEST is at 0V; it is disabled i.e. normal operation if the pin is at +10V.

Data ports C (low-nibble) and D (high-nibble) are used to transfer the ROM bytes to the dumping microcontroller (it is not known if this port can be also used for more factory testing functionalities e.g. RAM check or so.
They switch to 0V when "high".
