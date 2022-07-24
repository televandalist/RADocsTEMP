_Advanced Developer Topic_

- [What are Subsets?](#what-are-subsets)
- [Types of Subsets](#types-of-subsets)
  - [Bonus Sets](#bonus-sets)
  - [Multi Sets](#multi-sets)
  - [Challenge Runs](#challenge-runs)
  - [DLC and Expansions](#dlc-and-expansions)
  - [Regional Differences](#regional-differences)
- [Naming Schemes](#naming-schemes)
- [Claims](#claims)
- [Approval](#approval)
- [How Do I Create a Subset?](#how-do-i-create-a-subset)
- [To Do](#to-do)

## What are Subsets?
When browsing the [list of games](http://retroachievements.org/gameList.php), you will see that some games have a `[Subset]` tag in the title. Each of these contain achievements that for some reason or another, are not available in a game's base set. 
Subsets are typically home to specific types of challenge runs. They have also inherited what have been known simply as `[Bonus]` and `[Multi]` sets. 

The methods to create a Subset and means to play them will change once they become a more integrated feature. As of now, they require a patch to generate a unique hash and are separate entries from the base set, so achievements must be obtained separately as well.

## Types of Subsets
### Bonus Sets
While Bonus sets are subject to debate amongst both players and achievement creators, the overall purpose of a bonus set is for achievements that were not fit for the base set to have a home and still be obtainable by a devoted player. Think of them as "deluxe" challenges. The following types of achievements are the most suitable for Bonus Sets:
- **Extreme Challenges**: If it's generally voiced a challenge is **too difficult**, it's a prime candidate for a Bonus set.  However, just because the achievement(s) are possible to code does not mean they are possible to obtain; therefore, the achievement must still be obtainable. A good example of this is the infamous [Mr. Perfect from Mega Man (NES)](https://retroachievements.org/achievement/53290), which requires the player to complete the *entire* game without taking damage.
- **Grind Sessions**: If achievements involve overly long and frustrating grinds that have no meaningful purpose, they're better suited for Bonus sets. These include leveling characters to the maximum level, maxing out stats, performing a task an absurd amount of times, etc. when none of those things award the player. A good example of something grindy that awards the player, thus making it suitable for a base set, is [One of a Kind from Final Fantasy IV (SNES)](https://retroachievements.org/achievement/108720), which requires a highly RNG-reliant grind for an item to trade for said armor.
- **Variety Packs** - Want to do a mixture of Subset ideas all within one set because you don't want to do several different Subsets? Then do it and throw it in a Bonus set.
- **Showcasing of or Abuse of Glitches**: Glitching can have unpredictable effects in a game's memory, which can result in unwanted behavior for some achievements, thus making them not suitable for a base set. Some examples of this are [Replica from Final Fantasy VII (PlayStation)](https://retroachievements.org/achievement/83776) and [Rare Candy Addiction from Pokemon - Red and Blue Versions (Game Boy](https://retroachievements.org/achievement/57643).

### Multi Sets
This one is simple. If an achievement *requires* input from more than one player in order to unlock it, then it cannot be in the base set. 

### Challenge Runs
While many base sets include plenty of challenges, developers have the option to add challenges that last the duration of a game's playthrough to a Subset. These are typically self-imposed challenges that go against how a game is normally played. Examples:
- [Chrono Trigger - No Level Up](https://retroachievements.org/game/9966) - requires players to complete the game without ever leveling up their characters. 
- [EarthBound - Rare Drops](https://retroachievements.org/game/18280) - requires players to obtain all the rare drops from enemies.
- [Final Fantasy - Solo Class](https://retroachievements.org/game/17996) - requires players to complete the game using only one character class, but they need to do it with every class to master the set.
- [Pokemon - Professor Oak Challenge](https://retroachievements.org/searchresults.php?s=Professor+Oak+Challenge) - There are several of these so far! This challenge requires players to catch and/or evolve every Pokemon possible between major story points in the game.
- [Trails in the Sky FC - NG Nightmare](https://retroachievements.org/game/11115) - requires players to obtain 100% completion in a single, NG (New Game) playthrough on the Nightmare difficulty setting, as opposed to doing it on NG+ with carryovers. 

### DLC and Expansions
Not very common, but will become more common as our console support expands. Achievements in these sets are exclusive to a game's downloadable content or expansion pack(s). Examples:
- [Arc the Lad 2 - Arc Arena: Monster Tournament](https://retroachievements.org/game/17001) - released as a bonus disc in the Arc the Lad Collection, this requires save data from Arc the Lad 2 in order to play.
- [F-Zero X - Expansion Kit](https://retroachievements.org/game/10962) - achievements are for content exclusive to the 64DD expansion of the game.
- [Return Fire - Maps o' Death](https://retroachievements.org/game/16851) - a separate release that provides additional maps to the game. It requires save data from the original game in order to play.

### Regional Differences
If a regional variant of a game does not have enough differences to warrant a "full" set, but you don't want to include it with the base set due to interference with base challenges, you can make a Subset to showcase the differences. 

## Naming Scheme
To prevent players from getting confused, there is a specific naming scheme required for all Subsets:
- **Bonus Sets**: Must have `[Subset - Bonus]` following the base game title. For example: `Castlevania [Subset - Bonus]` and `Darkwing Duck [Subset - Bonus]`
- **Multi Sets**: Must have `[Subset - Multi]` following the base game title. For example: `Contra [Subset - Multi]` and `Kirby 64: THe Crystal Shards [Subset - Multi]`
- **Challenge Runs**: Must have `[Subset - Challenge Name/Type]` following the base game title. For example: `Chrono Trigger [Subset - No Level Up]` and `Pocket Monsters Midori [Subset - Monotype Challenge]`
- **DLC and Expansions**: Must have `[Subset - DLC/Expansion Name` following the base game title. For example: `Return Fire - [Subset - Maps o' Death]` and `F-Zero X [Subset - Expansion Kit]`

## Claims
A developer does not need to claim an approved Subset if they are the sole author of the base set. If the developer is *not* the sole author of the base set, then they will need to post a plan in the forum and have it approved via revision voting. 

If a junior developer wants to publish a Subset alongside a core set, they need to have their plan approved by code reviewers. 

## Approval
The following are types of Subsets that are approved by default:
- Bonus
- Multi
- DLC/Expansions
- Glitch Showcases
- Regional Differences
- Challenge Run: Low Level Game/No Leveling Runs
- Challenge Run: Solo Class/Monotype Runs
- Challenge Run: Checkpoint Challenges, such as Professor Oak Challenges
- Challenge Run: Perma-Death Challenges, such as Nuzlocke Challenges

Subsets that deviate from the above list, such as Rare Drops, will need to be approved by DevCompliance, which in turn may require a revision vote.

## How Do I Create a Subset?
In their current state, Subsets require a patch to modify the ROM. This ensures that the hash will be different so it can be linked to a separate entry. You should not use existing patches or alternate versions of the ROM since this can flag the hash when ran against existing DATs. In other words, the hash needs to be **unique**. 

If you do not know how to create one of these patches, you can contact [RAdmin](https://retroachievements.org/user/RAdmin) and request for one to be made. 

### **Step 1** - Create a copy of the original game ROM
This will be the file you will be editing to become the bonus set ROM

### **Step 2** - Grab a hex editor or sprite-hacking tool.

You can skip this if you already have one. Several games already special ROM hacking tool chains.  A lot of them are available on GitHub, but there's a plethora of them on ROMHacking.net that make the task easier. You'll need to use a more generic tool for a game that doesn't have one. The edit needs to be enough to create a new hash for the ROM file. Tools to edit your ROM can be found on [ROMHacking.net's Utilities Page](https://www.romhacking.net/utilities/). 

Here are some narrowed searches which may help:

- Sprite Hacking tools - [ROMHacking.net Filtered Search](https://www.romhacking.net/?page=utilities&category=10&platform=25&game=&author=&os=&level=&perpage=20&title=&desc=&utilsearch=Go)
- Text and text table hex editors - [ROMHacking.net Filtered Search](https://www.romhacking.net/?page=utilities&category=13&platform=&game=&author=&os=&level=&perpage=20&title=&desc=&utilsearch=Go)

### **Step 3** - Create a BPS Patch for the [RAPatches Repository](https://github.com/RetroAchievements/RAPatches)

The easiest way to do this is with [Floating IPS](https://www.romhacking.net/utilities/1040/); all you do is click "Create Patch,", select the unmodified ROM then modified ROM, and save a BPS patch. Providing this patch is a **must** as it ensures players will be able to play the bonus set.

You can put the patch in the RAPatches repository by opening a pull request to add it to appropriate directory. If for any reason, you are not able to or are not comfortable doing so, you can contact [RAdmin](https//retroachievements.org/user/RAdmin) to make sure the patch finds its way into the repository. 

### **Step 4** - Link the Hash to the Bonus Set Entry

Linking the hash is no different than any other game. Be sure to provide the hash information in #hash-links-log on the RetroAchievements Discord or in the game's forum topic. Make sure all necessary information in the bonus set's game entry is filled out.

### **Step 5** - Create achievements for the set, announce, and release.

Again, just like any other set. Make sure the patch is linked in the forum so players are able to use it! Also, **remember that it is against the rules to release the patched ROM itself! You must release the patch by itself to meet with guidelines on not publicly releasing copyrighted content on RetroAchievements).**

## To Do
- Game Icon guidelines for Subsets + include the border templates for Bonus and Multi icons.

