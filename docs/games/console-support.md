## Console Support

#### 3DO Interactive Multiplayer
* ✅ libretro core: **Opera**
    - Some issues depending on BIOS

#### Amiga
* ❌ libretro core: **P-UAE**
    - Needs memory map to see exposed memory
    - Locks disk files so they can't be opened for hashing
    - Hard disk support?

#### Amstrad CPC
* ✅ libretro core: **Caprice32**
    - Core does not currently support writing to disk, which may affect hashing
      when implemented
* ❌ libretro core: **CrocoDS**

#### Apple II
* ✅ Standalone emulator: **[RAppleWin](https://retroachievements.org/download.php#rapplewin)**
* ⌛ Bizhawk core: **Virtu (Port)**
    - Testing and pending rollout

#### Arcade
* ✅ libretro core: **FinalBurn Neo**
    - Some boards may not be fully exposed
* ✅ libretro core: **flycast**
    - Used for Atomiswave, NAOMI, and NAOMI2
* ❌ libretro core: **FB Alpha**
    - Deprecated

#### Arcadia 2001
* ⌛ Standalone emulator: **[WinArcadia](https://amigan.1emu.net/releases/)**
    - Pending rollout

#### Arduboy
* ✅ libretro core: **Arduous**

#### Atari 2600
* ✅ libretro core: **Stella**
* ⌛ Bizhawk core: **AtariHawk**
    - Testing and pending rollout

#### Atari 5200
* ❌ _Not supported_ - needs hashing method and memory map
* ❌ libretro core: **atari800**
    - Appears to work fine, but the core is a bit of a headache to use.
        - The BIOS has to be configured within the core (F1 > Emulator
          Configuration > System ROM settings)
    - Couldn't figure out controls - does the joystick need to be configured
      within the core too?
    - Allows loading arbitrary files from the internal menu, which bypasses
      hashing
* ❌ libretro core: **a5200**
    - Does not expose memory

#### Atari 7800
* ✅ libretro core: **ProSystem**
* ⌛ Bizhawk core: **A7800Hawk**
    - Testing and pending rollout

#### Atari Jaguar
* ✅ libretro core: **Virtual Jaguar**
    - No save state support
    - [Many issues with emulation](https://github.com/libretro/virtualjaguar-libretro/issues/38)

#### Atari Jaguar CD
* ⌛ Bizhawk core: **Virtual Jaguar**
    - Pending rollout
    - Some formats not supported

#### Atari Lynx
* ✅ libretro core: **Beetle Lynx**
* ✅ libretro core: **Handy**
* ⌛ Bizhawk core: **Handy (Port)**
    - Testing and pending rollout

#### Atari ST
* ❌ _Not supported_ - needs hashing method and memory map
* ❌ libretro core: **Hatari**
    - Memory not exposed

#### Cassette Vision
* ❌ _Not supported_ - needs hashing method and memory map

#### CHIP-8
* ❌ _Not supported_ - needs console ID, hashing method and memory map
* ❌ libretro core: **Emux CHIP-8**
* ❌ libretro core: **JAXE**
    - 16 Apr 22 - Seems ready when we are
    - May need settings blacklist to prevent lowering speed

#### Commodore 64
* ❌ _Not supported_ - needs memory map
* ❌ libretro core: **vice_x64**
    - NOTE: Joystick is in port 2 by default. Use JOY button on virtual keyboard
      (select) to switch it to port 1.
    - 1 May 2022 - Reset does not autorun game
    - 1 May 2022 - Hashing often fails because core has a lock on the file
* ⌛ Bizhawk core: C64Hawk
    - Pending rollout
    - Some formats are problematic. Tapes do not load.

#### ColecoVision
* ✅ Standalone emulator: **[RAMeka](https://retroachievements.org/download.php#rameka)**
* ✅ libretro core: **blueMSX**
* ⌛ Bizhawk core: **ColecoHawk**
    - Testing and pending rollout

#### Elektor TV Games Computer
* ⌛ Standalone emulator: **[WinArcadia](https://amigan.1emu.net/releases/)**
    - Pending rollout
    - TVGC may be scrapped in favor of Interton VC 4000.

#### Fairchild Channel-F
* ✅ libretro core: **FreeChaF**

#### Famicom Disk System
* ✅ Standalone emulator: **[RANes](https://retroachievements.org/download.php#ranes)**
* ✅ libretro core: **FCEUmm**
* ✅ libretro core: **Mesen**

#### FM Towns
* ❌ _Not supported_ - needs hashing method and memory map

#### Game & Watch
* ❌ _Not supported_ - needs hashing method and memory map
* ❌ libretro core: **gw**
    - Does not expose memory

#### Game Boy
* ✅ Standalone emulator: **[RAVBA](https://retroachievements.org/download.php#ravba)**
* ✅ libretro core: **Gambatte**
* ✅ libretro core: **Gearboy**
* ✅ libretro core: **VBA-M**
* ❌ libretro core: **mGBA**
    - 13 May 2020 - [crashes when unloading](https://github.com/libretro/mgba/issues/188) the core because RALibretro doesn't implement the camera interface

#### Game Boy Color
* ✅ Standalone emulator: **[RAVBA](https://retroachievements.org/download.php#ravba)**
    - Cartridge RAM may appear as all FFs
* ✅ libretro core: **Gambatte**
* ✅ libretro core: **Gearboy**
* ✅ libretro core: **VBA-M**
* ⌛ Bizhawk core: **Gambatte**
    - Testing and pending rollout
* ⌛ Bizhawk core: **GBHawk**
    - Testing and pending rollout

#### Game Boy Advance
* ✅ Standalone emulator: **[RAVBA](https://retroachievements.org/download.php#ravba)**
* ✅ libretro core: **VBA-M**
* ✅ libretro core: **Beetle GBA**
* ✅ libretro core: **VBA Next**
* ✅ libretro core: **mGBA**
* ⌛ Bizhawk core: **VBA**
    - Testing and pending rollout
* ⌛ Bizhawk core: **mGBA**
    - Testing and pending rollout

#### GameCube
* ❌ _Not supported_ - needs hashing method and memory map
* ❌ Standalone emulator: **Dolphin**
* ❌ libretro core: **Dolphin**

#### Game Gear
* ✅ Standalone emulator: **[RAMeka](https://retroachievements.org/download.php#rameka)**
* ✅ libretro core: **Genesis Plus GX**
* ✅ libretro core: **GearSystem**

#### Genesis / Mega Drive
* ✅ libretro core: **Genesis Plus GX**
* ✅ libretro core: **Picodrive**
* ✅ libretro core: **Blastem**
* ⌛ Bizhawk core: **Genplus-GX**
    - Testing and pending rollout

#### Intellivision
* ✅ libretro core: **FreeIntV**
    - Crashes when game is reset
    - Some crashes which might be related to Intellivoice
* ⌛ Bizhawk core: **Intellihawk**
    - Testing and pending rollout

#### Interton VC 4000
* ⌛ Standalone emulator: **[WinArcadia](https://amigan.1emu.net/releases/)**
    - Rollout pending

#### J2ME
* ❌ _Not supported_ - needs console ID, hashing method and memory map
* ❌ libretro core: **freej2me**

#### Magnavox Odyssey 2
* ✅ libretro core: **O2EM**
* ⌛ Bizhawk core:
    - Testing and pending rollout

#### Master System | Mark III
* ✅ Standalone emulator: **[RAMeka](https://retroachievements.org/download.php#rameka)**
* ✅ libretro core: **Gearsystem**
* ✅ libretro core: **Genesis Plus GX**
* ✅ libretro core: **Picodrive**
* ⌛ Bizhawk core:
    - Testing and pending rollout

#### Mega Duck
* ✅ libretro core: **SameDuck**

#### MS-DOS
* ❌ _Not supported_ - needs hashing method and memory map
* ❌ libretro core: **dosbox-core**
* ❌ libretro core: **dosbox-SVN**
* ❌ libretro core: **dosbox-pure**
    - Needs a way to prevent launching with user-specified command line parameters
    - Needs a way to prevent TSRs
    - Needs a way to deactivate achievements if game drops to command prompt

#### MSX
* ✅ libretro core: **blueMSX**
    - Hash relies on .DSK file not being modified
    - .DSK files appear to be unsupported if they also require a cartridge. There
      is a core option for this, but it doesn't seem to function properly. See
      "SD Snatcher", which used a 'sound' cartridge.

#### Neo Geo CD
* ⌛ libretro core: **NeoCD**
    - Appears fully functional

#### Neo Geo Pocket
* ✅ libretro core: **Beetle NeoPop**
* ⌛ Bizhawk core: **Beetle NeoPop (Port)**
    - Testing and pending rollout

#### Neo Geo Pocket Color
* ✅ libretro core: **Beetle NeoPop**
* ⌛ Bizhawk core: **Beetle NeoPop (Port)**
    - Testing and pending rollout

#### NES / Famicom
* ✅ Standalone emulator: **[RANes](https://retroachievements.org/download.php#ranes)**
* ✅ libretro core: **FCEUmm**
* ✅ libretro core: **Mesen**
* ✅ libretro core: **QuickNES**
* ❌ libretro core: **NEStopia**
    - Does not map SRAM

#### Nintendo 3DS
* ❌ _Not supported_ - needs hashing method and memory map
* ❌ libretro core: **Citra**
    - Only exposes 64MB of memory - documentation suggests there should be 128MB.
    - Does not support save states

#### Nintendo 64
* ✅ Standalone emulator: **[RAProject64](https://retroachievements.org/download.php#rap64)**
* ✅ libretro core: **ParaLLEl N64**
    - RALibretro does not map C buttons correctly
* ✅ libretro core: **Mupen64Plus-Next**
    - RALibretro does not map C buttons correctly
* ❌ Bizhawk core: **Mupen64plus**
    - Many games have various graphical issues

#### Nintendo DS
* Limited microphone support
* ✅ libretro core: **DeSmuME**
* ✅ libretro core: **DeSmuME 2015**
* ✅ libretro core: **melonDS**
* ⌛ Bizhawk core: **MelonDS**
    - Testing and pending rollout

#### Nintendo DSi
* ⌛ Bizhawk core: **melonDS**
    - Rollout in progress
    - Saving is currently not supported
* ❌ libretro core: **DeSmuME**
* ❌ libretro core: **melonDS**

#### Nokia N-Gage
* ❌ _Not supported_ - needs hashing method and memory map

#### Oric
* ❌ _Not supported_

#### PC Engine | TurboGrafx-16 | SuperGrafx
* ✅ libretro core: **Beetle PCE Fast**
    - SuperGrafx games do not work on the Beetle PCE Fast core
* ✅ libretro core: **Beetle SuperGrafx**

#### PC Engine CD | TurboGrafx-CD
* ✅ libretro core: **Beetle PCE Fast**
* ✅ libretro core: **Beetle SuperGrafx**
* ⌛ Bizhawk core:
    - Testing and pending rollout

#### PC-6001
* ❌ _Not supported_ - needs hashing method and memory map

#### PC-8800
* ✅ Standalone emulator: **[RAQuasi88](https://retroachievements.org/download.php#raquasi88)**
* ❌ libretro core: **quasi88**
    - PC-88VA not supported
    - 16 Apr 2022 - Cannot load m3u. Hash fails because core locks disk file.
    - 16 Apr 2022 - Attempting to load a single disk game in RALibretro just
      goes to "How many disks?" prompt. Seems to work in RetroArch
    - 16 Apr 2022 - RALibretro does not provide subsystem interface for loading
      multi-disk games
    - Technically supported; not recommended.

#### PC-9800
* ❌ _Not supported_ - needs hashing method and memory map
* ❌ libretro core: **Neko Project II Kai**
    - Memory is not exposed.
        - It appears to be exposed in some games depending on the RAM size
          selected, but it seems like the machine RAM and not actually related
          to the game.

#### PC-FX
* ✅ libretro core: **Beetle PC-FX**
* ⌛ Bizhawk core:
    - Testing and pending rollout

#### Philips CD-I
* ❌ _Not supported_ - needs hashing method and memory map
* ❌ libretro core: **SAME CDi**

#### Pico-8
* ❌ _Not supported_ - needs hashing method and memory map
* ❌ libretro core: **FAKE-08**

#### PlayStation
* ✅ Standalone emulator: **[DuckStation](https://www.duckstation.org/wiki/Main_Page)**
    - There may be memory leak and/or burn-in when using save states. Softcore players beware!
* ✅ libretro core: **Beetle PSX HW**
    - Most recommended
* ✅ libretro core: **Beetle PSX**
* ✅ libretro core: **ReARMed**
    - BIOS are not required for this core and will zero out the Kernal RAM.
    - Technically supported; not recommended.
* ✅ libretro core: **SwanStation**
* ⌛ Bizhawk core: **psxhawk**
    - Testing and pending rollout

#### PlayStation 2
* ✅ Standalone emulator: **[PCSX2](https://pcsx2.net/)**
    - PCSX2 is currently **the only officially supported** option for earning achievements.
* ❌ libretro core: **PCSX2**
    - Still in alpha state
    - Does not expose memory
* ❌ libretro core: **play**
    - Low compatibility with most commerical games
    - Black screen with stuttering sound

#### PlayStation Portable
* ✅ libretro core: **PPSSPP**
    - Loading save states too fast can cause it to crash
    - Some games have graphical issues 

#### PocketStation
* ❌ _Not supported_ - needs console ID, hashing method and memory map
* ❌ libretro core: **pockystation**
    - Core doesn't seem functional, even in RetroArch

#### Pokemon Mini
* ✅ libretro core: **PokeMini**

#### Sega 32X
* ✅ libretro core: **PicoDrive**
    - Several games are problematic
    - Appears to still have unmapped RAM

#### Sega CD
* Appears to still have unmapped RAM
* ✅ libretro core: **Genesis Plus GX**
* ✅ libretro core: **Picodrive**

#### Sega Dreamcast
* ✅ libretro core: **flycast**
    - Must disable threaded rendering to use save states

#### Sega Pico
* ❌ _Not supported_ - needs hashing method and memory map
* ❌ libretro core: **picodrive**
    - Needs controls related to turning pages in the attached books

#### Sega Saturn
* ✅ libretro core: **Beetle Saturn**
    - The only *recommended* core
* ❌ libretro core: **Yabause**
    - Technically supported; not recommended.
* ❌ libretro core: **Kronos**
    - Saving and loading states often locks up the UI in RALibretro
    - Technically supported; not recommended.
* ⌛ Bizhawk core: **Beetle Saturn**
    - Testing and pending rollout

#### SG-1000
* ✅ Standalone emulator: **[RAMeka](https://retroachievements.org/download.php#rameka)**
* ✅ libretro core: **Genesis Plus GX**
* ✅ libretro core: **blueMSX**

#### Sharp X1
* ❌ _Not supported_ - needs hashing method and memory map
* ❌ libretro core: **X1 Millennium**
    - 16 Apr 2022 - Disk writes modify source media, which breaks hashing

#### Sharp X68K
* ❌ _Not supported_ - needs hashing method and memory map
* ❌ libretro core: **px68k**
    - Crashes RALibretro upon loading a game

#### SNES | Super Famicom | Satellaview | Sufami Turbo
* ✅ Standalone emulator: **[RASnes9x](https://retroachievements.org/download.php#rasnes9x)**
* ✅ libretro core: **RASnes9x**
    - Most recommended
* ✅ libretro core: **Mesen-S**

#### Super Cassette Vision
* ❌ _Not supported_ - needs hashing method
* ❌ libretro core: **EmuSCV**

#### Thomson TO8/TO8D
* ❌ _Not supported_ - needs hashing method
* ❌ libretro core: **Theodore**
    - Seems to work
    - Uncertain how core handles writing to disk/tape. May affect hashing.

#### TI-83
* ⌛ Bizhawk core: TI83Hawk
    - Pending rollout

#### TIC-80
* ❌ _Not supported_ - needs hashing method
* ❌ libretro core: **TIC-80**
    - Doesn't export memory correctly. Can only see 8 bytes.

#### Uzebox
* ⌛ Bizhawk core: **uzem**
    - Pending rollout
* ⌛ libretro core: **Uzebox**

#### Vectrex
* ✅ libretro core: **VecX**

#### VIC-20
* ❌ _Not supported_ - needs hashing method and memory map
* ❌ libretro core: **VICE xvic**

#### Virtual Boy
* ✅ libretro core: **Beetle VB**
* ⌛ Bizhawk core: **VBoy**
    - Testing and pending rollout

#### VMU
* ❌ _Not supported_ - needs console ID, hashing method and memory map
* ❌ libretro core: **VeMUlator**

#### WASM-4
* ✅ libretro core: **wasm4**

#### Watara Supervision
* ✅ libretro core: **potator**

#### Wii
* ❌ Standalone emulator: **Dolphin**
* ❌ libretro core: **Dolphin**

#### Wii U
* ❌ _Not supported_ - needs hashing method and memory map

#### WonderSwan
* ✅ libretro core: **Beetle Cygne**
* ⌛ Bizhawk core: **Cygne (Port)**
    - Testing and pending rollout

#### WonderSwan Color
* ✅ libretro core: **Beetle Cygne**
* ⌛ Bizhawk core: **Cygne (Port)**
    - Testing and pending rollout

#### XBOX
* ❌ _Not supported_ - needs hashing method and memory map

#### Zeebo
* ❌ _Not supported_ - needs hashing method and memory map

#### ZX81
* ❌ _Not supported_ - needs hashing method and memory map
* ❌ libretro core: **EightyOne**
    - Memory not exposed

#### ZX Spectrum
* ❌ _Not supported_ - needs hashing method and memory map
* ❌ libretro core: **FUSE**
    - Requires ability to map keyboard to port 3
    - Uncertain about save support. Cannot seem to insert save disk
* ⌛ - Bizhawk core: **ZXHawk**
    - Hashing needs to be corrected
    - Testing and pending rollout

More details on Bizhawk cores can be found [here](https://tasvideos.org/BizHawk).

### Other
These are cores that are pending explanation:<br>
Beetle bsnes, Beetle Supafaust, BlastEm, bnes, bsnes, bsnes 2014 Accuracy, bsnes 2014 Balanced, bsnes 2014 Performance, bsnes C++98 (v085), bsnes-hd beta, bsnes-mercury Accuracy, bsnes-mercury Balanced, bsnes-mercury Performance, DirectXBox, Emux GB, Emux NES, Emux SMS, EmuSCV, fixGB, fixNES, Flycast GLES2, fMSX, Frodo, FS-UAE, Gearcoleco, gpSP, higan Accuracy, Meteor, Minivmac, Mu, nSide Balanced, Numero, PCem, PCSX1, PCSX ReARMed Neon, PUAE 2021, PX68k, RACE, Retro8, RetroDream, Rustation, SameBoy, Snes9x 2002/2005/2005+/2010, SquirrelJME, Stella 2014, Temp GBA, TGB Dual, UAE4ARM, and YabaSanshiro.