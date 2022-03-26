## Supported Consoles

|Console ID|Console Name|Standalones|Cores|RALib Support|Notes|
|---|---|---|---|---|---|
|1|• Sega Genesis<br>• Mega Drive| |Genesis Plus GX<br>Picodrive|Yes|   |
|2|Nintendo 64|Project64 |ParaLLEl N64<br>Mupen64Plus-Next|Yes|   |
|3|• SNES<br>• Super Famicom<br>• Satellaview<br>• Sufami Turbo|RASnes9x|Snes9x<br>Mesen-S|Yes|   |
|4|Game Boy|RAVBA|Gambatte<br>Gearboy<br>VBA-M|Yes|• mGBA [crashes when unloading](https://github.com/libretro/mgba/issues/188) the core because RALibretro doesn't implement the camera interface|
|5|Game Boy Advance|RAVBA|mGBA<br>VBA-M<br>Beetle GBA<br>VBA Next|Yes|   |
|6|Game Boy Color|RAVBA|Gambatte<br>Gearboy<br>VBA-M|Yes|   |
|7|• NES<br>• Famicom<br>• Famicom Disk System|RANes|Mesen<br>FCEUmm<br>QuickNES|Yes|   |
|8|• TurboGrafx-16<br>• PC Engine<br>• TurboGrafx-CD<br>• PC Engine CD<br>• SuperGrafx| |Beetle PCE FAST<br>Beetle SuperGrafx|Yes|• SuperGrafx games do not work on the Beetle PCE FAST core|
|9|• Mega CD<br>• Sega CD| |Genesis Plus GX|Yes|Appears to still have unmapped RAM (Ecco 1+2)|
|10|Sega 32X| |PicoDrive|Yes|• Several games are problematic|
|11|• Master System<br>• Mark III|RAMeka|Genesis Plus GX<br>Gearsystem<br>Picodrive|Yes|   |
|12|PlayStation| |Beetle PSX<br>Beetle PSX HW<br>PCSX ReARMed<br>SwanStation|Yes|   |
|13|Atari Lynx| |Beetle Lynx<br>Handy|Yes|   |
|14|• Neo Geo Pocket<br>• Neo Geo Pocket Color| |Beetle NeoPop|Yes|   |
|15|Game Gear|RAMeka|Genesis Plus GX<br>Gearsystem|Yes|   |
|17|Atari Jaguar| |Virtual Jaguar|Yes|• No savestate support<br> • [Many issues with the emulation](https://github.com/libretro/virtualjaguar-libretro/issues/38)|
|18|Nintendo DS| |DeSmuME<br>MelonDS|Yes|• Limited Microphone Support<br>• No DSi support|
|23|Magnavox Odyssey 2||O2EM|Yes|   |
|24|Pokemon Mini| |PokeMini|Yes|   |
|25|Atari 2600| |Stella|Yes|   |
|27|Arcade| |FinalBurn Neo|Yes|•  Needs Updated Board List<br>• Some boards may not be fully exposed|
|28|Virtual Boy| |Beetle VB|Yes|   |
|29|MSX/MSX2| |blueMSX|Yes|• Hash relies on dsk file not being modified<br>• .DSK files appear to be unsupported if they also require a cartridge (typically a "sound" cartridge, which was the case with SD Snatcher). There is a core option for this, but it doesn't seem to function properly.|
|33|SG-1000|RAMeka|Genesis Plus GX<br>blueMSX|Yes|   |
|38|Apple II|RAppleWin| |No|   |
|39|Saturn| |Beetle Saturn<br>Yabause<br>Kronos|Yes|• Saving or Loading states in Kronos often locks up the UI in RALibretro|
|40|Dreamcast| |flycast| Yes |• Must disable threaded rendering to use save states|
|41|PlayStation Portable| |PPSSPP|Yes|• Loading save states too fast can cause it to crash<br>• Some games have various graphical issues|
|43|3DO Interactive Multiplayer| |Opera|Yes|   |
|44|ColecoVision|RAMeka|blueMSX|Yes|   |
|45|Intellivision| |FreeIntV|Yes|• Controls are much better than they were<br>• Crashes if game is reset<br>• Some crashes that might be related to Intellivoice|
|46|Vectrex| |VecX|Yes|   |
|47|• PC-8001<br>• PC-8801|RAQUASI88|QUASI88|No|• QUASI88 crashes RALib [when loading core](https://github.com/libretro/quasi88-libretro/issues/35). Core [writes over dsk file when emulator writes to dsk](https://github.com/libretro/quasi88-libretro/issues/44) - this breaks hashing<br>• PC-88VA not supported|
|49|PC-FX| |Beetle PC-FX|Yes|   |
|51|Atari 7800| |ProSystem|Yes|   |
|53|• WonderSwan<br>• WonderSwan Color| |Beetle WonderSwan|Yes|   |
|63|Watara Supervision| |Potator|Yes|   |

## Supported But Not Validated

|Console ID|Console Name|Standalones|Cores|RALib Support|Notes|
|---|---|---|---|---|---|
|37|Amstrad CPC| |Cap32|Needs Work|• Updates seem to have made it fully functional<br>• Uncertain how core handles writing to disk - may affect hashing|
|56|Neo Geo CD| |NeoCD| |• Appears fully functional<br>• Needs hashing method|
|71|Arduboy| |Arduous| |• Appears fully functional<br>• Needs hashing method|

## Unsupported Consoles

|Console ID|Console Name|Standalones|Cores|RALib Support|Notes|
|---|---|---|---|---|---|
|16|GameCube| |Dolphin|Needs work|Generates sound but not video in RALibretro|
|19|Wii| |Dolphin|Needs work|Crashes RALib when testing|
|20|Wii U| |   |   |Untested|
|21|PlayStation 2| |Play!|   |Low compatibility with most commercial games; black screen with stuttering sound|
|21|PlayStation 2| |PCSX2| |PCSX2 is still in an alpha state, does not yet expose memory|
|22|Xbox| |   |   |   |
|26|DOS| |dosbox-pure|Needs work|• Needs a reliable hashing method<br>• Needs a way to prevent launching with user-specified command-line parameters<br>• Needs a way to prevent TSRs|
|30|Commodore 64| |vice_x64|Needs Work|• Save disks are generated with a virtual command (`#SAVEDISK:`) in the m3u (how to ignore for hashing?)<br>• How to handle multi-disk games that come in a zip _without an m3u_?|
|31|ZX81| |EightyOne|Needs Work|• Memory not exposed.|
|32|Oric| |   |   |   |
|34|Vic-20| |   |Needs Work|Untested with proper BIOS.|
|35|Amiga| |P-UAE|Needs Work|• Seems to run fine if zips are loaded. Memory is not exposed.|
|36|Atari ST| |Hatari|Needs Work|• Memory not exposed. Games seem to run fine.|
|42|Philips CD-I| |SAME CDi| |Untested|
|48|PC-9800| |np2kai|Needs Work|• Memory is not exposed. It *appears* to be exposed in some games depending on the RAM size selected, but it seems like it's machine RAM and not actually related to the game(s).<br>Performance wise, all games tested run without issues.|
|50|Atari 5200| |Atari800|Needs Work|• Appears to work fine, but the core itself is a bit of a headache. The BIOS has to be configured within the core (F1 > Emulator Configuration > System ROM settings).<br>• Couldn't figure out controls - does Joystick also need to be configured within the core?<br>• Currently allows loading arbitrary files from the internal menu, bypassing hashing. Can't be supported in hardcore unless that can somehow be blocked.|
|52|Sharp X68K| |px68k|   |Crashes RALib upon loading a game|
|54|Cassette Vision| |   |   |   |
|55|Super Cassette Vision| |   |   |Currently only playable in MAME, which cannot be supported|
|57|Fairchild Channel-F| |FreeChaF<br>FBNeo|   |FreeChaF exposes memory, but has some control issues<br>FBNeo appears fine|
|58|FM Towns| |   |   |   |
|59|ZX Spectrum| |FUSE| |• Requires rcheevos memory map to leverage memory descriptors<br>• Requires ability to map keyboard to port 3 (RALibretro)<br>• Uncertain about save support; cannot seem to insert save disk|
|60|Game & Watch| |gw| |• Doesn't expose memory yet|
|61|Nokia N-Gage| |   |   |   |
|62|Nintendo 3DS| |Citra| |• Only exposes 64MB of memory - documentation suggests there should be 128MB.<br>• Does not support save states|
|64|Sharp X1| |X1 Millennium| |• Does not expose memory<br>• [Crashes RALibretro](https://github.com/r-type/xmil-libretro/issues/3)<br>• Uncertain how core handles writing to disk/tape - may affect hashing|
|65|TIC-80| |TIC-80|   |• Doesn't expose memory correctly (only see 8 bytes)|
|66|Thomson TO8/TO8D| |Theodore| |Seems to work. Uncertain how core handles writing to disk/tape - may affect hashing|
|67|PC-6001| |N/A| | |
|68|Sega PICO| |Picodrive|   |Can't be controlled fully, needs controls related to turning pages in attached books|
|69|Mega Duck| |SameDuck| |• Shares SameBoy's issue of reinitializing memory |
|70|Zeebo| |N/A | | |

## Does Not Have Console ID

|Console ID|Console Name|Standalones|Cores|RALib Support|Notes|
|---|---|---|---|---|---|
|   |PocketStation| |pockystation| |Core doesn't seem functional even in Retroarch|
|   |VMU| |VeMUlator| |Untested |
|   |J2ME| |freej2me| |Untested |

***

