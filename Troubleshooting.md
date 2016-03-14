If you are unable to boot your 3DS, please look for the section relevant to you, and follow the instructions. Once a solution works for you, you can proceed on with the main guide.

#### Black screen on EmuNAND boot

1. Restore a backup to EmuNAND. *(You should have one of these)*

#### <a name="ts_sys_down" />Black screen on SysNAND boot upon downgrading

1. Try booting with your SD card out, and then reinserting it after booting.
   1. Power off your 3DS by holding down the power button.
   2. Take out the SD card.
   3. Power on the 3DS.
   4. When the home menu appears, reinsert your SD card.
   5. You may consider running a downgrade checker to see if you have a partial downgrade.
2. If you have a hardmod and a NAND backup, flash the backup back to SysNAND.
3. Try booting into recovery mode and updating your system.    
   *This probably will not work for an Old 3DS downgraded to 2.1.0*    
   **This will BRICK a New 3DS downgraded to 2.1.0**
   1. Power off your 3DS by holding down the power button.
   2. Hold L+R+A+Up.
   3. Power on the 3DS.
   4. If you enter safe mode, update your 3DS **only if you have an entrypoint for the latest FW version and it is possible to downgrade from it** and attempt the downgrade again.
4. Your 3DS may be bricked. For real time support, contact me or any other channel operator at [#3dshacks on Rizon IRC](https://qchat.rizon.net/?channels=3dshacks&uio=d4).

#### <a name="ts_sys_a9lh" />Black screen on SysNAND boot upon installing arm9loaderhax

1. Ensure you have a working payload.
   1. Check for the existence of `arm9loaderhax.bin` in the root of your SD card.
   2. If you are following the AuReiNand guide, check that
      1. `/rei/updatedsysnand` and `/rei/firmware.bin` exist; and
      2. `/rei/firmware.bin` is the correct one for your console.
   3. If you are following the CakesFW guide, check that
      1. `/arm9bootloader.bin` exists;
      2. `/Cakes/firmware.bin` and `/Cakes/firmkey.bin` exist and are the correct ones for your console; and
      3. `/boot_config.ini` exists.
2. Try [this test payload](https://gbatemp.net/attachments/arm9loaderhax-7z.39669/).
   1. Rename `/arm9loaderhax.bin`, if it exists, to something else.
   2. Place the `arm9loaderhax.bin` from the archive linked above in your SD root.
   3. Insert your SD card into your 3DS and power on.
   4. Press A. Your 3DS should power off; this means arm9loaderhax is working and something else is broken; your device is **not** bricked.
3. Your 3DS may be bricked. For real time support, contact me or any other channel operator at [#3dshacks on Rizon IRC](https://qchat.rizon.net/?channels=3dshacks&uio=d4).

#### <a name="ts_sys_blue" />Blue screen on boot (bootrom error)

1. Your 3DS is bricked.
2. You will need to get a [hardmod](https://gbatemp.net/threads/414498/) or repair / replace the device.