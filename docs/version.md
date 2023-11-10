# Document Version History
## 20231110 - `b794f05`
- Update the CFW FAQ (fix date from Oct 20th to Nov 5th).
## 20231110 - `3911adf` (1.45)
- Update to version 1.45 of the official site (20231105 - `5c4affd`).
- Changelog:
    * Updated the [is-this-any-good](faq.md#is-this-thing-any-good) FAQ to mention screen tearing (thanks for the suggestion `superbottle`!), as well as references to the demonstration of the screen tearing fix. 
    * Updated the CFW FAQ with the latest details regarding the multicore alpha. 
    * Added a note about the screen tearing fix demo to the Display section. 
    * Added a note to the Wireless Connectivity section to mention that wireless controllers compatible with the froggy cannot be used with non-froggy-style devices. 
    * Rearranged some files in the Used and Unused sections, and moved that one pesky unknown file to the Other section (thanks for the help, `bnister`!).
## 20231104 - `f352ab2`
- Add the missing zaqrc file, changed the color, add README.md
## 20231103 - `bc8065f` (1.44)
- First time that the site is uploaded - based on v1.44 with relative links fixed (no more changes)
## *pre-1.44 _ official changelog* 
- `20231020 - 1.44`: Updated [the CFW FAQ](#is-there-any-custom-firmware) with some more details on the multicore experiment. Fixed a typo (Cave Story, not Cave Store - thanks `neddunn`!).

- `20231019 - 1.43`: Refactored [the CFW FAQ](#is-there-any-custom-firmware) to make the hcRTOS and multicore efforts more distinct. Refactored [the shortcuts FAQ](#how-do-i-change-the-four-shortcutsgames-listed-on-each-systems-main-menu-page) to mention Tadpole first (easier for most folks). Refactored [the slow SNES FAQ](#snes-games-run-really-slowly-whats-wrong) in light of 1.71. Refactored [the quiet A/V output FAQ](#when-i-connect-the-sf2000-to-a-tv-via-the-av-cable-the-sound-is-very-quietlow---is-that-normal) to suggest firmware updating first. Added details about the new 1.71 firmware version to the [Firmware](#firmwarebios-bisrvasd) and [Resources](#resources) sections, and did a lot of little edits throughout the doc as well to standardise on Data Frog's version numbering (seems to be what most folks refer to). Added a note that [the permanent bootload bugfix](#if-your-sf2000-is-currently-able-to-boot-normally) only needs to be applied once per device. Added another modification example to the analysis of [`Foldername.ini`](#foldernameini) courtesy of `wyverino`.

- `20231014 - 1.42`: Have now confirmed that no resource files changed with the new October 7th/1.7 firmware, so have updated the tables in the [Resources](#resources) section to reflect this. Also added a reference to `detyn`'s Battery Meter Fix tool to [the FAQ on stuff new SF2000 owners can do](#i-just-got-my-sf2000-what-modding-can-i-do-with-it).

- `20231012 - 1.41`: Added basic information about the new (and critically broken) October 7th/1.7 firmware version to the [Firmware](#firmwarebios-bisrvasd) section (I'm waiting for my official copy to finish downloading before updating the tables in the [Resources](#resources) sections).

- `20231010 - 1.40`: Updated [CFW FAQ](#is-there-any-custom-firmware) with the latest details, and did a little re-arranging of existing info. Changed several links to Data Frog's YouTube firmware update process to links to the [Firmware](#firmwarebios-bisrvasd) section instead, as that section has more information about other options for firmware updates (e.g., Tadpole). Added links to `dteyn`'s SNES fix tool, and information about `bnister`'s discovery as to why SNES games had to be launched twice for full speed.

- `20231003 - 1.39`: Updated [CFW FAQ](#is-there-any-custom-firmware) with the latest details. Corrected a detail about the relationship between arcade `.zfb` files and the `.zip` files they point to (thanks `.ericgoldstein`!). Added a note to the [Firmware](#firmwarebios-bisrvasd) section about the official firmware update process wiping the microSD card, and a note to the [Save States](#save-states) section about how to back up game saves (thanks for the suggestion `@uli42`!). Added [a simple firmware version checking tool](https://vonmillhausen.github.io/sf2000/tools/firmwareVersionChecker.htm), so that folks don't have to use the boot logo changer to check (which always seemed clunky to me). Added a link to `dteyn`'s Silent Sounds pack. Fixed some small typos.

- `20230926 - 1.38`: Updated [CFW FAQ](#is-there-any-custom-firmware) with the latest details. Added some additional references to Tadpole, and added credits for `jasongrieves_02643` who has been doing a lot of recent development work on the tool lately. Updated the [CPU section](#cpu) to reference the fact that the CPU clock has been increased in the latest firmware. Added links to `iq_132`'s Bluetooth mod. Added [a section about the `.zfb` files](#zfb-files) used in the arcade section. Rearranged the details in [the Bootloader Bug section](#bootloader-bug) to hopefully make things a bit clearer.

- `20230905 - 1.37`: Added note about `bnister`'s CPU clock bump discovery to the [Firmware](#firmwarebios-bisrvasd) section. Added link to `dteyn`'s new background music tool to the [Sounds](#sounds) and [Tools and Links](#tools-and-links) sections.

- `20230903 - 1.36`: Added links to `detyn`'s new Battery Meter Fix tool to both the [Battery](#battery) section and [Tools and Links](#tools-and-links). Updated the [custom firmware FAQ](#is-there-any-custom-firmware) with the latest progress notes.

- `20230829 - 1.35`: Added a [MicroSD Card](#microsd-card) section to [Hardware](#hardware) to provide some detail about the SF2000's slightly unusual microSD card situation. Added detail about the [Neo Geo Unibios Menu](#neo-geo-unibios-menu) discovery to the [Arcade](#arcade) section (thanks `nanchon18#2262`!). Updated the custom firmware FAQ with the latest details. Updated the "what modding can I do" FAQ to strongly suggest fixing the [bootloader bug](#bootloader-bug) before doing any other modding to the device; also added a note that the Tadpole tool can perform a lot of the modding tasks. Updated the "quiet A/V sound" FAQ with details about the fix in the 1.6 firmware. Updated the "in game saves don't work" FAQ with details about this apparently being fixed for GBA in the 1.6 firmware. Added a note to the [Battery](#battery) section about the SF2000's poorly calibrated power monitoring curve, along with a link to `dteyn`'s SF2000 Battery Level Patcher script (also added a link to that in the [Tools and Links](#tools-and-links) section). Data Frog has now officially released the 1.6 firmware, so added that to the [Firmware](#firmwarebios-bisrvasd) section; also updated all of the tables in the [Resources](#resources) section to include the new firmware. Finally, renamed this "Version History" section to "Document Version History", to help prevent any confusion in regards to what the version numbers in this section refer to (they're not related to firmware).

- `20230819 - 1.34`: Updated the custom firmware FAQ answer with the latest progress notes. Replaced the bootloader bug FAQ with a more generic FAQ covering the main situations under which the SF2000 fails to boot correctly. Added a brief note on the mysterious new 1.6 firmware that has started appearing on some newer devices.

- `20230804 - 1.33`: Updated the custom firmware FAQ answer with the latest progress notes.

- `20230730 - 1.32`: Added a link to "ZFBTool" by `dteyn` in the "Tools and Links" section. Updated the custom firmware FAQ answer with the latest progress notes.

- `20230724 - 1.31`: Fixed Discord links (thanks `xdpirate`!). Added mention of Tadpole to FAQ about changing menu links.

- `20230720 - 1.30`: Corrected that gpSP Retroarch core demo does indeed have sound (but it's stuttery/crackly). Added a new FAQ about where to ask questions. Updated the Audacity steps for custom sound creation with some additional detail.

- `20230720 - 1.29`: Another custom firmware FAQ update (a second core, gpSP, has now been compiled and is at an early stage of running).

- `20230719 - 1.28`: Moved most of the intro section under the "Is this thing any good?" FAQ, and slightly reworded parts of it. Fixed a few typos.

- `20230718 - 1.27`: Updated FAQ about custom firmware with latest details (first running Retroarch core! 🎉)

- `20230714 - 1.27`: Updated FAQ about custom firmware with latest details (Retroarch input driver in basic functional state)

- `20230712 - 1.26`: Updated FAQ about custom firmware with latest details (Retroarch video driver is now able to display the main menu!)

- `20230710 - 1.25`: Added link to `Zerter#4954`'s new main menu icon editor tool.

- `20230709 - 1.24`: Updated FAQ about custom firmware with latest details (initial Retroarch build! 🎉)

- `20230705 - 1.23`: Updated FAQ about custom firmware with latest details. Moved "what can I do" bullet point about custom themes to its own separate FAQ to make it easier to find, and added more details about how to actually _install_ a theme.

- `20230630 - 1.22`: Added a FAQ about save games not working.

- `20230626 - 1.21`: Added a FAQ about slow SNES games. Updated details of CFW development with the latest status. Added a link to the discovered SDK. Added a link to `Zerter#4954`'s new theme collection site. Added a link to the Tadpole tool by `.ericgoldstein`.

- `20230622 - 1.20`: Added a note to the Game Boy Advance section about the newly discovered `gba_bios.bin` loading bug, and how to work around it (thanks `bnister`!)

- `20230618 - 1.19`: Added a question to the FAQ regarding how to change the main menu shortcuts.

- `20230617 - 1.18`: Added an FAQ. Added a section about the bootloader bug, along with steps for installing `bnister`'s patch. Added a link to `ignatzdraconis`'s Gitlab Repo. Some folks have updated their Discord handles to Discord's new naming convention, and those handles have been updated throughout.

- `20230609 - 1.17`: Added a section about the default ROMs that come with the SF2000, including a HTML file and a CSV file that have the SHA256/SHA1/MD5/CRC32 hashes for all non-arcade ROMs, and details about which ROMs match the current No-Intro database.

- `20230605 - 1.16`: Added my new [Save State Tool](https://vonmillhausen.github.io/sf2000/tools/saveStateTool.htm). Added documentation to the Emulators section about the save state files and their format. Also added a note specifically to the Arcade section about the `.skp` files (which are secretly just save state files with a different extension). Added a "Favourites and History" section detailing the format of the `Favorites.bin` and `History.bin` files.

- `20230530 - 1.15`: Added link to the community ROM compatibility list. Added some personal notes for theme creators.

- `20230529 - 1.14`: Updated the main menu BGM sample rate details with the latest findings from `bnister`. Clarified which menu text colour resets after exiting a game. Added a note about charging safety (thanks for your sacrifices, `Zerter#4954`! 🫡)

- `20230526 - 1.13`: Updated Audacity instructions to support latest version of Audacity. Added a BIOS CRC32 patcher tool for the reckless and brave. Added a note about `Foldername.ini` text colours reverting after loading a game (thanks `Zerter#4954`!)

- `20230525 - 1.12`: Added a section about the internals of the `Foldername.ini` file. Added a note to the Arcade section about the "inrom" column in `adcockm`'s metadata document. Added a small 1.5 firmware note about community-spotted GBA performance improvements. Added specific emulator versions and Git commit links for each emulator (thanks `bnister` and `notv37`!). Added specific steps for producing SF2000-format audio files using Audacity.

- `20230524 - 1.11`: Added my new [Generic Image Tool](https://vonmillhausen.github.io/sf2000/tools/genericImageTool.htm). Added more exceptional information from `adcockm` in regards to arcade emulation on the SF2000, and cleaned up the old info accordingly. Corrected some typos related to `bisrv.asd` (thanks `luke7352`!). Usage of `nvinf.hsp` was tracked down to the numbers of games available on the main menu pages (thanks `kid_sinn#9691`!).

- `20230522 - 1.10`: Updated resource tables for the new 1.5 firmware (no changes); added a table with details about known firmware versions. Added a "Tools & Links" section.

- `20230516 - 1.9`: Updated most of the Resources file lists to include firmware-related information (added, (un)changed, removed). Added new image resources for the latest May 15th firmware. Updated some images files previews to contain the fake name extensions as well. Added detail about the removal of per-game button maps from May 15th firmware. Renamed the sound previews to contain the fake name extensions as well.

- `20230513 - 1.8`: Discovered two "unused" images (the yes/no buttons) are indeed actually used, when being asked if you want to overwrite a saved game. Fixed a few typos. Changed formatting of file names used throughout. A bit more info on A/V out.

- `20230512 - 1.7`: Added a note about stock battery runtime. Added a section with information about A/V output performance. Added a bit of info about PAL/NTSC region speed for Genesis/Mega Drive. Retitled the "bisrv.asd" section to make it clearer that's the BIOS/firmware. 

- `20230511 - 1.6`: Added a quick note about the display panel to the Hardware section, and added a new section for Emulators, including an incredible collection of ROM notes for Arcade thanks to `adcockm`! Also added a "silent" background music file for download, and a table of contents (this page is getting fairly long 😅). Added a `favicon.ico` to get rid of that one annoying console error.

- `20230510 - 1.5`: Added additional detail to the Hardware section about the buttons, d-pad, thumb-stick, battery, and wireless controller support.

- `20230510 - 1.4`: Added my own version of `bnister`'s button mapping tool at their request, and changed the link in the Key Mapping section accordingly.

- `20230509 - 1.3`: Added more details about how the boot logo ends up scaled on the screen, as well as a link to a new tool I wrote for altering the logo. Corrected one small formatting error.

- `20230508 - 1.2`: Added details for `Archive.sys` - thanks to `bnister` for the hints on what it related to!

- `20230507 - 1.1`: Some "unknown" files from the `Resources` folder identified with `taizou`'s help (thanks!); moved them to the Sounds and Rom Lists sections with details. Only two files left!

- `20230507 - 1.0`: Original creation of this page.
