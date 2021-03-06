The Homebrew Launcher has many different entrypoints, or methods of launching. The most common is browserhax, which launches the Homebrew Launcher using nothing more than the included browser. This can then be used to install menuhax, which lets you hold a button while the console is booting up to launch the Homebrew Launcher before the rest of the system starts.

If you are between versions 9.0.0 and 9.8.0, you should follow this guide, but you can skip changing the date and time and initializing savedata in the beginning.

If you are between versions 9.9.0 and 10.5.0, you should follow this guide as written.

If you are between versions 10.6.0 and 11.0.0, or have a browser version (the last number in the version, such as 11.0.0**-33**) of less than **-20**, you must use the following instructions for various alternate entrypoints *in place of* Part 1    
+ [Ninjhax](http://smealum.github.io/ninjhax2/) (requires Cubic Ninja)    
+ [smashbroshax](https://gbatemp.net/threads/397194/) (requires Super Smash Bros. and **only works on New 3DS**) 
+ [oot3dhax](https://github.com/yellows8/oot3dhax) (requires Ocarina of Time 3D and either a powersaves or another 3DS which has the HomeBrew Launcher)       
+ [supermysterychunkhax](https://smd.salthax.org/) (requires Pokemon Super Mystery Dungeon and another 3DS which has the HomeBrew Launcher)
+ [freakyhax](http://plutooo.github.io/freakyhax/) (requires Freakyforms Deluxe)
+ [basehaxx](http://mrnbayoh.github.io/basehaxx/) (requires Pokemon Omega Ruby/Alpha Sapphire ver 1.0/1.4 with the ability to have a secret base and another 3DS which has the HomeBrew Launcher)

**If you are on version 11.0.0, you MUST have used a hardmod downgrade to successfully complete Part 2 later.**

Browserhax and menuhax were patched with 10.6.0 and will no longer work.

If you are below version 9.0.0, you can find instructions for updating to 9.2.0-20 [here](https://github.com/Plailect/Guide/wiki/9.2.0-Update). Browserhax does not support versions below 9.0.0.

If you are using a game for hacks, you will need to enter HomeBrew Launcher using it instead of browserhax or menuhax while on 10.6.0/10.7.0. After completing the initial 9.2.0 downgrade, you no longer need the game to complete the rest of the guide.

#### Overview of steps

This section will take you through the steps of downloading [smea](https://github.com/smealum)'s Homebrew Starter Pack which includes the necessary file to run the Homebrew Launcher (`boot.3dsx`) along with some other useful utilities (the apps in `/3ds/`).

All \*hax variety entrypoints (which are the most commonly used entrypoints such as Ninjhax, oot3dhax, menuhax, and browserhax), after setting up their exploit code, launch a file named `boot.3dsx`, which is the Homebrew Launcher in this case. The file itself can be any valid `.3dsx` homebrew, but the Homebrew Launcher is prefered because it lets us launch *other* homebrew once it's running.

This guide uses browserhax, which runs the homebrew launcher through an exploit site, to install menuhax, which is an exploited theme that can run the Homebrew Launcher at boot. Both of these exploits were patched in 10.6.0, and as a result if you are using 10.6.0 or higher, you will need one of the alternate entrypoints described at the top.

All versions above 9.9.0 include a browser version check that will not allow you to go to any sites if you are not on the latest system version, which means you'd normally have to update to the latest to run browserhax, but that would result in patching out browserhax.

The [workaround](https://yls8.mtheall.com/3dsbrowserhax.php) for this, discovered by [yellows8](https://github.com/yellows8), is to change the clock to the date detailed below, then initialize the savedata quickly (*before* the 3DS connects to Nintendo to verify browser version). At this point, you can continue to use the browser normally until the clock hits one day later or you exit the browser using the home button.

Following this, we setup menuhax (a custom exploit theme) to launch `boot.3dsx` (in this case the Homebrew Launcher) when we hold D-Pad Down on boot.

#### What you need

+ The Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
+ An internet connection setup on your 3DS

#### Instructions

1. Copy the contents of the `starter` folder in `starter.zip` to the root of your SD card, then put the SD card back into your 3DS
2. Open the theme menu, change your theme to any other theme, then switch back. This will initialize the theme data and is required
3. Launch the Settings application
4. Change the date to `January 1, 2000`
5. Change the time to `00:00`
6. Launch the browser, then open the browser settings as fast as possible
7. Scroll to the bottom and Initialize Savedata (it also may be called Clear All Save Data) as fast as possible
8. Navigate to `http://yls8.mtheall.com/3dsbrowserhax_auto.php` or scan the QR code on your 3DS (if you get a slider, zoom all the way in on it, then tap the very right edge of it; this can take quite a few tries)    
![browserhax_auto](https://yls8.mtheall.com/3dsbrowserhax_auto_qrcode.png)
9. Your console should load the homebrew menu
10. Open the menuhax_manager application
11. Press A to install, it may show some errors but that's fine as long as it shows "Success" towards the end
12. Go back to the main menuhax_manager menu, then select "Configure/check haxx trigger..."
13. Press A to continue, then select "Type1"
14. Hold down on the D-Pad, then tap the touch screen; this is the recommended button to use for launching menuhax in this guide because it does not interfere with any other functions of tools we will be using
15. Go back to the main menuhax_manager menu, then press B, followed by Start to exit back into the Homebrew Launcher
16. Use the Start button to reboot
17. You can now hold D-Pad down while the system is booting to launch the Homebrew Launcher
