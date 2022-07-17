---
hide:
  - toc
---

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