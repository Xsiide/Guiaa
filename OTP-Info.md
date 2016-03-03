*These links are here for anyone who is not following the main guide or was redirected from the old OTP guide.*

New 3DS | Old 3DS / 2DS
:---: | :---:
[With Cubic Ninja](https://github.com/Plailect/plailect.github.io/wiki/OTP-(With-Cubic-Ninja-on-New-3DS)) | [With Cubic Ninja](https://github.com/Plailect/plailect.github.io/wiki/OTP-(With-Cubic-Ninja-on-Old-3DS---2DS))
[Without Cubic Ninja](https://github.com/Plailect/plailect.github.io/wiki/OTP-(Without-Cubic-Ninja-on-New-3DS)) | [Without Cubic Ninja](https://github.com/Plailect/plailect.github.io/wiki/OTP-(Without-Cubic-Ninja-on-Old-3DS-or-2DS))

The OTP is a 0x100 byte region of seemingly random data at address 0x10012000. It is presumed that console unique keys are derived from this region, although it is currently unknown exactly how. The region is likely the console unique data store which is decrypted by the bootrom, but we don't know how that is done until somebody dumps the full protected bootrom. It is unknown at this time if anyone has successfully dumped the protected bootrom.

Prior to version 3.0.0-X, Nintendo locked access to this region using Kernel9, presumably under the assumption that an attacker would never gain access to arm9 userland (as arm9 kernel and userland are functionally identical thanks to svc 0x7B).

After version 3.0.0-X, Nintendo switched to locking this region using the register CFG_SYSPROT9, which also locks the bootloader and is set extremely early in boot, long before we are able to gain code execution. This register can be set exactly once, and cannot be switched off until the unit is fully powered off, and therefore it is impossible to dump the full OTP without a version 2.1.0-X or below.

There is, however, a method to dump the hash of the OTP on version 9.6.0-X. Because Kernel9Loader does not clear the SHA_HASH register after it has been used, dumping the SHA_HASH will give the hash of the OTP which was handed over to Kernel9 from Kernel9Loader. In addition, there is a long standing vulnerability where an MCU reboot caused by the i2c will not clear RAM like it's supposed to.

This allows for a hardware based attack where arbitrary data is written to nand_sector96+0x10 in a sysNAND backup and flashed to the device. Afterwards we wire the i2c to MCU reboot on our command, write a payload (which will write 0x1000A040 - 0x1000A060 to a file on the SD card) to arm9 memory somewhere, fill all memory with a NOP sled followed by a JMP instruction pointing to the payload. We can then MCU reboot repeatedly (incrementing nand_sector96+0x10 by 1 each time) until the Kernel9Loader jumps to the payload by random chance.

Because of the complexity and extra hardware involved in the method described above, I have decided to limit the scope of this guide strictly to the software based approach of downgrading to a version below 3.0.0-X. Version 2.1.0-X was selected because it is the only version below 3.0.0-X that contains a fully exploitable browser version (2.0.0-X has a partially exploitable browser, but it won't work for other reasons).

This guide will take you through the process of downgrading you emuNAND to 2.1.0-X to ensure you do not get a partial downgrade (which is when some titles are on one version and others are on a different version) which are difficult to recover from. On the New 3DS you must then decrypt with your console's 0x5 xorpad (which is New 3DS only) and then reencrypt with your console's 0x4 xorpad. Afterwards you overwrite the New 3DS's NAND NCSD (the header that specifies each partition's location) with the NCSD from an Old 3DS and flash the emuNAND to sysNAND. These steps are unneeded on an Old 3DS.