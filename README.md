DC20Badge_PV
============

Hacked together by Raiford, KC and some minor input from me.



Defcon 20 Badge IR Solutions 
============

For the Defcon 20 Badge there are a series of IR codes sent via the sircs 
protocol.

I archived and included the badge libraries required incase it's five years
from now and nobody can find the deps.

We hacked together the following files (based on Kyle Cs derivative of the 
included light_example.spin)

In order to figure out the badge codes we had to sniff them out of the air, 
so we hacked together a sniffer:

The IR Sniffer
============
It's pretty much what it says, it reads inputs from the sircs_rx obj and 
outputs it to a serial console @ 57600 baud.

irsniff.spin


The Badge Spoofer
============
Once we knew what the badge codes were, we created an irspoofer that spammed
the codes.  (And mainly just spammed uber everywhere, and eventually 1057)
This is the iteration that randomly selects a badge code (displays the last 8
bits of the code on the LED) and spams the ir for it.  With this, and two badges
you could unlock all the standard codes pretty easily.

irspoof.spin

The Persistent Vision version
============
Inspired by Kyle C @ BsidesLV, Each badge type outputs a PV set consistent with
their type.  It also includes a dat section with the 26 alphabetic values and a pad
value to space the text:

irspoof.PV.spin 

As R figured out the serial.tx function is blocking in this instance, and should be 
done via a cog, but it worked enough to let the team figure out the pattern.

All testing/coding/compiling was done via Linux (Debian based) systems 
using propgcc (code.google.com/p/propgcc)

Big thanks to 1o57 for getting us antisocial folks to talk to each other and 
collaborate on such an awesome little piece of hardware.  Many thanks to all 
involved, you made it an incredible Con this year.

If you have any questions re: hacking the badge in linux email me:
mycroft.tovarish@gmail.com