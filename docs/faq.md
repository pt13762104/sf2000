# FAQ (Frequently Asked Questions)
## Is this thing any good?
For a cheap device, it's actually fairly capable - most Game Boy, Game Boy Color, NES and Genesis/Mega Drive games play at full speed, and many arcade, Game Boy Advance and SNES titles do as well. The device has an IPS panel (not OCA laminated), and a user-replaceable 18650 battery, which can be charged via a USB-C port on the device. It also has analog A/V out (note: not HDMI), meaning it can be connected to a CRT TV - the type of display most arcade, Genesis/Mega Drive and SNES games were originally intended to be displayed on. It has a built-in 2.4GHz antenna, and can receive input from a compatible wireless controller (usually sold separately).

Some downsides to the device: There's a decent amount of screen-tearing, due to a difference between the display panel's refresh rate and the rate at which it's fed image data by the rest of the hardware (although this has been shown to be mostly addressable via software changes). It's mono only; and worse yet, you only get the left-channel audio (so stereo games just lack the right audio channel entirely). There's no headphone jack (although there is a volume wheel), screen brightness cannot be altered (it's fairly bright), SNES and Game Boy Advance are hit-or-miss in terms of performance (some games are fine, many games run unplayably slowly), the stock firmware is closed-source so the device's performance may never get any better than as-shipped, and some folks have had issues with the buttons (quality control is hit-or-miss, and some folks have had terrible button response, such as a d-pad that can't do diagonals reliably, or ABXY buttons that sit flush with or even go under the case). Finally, while the device features A/V out, it does so in a slightly odd resolution (576i) which may result in borders being chopped off on your TV, depending on how your TV deals with the signal.

So is the "Data Frog" any good? Only you can answer that question for yourself. There are certainly more powerful devices out there, more fully featured devices, devices with better hardware, etc. - but almost all of those devices cost a lot more than the SF2000. At the end of the day, you have to look at the features offered at the given price-point, and only then can you decide if you're interested in the device or not.

## Is there any custom firmware?
As of October 20th 2023, **no**, not yet. Two main efforts have been made:

- ### hcRTOS (true CFW)
Earlier this year, an SDK for the CPU in the SF2000 was been identified. Theoretically, this would allow a full custom firmware to be built and compiled for the device. The developers working on custom firmware spent some considerable time and effort working on porting Retroarch (as it seemed like it would be the quickest route to a custom firmware with support for many systems), however they ran into several problems. It appears that the SDK was unfinished and of low quality - core features like video and audio drivers were missing (and thus had to be developed from scratch), and overall system stability of the produced builds very low. When crashed happened with running cores (which was frequently) no useful debugging information was produced, and so tracking down the source of issues became a major time-sink. Additionally, most of the experimental builds when they did work had audio and/or video performance issues, and most also caused the SF2000 to run "hot", which would likely have impacted the lifespan of the device and thus are not recommended for usage beyond a few minutes at a time. [A GitLab repo](https://git.maschath.de/ignatz/hcrtos) was set up by `ignatzdraconis` for the work based on this SDK, however work on developing a full custom firmware using this SDK has been parked for now.

- ### Multicore (modified stock)
More recently, a new tack is being tried by the development team - they're trying to modify the stock SF2000 firmware to add additional functionality. Theoretically, this would come with the benefit of having audio and video drivers already built (the contractors producing the stock firmware for the SF2000 have access to these), providing no worse performance than stock firmware, while also providing features like support for additional emulated systems. An experimental developer build called the "multicore" build has been produced which hijacks the stock Game Boy Advance emulator to run additional systems like Atari 2600 and PC-Engine, some stand-alone engines for games like Doom and Cave Story, as well as alternatives for some of the stock emulators already included with the SF2000. Some of the new systems appear to run at full speed; some run without sound or with less than full speed, and others don't work at all yet. [A GitLab repo](https://gitlab.com/kobily/sf2000_multicore) has been set up by `kobil` for the work on modifying the stock firmware. If you want to try the current **experimental** pre-alpha build, see the pinned post in the `SF2000 Dev` thread in the `🐸data_frog_sf2000` channel of the [`Retro Handhelds` Discord server](https://discord.gg/retrohandhelds). Please do read the pinned messages both in the main channel and the thread before asking any questions of the devs, their time is precious 🙂

## I just got my SF2000; what modding can I do with it?
If you're planning to customise your SF2000 in _any_ way, then I **strongly** recommend the _very_ first thing you do is [fix an annoying bug in the device's bootloader](sf2000/firmware.md#bootloader-bug) - otherwise you're likely to end up with a non-booting device. Seriously - **do this before you do anything else!**

Afterwards, in no particular order, some of the current customisation options available are:

* I'm not kidding - [fix the bootloader bug](sf2000/firmware.md#bootloader-bug) before you do _anything_ with your SF2000!
* You can potentially [upgrade the firmware to the latest version](sf2000/firmware.md#firmwarebios-bisrvasd) (many of the other things below modify your installed firmware, so if you're going to do some of the others, do this one before them)
* You can swap out the [buttons](sf2000/hardware.md#buttons) and [d-pad](sf2000/hardware.md#d-pad) (and their membranes) for ones from original SNES controllers (not SNES Classic), which gives a more retro "mushy" feel (if your replacement buttons have 3 "pins", you may need to file or clip one of the pins off)
* You can swap the [battery](sf2000/hardware.md#battery) for a higher-capacity `3500 mAh` 18650, which will give you longer playtime (at the cost of longer charging time). If you do decide to replace the battery, make sure you use one with a built-in protection circuit, as the SF2000 has no under-charge protection.
* You can [patch the battery monitoring curve](https://github.com/Dteyn/SF2000_Battery_Level_Patcher) for the **stock** battery to make it more accurate using a web tool by `dteyn` (only use if you're keeping the stock battery; if you've put in a more powerful battery, the stock battery monitoring curve should be fine)
* You can [replace the boot logo](https://vonmillhausen.github.io/sf2000/tools/bootLogoChanger.htm) with a custom one
* You can [replace the main menu music, or remove it entirely](sf2000/resources.md#sounds)
* You can [change the default button mappings](https://vonmillhausen.github.io/sf2000/tools/buttonMappingChanger.htm) for each emulator (newer firmwares have this feature built-in, but the built-in implementation is buggy)
* You can add your own ROMs to the `roms` folder on the microSD card, which will then appear in the user ROMs menu of the device. You can also modify the built-in ROM lists using [FROGTOOL](https://github.com/tzlion/frogtool)
* You can [replace the default menu theme with a custom one](#how-do-i-install-new-menu-themes)
* You can [fix a bug with SNES emulation](#snes-games-run-really-slowly-whats-wrong) if you're using a firmware version prior to 1.71

Many of the above tasks can be done using [Tadpole](https://github.com/EricGoldsteinNz/tadpole), a general management tool for the SF2000 developed by `.ericgoldstein` and `jasongrieves_02643`.

## How do I install new menu themes?
The SF2000 doesn't natively support themes at all; however, all of the images and sounds for the stock theme live in the `Resources` folder on the microSD card. Therefore, by simply replacing the stock theme's files, the stock theme can be replaced.

A centralised repository for boot logos, custom themes and background music has been created by `Zerter#4954`, which you can [find here](https://zerter555.github.io/sf2000-collection/); you can also find many of them linked in the `The Frog's Best Bits 🐸` thread of the `🐸data_frog_sf2000` channel in the [`Retro Handhelds` Discord server](https://discord.gg/retrohandhelds).

The community built tool [Tadpole](https://github.com/EricGoldsteinNz/tadpole) can be used to change the theme on the SF2000, amongst many other features.

If you wish to manually install a theme you've downloaded, just take the files from the theme, and use them to replace the existing files on the microSD card. You might want to make your own backup of the stock `Resources` folder first, in case you want to go back to the stock theme yourself at a later date. Note also that in addition to theme assets, [the `Resources` folder](sf2000/resources.md#resources) also contains data files related to your [button mapping](sf2000/resources.md#button-mappingskey-bindings), [favourites and history](sf2000/resources.md#favourites-and-history), etc.; so when backing up or replacing files in `Resources` for themes, just be aware not to overwrite anything non-theme-related you want to keep.

Another thing to note: some themes might come with an updated boot logo. If that logo is provided as [a `bisrv.asd` file](sf2000/firmware.md#firmwarebios-bisrvasd) in the `bios` folder, this is actually a modified _firmware_ for the device, which happens to contain the new logo. If you decide to replace your existing `bisrv.asd` file, you might want to make sure that the theme's firmware version matches the firmware version already on your device. Generally, it's probably safer just to [update your own firmware's boot logo](https://vonmillhausen.github.io/sf2000/tools/bootLogoChanger.htm) with an image file.

## How do I change the four shortcuts/games listed on each system's main menu page?
Recent versions of [Tadpole](https://github.com/EricGoldsteinNz/tadpole) by `.ericgoldstein` and `jasongrieves_02643` have support for changing the shortcuts if you're looking for an automated way to do things. There's also a separate web-based tool from `Zerter#4954` which lets you edit these icons, [you can find it here](https://zerter555.github.io/sf2000-collection/mainMenuIcoEditor.html).

Alternatively, you can do it manually with a fair bit of work. The _images_ for the shortcuts are baked into each system's main menu background image - check out the ["Images (Used)"](sf2000/resources.md#images-used) section below, and use your browser's search feature to search for `main menu background`, and you'll see what I mean. The _text_ under each shortcut is stored in a separate image - in firmware version 1.5 onwards, the files are `gkavc.ers` if the device's language is set to Chinese, or `gakne.ctp` for all other languages (again, check the details in the ["Images (Used)"](sf2000/resources.md#images-used) section below). Finally, the actual roms that are launched for each shortcut are stored in the `xfgle.hgp` file, which is plain text - you can learn more about it in the ["ROM Lists"](sf2000/resources.md#rom-lists) section below.

## SNES games run really slowly... what's wrong?
There's a bug in all stock firmware versions prior to 1.71 which often causes SNES games to run really slowly on first launch (and their sound is slow and lower pitch too); this only impacts SNES. `bnister` discovered that this appears to be related to a firmware bug, in which certain settings (audio rate and clock speed) for the SNES emulator are set _after_ Retroarch has been initialised, causing Retroarch to get confused and run at half rate. This bug was fixed in firmware 1.71, so you can [upgrade to that firmware version](sf2000/firmware.md#firmwarebios-bisrvasd) to fix things. If you don't want to upgrade to 1.71, there are two other ways to fix or work-around the issue:

  * `Dteyn` has created a web-based tool which will patch your BIOS with a workaround to correct the issue - [you can find their tool here](https://dteyn.github.io/sf2000/tools/snesEmulatorFix.htm);
  * Quitting back to the game selection menu via `START + SELECT`, and then immediately re-launching the game again will get the game to run at full speed the second time around; this would need to be done at least once every time you power on the SF2000.

Note however that the stock firmware does also struggle a bit with SNES emulation in general, so any slowdown or poor SNES performance you see after addressing the bug is just what you get.

## Help! My SF2000 won't turn on, or is stuck at a black screen!
The three most likely causes for this are:

* If you've switched to using a different microSD card than the one your SF2000 switched with, there's a good chance the new microSD card you're using is not compatible with the SF2000. The device seems to be very picky about the types of microSD cards it will or won't read. Try putting your original microSD card back into the SF2000 and see if it'll boot OK from that.
* If you've done anything at all to the `bios` folder on the microSD card (_anything_ at all), then there's a good chance you've run into the bootloader bug - you can [find the two fixes to it below](sf2000/firmware.md#bootloader-bug). Alternatively (or if neither of the two fixes work for you), [follow Data Frog's instructions](https://www.youtube.com/watch?v=j8dT2fdGfck) to wipe your microSD card and flash a clean firmware image, or try using [Tadpole](https://github.com/EricGoldsteinNz/tadpole)'s built-in fix feature.
* Your battery could be running low. The SF2000 will still "turn on" when its battery is low on charge (the red light will still come on), but the device itself will actually fail to boot, just leaving you with a black screen. Turn the device off, and charge it fully (the stock battery takes 3.5 hours to charge from empty - the green charging light will not go out, so you'll have to time it yourself).

## When I connect the SF2000 to a TV via the A/V cable, the sound is very quiet/low - is that normal?
This was due to a bug in some earlier firmware versions; it was officially fixed in firmware 1.6, so if you're running a prior firmware version ([check here](https://vonmillhausen.github.io/sf2000/tools/firmwareVersionChecker.htm)), you can [upgrade to a newer firmware version](sf2000/firmware.md#firmwarebios-bisrvasd).

Alternatively, `Zerter#4954` from Discord found a workaround if you don't want to upgrade:

> when I did this the AV audio work normally: I had to load the game first then plug-in the 2.5mm to rca jack. [...] but when I quit then exit then tried the game again it returns to very low audio. [...] will need to do the work around again

So you can try launching the game first, and _then_ plug in the A/V cable to get full volume on the TV.

## Game saves don't seem to be working for me? Save states are fine, but the built-in save function in games doesn't seem to work?
Unfortunately, correct - with the stock firmware, the built-in save feature of emulated games does not work correctly, and the SF2000 won't store new save data after the first time it's created for a game. If you want to save your progress in a game on the SF2000's stock firmware, use save states instead. Note that firmware 1.6 _appears_ to have fixed this for GBA based on community reports, but not for other emulated systems.

## I have a question that isn't answered here... who or where do I ask?
If you have questions about the SF2000 you can't find the answer to, the best place to ask is in the `🐸data_frog_sf2000` channel in the [Retro Handhelds Discord server](https://discord.gg/retrohandhelds).
