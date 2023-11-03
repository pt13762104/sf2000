# Resources
The Resources folder on the microSD card contains all of the resources used by the device's firmware to construct the user interface at runtime. The following tables list the files from various firmware versions (the numbered columns, in approximate `mm.dd` format for firmwares we don't have official version numbers for, and regular version numbers for the rest) and what they are used for, grouped by broad categories. Resolution and format given are for the latest firmware version only; details may be different for older firmwares. The icons in the firmware columns have the following meanings:

- ✨: file is new to this firmware version
- ✅: file is unchanged this firmware version
- 🚩: file is changed this firmware version
- ❌: file is removed this firmware version

## Fonts
| Filename | 03.15 | 04.20 | 05.15 | 1.5 | 1.6 | 1.7 | 1.71 | Description |
| -------- | ----- | ----- | ----- | --- | --- | --- | ---- | ----------- |
| `Arial_cn.ttf` |  | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | The "Arial" typeface, containing Latin, Greek, Cyrillic, Chinese, and Japanese characters. Duplicate of `yahei_Arial.ttf`, the single font file from the original firmware version |
| `Arial_en.ttf` |  | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | The "Arial" typeface, containing Latin, Greek, Cyrillic, Armenian, Hebrew and Arabic characters |
| `Arial_jp.ttf` |  | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | The "Arial" typeface, containing Latin, Greek, Cyrillic, Chinese and Japanese characters |
| `Arial_kr.ttf` |  | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | The "Arial" typeface, containing Latin, Greek, Cyrillic, Chinese, Japanese and Korean characters |
| `Tahoma.ttf` |  | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | The "Tahoma" typeface, containing Latin, Greek, Cyrillic, Armenian, Hebrew, Arabic and Thai characters  |
| `yahei_Arial.ttf` | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | The "Arial" typeface, containing Latin, Greek, Cyrillic, Chinese, Japanese and Korean characters |

## Images (Used)
As far as I am aware, all of the below images are actively used by the latest firmware version; happy to take any corrections if it turns out any of them are unused! Note that while the stock theme is based around a `640x480` resolution, the actual _display_ on the SF2000 is a `320x240` one. The OS on the device uses nearest-neighbour scaling for its images, giving the stock UI a somewhat aliased appearance. If you're planning to make your own theme for the SF2000, see my [Notes For Theme Creators](#notes-for-theme-creators) section below for some tips and tricks. I've written a generic image tool for the SF2000 - it lets you convert SF2000-formatted images to PNG files, and lets you convert PNG or JPEG images to SF2000 formats (which may be useful if you want to theme your device); you can [find this tool here](https://vonmillhausen.github.io/sf2000/tools/genericImageTool.htm).

| Filename | Resolution | Format | 03.15 | 04.20 | 05.15 | 1.5 | 1.6 | 1.7 | 1.71 | Description | View |
| -------- | ---------- | ------ | ----- | ----- | ----- | --- | --- | --- | ---- | ----------- | ---- |
| `aepic.nec` | 1008x164 | BGRA |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in Korean | [view](../images/aepic.nec.png) |
| `apisa.dlk` | 640x480 | RGB565 Little Endian | ✨ | ✅ | 🚩 | ✅ | ✅ | ✅ | ✅ | Arcade game-list background | [view](../images/apisa.dlk.png) |
| `appvc.ikb` | 150x214 | BRGA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Game art placeholder | [view](../images/appvc.png) |
| `awusa.tax` | 1008x164 | BRGA |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in Thai | [view](../images/awusa.tax.png) |
| `bisrv.nec` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | In-game menu (position 3) | [view](../images/bisrv.png) |
| `bttlve.kbp` | 60x144 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Battery level indicator icons | [view](../images/bttlve.png) |
| `c1eac.pal` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | SNES game-list background | [view](../images/c1eac.png) |
| `cero.phl` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Game Boy Color game-list background | [view](../images/cero.png) |
| `certlm.msa` | 40x24 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | NES game-list indicator | [view](../images/certlm.png) |
| `cketp.bvs` | 640x816 | RGB565 Little Endian |  |  | ✨ | ✅ | ✅ | ✅ | ✅ | The console selection images at the bottom of the new button mapping feature screen | [view](../images/cketp.bvs.png) |
| `d2d1.hgp` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | In-game menu (position 2) | [view](../images/d2d1.png) |
| `dism.cef` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | In-game menu (position 1) | [view](../images/dism.png) |
| `djctq.rsd` | 40x24 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | SNES game-list indicator | [view](../images/djctq.png) |
| `djoin.nec` | 1008x164 | BRGA |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in Spanish | [view](../images/djoin.nec.png) |
| `dpskc.ctp` | 640x320 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | In-game menu save-state slots (positions 1, 2, 3 and 4) | [view](../images/dpskc.png) |
| `drivr.ers` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | SNES main menu background | [view](../images/drivr.png) |
| `dsuei.cpl` | 640x480 | RGB565 Little Endian | ✨ | ✅ | 🚩 | ✅ | ✅ | ✅ | ✅ | User ROMs main menu background | [view](../images/dsuei.cpl.png) |
| `dxdiag.bin` | 40x24 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Genesis/Mega Drive game-list indicator | [view](../images/dxdiag.png) |
| `dxkgi.ctp` | 1008x164 | BRGA | ✨ | ✅ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in English | [view](../images/dxkgi.ctp.png) |
| `dxva2.nec` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Search keyboard (pressed) | [view](../images/dxva2.png) |
| `ectte.bke` | 161x126 | BRGA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Main menu icon selection box | [view](../images/ectte.png) |
| `efsui.stc` | 640x480 | RGB565 Little Endian | ✨ | ✅ | 🚩 | ✅ | ✅ | ✅ | ✅ | Game Boy Advance game-list background | [view](../images/efsui.stc.png) |
| `esent.bvs` | 1008x164 | BRGA |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in Turkish | [view](../images/esent.bvs.png) |
| `exaxz.hsp` | 152x1224 | BRGA | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | ✅ | Main menu "Games Exist" and "Start: Open" labels for all languages | [view](../images/exaxz.png) |
| `fixas.ctp` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | NES main menu background | [view](../images/fixas.png) |
| `fltmc.sta` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Game Boy game-list background | [view](../images/fltmc.png) |
| `fvecpl.ai` | 40x24 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Game Boy game-list indicator | [view](../images/fvecpl.png) |
| `gakne.ctp` | 576x256 | BGRA |  |  | ✨ | ✅ | ✅ | ✅ | ✅ | A new copy of the English menu labels image, identical to older versions of `dxkgi.ctp` (which was changed entirely in the May 15th firmware) | [view](../images/gakne.ctp.png) |
| `gkavc.ers` | 576x256 | BGRA |  |  | ✨ | ✅ | ✅ | ✅ | ✅ | A new copy of the Chinese menu labels image, identical to older versions of `itiss.ers` (which was changed entirely in the May 15th firmware) | [view](../images/gkavc.ers.png) |
| `gpsvc.bvs` | 392x80 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | In-game menu save-state slot (position 3) | [view](../images/gpsvc.png) |
| `hctml.ers` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Arcade main menu background | [view](../images/hctml.png) |
| `hgcpl.cke` | 392x80 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | In-game menu save-state slot (position 2) | [view](../images/hgcpl.png) |
| `hlink.bvs` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Search keyboard (hover) | [view](../images/hlink.png) |
| `htui.kcc` | 40x24 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Game Boy Color game-list indicator | [view](../images/htui.png) |
| `icm32.dll` | 40x24 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Game Boy Advance game-list indicator | [view](../images/icm32.png) |
| `icuin.cpl` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Genesis/Mega Drive main menu background | [view](../images/icuin.png) |
| `igc64.dll` | 217x37 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | "Yes" and "No" text, with "No" selected; used when being asked if you want to overwrite a save-game slot | [view](../images/igc64.png) |
| `ihdsf.bke` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Genesis/Mega Drive game-list background | [view](../images/ihdsf.png) |
| `irftp.ctp` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Game Boy Advance main menu background | [view](../images/irftp.png) |
| `irmon.tax` | 1008x164 | BRGA |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in Dutch | [view](../images/irmon.tax.png) |
| `itiss.ers` | 1008x164 | BRGA | ✨ | ✅ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in Chinese | [view](../images/itiss.ers.png) |
| `jccatm.kbp` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | "Battery Empty" screen | [view](../images/jccatm.png) |
| `ke89a.bvs` | 1008x164 | BRGA |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in Portuguese | [view](../images/ke89a.bvs.png) |
| `kmbcj.acp` | 640x480 | RGB565 Little Endian |  |  | ✨ | ✅ | ✅ | ✅ | ✅ | The full-screen background image for the new button mapping screen | [view](../images/kmbcj.acp.png) |
| `ksxbar.ax` | 392x80 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | In-game menu save-state slot (position 4) | [view](../images/ksxbar.png) |
| `lfsvc.dll` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Search game-list background | [view](../images/lfsvc.png) |
| `lk7tc.bvs` | 52x192 | BGRA |  |  | ✨ | ✅ | ✅ | ✅ | ✅ | Transparent labels for the button assignments in the new button mapping feature; these are the ones overlaid on the big SF2000 image showing the current assignments | [view](../images/lk7tc.bvs.png) |
| `lkvax.aef` | 640x480 | RGB565 Little Endian |  |  | ✨ | ✅ | ✅ | ✅ | ✅ | History game-list background | [view](../images/lkvax.aef.png) |
| `mkhbc.rcv` | 640x1440 | RGB565 Little Endian |  |  | ✨ | ✅ | ✅ | ✅ | ✅ | Six vertically-stacked images of the SF2000 with different buttons highlighted, used as part of the new button mapping feature's UI | [view](../images/mkhbc.rcv.png) |
| `mksh.rcv` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Search keyboard (normal) | [view](../images/mksh.png) |
| `msdmo.gdb` | 392x80 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | In-game menu save-state slot (position 1) | [view](../images/msdmo.png) |
| `msgsm.dll` | 40x24 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Arcade game-list indicator | [view](../images/msgsm.png) |
| `mssvp.nec` | 1008x164 | BRGA |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in Japanese | [view](../images/mssvp.nec.png) |
| `normidna.bin` | 40x24 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Search game-list indicator | [view](../images/normidna.png) |
| `ntdll.bvs` | 1008x164 | BRGA |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in Polish | [view](../images/ntdll.bvs.png) |
| `nvinf.hsp` | 16x240 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Latin numbers 0 to 9 listed vertically, used for the number of games available in each main menu category | [view](../images/nvinf.hsp.png) |
| `okcg2.old` | 32x32 | BGRA |  |  | ✨ | ✅ | ✅ | ✅ | ✅ | The star icon that appears beside favourited games in the game-lists | [view](../images/okcg2.old.png) |
| `pcadm.nec` | 1008x164 | BRGA |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in Italian | [view](../images/pcadm.nec.png) |
| `pwsso.occ` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | In-game menu (position 4) | [view](../images/pwsso.png) |
| `qasf.bel` | 640x480 | RGB565 Little Endian | ✨ | ✅ | 🚩 | ✅ | ✅ | ✅ | ✅ | User game-list background | [view](../images/qasf.bel.png) |
| `qwave.bke` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Game Boy Color main menu background | [view](../images/qwave.png) |
| `rmapi.tax` | 1008x164 | BRGA |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in German | [view](../images/rmapi.tax.png) |
| `sdclt.occ` | 120x240 | RGB565 Little Endian | ✨ | 🚩 | 🚩 | ✅ | ✅ | ✅ | ✅ | TV system selection icons | [view](../images/sdclt.occ.png) |
| `sensc.bvs` | 1008x164 | BRGA |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in French | [view](../images/sensc.bvs.png) |
| `sfcdr.cpl` | 576x1344 | BRGA | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | ✅ | Main menu system logos | [view](../images/sfcdr.png) |
| `subst.tax` | 1008x164 | BRGA |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in Russian | [view](../images/subst.tax.png) |
| `ucby4.aax` | 1008x164 | BRGA |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in Arabic | [view](../images/ucby4.aax.png) |
| `urlkp.bvs` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | NES game-list background | [view](../images/urlkp.png) |
| `uyhbc.dck` | 640x480 | RGB565 Little Endian |  |  | ✨ | ✅ | ✅ | ✅ | ✅ | Favourites game-list background | [view](../images/uyhbc.dck.png) |
| `vidca.bvs` | 1008x164 | BRGA |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in Hebrew | [view](../images/vidca.bvs.png) |
| `vssvc.nec` | 1008x164 | BRGA |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | User settings screen icons and labels in Malay | [view](../images/vssvc.nec.png) |
| `wshrm.nec` | 217x37 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | "Yes" and "No" text, with "Yes" selected; used when being asked if you want to overwrite a save-game slot | [view](../images/wshrm.png) |
| `xajkg.hsp` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Game Boy main menu background | [view](../images/xajkg.png) |
| `ztrba.nec` | 64x320 | RGB565 Little Endian |  |  | ✨ | ✅ | ✅ | ✅ | ✅ | Non-transparent labels for the button assignments in the new button mapping feature; these are the ones that pop up when you go to change a button assignment | [view](../images/ztrba.nec.png) |

## Images (Unused)
To the best of my knowledge, the following image files are currently __unused__ by the `20230515` firmware, and were probably left over from previous devices (the SF2000 shares a bit of lineage with some USB-stick devices) or development. The images marked "Alternate UI" below appear to have been for a UI where the systems were scrolled through horizontally, and the "shortcut" games for each system were scrolled vertically.

| Filename | Resolution | Format | 03.15 | 04.20 | 05.15 | 1.5 | 1.6 | 1.7 | 1.71 | Description | View |
| -------- | ---------- | ------ | ----- | ----- | ----- | --- | --- | --- | ---- | ----------- | ---- |
| `aeinv.bke` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Alternate UI: Genesis/Mega Drive main menu background | [view](../images/unused/aeinv.bke.png) |
| `aepic.ers` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Alternate UI: User main menu background | [view](../images/unused/aepic.ers.png) |
| `c1e.pal` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | CPS2 game-list background | [view](../images/unused/c1e.pal.png) |
| `cca.bvs` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | In-game menu (position 1; Chinese language hardcoded) | [view](../images/unused/cca.bvs.png) |
| `dectMap.key` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Button test screen (active) | [view](../images/unused/dectMap.key.png) |
| `desk.cpl` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Eight-game selection screen | [view](../images/unused/desk.cpl.png) |
| `djoin.hsp` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Alternate UI: Arcade main menu background | [view](../images/unused/djoin.hsp.png) |
| `fcont.ctp` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Alternate UI: User main menu background | [view](../images/unused/fcont.ctp.png) |
| `fdbil.ph` | 1100x120 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Large icons for each system, including systems not supported by the SF2000 (selected) | [view](../images/unused/fdbil.ph.png) |
| `gpapi.bvs` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | In-game menu (position 5; looks like it was for some kind of button layout changing UI) | [view](../images/unused/gpapi.bvs.png) |
| `ihds.bke` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Genesis/Mega Drive game-list background, with baked-in thumbnail placeholder | [view](../images/unused/ihds.bke.png) |
| `kdill.hsp` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Alternate UI: Game Boy Advance main menu background | [view](../images/unused/kdill.hsp.png) |
| `logilda.be` | 40x24 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | CPS1 game-list indicator | [view](../images/unused/logilda.be.png) |
| `mfc64.emc` | 40x24 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | CPS2 game-list indicator | [view](../images/unused/mfc64.emc.png) |
| `mfpmp.ers` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Alternate UI: Arcade main menu background | [view](../images/unused/mfpmp.ers.png) |
| `mhg4s.ihg` | 400x192 | RGB565 Little Endian |  |  | ✨ | ✅ | ✅ | ✅ | ✅ | Background and buttons for a "warning" prompt with "OK", "Yes" and "No" buttons. Also has rounded edges stored in a separate image file, `zaqrc.olc` | [view](../images/unused/mhg4s.ihg.png) |
| `mrtac.klo` | 40x24 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Neo Geo game-list indicator | [view](../images/unused/mrtac.klo.png) |
| `msdtc.bke` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Alternate UI: Game Boy Advance main menu background | [view](../images/unused/msdtc.bke.png) |
| `mswbv.cpl` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Alternate UI: Game Boy Advance main menu background | [view](../images/unused/mswbv.cpl.png) |
| `nettrace.dll` | 40x24 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Unknown game-list indicator (grey joystick with yellow buttons) | [view](../images/unused/nettrace.dll.png) |
| `nsibm.ctp` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Alternate UI: Arcade main menu background | [view](../images/unused/nsibm.ctp.png) |
| `nvinfohsp` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Alternate UI: Genesis/Mega Drive main menu background (note: there's no extension separator for this file, I suspect the file name is typo'd in the filesystem!) | [view](../images/unused/nvinfohsp.png) |
| `pcadm.hsp` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Alternate UI: User main menu background (NTSC TV system selected) | [view](../images/unused/pcadm.hsp.png) |
| `plasy.ers` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Alternate UI: Game Boy Advance main menu background | [view](../images/unused/plasy.ers.png) |
| `rmapi.cpl` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Alternate UI: User main menu background (English UI language selected) | [view](../images/unused/rmapi.cpl.png) |
| `seltMap.key` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Button test screen | [view](../images/unused/seltMap.key.png) |
| `spmpm.gdp` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Alternate UI: NES game-list background, with baked-in thumbnail placeholder | [view](../images/unused/spmpm.gdp.png) |
| `subst.bke` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Alternate UI: Arcade main menu background | [view](../images/unused/subst.bke.png) |
| `tsmcf.cpl` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Alternate UI: Arcade main menu background | [view](../images/unused/tsmcf.cpl.png) |
| `url.bvs` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | CPS1 game-list background | [view](../images/unused/url.bvs.png) |
| `werui.ioc` | 320x240 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | "NODATA" save-state thumbnail placeholder image, with a "horror" style typeface | [view](../images/unused/werui.ioc.png) |
| `wshom.ocx` | 1100x120 | BGRA | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Large icons for each system, including systems not supported by the SF2000 (normal) | [view](../images/unused/wshom.ocx.png) |
| `x86e.hgp` | 640x480 | RGB565 Little Endian | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | Neo Geo game-list background | [view](../images/unused/x86e.hgp.png) |
| `zaqrc.olc` | 8x224 | BGRA |  |  | ✨ | ✅ | ✅ | ✅ | ✅ | Rounded ends that pair with the warning dialogue stored in `mhg4s.ihg` | [view](../images/zaqrc.olc.png) |

## Other Files
These are other files that have been identified, which don't fit into the other categories. Non-Latin characters in the files are encoded in UTF-8.

| Filename | 03.15 | 04.20 | 05.15 | 1.5 | 1.6 | 1.7 | 1.71 | Description |
| -------- | ----- | ----- | ----- | --- | --- | --- | ---- | ----------- |
| `Archive.sys` | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | ✅ | Stores the settings for UI language and TV system. Two 32-bit words (4-bytes), little endian. The first is UI language; `0x00000000` is English, `0x01000000` is Chinese, etc.. The second is the TV system setting; `0x00000000` is NTSC, `0x01000000` is PAL. Note the "🚩" icon here indicates the format of the data, or the permissible values were changed (as opposed to the data itself, which will vary from device to device based on user settings) |
| `bfrjd.odb` |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in Korean |
| `bxvtb.sby` |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in Thai |
| `dufdr.cwr` |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in Turkish |
| `eknjo.ofd` |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in Spanish |
| `Favorites.bin` |  |  | ✨ | ✅ | ✅ | ✅ | ✅ | Used to store the list of ROMs added to the Favorites list; only appears after the first game is favourited after installing the 05.15 or later firmware. User ROMs cannot be added to favourites, only built-in games |
| `fhshl.skb` | ✨ | ✅ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in English |
| `Foldername.ini` | ✨ | 🚩 | 🚩 | ✅ | ✅ | ✅ | ✅ | Used to control menu rotation for the main menu; see below for more notes on this |
| `History.bin` |  |  | ✨ | ✅ | ✅ | ✅ | ✅ | Used to store the history of played ROMs; only appears after the first game is played after installing the 05.15 or later firmware. User ROMs are not added to history, only built-in games. If a built-in game that is referenced in history is removed from the device, the device will crash when trying to view the History screen. You can delete the History.bin file to clear the device's history; there is no built-in functionality to do so |
| `jsnno.uby` |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in Dutch |
| `kcbn7.avc` |  | ✨ | ❌ |  |  |  |  | Duplicate copy of `bisrv.asd`, the main firmware for the device which is found in the BIOS folder  |
| `KeyMapInfo.kmp` |  |  | ✨ | ✅ | ✅ | ✅ | ✅ | Used to store the user-assignable global button mappings for each emulated system |
| `lf9lb.cut` |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in Portuguese |
| `ntrcq.oba` |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in Japanese |
| `ouenj.dut` |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in Polish |
| `qdbec.ofd` |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in Italian |
| `sgotd.cwt` |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in French |
| `snbqj.uby` |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in German |
| `t2act.sgf` | ✨ | ✅ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in Chinese |
| `Test.zsf` |  | ✨ | ❌ |  |  |  |  | A SNES ROM, which displays a controller test program |
| `tvctu.uby` |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in Russian |
| `vdaz5.bjk` |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in Arabic |
| `wtrxj.lbd` |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in Malay |
| `xjebd.clq` |  | ✨ | 🚩 | ✅ | ✅ | ✅ | ✅ | UI strings in Hebrew |

### Foldername.ini
This file controls some of the UI settings for the main menu. It's a plain-text file, but not an actual INI file. It's contents from the 1.5 firmware (just as an example) are as follows:

```
SF2000
17
FFFFFF
FF8000 ROMS
FF8000 FC
FF8000 SFC
FF8000 MD
FF8000 GB
FF8000 GBC
FF8000 GBA
FF8000 ARCADE
FF8000 ROMS
FF8000 ROMS
8 7 0
24 184 144 208
40 24

```

And here's my current understanding of what each line is used for:

- `SF2000`: The name of the device; I don't believe it's actively used anywhere, please correct me if I'm wrong!
- `17`: The number of languages supported by the firmware
- `FFFFFF`: Hexadecimal colour (RGB) for the general game-list texts, and the `x/yyy` game count in the top-right corner of each game-list
- `FF8000 ROMS`: The first defined main menu section (the sections that are scrolled vertically on the main menu). Internally they are numbered from 0; so the `ROMS` section (user ROMs and settings) is 0, `FC` (NES) is 1, `SFC` (SNES) is 2, etc.. The `FF8000` is the hexadecimal colour (RGB) to display the text of the currently selected/highlighted game in the list; the default colour is orange. _Side note:_ after the `ARCADE` section, there's two additional `ROMS` sections; the firmware is hard-coded to have ten sections. The SF2000 appears to share its firmware with other similar devices, and some of those devices feature different menu sections (e.g., "CPS1", "Neo Geo", etc.). I suspect that the best of those systems has ten sections in its main menu, which doesn't match up with the eight sections on the SF2000 (seven supported systems + the user ROMs/settings section). As the firmware requires ten sections to be defined, they just repeated the `ROMS` section to fill in the remaining places. Like I say, that's just a guess!
- `8 7 0`: This is used to control the main menu rotation. `8` tells the firmware how many main menu sections are actually in-use on this device; for the SF2000 that's seven supported consoles + the user ROMs/settings section, for eight total. `7` tells the firmware which menu section to default to when the device boots up, which is why by default it always starts in the `ARCADE` section. `0` tells the firmware which section to display the special "user settings" menu on (the one with History, Favourites, TV System, Language, etc.). So for example, if you wanted the SF2000 to start up on the user ROMs/settings screen instead of Arcade, you could change this line to read `8 0 0`; or if you wanted the user ROMs/settings screen to be the _only_ screen available (e.g., if you were intending to hand the device to someone unfamiliar with retro emulation, and you wanted to reduce sources of confusion for them), you could set it to `1 0 0` (suggestion from `wyverino`)
- `24 184 144 208`: These numbers control the position and size of the game artwork in each system's game-list. The first two numbers are the X and Y coordinates from the top-left corner of the screen for where to start drawing the artwork; the second two numbers are the width and height of the artwork to draw. Note that the SF2000 doesn't do any image scaling; the dimensions are for the rectangular area the device will begin adding each pixel of the source artwork to. If the artwork's dimensions don't exactly match the dimensions specified here, the artwork will not display properly
- `40 24`: The width and height of the icon shown beside the currently selected/highlighted game in a game-list. Again, these are the dimensions of the rectangular area the SF2000 draws the pixel data into, so if these numbers don't match the dimensions of the list indicator image, the image will not display properly

NOTE: While the text colours above work just fine with the SF2000 _first_ boots up, after loading a game and returning to the menu the general game-list/game count colour reverts to an off-white colour, and is likely being pulled from inside the BIOS somewhere. Also note that currently there is no way to choose a highlight colour for the Favourites or History sections - those are fixed at the stock orange colour (FF8000), and are almost certainly hardcoded in the BIOS as well.

### Favourites and History
The `Favorites.bin` and `History.bin` files above both share the same file structure:

* The first 4 bytes are a little-endian Uint32 storing the number of entries in the list
* The rest of the file is composed of pairs of 2 byte little-endian Uint16s - the first byte pair is a number indicating which ROM list the entry belongs to (more on that below); the second number is the 0-based game number within that list

The ROM lists are numbered as follows:

| Number | ROM List | List File |
| ------ | -------- | --------- |
| 1 | NES | `rdbui.tax` |
| 2 | SNES | `urefs.tax` |
| 3 | Genesis/Mega Drive | `scksp.tax` |
| 4 | Game Boy | `vdsdc.tax` |
| 5 | Game Boy Color | `pnpui.tax` |
| 6 | Game Boy Advance | `vfnet.tax` |
| 7 | Arcade | `mswb7.tax` |

So, for example: if your most recently played game (first in the history list) was "Batman - The Video Game" for Game Boy, and that game happened to be the ninth game listed in the Game Boy section on your device, the fifth and sixth bytes in your `History.bin` would be `0x04 0x00` (which is `4` in decimal, i.e. the "Game Boy" ROM list), and the seventh and eighth bytes would be `0x08 0x00` (which is `8` in decimal, i.e. the 9th game in the 0-based list of Game Boy games). The `Favorites.bin` file works exactly the same way, just with games you've favourited rather than played recently.

For more information on the ROM lists in general, see the next section.

## ROM Lists
Credit for this section goes to `taizou`, author of [FROGTOOL](https://github.com/tzlion/frogtool). These files relate to the built-in game-lists under each main system; the list of games is pulled from these files instead of being built at runtime - annoying, but presumably for performance reasons. It means if you want to change the list of built-in games (instead of using the User ROMs section), you have to edit these files - hence FROGTOOL, you should really check it out. There is also a tool called [Tadpole](https://github.com/EricGoldsteinNz/tadpole) by `.ericgoldstein` which provides a GUI for FROGTOOL along with some additional features.

| Files | Description |
| ----- | ----------- |
| `mfpmp.bvs` (Arcade), `mgdel.bvs` (Game Boy Color), `nethn.bvs` (NES), `qdvd6.bvs` (Game Boy), `sppnp.bvs` (Game Boy Advance), `wmiui.bvs` (Genesis/Mega Drive), `xvb6c.bvs` (SNES) | Pinyin translations of the English ROM names, used for Chinese language searching. Not all game names are translated |
| `adsnt.nec` (SNES), `fhcfg.nec` (NES), `htuiw.nec` (Game Boy Advance), `msdtc.nec` (Arcade), `setxa.nec` (Genesis/Mega Drive), `umboa.nec` (Game Boy), `wjere.nec` (Game Boy Color) | Chinese translations of the English ROM names, used to display the game-lists when the UI language is set to Chinese. Not all game names are translated |
| `mswb7.tax` (Arcade), `pnpui.tax` (Game Boy Color), `rdbui.tax` (NES), `scksp.tax` (Genesis/Mega Drive), `urefs.tax` (SNES), `vdsdc.tax` (Game Boy), `vfnet.tax` (Game Boy Advance) | English ROM Names, used to display the game-lists when the UI language is set to English |
| `xfgle.hgp`, `xfgle.hgp.bak` | The `xfgle.hgp` file is a plain-text file containing the ROM "shortcuts" on the main menu for each game system. The `xfgle.hgp.bak` file appears to be a test version of this file that was not removed from the firmware before being sent to production |
| `TSMFK.TAX` | This is a ROM list file similar to the other `.tax` files, except it is built at run-time from the ROM files in the user roms folder. The file is regenerated each time the device boots |

## Sounds
There are several sound files in the `20230420` firmware, stored in raw signed 16-bit PCM format (mono, little-endian at 22050 Hz). The SF2000 seems to play the files back at an incorrect sample rate vs. the raw data; if you want to customise the background music, resample your audio to 21560 Hz (21561.1 Hz is technically precise, but 21560 Hz is easer to remember, and all but the most exacting of human ears is unlikely to detect the difference), and then speed the audio up to 22050 Hz, using the resulting audio as the raw data (credit to `notv37` in Discord for doing the initial discovery math, and to `bnister` for doing technical follow-up in the firmware - you can [read their deep-dive into the details here](https://discord.com/channels/741895796315914271/1099465777825972347/1112643797344583710) (Discord link - you may need to be a member of the [`Retro Handhelds` Discord server](https://discord.gg/retrohandhelds) first for the link to work)).

If you want to do it using [Audacity](https://www.audacityteam.org/), the steps are:

1. Open your audio file; there's a hard-coded limit of 1 minute 30 seconds on the maximum length of the audio you can use, so if your audio file is longer than that, you'll need to trim it to be 1 minute 30 seconds or shorter (longer audio will glitch)
2. Click the "Audio Setup" button on the top toolbar, choose "Audio Settings..."
    * Set "Project Sample Rate" to "22050 Hz"
    * Click "OK"
3. Click the "Select" button in the lower-left corner of your audio track area to select all the audio
4. If your track is stereo, down-mix to mono: "Tracks" menu > "Mix" > "Mix Stereo Down to Mono"
5. "Tracks" menu > "Resample..."
    * Set "New sample rate (Hz)" to "22050"
    * Click "OK"
6. "Effect" menu > "Pitch and Tempo" > "Change Speed..."
    * Set "Speed Multiplier" to "1.023"
    * Click "Apply" (your audio will now sound slightly too high-pitched if you play it back, but don't worry - the SF2000 plays everything slightly slow/low-pitched, so we speed/pitch things up before exporting so it plays back correctly)
7. "File" menu > "Export" > "Export Audio..."
    * Set "Save as type" to "Other uncompressed files"
    * In "Format Options", set "Header" to "RAW (header-less)"; set "Encoding" to "Signed 16-bit PCM"
    * Enter your "File name" as `pagefile.sys`, and click "Save"
    * If the "Edit Metadata Tags" window appears, just leave everything blank and click "OK"
8. Replace the existing `pagefile.sys` file in the `Resources` folder on your SF2000 microSD card

`dteyn` has also created a Python script called `Kerokero` which can take a `.WAV` file, trim it if it's longer than 90 seconds, and convert it to a `pagefile.sys` for you - you can [find Kerokero here](https://github.com/Dteyn/SF2000_BGM_Tool).

| Filename | 03.15 | 04.20 | 05.15 | 1.5 | 1.6 | 1.7 | 1.71 | Description | Listen |
| -------- | ----- | ----- | ----- | --- | --- | --- | ---- | ----------- | ------ |
| `c2fkec.pgt` | ✨ | ✅ | 🚩 | ✅ | ✅ | ✅ | ✅ | "Popping" sound that is played when moving around the search keyboard | [listen](../sounds/c2fkec.pgt.mp3) |
| `dpnet.dll` | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | "Downwards Zap" sound, unknown usage | [listen](../sounds/dpnet.dll.mp3) |
| `dsreg.bvs` | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | "Upwards Bleeping" sound, unknown usage | [listen](../sounds/dsreg.bvs.mp3) |
| `help.lis` | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | "Double Buzzer" sound, unknown usage | [listen](../sounds/help.lis.mp3) |
| `mfsvr.nkf` | ✨ | ✅ | 🚩 | ✅ | ✅ | ✅ | ✅ | "Beep" sound that is played when entering a letter on the search keyboard | [listen](../sounds/mfsvr.nkf.mp3) |
| `nyquest.gdb` | ✨ | ✅ | 🚩 | ✅ | ✅ | ✅ | ✅ | "Whooshing" sound that is played when switching between emulated systems on the main menu, between the "Resume", "Quit", "Load" and "Save" options on the in-game menu, and scrolling by pages within a system's game-list | [listen](../sounds/nyquest.gdb.mp3) |
| `oldversion.kbe` | ✨ | ✅ | 🚩 | ✅ | ✅ | ✅ | ✅ | "Three Note Upward Chime" sound that is played when deleting a letter on the search keyboard | [listen](../sounds/oldversion.kbe.mp3) |
| `pagefile.sys` | ✨ | ✅ | 🚩 | ✅ | ✅ | ✅ | ✅ | Main menu background music. If you don't like background music, and would rather just have silence, you can [find a replacement silent `pagefile.sys` here](../sounds/silentMusic/pagefile.sys) - just replace the one in the `Resources` folder (don't forget to backup the original file first, in case you ever want that jaunty tune again!) | [listen](../sounds/pagefile.sys.mp3) |
| `swapfile.sys` | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | "Squishy" sound played when navigating horizontally through "shortcut" games on the main menu, or vertically within a system's game-list | [listen](../sounds/swapfile.sys.mp3) |

If you would like to silence all the _UI_ sounds (everything other than the background music), `dteyn` has created a [Silent Sounds Pack](https://github.com/Dteyn/sf2000/raw/main../sounds/silentSounds/SF2000_Silent_Sounds_Pack.zip) (direct link to `.zip`). It contains eight replacement silent audio files - just drop them into the `Resources` folder on the microSD card, replacing the eight current files, and say goodbye to the SF2000's UI noises.

## Unknown Files
These are files that I have not yet determined what they do; if anyone has any information on these, do post about it in the Data Frog channel in the Retro Handhelds Discord server please!

| Filename | 03.15 | 04.20 | 05.15 | 1.5 | 1.6 | 1.7 | 1.71 | Description |
| -------- | ----- | ----- | ----- | --- | --- | --- | ---- | ----------- |
| `kcnuv.lit` | ✨ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | UNKNOWN; a bunch of 4-byte binary chunks (e.g., `0xC4 0x00 0x00 0x00`), followed by a list of .NES ROM file names. Very similar to the `.bvs`/`.nec`/`.tax` files detailed above, but doesn't have the same type of "header" they have |

## Notes For Theme Creators
This section isn't really about the `Resources` files per-se, but it's tangentially related. The fact that the SF2000's UI resources are pulled from the microSD card opens up the door to "theming" the device, which is great. However, if you do decide you want to make a theme for the SF2000, here's a few things I've found that you may want to bear in mind:

- If you're including background music in your theme, note that when the SF2000 starts up it fails to output about the first 1 second of audio; therefore, if you'd like the person using your theme to hear your background music from the start, cut one second off the end of your background music loop, and move it to the start of the loop instead.
- If you're creating custom system logos (`sfcdr.cpl`), make sure the logos don't overlap the "Games Exist" image's screen area (`exaxz.hsp`, top-left coordinate `456, 88`, width and height `152, 72`); the main menu compositor clips an area of the section's _background_ image behind where the "Games Exist" artwork will be drawn, renders the "Games Exist" artwork into that clipped section, and then draws the result _on top_ of the system logo. As a result, any pixels of the system logo that should be visible in that area will be replaced by the background image, even if you make the "Games Exist" image fully transparent. Removing the `exaxz.hsp` file entirely doesn't work either, as you get garbage drawn on the screen in the same area instead. The only section not impacted by this is the "User ROMs and Settings" section, as on that screen the "Games Exist" artwork is not drawn.
  - There's a workaround, but it's not perfect: you can bake a system's logo directly into the background for its main-menu section, and make it's portion of `sfcdr.cpl` fully transparent (so that you don't see the logo physically moving). As the code for drawing the "Games Exist" image pulls from the section's background, it'll pull the portion that overlaps with the system logo and render that too. The _downside_ is that the poor draw code of the stock OS only updates the horizontal portion of the screen that contains the rotating logos during section transitions, and only draws the lower portion of the screen (the bit under the rotating logos) afterwards. So baking your logo into background for the section will create some artificial "latency" for the theme user - they'll see the new logo appear instantly, then have to wait the quarter second for the invisible "rotation" animation to complete, before the lower portion of the screen with the new shortcuts for the new section appears.
  - One _other_ workaround (that's even worse than the first workaround): bake just the portion of the system logo that overlaps with `exaxz.hsp` into the background. Doing it this way, you can still have your custom system logo in `sfcdr.cpl`, and still have it in the rotation animation (which gives the user something to look at, and reduces that fake "latency" feeling from the workaround above)... but you'll see the bit of logo baked into the background appear instantly, and then the rotating logo will slide up/down to meet it, so it'll still look a bit janky. So really it comes down to picking your particular flavour of jank: scaling your logos to avoid the `exaxz.hsp` screen area (which might leave you with a lot of empty space), baking your logo into the section background (adding fake "latency" to the experience), or only partially baking your logo into the section background (which will make things look jank during the rotation animation, but perfect otherwise)... the decision is yours!
- When designing your theme, think carefully about the use case in which you want your theme to look best. Although the SF2000 uses many different UI images at many different scales, internally the screen area it draws to is `640 x 480` pixels in size. However, the actual physical display is only `320 x 240`; as the SF2000's OS does not do any image resampling when downscaling its UI output to the screen, what essentially happens is every second row and column of pixels is thrown away - and as a result, a theme designed for the internal `640 x 480` resolution can look a bit aliased or "jagged" on the internal display. If you want your theme to look pixel-perfect on the internal display, design it for `320 x 240` instead (i.e., for any image asset you create, design and create it at half of the original resolution of the same file in the stock SF2000 theme), and perform a nearest-neighbour upscale of the image back to the original resolution when converting it to an SF2000 data format. The resulting images will be pixel perfect on the internal display. _HOWEVER... there is one major downside to do thing this_: AV output. When using the AV output of the SF2000, it does so at 576i - higher than the resolution of the internal display. If you're using a theme that was scaled up from a `320 x 240` design base, you can clearly see pixelisation of the UI assets on the external display; a `640 x 480` based theme displays smooth assets. So what if you want to design a theme that looks decently sharp (not aliased) on the internal display, _and_ looks decently smooth on an external display, then design your theme for three-quarters resolution (`480 x 360` design base), and do a bilinear upscale to `640 x 480` based resolutions during final data conversion. To summarise:
  - If you only care about how your theme looks on the internal display, and don't care about how it looks on AV output, design for a `320 x 240` base resolution and do a **nearest-neighbour** 2x upscale when converting to SF2000 formats
  - If you only care about how your theme looks via AV out, and don't care about it looking aliased/jagged on the internal display, design for the regular `640 x 480` base
  - If you care about both display types, and want your theme to look great (but not perfect) on both, design for a three-quarters `480 x 360` base, and do a **bilinear** upscale to regular `640 x 480` base resolutions when converting to SF2000 formats