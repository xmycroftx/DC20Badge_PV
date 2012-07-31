DC20Badge_PV
============

Defcon 20 Badge Spin Files For Persistent Vision (Parallax processor)
============

For the Defcon 20 Badge there are a series of IR codes sent via the sircs 
protocol.

I archived and included the badge libraries required incase it's five years
from now and nobody can find the deps.

We hacked together the following files (based on Kyle C and the included 
light_example.spin)

irspoof.pv.spin
irspoof.spin

In order to figure out the badge codes we had to sniff them out of the air, 
so we hacked together a sniffer:

irsniff.spin

As R figured out the serial.tx function is blocking in this instance, and should be 
done via a cog, but it worked enough to let the team figure out the pattern.

All testing/coding/compiling was done via Linux (Debian based) systems 
using propgcc (code.google.com/p/propgcc)

Many thanks to all involved, it was a great Con this year.
