# Report

| Verified by | Date |
|:------------|:-----|
|DL | 7 November |

## Speculation

> In your own words, describe what the 6522 tester code does.

The tester code writes values to the 6522’s registers and reads them back to make sure the chip is wired correctly. It checks that the CPU can communicate with the VIA and that the I/O ports and registers respond as expected.

> There are some addresses dedicated to using the interface. What are they and what do they seem to do?
> _HINT_: for this part, focus on the wiring of the _address bus lines_.

The 6522 is mapped to a small block of addresses. Within that block, the lowest address bits (A0–A3) select which internal register of the 6522 is being accessed. These addresses let the CPU read and write the VIA’s ports and control registers.

> Why is creating specific, separate addresses important to achieve this function?

Each device must have its own unique section of the memory map so only that device responds. Without separate addresses, multiple chips could activate at the same time, causing incorrect data or bus conflicts.

> What is the value of the interface module (i.e. what does it _do_)?

The 6522 provides input/output capabilities the CPU doesn’t have on its own. It gives the system programmable I/O ports, timers, and interrupt features, allowing the 6502 to interact with external devices.

