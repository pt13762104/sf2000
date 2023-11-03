# Firmware/BIOS (bisrv.asd)
The firmware for the SF2000 is actually located on the microSD card, in a file called `bisrv.asd` located in the `bios` folder. This file is a monolithic binary blob, which contains the device's OS, the emulators, their settings... basically everything. Data Frog have issued some firmware updates for the device since launch; the updates have added new features (e.g., additional language support, favourites, history, etc.), but have also occasionally introduced bugs (e.g., some SNES games run very slowly until they are quit and launched again, etc.). Data Frog have published a YouTube video showing how to update the firmware on the device, which [you can find here](https://www.youtube.com/watch?v=j8dT2fdGfck); the video's description contains a link to where you can download the latest firmware. Note that Data Frog's official firmware update/reinstallation process involves fully erasing the device's microSD card and replacing its contents with a fresh set of files - this will also erase any user-created files including saves states or user-installed ROMs. You can learn more about save state files and how to back them up in [the Save States section](emulators.md#save-states).

Note that Data Frog's official server for downloading firmware is _very_ slow, with typical transfers taking many hours to complete as their firmware images are full images including ROM files. If you don't care about the stock ROM files, an alternative method for downloading the latest firmware _without_ the ROM files is to use [Tadpole](https://github.com/EricGoldsteinNz/tadpole). Refer to Tadpole's documentation for more information.

Known firmware versions are currently (dates approximate):

| Date | Version | Notes |
| ---- | ------- | ----- |
| Mid-March | ? | The original firmware that shipped with the first batch of devices |
| April 20th | ? | The first official firmware update; fixed some button mappings for Genesis, added support for 15 new languages. Also partially broke SNES compatibility - many SNES games will run very slowly on first launch, but quitting and immediately re-launching the game will have it run at normal speed (normal for the SF2000, anyway) |
| May 15th | ? | Added a built-in UI for global button mapping (which is broken in several ways, mainly SNES and Genesis controls are swapped, and no support for setting Player 2 controls), added a History feature, added a Favourites feature |
| May 22nd | 1.5 | First firmware with an official version number. Fixed the SNES/Genesis swapped button mappings, and now sets Player 2 controls to be identical to Player 1 (no way to set independently). There's some evidence of undocumented emulation improvements; some GBA homebrew that was non-functional in previous firmwares now loads correctly, and some GBA titles see marginally improved performance |
| August 3rd | 1.6 | The only official release note indicates that the issue with low sound volume when using A/V out was fixed. Aside from that, community members have noticed that the inability of the SF2000 to work with in-game saves appears to have been fixed for GBA (but not other emulators), and that the CPU clock has been changed from 810 MHz to 918 MHz (an overclock); this may be responsible for some community reports of slightly better performance for some games |
| October 7th | 1.7 | The [SNES first-launch speed bug](../faq.md#snes-games-run-really-slowly-whats-wrong) was fixed, however there is a new critical bug in SNES save-states - they're not created correctly, and attempting to load one created with this firmware version hangs the device. DO NOT USE THIS FIRMWARE VERSION! |
| October 13th | 1.71 | This is a bugfix release - the bug with SNES save states introduced in 1.7 was fixed, so this firmware appears to be stable again. Analysis shows no other significant changes from 1.7 |

If you want to check which version of the firmware you currently have on your SF2000, you can [use the Data Frog SF2000 Firmware Version Checker tool here](https://vonmillhausen.github.io/sf2000/tools/firmwareVersionChecker.htm).

Custom firmware (CFW) is currently in the very early stages of development (see [here](../faq.md#is-there-any-custom-firmware)). In the meantime, the stock firmware has been investigated quite a bit; here are some findings from it:

## Bootloader Bug
The bootloader on the SF2000 (the bit of code embedded in the devices hardware; it initialises things, and kicks-off loading of the BIOS from `bisrv.asd`) has a bug, which can cause the SF2000 to lock-up with a black screen during boot if the `bios` folder has been messed with. Specifically, the bug is triggered when the `bios` folder's FAT table contains a multiple of `4` entries, or a multiple of `4` plus `1`.

It's strongly recommended that you fix the bug on your SF2000, as failure to do so can cause some headaches for you down the road with a non-booting device. There's a couple of ways to go about fixing it:

## If Your SF2000 Is Currently Able To Boot Normally
If your SF2000 is currently able to boot normally (i.e., when you power it on, you get to the stock main menu), then you can permanently fix the bug in the device's hardware as follows (credit to `bnister` for both finding the root cause for the bug, and creating the permanent fix) - this only needs to be done _once_ per SF2000, and is not tied to the microSD card or BIOS in any way:

1. Ensure your SF2000 is in a state where it boots normally when turned on (displays a boot logo, proceeds to the stock firmware main menu)
2. Ensure your SF2000's battery is fully charged (having the device power off during the patching process will likely "brick" it, rendering it inoperable)
3. Power off the SF2000, and remove the microSD card
4. Connect the microSD card to your computer
5. Download this zip file: [SF2000_bootloader_bugfix.zip](https://cdn.discordapp.com/attachments/1099465777825972347/1105582470990135316/SF2000_bootloader_bugfix.zip)
6. Extract the zip file; inside is a folder called `UpdateFirmware`, containing a single file called `Firmware.upk`
7. Copy the `UpdateFirmware` folder to the root of the microSD card, so that the `UpdateFirmware` folder is in the same place as the `bios` and `roms` folders (i.e., you'll have an `SD:/UpdateFirmware/Firmware.upk` file)
8. Eject the microSD card from your computer, and put it back in the SF2000
9. Turn the SF2000 on; you should see a message in the lower-left corner of the screen indicating that patching is taking place. The process will only last a few seconds. If you do not see this message, and instead just go to the main menu as normal, then either this means your SF2000 has previously had the fix applied already, or you should double-check you've placed the patch file in the right place
10. When the patching is complete, you will be taken to the main menu as usual
11. Power off the SF2000, and remove the microSD card
12. Connect the microSD card to your computer
13. Delete the `UpdateFirmware` folder (it's no longer needed)

## If Your SF2000 Is Currently Not Booting (Black Screen)
If your device is currently _not_ booting, and you've modified the `bios` folder in any way (e.g., patching a new boot logo, upgrading firmware, etc.), you can attempt to get the SF2000 booting again by creating empty text files inside the `bios` folder, one at a time (this creates new FAT entries, and should get you away from numbers of entries the stock bootloader doesn't like). For example, create an empty file in the `bios` folder called "temp1.txt", put the microSD card back in the SF2000, and see if it boots. If it still doesn't, add a "temp2.txt" file to the `bios` folder, put the card back in the SF2000 and try booting again, etc..

Alternatively, recent versions of [Tadpole](https://github.com/EricGoldsteinNz/tadpole) can help to automate this process for you.

**NOTE**: Once you get your SF2000 booting again, I strongly suggest you perform [the permanent fix to the bug](../faq.md#if-your-sf2000-is-currently-able-to-boot-normally) to prevent from getting into the same situation again in the future.

There are also some [other reasons why an SF2000 may not be booting](../faq.md#help-my-sf2000-wont-turn-on-or-is-stuck-at-a-black-screen).

## Button Mappings/Key Bindings
`bnister` discovered that the OS supports loading game-specific key bindings from `.kmp` files, stored in the `save` folder for each system and named after a game's ROM file (e.g., `/FC/save/Game Name.EXT.kmp`). They also discovered where in the `bisrv.asd` file the default mappings for each emulator are stored. Working with this information, `notv37` worked out what bits related to what buttons for each emulator. Using both their findings, we now have a tool which can be used to update both the global button mappings for the emulators, as well as create per-ROM mappings - you can [find this tool here](https://vonmillhausen.github.io/sf2000/tools/buttonMappingChanger.htm).

Note that the game-specific key bindings function have been removed from the May 15th firmware onwards.

## Boot Logo
When the device is powered on, a "Welcome" image is displayed for a short time before the main menu appears. This image comes from inside `bisrv.asd`, (towards the end; exact offset varies between BIOS revisions). It's a `512x200` RGB565 Little Endian raw image file, and looks like this:

![Boot Logo](../images/bootlogo.png)

The image is _actually_ displayed at half-resolution on the internal display though, `256x100`, centred in the middle of the screen. The boot logo can be changed to an arbitrary `256x100` image using a web-based tool I wrote, which you can [find here](https://vonmillhausen.github.io/sf2000/tools/bootLogoChanger.htm).
