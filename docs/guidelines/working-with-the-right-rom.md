**Related:** [Achievements for ROM hacks](/guidelines/achievements-for-rom-hacks/), [Subsets](/development/subsets/)

Only one achievement set is allowed per game per console. This is true in cases of existing official revisions (ex. Rev 1), official and unofficial fix patches, and alternate regions.

[Subsets](/development/subsets/) are an exception to this rule, but are considered an extension to a standard set and follow different rules for what types of achievements are allowed.

Regional exceptions may exist -rarely- when regional variations massively change the game.

## ROM Selection

Almost every game has multiple ROM versions available, sometimes dozens. Often there are major differences under the hood that prevent achievement compatibility between version. Because of this, finding the best ROM for achievements is critical and should be done carefully.

- **Region Selection**: For TV-connected consoles, when possible choose No-Intro (cartridge) or Redump (disc) `NTSC USA` release ROMs, because 60Hz is a smoother gaming experience and generally matches the intended play speed. `PAL European` releases run at 50Hz, and are to be avoided in most cases. `NTSC Japan` releases also run at 60Hz, but are only the best choice if the game was a Japan-exclusive release. `PAL European` releases should be used as a last resort only (Europe-only exclusive), and are typically limited to a very select few *unique* games from the entire console's library. Handheld consoles don't have regional timing differences, so language options should be prioritized there whenever possible.

- **Revision Selection**: Since revisions primarily contain bug and typo fixes, unless you have a -specific- reason not to, always choose the final revision. This will often save both players and developers headaches in the long run. Before working on a game, do a quick search for known revisional changes and take a look at [TCRF](https://tcrf.net/) to see if there's a reason to prefer an earlier revision.

- **Ring Codes**: Some systems, such as Sega Saturn, have multiple version of the game with different "ring codes". These are alphanumeric identifiers stamped on the inner ring of the physical discs. In most cases these will have no functional effect on the game or perhaps even the hash, but as mentioned with Revisions, check to see if there are known differences first.

- **Format**: For most systems this won't be an issue if you've used verified good dumps. For N64 in particular, games can exist in three formats based on the order of the bytes in the file: n64 (little endian), v64 (byteswapped), and z64 (big endian). Despite producing unique hashes, these three formats are identical for the same dump. Because big endian is the most accurate representation of the N64's cartridges, the big endian (z64) hash -must- be linked for any N64 game, in addition to whatever format you may wish to use personally as a developer. This ensures a single set of roms can consistently be used to play. If required, [Tool64](https://gbatemp.net/download/tool-64.32494/) can be used to change byte order.

- **Arcade**: Arcade ROMs are a bit of a special case because FBNeo mandates the exact contents of the game's archive. When different versions exist, the base version of the name should be preferred in general (for instance, mslug2 should be preferred over mslug2dg or mslug2t). This is merely a guideline, as there may be various reasons to prefer a different version.

- **No Mods**: Use a clean ROM. Do not use a ROM with a modded/custom launch screen such as Mode7 and RisingSun have because it changes RAM values and complicates users' ability to use their own legally dumped ROMs.

- **No Trainers**: Do not use a ROM that includes an integrated cheat feature. These are most often refereed to as after-market `ROM trainers`, are not official, and are not in any way supported by RetroAchievements. These ROMs cannot be linked even as secondary options.

## Preservation Groups

[No-Intro](http://www.no-intro.org/) and [Redump](http://redump.org/) are the primary groups responsible for verifying clean dumps of console games, excluding all modifications and untrustworthy sources in the process. They offer dat files that can be used to verify your own dumps via a ROM manager. ROMs verified by these groups are preferred whenever possible, and can generally be identified by the following naming scheme:

**Game Name (Region) (Available Languages if Applicable) (Current Revision if Applicable)**
_**Example:**  Diddy Kong Racing (USA) (En,Fr) (Rev 1)_

[TOSEC](https://www.tosecdev.org/) is another less restrictive preservation group. Their hashes often will match Redump for discs, but will frequently contain less thoroughly verified dumps. For floppy discs, cassettes, and less well-known systems where No-Intro and/or Redump verification aren't avaliable, TOSEC is a good fallback choice.

You can verify that your ROM checksum matches the databases of No-Intro, Redump, or TOSEC either by using a rom manager with a dat provided by the preferred group or by verifying checksum manually and searching the dat for it in a text editor. Bear in mind that unlike a manual check, the rom manager may be able to skip over external headers to accurately verify integrity. Standard choices are [clrmamepro](https://mamedev.emulab.it/clrmamepro/) and [Romulus](https://romulus.cc/).

### Consoles Per Group

The follow are lists of supported consoles per group:

**No Intro**
  - Atari 2600
  - Atari 7800
  - Atari Jaguar
  - Atari Lynx
  - Bandai WonderSwan
  - Bandai WonderSwan Color
  - ColecoVision
  - Emerson - Arcadia 2001
  - Fairchild - Channel F
  - GCE - Vectrex
  - Interton - VC 4000
  - Magnavox Odyssey2
  - Mattell - Intellivision
  - Microsoft - MSX (Cartridges)
  - Microsoft - MSX2 (Cartridges)
  - NEC PC Engine | TurboGrafx-16
  - NEC SuperGrafx
  - Nintendo - Famicom Disk System
  - Nintendo - Game Boy
  - Nintendo - Game Boy Advance
  - Nintendo - Game Boy Color
  - Nintendo - Nintendo 64
  - Nintendo - Nintendo DS
  - Nintendo - Nintendo Entertainment System
  - Nintendo - Pokemon Mini
  - Nintendo - Satellaview
  - Nintendo - Sufami Turbo
  - Nintendo - Super Nintendo Entertainment System
  - Nintendo - Virtual Boy
  - Sega - 32X
  - Sega - Game Gear
  - Sega - Master System - Mark III
  - Sega - Mega Drive - Genesis
  - Sega - PICO
  - Sega - SG-1000
  - Sega - Neo Geo Pocket
  - Sega - Neo Geo Pocket Color
  - Sony - PlayStation Portable (Digital Releases)
  - Watara - Supervision
  - Wellback - Mega Duck
  
**Redump**
  - 3DO
  - NEC - PC Engine CD - TurboGrafx-CD
  - NEC - PC-FX
  - Sega - Dreamcast
  - Sega - Sega CD
  - Sony - PlayStation
  - Sony - PlayStation 2
  - Sony - PlayStation Portable

**Neo Kobe**
  - NEC - PC-8001
  - NEC - PC-8801

**TOSEC**
  - Apple - Apple II
  - Microsoft - MSX (Disks)
  - Microsoft - MSX2 (Disks)

**Final Burn Neo**
  - Arcade
  - Various Home Consoles

**CleanCPC**
  - Amstrad CPC


## Translation patches

(see also: [ROM Localization Policy](#rom-localization-policy) below)

English is the Primary language of RetroAchievements. Translation Patches are sometimes applied by developers to non-English titles as the main hash for an achievement set where no licenced English version exists. In these cases patching instructions will be provided in the forum thread of that title. Whenever reasonable, the original unpatched version should still be supported as well.

Sometimes translation patches may produce critically different memory from the linked hashes. All linked hashes are expected to be fully supported by the -entire- achievement set. If you can't personally guarantee this, don't link the hash.

If you aren't the original developer of the set in question and the developer is active, verify memory personally using testing mode and contact the developer before attempting to add a new translation.

## ROM Localization Policy

As English is the primary language of the community, English ROMs are preferred. When choosing which ROM to build achievements for, we give priority to **No-Intro or Redump US ROMs for non-handheld consoles** and **European ROMs for handheld consoles**. 

We would like to continue improving our support for all regional versions, especially Japanese (as the majority of our game library was created in Japan). Some users may also prefer a specific regional version of a game and it is better to include broad support so that any good ROM can link to a good entry and give appropriate achievements. That said, regional variants must still be fully supported, and 50Hz slowdown needs to be mitigated (via additional patches) or proven to be a non-issue when present.

When looking at how games with regional versions are handled, our standard is **one entry per game per console**. It is ideal that if a player loads up the US or Japanese version of Donkey Kong, Pac-Man, or Contra, they will earn the same achievements from the same entry. As mentioned above, there are some extremely rare situations where it is better for our library and players to split off regional versions into their own unique entry. If the community has reason to believe that it's better for an entry to be split, it can be reviewed and approved by the RetroAchievements staff.

**Tip:** For games with text-triggered achievements (especially RPGs) it's recommend to find an event flag instead of hooking onto text or text ID. Text presentation varies between regional versions, making multi-region support difficult.

### Localization Differences

The types of changes made during localization (most commonly from Japanese to English) can vary wildly. Any of the following changes may result from a localization:

- Little or no change at all;
- Passwords replace battery saves;
- Bugs fixed;
- Light or extensive translations;
- Light or extensive cosmetic changes including "offensive" elements being censored, sfx changes, licenced assets being replaced with generic ones, and/or unknown characters becoming Nintendoed (e.g. Tetris Attack, Super Mario Bros. 2);
- Stages added, modified or removed;
- Game physics and game mechanics modified;
- Game modes, difficulty levels and game options added or removed;
- Cheat codes or debug modes added or removed;
- Game rebalancing resulting in a harder or easier experience, sometimes significantly so;
- Two games combined into one;
- And more.

Because of this variation and to avoid filling the database with unnecessary duplicates, our goal is to minimize the number of split sets. For a set to be split it needs compelling reasons; we take great care to determine when to approve these splits.
