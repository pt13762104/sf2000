# Hardware
## CPU
Although the main CPU of the SF2000 has literally had it's markings milled off by a routing tool, the community has determined that it's a HCSEMI B210, a single-core MIPS processor running at 810 MHz (or 918 MHz with the 1.6 firmware onwards). It appears to be a clone of an ALi Tech chip. [An SDK has been found](http://www.zcsd-tech.com//download/content-54.html) for it.

## Display
The SF2000 features a `240x320` IPS display panel (not OCA laminated), which has been rotated 90&deg; clockwise to give a `320x240` display. It demonstrates screen tearing for all emulators, running from the right of the console to the left due to the panel rotation.

## Buttons
The ABXY are basically a clone of the original SNES controller buttons. Although everyone seems to be getting two purple and two lilac coloured buttons, there's a disparity to the _type_ of buttons folks are getting - some get two convex and two concave buttons, others have gotten three concave and one convex, etc..

Both the buttons and the underlying membrane from an original SNES controller can be swapped into the SF2000, which may improve the "feel" of the buttons. Note that the SF2000 uses ABXY buttons that have two plastic tabs sticking out to keep them in the shell (at 180 degrees from each other); some after-market SNES-style buttons have _three_ tabs, and won't fit the housing.

Some folks have modded the stock ABXY buttons on their SF2000s by adding a thin strip of tape or other thin material into the circular depression under each button - this causes the buttons to be raised a bit higher out of the shell, and to not sink as far into the shell when the button is pressed.

## D-Pad
Just like the ABXY buttons, the d-pad is a clone of the SNES d-pad. An original SNES d-pad and membrane can be swapped into the SF2000 as well.

## Thumb Stick
The SF2000 uses a Switch-style thumb stick that does _not_ depress for L2/R2. It is compatible with Switch thumb stick third-party covers.

## MicroSD Card
The SF2000 uses a microSD card for storing everything, including the device's firmware. Most SF2000s ship with an included card, formatted for 16 GB of storage. Some of the included "16 GB" microSD cards are actually 32 GB cards, even though "16 GB" is printed on them - they are genuinely 32 GB cards, and the default 16 GB partition can be expanded to use the rest of the card if desired.

The SF2000 is _very_ picky about the types of microSD cards it works with - many folks have had issues where well know, name-brand cards refuse to work in the device, while cheaper cards (like the stock card) work fine. The reasons for this have not yet been determined. If you've swapped over to using a non-stock microSD card, and your SF2000 isn't booting (and you've ruled out [the bootloader bug](firmware.md#bootloader-bug)), then there's a good chance your SF2000 just won't work with the microSD card you're using.

## Battery
The SF2000 takes a 18650 type rechargeable battery, which is easily user replaceable (it's behind a battery door with a screw), and comes with a 1,500mAh one which runs for about 4 hours. 18650 batteries with and without "nubs" both fit fine. The console has built-in over-charge protection, but _does not have under-charge protection, so for safety do not leave the console turned on when the battery is low_. From when it displays a full-screen low battery indicator, it takes about 3.5 hours to charge the stock battery. The green charging light does _not_ turn off when fully charged.

Also note that while you can technically charge the SF2000 while it is powered on, doing so using a charger that supports fast charging or power delivery has a high chance of blowing the charging module IC and killing the device (multiple community reports). For safest charging, use a charger that only supports a maximum output of 5v.

The stock firmware's power monitoring system (which controls the battery level indicator on the main menu, along with when the device warns the user about a low battery condition) is poorly calibrated for the stock battery that comes with the device; as such, the SF2000 basically indicates it has a full battery at all times. `bnister` and `dteyn` from Discord worked together to identify the locations within the stock firmware where the calibrations are stored, and determined more appropriate calibration values for the stock battery. `dteyn` wrote a web-based tool which will patch an existing `bisrv.asd` file to use the new values; you can [find their "Data Frog SF2000 Battery Meter Fix" tool here](https://dteyn.github.io/sf2000/tools/batteryMeterFix.htm). They also have a Python script to do the patching specifically for the 1.6 firmware - you can [find that script here](https://github.com/Dteyn/SF2000_Battery_Level_Patcher), along with much more detail about the issue and the solution.

## Wireless Connectivity
The SF2000 does not feature WiFi or Bluetooth, but it _does_ have a 2.4Ghz antenna to support local wireless multiplayer using a compatible 2.4Ghz wireless controller for Player 2. The Y2 SFC wireless controller and the SF900 wireless controller have both been reported to work fine.

## A/V Output
The SF2000 features a mini-jack for analogue composite A/V output. The device is capable of output a user-selectable PAL or NTSC video signal. Only the _left_ audio channel is output - the device does _not_ down-mix to mono, which results in missing audio channels in games that expect to output stereo sound.

There's some limited evidence to suggest the A/V output is at 576i. When outputting a PAL signal, while the signal is indeed 50Hz, it seems like the emulators are still targeting 60Hz output - PAL scrolling is "jerky". Switching the device to output NTSC, scrolling becomes smooth. This holds true regardless of using a PAL or NTSC version of a ROM. Depending on your external display, video output over A/V may be somewhat heavily cropped on all screen edges - if so, this can result in UI elements at screen edges in games (health bars, remaining credits, etc.) being out-of-frame. Switching between PAL and NTSC doesn't alter the visible screen area. I've tested with a modern flat-panel Panasonic TV (cropped), a 1980s Commodore 1702 monitor (cropped), and with a cheap USB 2.0 "EasyCap" video-capture USB stick (not cropped).

On my own unit, plugging in a charging cable while outputting over A/V introduces a lot of video noise in the A/V signal; so those planning to use the SF2000 as a TV console may need to do so while running on battery for the best experience.

While not strictly related to the A/V jack, Discord user `iq_132` has written a guide on how to add Bluetooth audio support to the SF2000 by feeding off of the contacts for the internal speaker; you can [find their guide here](https://neo-source.com/stuff/datafrog/).