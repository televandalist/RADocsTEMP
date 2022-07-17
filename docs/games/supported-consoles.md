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
|37|Amstrad CPC| |Cap32|Yes|• Core does not currently support writing to disk - may affect hashing when implemented|
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