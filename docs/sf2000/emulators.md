# Emulators

The device advertises support for arcade, NES, SNES, Genesis/Mega Drive, Game Boy, Game Boy Color and Game Boy Advance; it also supports loading Master System ROMs. SNES and GBA performance are very hit-or miss (more miss than hit, really); the other consoles actually perform fairly well. All consoles currently stretch their output to fill the display, and do not maintain aspect ratio.

The SF2000 appears to be using Libretro with a custom front-end (i.e., not RetroArch).

## Arcade
The device is running Final Burn Alpha v0.2.97.42 (Git commit [`621e371`](https://github.com/Aftnet/fbalpha/commit/621e371)). Thanks to some truly exceptional work by `adcockm` from the Retro Handhelds Discord, we know it supports an unusual mix of ROM sets, largely based on MAME 0.106 and Final Burn Alpha v0.2.97.42. `adcockm` has gone ahead and compiled two separate [Clrmamepro](https://mamedev.emulab.it/clrmamepro/) dat files - [one for _all_ sets technically supported by the SF2000's current BIOS](../arcade/DataFrog_SF2000_FBA_v0.2.97.42.dat) (as of May 2023; though note that "supported" does not mean working or playable), and [one for all playable sets](../arcade/DataFrog_SF2000_FBA_v0.2.97.42_playable_no_dups.dat) with duplicates removed (and note, "playable" may include games with missing sound, graphical glitches, performance issues, but are otherwise technically functional). If you want to build a working set (must be non-merged) from the dat files, `adcockm` has further provided [a list of "hints"](../arcade/Building_the_DataFrog_SF2000_FBA_v0.2.97.42_set.txt) as the sets you'll need to track down - for obvious reasons neither I nor anyone else can provide links to such material, but hopefully the hints will get you something you can start searching for. Finally, there's also [a HTML document](../arcade/DataFrog_SF2000_FBA.html) with a list of all of the supported sets along with some useful metadata, such as the set's full name, playability information, screen orientation, etc.. The `inrom` column indicates if the ROM was included on the SF2000's stock microSD card; it's interesting to note that there were more ROMs located on the card than were defined in the `mswb7.tax` file (and thus available from the arcade game list); none of the unlisted games were actually playable on the SF2000, so it's possible someone from Data Frog actually tested the games to an extent, and removed ones from the available list that were broken.

`adcockm` also provided the following interesting statistics:

- Number of arcade ROMs known by the SF2000's firmware: `1431`
- Number properly rotated: `1291`
- Number with vertical orientation: `134`
- Number with screen upside-down: `6`
- Number "playable" (maybe no sound, some slowness, minor graphics issues): `949`
- Number unplayably broken but technically running: `175`
- Number fully broken (load hang/crash, etc.): `307`
- Number of playable unique games (dupes filtered out) in proper rotation: `354`
- Number of playable unique games (dupes filtered out) with rotated display: `61`
- Number of different versions of Street Fighter 2: `60+` 😵‍💫 [Von Millhausen: I think this stat is only half a joke!]
- Playable set total size: `3.10 GB` (3,336,344,502 bytes)
- Full set total size: `11.4 GB` (12,245,306,389 bytes)

### Neo Geo Unibios Menu
Discord user `nanchon18#2262` discovered that with Neo Geo games using the Unibios, the Unibios menu can be accessed in-game by pressing `SELECT + START + up` simultaneously. The Unibios allows access to features like cheats and DIP-switch settings for the game.

### .skp Files
Another thing worth mentioning about arcade emulation on the SF2000; in the `ARCADE` folder on the microSD card is a sub-folder called `skp`. This folder contains (by default) 167 `.skp` files, each named after one of the zipped ROM sets in the `ARCADE/bin` folder (e.g., `mslug.zip.skp`). These files are actually save state bundle files, just like the ones you can save yourself using the save state feature - the only difference is that these have the `.skp` extension instead of `.sa#`, and these are loaded automatically when the game itself is loaded. Many of these files start their respective arcade game up with a credit already inserted. One speculative possibility for why these files exist is that some arcade games will start to a dip-switch screen, or some other ROM-check screen, which may be difficult to bypass with the SF2000's limited controls - a save state that automatically loads _past_ such a screen is therefore very useful to have.

As the `.skp` files are just save states under a different name, if you want to mess around with them you can [use my Save State Tool](https://vonmillhausen.github.io/sf2000/tools/saveStateTool.htm) to do so - if you're creating a new `.skp` file, just pick any save state slot, and change the downloaded SF2000 save state bundle extension from `.sa#` to `.skp`.

You can [learn more about save states below](#save-states).

### .zfb Files
Due to the different nature of arcade emulation compared to any of the other systems the SF2000 supports, the ROM layout for the arcade section is different as well. Inside the `/ARCADE` folder in the root of the microSD card you'll find a `bin` subfolder, and a bunch of `.zfb` files. The `bin` folder contains `.zip` files with an enforced 8.3 file naming scheme, and they contain the actual ROM data for the FBA emulator. The `.zfb` files are used to populate the arcade game list when you go into the arcade section on the SF2000's menu, and their file structure is as follows:

* The first 59,905 bytes are an RGB565 image for the game thumbnail art shown in the menu (208px by 144px)
* The next four bytes are `0x00`
* The next sequence of bytes is the name of a `.zip` file in the `bin` folder, without any path (SF2000's firmware automatically looks for the `.zip` in a `bin` subfolder relative to where the `.zfb` file is stored - thanks `.ericgoldstein` for the testing!), e.g. `gamename.zip`
* Finally, the file ends with two `0x00` bytes

The name of the `.zfb` file is how the game is named in the SF2000 menu. The four arcade game shortcuts on the top-level SF2000 menu point directly to their respective `.zip` files, and not to the `.zfb` files (as the `.zfb`s are just for a name and a thumbnail, neither of which are required on the top-level menu).

## NES
Emulator is FCEUmm (Git commit [`7cdfc7e`](https://github.com/libretro/libretro-fceumm/commit/7cdfc7e)). There are references in the firmware to different NES palettes, but there's no interface or configuration for the emulator itself to choose one. On the original firmware, the A and B buttons were swapped. See "[Button Mappings/Key Bindings](#button-mappingskey-bindings)" section below.

## SNES
Emulator is Snes9x 2005 v1.36 (Git commit [`b94a804`](https://github.com/libretro/snes9x2005/commit/b94a804)). For most firmware versions before 1.71, SNES games often appear to run very slowly _on first launch_; you can [learn more about this issue and how to correct it here](#snes-games-run-really-slowly-whats-wrong).

## Genesis/Mega Drive
Emulator is PicoDrive 1.91 (Git commit [`cbc93b6`](https://github.com/libretro/picodrive/commit/cbc93b6)). Works pretty well. This emulator is capable of loading Master System ROMs if placed in the user ROMs folder on the microSD card; Game Gear ROMs do not load. Some PAL-region games may run too fast; NTSC-region games seem to always run at the correct speed. On the original firmware, A was mapped to A, B was mapped to B, and RB was mapped to C for some reason. See "[Button Mappings/Key Bindings](#button-mappingskey-bindings)" section below.

## Game Boy
Emulator is TGB Dual v0.8.3 (Git commit [`9be31d3`](https://github.com/libretro/tgbdual-libretro/commit/9be31d3)). Uses a black and white colour palette, which currently cannot be changed. On the original firmware, the A and B buttons were swapped. See "[Button Mappings/Key Bindings](#button-mappingskey-bindings)" section below.

## Game Boy Color
Emulator is TGB Dual v0.8.3 (Git commit [`9be31d3`](https://github.com/libretro/tgbdual-libretro/commit/9be31d3)). On the original firmware, the A and B buttons were swapped. See "[Button Mappings/Key Bindings](#button-mappingskey-bindings)" section below.

## Game Boy Advance
Emulator is gpSP v0.91 (Git commit [`261b2db`](https://github.com/libretro/gpsp/commit/261b2db)). Performance is fairly poor. On the original firmware, A and B buttons are mapped correctly, but the GBA shoulder buttons are mapped to X and Y for some reason. See "[Button Mappings/Key Bindings](#button-mappingskey-bindings)" section below.

While the SF2000 does include a copy of the real GBA BIOS file in the `bios` folder, there's a bug in the 1.5 firmware (and possibly earlier firmwares) that prevents that BIOS from ever actually being loaded. As such, gpSP _always_ falls back to the built-in "NORMMATT" BIOS instead (a reverse-engineered BIOS that is not identical to Nintendo's one). This has been noted to have some compatibility issues - for example, the main menu on "The Legend of Zelda - The Minish Cap" is broken on a stock SF2000 using the 1.5 firmware due to the NORMMATT BIOS. You can correct for this bug by copying the `gba_bios.bin` file from the `bios` folder to the two following locations (create any folders as needed - and credit to `bnister` for the finding!):

- `GBA/mnt/sda1/bios/gba_bios.bin` (this fixes it for the main GBA game list)
- `ROMS/mnt/sda1/bios/gba_bios.bin` (this fixes it for GBA games added to the user `ROMS` folder)

## Save States
All of the above emulators support stave sates natively through an interface that is accessed by pressing SELECT + START simultaneously in-game. Four save state slots are provided per-game; the files have the extensions `.sa0`, `.sa1`, `.sa2` and `.sa3` depending on which slot they're for, and are stored in a `save` subfolder along-side wherever the game's ROM file is stored. The extension is appended to the name of the ROM file the save state is for; for example, if the ROM is called `SD:/ROMS/Apotris.gba`, and the save state is for slot 2, then the save state file name will be `SD:/ROMS/save/Apotris.GBA.sa1`. One weird note is that save states created for ROMs stored in the user `ROMS` folder on the device get their ROM file extension capitalised when a save state is created (as per the previous example with `Apotris`, where `.gba` became `.GBA`); this does _not_ happen with save states created in the other ROM folders. The capitalisation doesn't appear to matter - the SF2000 successfully loads save states with any extension capitalisation in any folder.

If you want to back-up the save states you've got on your SD2000's microSD card, simply back up the `save` folders and their contents (be sure not to mix up which `save` folder belongs to which ROM folder on the device). [Tadpole](https://github.com/EricGoldsteinNz/tadpole) also has a save backup feature, which will give you a `.zip` file containing all of your saves.

The save state files themselves contain two zlib-compressed data blobs, plus associated metadata - one blob for the raw save state data created by the emulator itself, and one blob for the thumbnail used for the save state in the UI. The exact format is as follows

* The first four bytes are a little-endian Uint32 storing the length of the zlib-compressed raw save state data
* The next N bytes are the zlib-compressed raw save state data
* The next four bytes are a little-endian Uint32 storing the width of the thumbnail image in pixels
* The next four bytes are a little-endian Uint32 storing the height of the thumbnail image in pixels
* The next four bytes are a little-endian Uint32 storing the length of the zlib-compressed thumbnail data
* The next N bytes are the zlib-compressed thumbnail data (deflates to a raw RGB565 image, much like many of the other images used by the SF2000 UI)
* The last four bytes are a little-endian Uint32 storing the offset within the file of where the thumbnail metadata starts (i.e., the offset of the first byte of width data)

If you want to mess around with SF2000 save states, you can [do so using my SF2000 Save State Tool, which you can find here](https://vonmillhausen.github.io/sf2000/tools/saveStateTool.htm).

## Default ROMs
The default full firmware for the SF2000 comes with over 6000 ROMs across the seven supported systems. The manual suggests these are for "demonstration purposes" only, and should be deleted by the owner (with any failure to do so not being their responsibility) - despite the fact that the SF2000's menus are hard-coded for this specific list of ROMs. The ROM files themselves are a custom bundle format; the first `59,904 bytes` are an RGB565 image shown as a thumbnail beside the game when selected in a game-list, and the remainder of the file is a slightly mangled/obfuscated ZIP file containing the game's single ROM file. The only exception to this format are the arcade ROMs, which consist of a plain-old Final Burn Alpha ROM zip file, coupled with a `.zfb` file containing the thumbnail image and a pointer to the ROM zip file name.

I was curious to see how the included ROMs matched up against the current "[No-Intro](https://no-intro.org/)" catalogue for each of the non-arcade systems, so I wrote a small script to extract the ROMs from the SF2000's bundles (taken from the 1.5 full firmware image), and compare the hashes against the current (June 9th, 2023) set of No-Intro DAT files. You can [find a big HTML file with all of the results here](../defaultRoms/defaultRomsNoIntroCheck.htm), and [a raw CSV file of the same data here](../defaultRoms/defaultRomsNoIntroCheck.csv). You can click most of the column headers in the HTML version to sort the table by that column. The NES ROMs had their first 16-bytes stripped to remove their "iNES" header (thanks for the tip, `bnister`!), and were compared against the "header-less" No-Intro NES dat file.
