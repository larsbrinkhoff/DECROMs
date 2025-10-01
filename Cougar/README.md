## About the Cougar firmware

Cougar was the nickname of the [VAXStation
4000/9x](https://www.netbsd.org/docs/Hardware/Machines/DEC/vax/vaxstations.html#vaxstations:vaxstation_4000_m90)
series, the fastest VAX desktop models available with a KA49(A) CPU.

The Cougar models didn't have EPROMs to store firmware anymore. DEC
used EEPROMs instead and enabled firmware update either from the
charon `>>>` prompt or while running VMS. It was even possible to
download firmware via network.


### Directory contents

This directory contains

- the original `readme.txt` from the firmware update package
- the original `VS4000.doc` file describing the firmware update procedure
- v1.3 sub-directory - firmware version 1.3
- v1.4 sub-directory - firmware version 1.4
- this README

### How to extract the firmware

The `.sys` files in the v1.3 and v1.4 subdirs are executables to be
run in VMS.
Extracting the "pure" firmware binary can be accomplished as follows:

For the `cougar.sys` files:

> dd if=cougar.sys of=BIOS.BIN skip=15 bs=512

For the `cougar_dsk.sys` files:

> dd if=cougar_dsk.sys of=BIOS.BIN skip=14 bs=512

As most other VAX firmware, the binaries originate at 0x20040000 (in
case you want to disassemble them).
