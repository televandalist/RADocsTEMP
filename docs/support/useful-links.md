## https://gamefaqs.gamespot.com/

Great place to find game guides, finding almost all you could want to know about game content, find cheat codes, for development utility and also for making proper protections against the codes.


## https://www.vgmaps.com/

Thousands of maps/screenshots of your favourite video games!


## https://tcrf.net/

It is a site dedicated to unearthing and researching unused and cut content from video games. From debug menus, to unused music, graphics, enemies, or levels, many games have content never meant to be seen by anybody but the developers — or even meant for everybody, but cut due to time/budget constraints.


## [Cumulative Probability Calculator](https://www.danielsoper.com/statcalc/calculator.aspx?id=71)

When working with achievements with an RNG factor you will often want to know the probability of success for players given a number of attempts. (see [unwelcome concepts, achievements with low odds](Developers-Code-of-Conduct#unwelcome-concepts)). Use it to calculate P(X>=1), assuming the player needs to succeed only once across several attempts, to estimate how many attempts an might require for less lucky players.


## https://www.zapstudio.net/framecalc/

Simple utility to calculate frames out of time given and the other way around.


## https://www.romhacking.net

The biggest repository of patches to hack ROMs. 


## http://datacrystal.romhacking.net/wiki/Hashes

Explains what hashes are. If you don't know what they are you should probably read this.


## https://emn178.github.io/online-tools/crc32_checksum.html

Drag and drop checksum checker utility. You can also get the checksum from the rom you have loaded from the retroachievements menu in the emulators.


## http://www.marcrobledo.com/RomPatcher.js

An online ROM patcher utility.


## http://jsonviewer.stack.hu

Excellent for viewing raw achievements


## http://gamehacking.org

Provides many Pro Action, Game Genie, and Game Shark codes which can be converted to RAW addresses on the site. 

!!! attention
    The links below were taken from the "Downloads" page.

## Tools 

- [ROM Hasher](https://www.romhacking.net/utilities/1002) - Calculates hashes and looks ROMs up in a ROM database
- [Floating IPS](https://www.romhacking.net/utilities/1040) - ROM Patcher, applies and creates IPS and BPS patches
- [Alcohol Portable](https://bit.ly/RAPortableA ) - Virtual Drive Software (For PCEngine)
- [7-Zip](https://bit.ly/RA7zip) - For unpacking downloads from this page
- [RapidCRC](http://rapidcrc.sourceforge.net/) - Drag and drop multiple files to get md5s and CRCs. Can output text files.

## Online Tools

- [CRC32 checksum](https://bit.ly/RACRC32) - For checking that you have the correct ROM
- [MD5 checksum](https://bit.ly/RAMD5) - For checking that you have the correct ROM
- [Marc Robledo's online RomPatcher](https://www.marcrobledo.com/RomPatcher.js/) - online ROM patcher for hacks and other ROM patches

!!! attention
    The links below were taken from the "Links" page under Dev Resources

## Helpful Website Links

- https://datacrystal.romhacking.net/wiki/Main_Page  - Defined RAM maps of many games.  

- http://www.thealmightyguru.com/Games/Hacking/Wiki/index.php?title=Category:Games - Defined RAM maps of many NES games.  

- https://gamehacking.org/ - Action Replay codes can be used to get defined memory address:  

Y – Address, X – Value
1-2 digit value will always be 8 bit – use 2 in front – 22YYYYYY 000000XX
3-4 digit value will always be 16 bit – use 1 in front – 12YYYYYY 0000XXXX
5-8 digit value will always be 32 bit – use 0 in front – 02YYYYYY XXXXXXXX
This will work for Action replay codes.  

For getting addresses out of GameGenie codes use this: (**outdated link, getting 404**)
http://www.d.umn.edu/~bold0070/projects/game_genie_codes/javascript_game_genie_encoders-decoders.html

- https://www.romhacking.net/ - biggest repository of hacked roms.  

- https://tcrf.net/The_Cutting_Room_Floor - Great place to find Easter Eggs for your set plans.

- https://www.gamefaqs.com/ - Great place to find game guides, finding almost all you could want to know about game content, find cheat codes, for development utility and also for making proper protections against the codes.

- https://wiki.nesdev.com/w/index.php/CPU_memory_map - Shows sections of the NES memory so you'll know what area of the memory you're examining. For nes most useful addresses will be between 0x0000--0x07FF.

- https://datacrystal.romhacking.net/wiki/Hashes - Explains what hashes are. If you don't know what they are you should probably read this.

- https://emn178.github.io/online-tools/crc32_checksum.html - Drag and drop checksum checker utility. You can also get the checksum from the rom you have loaded from the retroachievements menu in the emulators.

- https://www.getpaint.net/ - Excellent freeware image editor. You can use it for making badges and icons.

- https://www.marcrobledo.com/RomPatcher.js/ - An online ROM patcher utility.

- https://gregstoll.dyndns.org/~gregstoll/floattohex/ - Floating point to decimal converter

- http://jsonviewer.stack.hu/ - Excellent for viewing raw achievements

Turns this:  
![before](/sort/images-resources/jsonviewer1.png)

Into this:  
![after](/sort/images-resources/jsonviewer2.png)

Or get a plugin for Notepad++:
- http://jsminnpp.sourceforge.net/ to do similar

Speaking of Notepad++
- https://notepad-plus-plus.org/download/ - One of the best text editors and it's freeware (Windows only).

## Achievement Syntax

This is a good reference sheet, it's especially useful for Rich Presence and Leaderboards, getting your deltas and bit labels right.
![achievement syntax](/developers/resources/images-resources/cheevo-syntax.png)
For full size, right click an save image.

A 32bit requires the prefix "X" as in 0xX63
