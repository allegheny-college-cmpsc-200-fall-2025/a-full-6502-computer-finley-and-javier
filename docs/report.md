# Report

| Verified by | Date |
|:------------|:-----|
|DL | 7 November |

## Speculation

> In your own words, describe what the 6522 tester code does.

It checks that the 6502 can talk to the 6522 by writing to its registers and reading the values back.

> There are some addresses dedicated to using the interface. What are they and what do they seem to do?
> _HINT_: for this part, focus on the wiring of the _address bus lines_.

The 6522 uses addresses $6000–$600F, where A0–A3 pick which register inside the chip you’re using. These addresses let the CPU read and write the VIA’s ports.

> Why is creating specific, separate addresses important to achieve this function?

So only the 6522 responds in that range. This prevents other chips from interfering or trying to use the bus at the same time.

> What is the value of the interface module (i.e. what does it _do_)?

It gives the 6502 I/O abilities—letting it control ports, read inputs, and use timers.

