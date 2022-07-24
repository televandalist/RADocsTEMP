This page details the hashing method used for each supported system. First, systems where the entire game file is hashed are listed, and later systems where the RA hash may differ from the file MD5.

## Systems that Hash the Entire File

#### Apple II

_NOTE_: As saving and other manipulations can mutate disk data, local copies of loaded images are required to ensure that their hashes do not change across sessions.

#### Atari 2600

#### Atari Jaguar

#### ColecoVision

#### GameBoy

#### GameBoy Color

#### GameBoy Advance

#### GameGear

#### MSX

_NOTE_: As saving mutates disk data, local copies of loaded images are required to ensure that their hashes do not change across sessions. We do not believe this is working, but have yet to find a game where saving to disk actually works.

#### N64

_NOTE_: This may result in three unique hashes for each game. The z64 extension is big endian (ABCD). The n64 extension is little endian (DCBA). And the v64 extension is middle endian (BADC).

#### NeoGeo Pocket [Color]

#### PC-8001 / PC-8801

_NOTE_: As saving and other manipulations can mutate disk data, local copies of loaded images are required to ensure that their hashes do not change across sessions.

#### Pokemon Mini

#### Sega 32X

#### Sega Master System

#### Sega MegaDrive (Genesis)

#### TIC-80

#### Vectrex

#### VirtualBoy

#### Watara Supervision

#### WonderSwan  [Color]


## Systems that Hash a Portion of the File


#### 3DO

The volume header (first 132 bytes of sector 0) and the contents of the LaunchMe file are hashed.


#### Arcade

The filename string without the extension (path/galaga.zip -> galaga) is hashed. It is case-sensitive.


#### Atari 7800

If the ROM starts with `\1ATARI7800`, the first 128 bytes are ignored and the remaining file contents are hashed. If the ROM does not start with `\1ATARI7800`, the entire file is hashed.


#### Atari Lynx

If the ROM starts with `LYNX\0`, the first 64 bytes are ignored and the remaining file contents are hashed. If the ROM does not start with `LYNX\0`, the entire file is hashed.


#### Famicom Disk System

If the ROM starts with `FDS\1a`, the first 16 bytes are ignored and the remaining file contents are hashed. If the ROM does not start with `FDS\1a`, the entire file is hashed.

_NOTE_: As saving mutates disk data, local copies of loaded images are required to ensure that their hashes do not change across sessions.


#### NES

If the ROM starts with `NES\1a`, the first 16 bytes are ignored and the remaining file contents are hashed. If the ROM does not start with `NES\1a`, the entire file is hashed.


#### Nintendo DS

A NDS ROM has a 0x160 byte header. In this header are pointers to icon/title information and to the boot code for both processors. The hash method combines the header, the two pieces of boot code, and the icon/title information and hashes the result.

* The icon/title information is 0xA00 bytes starting at the address stored in the header at $68
* The arm9 code address is stored at $20 in the header, and the size is stored at $2C in the header
* The arm7 code address is stored at $30 in the header, and the size is stored at $3C in the header


#### PCEngine (TurboGrafx16)

If the size of the file is 512 bytes more than a multiple of 128KB, the first 512 bytes are ignored and the remaining file contents are hashed. If the size of the file is not 512 bytes more than a multiple of 128KB, the entire file is hashed.


#### PC Engine CD

The boot code and disc title are hashed as follows:
* Read 128 bytes from sector 1 of the data track (PCE predates ISO-9660, so there's no file system to read).
* If "PC Engine CD-ROM SYSTEM" does not exist at 32 bytes into the data, discard as invalid.
* Copy the last 22 bytes of the data into a buffer. This is the disc title, and _usually_ identifies the game.
* The first three bytes of the data are a little-endian sector index for the boot code.
* The fourth byte is the number of sectors that the boot code occupies.
* The boot code is appended to the buffer (N sectors, starting at sector X)
* The buffer is hashed.

#### PC-FX
The boot code and disc title are hashed as follows:
* Read 32 bytes from sector 0 of the data track (PC-FX predates ISO-9660, so there's no file system to read).
* If "PC-FX:Hu_CD-ROM" was not read, discard as invalid.
* Read 128 bytes from sector 1 of the data track into a buffer. This is the volume header and includes the disc title.
* The 32-bit value at 32-bytes into the buffer is the first sector of the boot code.
* The 32-bit value at 36-bytes into the buffer is the number of sectors that the boot code occupies.
* The boot code is appended to the buffer (N sectors, starting at sector X)
* The buffer is hashed.


#### PlayStation

The primary executable and its name are hashed as follows:
* The SYSTEM.CNF file is loaded and parsed. The primary executable is identified by the BOOT= line within.
* The primary executable name (and its path) are extracted from SYSTEM.CNF and written to a buffer.
* The contents of the primary executable are appended to the buffer.
* The buffer is hashed.


#### PlayStation 2

The primary executable and its name are hashed as follows:
* The SYSTEM.CNF file is loaded and parsed. The primary executable is identified by the BOOT2= line within.
* The primary executable name (and its path) are extracted from SYSTEM.CNF and written to a buffer.
* The contents of the primary executable are appended to the buffer.
* The buffer is hashed.


#### PlayStation Portable

The disc metadata and primary executable are hashed as follows:
* The contents of the PSP_GAME\PARAMS.SFO file are written to a buffer. This contains the game attributes displayed in the menu, including the name and serial.
* The contents of the primary executable (PSP_GAME\SYSDIR\EBOOT.BIN) are appended to the buffer.
* The buffer is hashed.


#### Sega CD / Sega Saturn

The first 512 bytes of track 0 are hashed. This contains the volume header and ROM header. The first 16 bytes must be "SEGADISCSYSTEM  " for Sega CD or "SEGA SEGASATURN " for Sega Saturn. If not, discard as invalid.

Immediately following those 512 bytes are an arbitrary amount of code that validates the region and loads the primary executable. Without processing the code, we cannot determine what additional file(s) to hash, so this was determined to be sufficient as an alternative to hashing the entire CD.


#### Sega Dreamcast

The disc metadata and primary executable are hashed as follows:
* The first 512 bytes of sector 0 are appended to the buffer. This contains the volume header and ROM header. The first 16 bytes must be "SEGA SEGAKATANA ". If not, discard as invalid.
* The contents of the primary executable (as identified by the volume header) are appended to the buffer.
* The buffer is hashed.


#### SNES

If the size of the file is 512 bytes more than a multiple of 8KB, the first 512 bytes are ignored and the remaining file contents are hashed. If the size of the file is not 512 bytes more than a multiple of 8KB, the entire file is hashed.

