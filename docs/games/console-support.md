## Supported Consoles

#### 3DO Interactive Multiplayer
* libretro core: **Opera** (supported)

#### Amiga
* libretro core: **P-UAE** (not supported)
    - Locks disk files so they can't be opened for hashing
    - Hard disk support?

#### Amstrad CPC
* libretro core: **Cap32** (supported)
    - Core does not currently support writing to disk, which may affect hashing
      when implemented

#### Apple II
* Standalone emulator: **[RAppleWin](https://retroachievements.org/download.php#rapplewin)**

#### Arcade
* libretro core: **FinalBurn Neo** (supported)
    - Some boards may not be fully exposed

#### Arduboy
* libretro core: **Arduous** (supported)

#### Atari 2600
* libretro core: **Stella** (supported)

#### Atari 5200
* _Not supported_ - needs hashing method and memory map
* libretro core: **atari800**
    - Appears to work fine, but the core is a bit of a headache to use.
        - The BIOS has to be configured within the core (F1 > Emulator
          Configuration > System ROM settings)
    - Couldn't figure out controls - does the joystick need to be configured
      within the core too?
    - Allows loading arbitrary files from the internal menu, which bypasses
      hashing
* libretro core: **a5200**
    - Does not expose memory

#### Atari 7800
* libretro core: **ProSystem** (supported)

#### Atari Jaguar
* libretro core: **Virtual Jaguar** (supported)
    - No save state support
    - [Many issues with emulation](https://github.com/libretro/virtualjaguar-libretro/issues/38)

#### Atari Lynx
* libretro core: **Beetle Lynx** (supported)
* libretro core: **Handy** (supported)

#### Atari ST
* _Not supported_ - needs hashing method and memory map
* libretro core: **Hatari**
    - Memory not exposed

#### Cassette Vision
* _Not supported_ - needs hashing method and memory map

#### CHIP-8
* _Not supported_ - needs console ID, hashing method and memory map
* libretro core: **jaxe**
    - 16 Apr 22 - Seems ready when we are
    - May need settings blacklist to prevent lowering speed

#### Commodore 64
* _Not supported_ - needs memory map
* libretro core: **vice_x64**
    - NOTE: Joystick is in port 2 by default. Use JOY button on virtual keyboard
      (select) to switch it to port 1.
    - 1 May 2022 - Reset does not autorun game
    - 1 May 2022 - Hashing often fails because core has a lock on the file

#### ColecoVision
* Standalone emulator: **[RAMeka](https://retroachievements.org/download.php#rameka)**
* libretro core: **blueMSX** (supported)

#### Fairchild Channel-F
* libretro core: **FreeChaF** (supported)

#### FM Towns
* _Not supported_ - needs hashing method and memory map

#### Game & Watch
* _Not supported_ - needs hashing method and memory map
* libretro core: **gw**
    - Does not expose memory

#### Game Boy
* Standalone emulator: **[RAVBA](https://retroachievements.org/download.php#ravba)**
* libretro core: **Gambatte** (supported)
* libretro core: **Gearboy** (supported?)
* libretro core: **VBA-M** (supported)
* libretro core: **mGBA** _(unsupported?)_
    - 13 May 2020 - [crashes when unloading](https://github.com/libretro/mgba/issues/188) the core because RALibretro doesn't implement the camera interface

#### Game Boy Color
* Standalone emulator: **[RAVBA](https://retroachievements.org/download.php#ravba)**
* libretro core: **Gambatte** (supported)
* libretro core: **Gearboy** (supported)
* libretro core: **VBA-M** (supported)

#### Game Boy Advance
* Standalone emulator: **[RAVBA](https://retroachievements.org/download.php#ravba)**
* libretro core: **VBA-M** (supported)
* libretro core: **Beetle GBA** (supported)
* libretro core: **VBA Next** (supported)
* libretro core: **mGBA** (supported?)

#### GameCube
* _Not supported_ - needs hashing method and memory map
* libretro core: **Dolphin**
    - Generates sound but no video in RALibretro

#### Game Gear
* Standalone emulator: **[RAMeka](https://retroachievements.org/download.php#rameka)**
* libretro core: **Genesis Plus GX** (supported)
* libretro core: **GearSystem** (supported)

#### Genesis / Mega Drive
* libretro core: **Genesis Plus GX** (supported)
* libretro core: **Picodrive** (supported?)

#### Intellivision
* libretro core: **FreeIntV** (supported)
    - Crashes when game is reset
    - Some crashes which might be related to Intellivoice

#### J2ME
* _Not supported_ - needs console ID, hashing method and memory map
* libretro core: **freej2me**

#### Magnavox Odyssey 2
* libretro core: **O2EM** (supported)

#### Master System
* Standalone emulator: **[RAMeka](https://retroachievements.org/download.php#rameka)**
* libretro core: **Gearsystem** (supported)
* libretro core: **Genesis Plus GX** (supported?)
* libretro core: **Picodrive** (supported)

#### Mega Duck
* libretro core: **SameDuck** (supported)

#### MS-DOS
* _Not supported_ - needs hashing method and memory map
* Needs a way to prevent launching with user-specified command line parameters
* Needs a way to prevent TSRs
* Needs a way to deactivate achievements if game drops to command prompt
* libretro core: **dosbox-pure**

#### MSX
* libretro core: **blueMSX**
    - Hash relies on .DSK file not being modified
    - .DSK files appear to be unsupported if they also require a cartridge. There
      is a core option for this, but it doesn't seem to function properly. See
      "SD Snatcher", which used a 'sound' cartridge.

#### Neo Geo CD
* _Not supported_ - needs hashing method
* libretro core: **NeoCD**
    - Appears fully functional

#### Neo Geo Pocket
* libretro core: **Beetle NeoPop** (supported)

#### NES / Famicom
* Standalone emulator: **[RANes](https://retroachievements.org/download.php#ranes)**
* libretro core: **FCEUmm** (recommended)
* libretro core: **Mesen** (supported)
* libretro core: **QuickNES** (supported?)

#### Nintendo 3DS
* _Not supported_ - needs hashing method and memory map
* libretro core: **Citra**
    - Only exposes 64MB of memory - documentation suggests there should be 128MB.
    - Does not support save states

#### Nintendo 64
* Standalone emulator: **[RAProject64](https://retroachievements.org/download.php#rap64)**
* libretro core: **ParaLLEl N64** (supported?)
* libretro core: **Mupen64Plus-Next** (supported?)
* RALibretro does not map C buttons correctly

#### Nintendo DS
* libretro core: **DeSmuME** (supported)
    - Limited microphone support
    - No DSi support
* libretro core: **MelonDS** (supported)
    - Limited microphone support
    - No DSi support

#### Nokia N-Gage
* _Not supported_ - needs hashing method and memory map

#### Oric
* _Not supported_

#### PC Engine/TurboGrafx-16
* libretro core: **Beetle PCE Fast**
    - SuperGrafx games do not work on the Beetle PCE Fast core
* libretro core: **Beetle SuperGrafx**

#### PC-6001
* _Not supported_ - needs hashing method and memory map

#### PC-8800
* Standalone emulator: **[RAQuasi88](https://retroachievements.org/download.php#raquasi88)**
* libretro core: **quasi88**
    - PC-88VA not supported
    - 16 Apr 2022 - Cannot load m3u. Hash fails because core locks disk file.
    - 16 Apr 2022 - Attempting to load a single disk game in RALibretro just
      goes to "How many disks?" prompt. Seems to work in RetroArch
    - 16 Apr 2022 - RALibretro does not provide subsystem interface for loading
      multi-disk games

#### PC-9800
* _Not supported_ - needs hashing method and memory map
* libretro core: **np2kai**
    - Memory is not exposed.
        - It appears to be exposed in some games depending on the RAM size
          selected, but it seems like te machien RAM and not actually related
          to the game.

#### PC-FX
* libretro core: **Beetle PC-FX** (supported)

#### Philips CD-I
* _Not supported_ - needs hashing method and memory map
* libretro core: **SAME CDi**

#### PlayStation
* Standalone emulator: **[DuckStation](https://www.duckstation.org/wiki/Main_Page)**
* libretro core: **Beetle PSX HW** (recommended)
* libretro core: **Beetle PSX** (supported)
* libretro core: **PCSX** (supported?)
* libretro core: **ReARMed** (supported?)
* libretro core: **SwanStation** (supported)

#### PlayStation 2
* _Not supported_ - RPCSX2 experimenting with integration
* libretro core: **PCSX2**
    - Still in alpha state
    - Does not expose memory
* libretro core: **play**
    - Low compatibility with most commerical games
    - Black screen with stuttering sound

#### PlayStation Portable
* libretro core: **PPSSPP**
    - Loading save states too fast can cause it to crash
    - Some games have graphical issues 

#### PocketStation
* _Not supported_ - needs console ID, hashing method and memory map
* libretro core: **pockystation**
    - Core doesn't seem functional, even in RetroArch

#### Pokemon Mini
* libretro core: **PokeMini** (supported)

#### Sega 32X
* libretro core: **PicoDrive**
    - Several games are problematic

#### Sega CD
* libretro core: **Genesis Plus GX** (supported)
    - Appears to still have unmapped RAM (reported against Ecco 1+2)

#### Sega Dreamcast
* libretro core: **flycast** (supported)
    - Must disable threaded rendering to use save states

#### Sega Pico
* _Not supported_ - needs hashing method and memory map
* libretro core: **picodrive**
    - Needs controls related to turning pages in the attached books

#### Sega Saturn
* libretro core: **Beetle Saturn** (supported)
* libretro core: **Yabause** (supported?)
* libretro core: **Kronos** (unsupported?)
    - Saving and loading states often locks up the UI in RALibretro

#### SG-1000
* Standalone emulator: **[RAMeka](https://retroachievements.org/download.php#rameka)**
* libretro core: **Genesis Plus GX** (supported)
* libretro core: **blueMSX** (supported)

#### Sharp X1
* _Not supported_ - needs hashing method and memory map
* libretro core: **X1 Millennium**
    - 16 Apr 2022 - Disk writes modify source media, which breaks hashing

#### Sharp X68K
* _Not supported_ - needs hashing method and memory map
* libretro core: **px68k**
    - Crashes RALibretro upon loading a game

#### SNES / Super Famicon
* Standalone emulator: **[RASnes9x](https://retroachievements.org/download.php#rasnes9x)**
* libretro core: **RASnes9x** (recommended)
* libretro core: **Mesen-S** (supported?)

#### Super Cassette Vision
* _Not supported_ - needs hashing method
* libretro core: Currently only available in MAME, which cannot be supported.

#### Thomson TO8/TO8D
* _Not supported_ - needs hashing method
* libretro core: **Theodore**
    - Seems to work
    - Uncertain how core handles writing to disk/tape. May affect hashing.

#### TIC-80
* _Not supported_ - needs hashing method
* libretro core: **TIC-80**
    - Doesn't export memory correctly. Can only see 8 bytes.

#### Uzebox
* _Not supported_ - needs console ID, hashing method and memory map
* libretro core: **Uzebox**
    - 16 Apr 2022 - Seems ready once we are

#### Vectrex
* libretro core: **VecX** (supported)

#### VIC-20
* _Not supported_ - needs hashing method and memory map

#### Virtual Boy
* libretro core: **Beetle VB** (supported)

#### VMU
* _Not supported_ - needs console ID, hashing method and memory map
* libretro core: **VeMUlator**

#### WASM-4
* libretro core: **wasm4** (supported)

#### Watara Supervision
* libretro core: **potator** (supported)

#### Wii
* _Not supported_ - needs hashing method and memory map
* libretro core: **dolphin**
    - Crashes RAlibretro when testing

#### Wii U
* _Not supported_ - needs hashing method and memory map

#### WonderSwan
* libretro core: **Beetle WonderSwan** (supported)

#### XBOX
* _Not supported_ - needs hashing method and memory map

#### Zeebo
* _Not supported_ - needs hashing method and memory map

#### ZX81
* _Not supported_ - needs hashing method and memory map
* libretro core: **EightyOne**
    - memory not exposed

#### ZX Spectrum
* _Not supported_ - needs hashing method and memory map
* libretro core: **FUSE**
    - Requires ability to map keyboard to port 3 (RALibretro)
    - Uncertain about save support. Cannot seem to insert save disk

