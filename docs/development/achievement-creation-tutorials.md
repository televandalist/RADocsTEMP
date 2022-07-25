## Intro
Page is heavily WIP, but the goal is to provide extensive documentation to cover every aspect of set development from start to finish. Will probably end up merging the "Real Examples" into this section somehow. Each flag, type, size, comparison, etc. will have its own page. Will also include several tips n' tricks, case studies, etc. 

  - RAM digging
    - Utilizing Game Genie, Game Shark, Codebreaker, Action Replay, etc. codes 
  - Code Notes
    - Formatting conventions

## Achievement Editor

### Flags
  - Pause If
  - Reset If
  - Reset Next If
  - Add Source
  - Sub Source
  - Add Hits
  - Sub Hits
  - Add Address
    - Indirect Pointers
    - Direct Pointers
  - And Next
    - Multi-Condition Counters and Checkpoints
    - Multi-Condition Resets and Pauses
  - Or Next
  - Measured
  - Measured If
  - Trigger

### Types
  - Mem
  - Value
  - Delta
    - `Mem > Delta` Comparisons
  - Prior
  - BCD
  - Float

### Sizes
  - bit0 - bit7
  - 8-Bit
  - 16-Bit
  - 24-Bit
  - 32-Bit
  - Lower4 and Upper4
  - 16-Bit BE
  - 24-Bit BE
  - 32-Bit BE
  - BitCount
  - Float
  - MBF32

### General Comparisons
  - `=`
  - `<`
  - `<=`
  - `>`
  - `>=`
  - `!=`

### Flag Specific Comparisons
  - `*`
  - `/`
  - `&`

### Other Toolkit Features
  - Hit Counts
    - Using with Reset If
    - Using with Pause If
  - Alt Groups

## Protections
  - Demo Protection
    - Finding and testing demo addresses
  - Save Protection
    - Delta and Prior
    - Using in-game timers
    - Using event flags
  - Password Protection
  - Cheat Protection
  - Multiplayer Protection
  - Other
    - Dipswitch
    - BIOS (PlayStation and Saturn)

## Logic Tips and Tricks
  - Checkpoints hits
  - Pause Locks
  - Various types of chains
  - When to use Reset If or Pause If
  - When to use Delta or Prior
  - Using BitCount for collectibles
  - Using Add Source with `Mem / Mem` comparisons
  - Using `bit0` to include or exclude odd-numbered values

## Real Examples

### Using Hit Counts as a timer
In this example, you'll see how hit counts can be used as a timer and award an achievement if a condition is true for 10 seconds.

Let's see what [Super Hang-On (Mega Drive)](http://retroachievements.org/Game/16)'s achievement [Speed Freak - Maintain at least 300kph for 10 seconds](http://retroachievements.org/Achievement/71) looks like in the Achievement Editor dialog:

**Addresses**

- `0x0055a`: is the speed.
- `0x0c757`: is 0x00 when the game is unpaused.

![speedfreak-example](/development/images/speedfreak-example.png)

For this achievement, we are looking for a condition that is met 600 times consecutively. The reason why is that the genesis is locked into processing 60 frames of logic per second (NTSC at least?). And the condition we're checking is "speed is over 300". Also, we want the player to keep the speed above 300 without pausing the game.

**Conditions**

1. Player's speed is above 300 for 600 frames (or 10 seconds have passed).
2. Reset the hit counter if the speed goes under 300.
3. Reset the hit counter if the player pauses the game.

### Using Delta Values and Hit Counts to Detect an Increment

Let's take [Streets of Rage 2 (Mega Drive)](http://retroachievements.org/Game/3)
as a case study, and [Steel Grip - Defeat 10 enemies without dropping your weapon](http://retroachievements.org/Achievement/55) achievement. This relies on four conditions:

**Addresses**

- `0xef33`: holding weapon 
- `0xef37`: weapon type
- `0xef4e`: number of KOs (player 1)

![steelgrip-example](/development/images/steelgrip-example.png)


**Conditions**

1. the player is holding a weapon. We require this to be true, once. This is actually not necessary, but it's useful to show the progression. We are requiring the player to hold a weapon, at least once.

2. number of KOs that the player has made. It's 16-bit (meaning the value can be more than 255), and by using the delta and 'greater than' symbols, we are saying that we require the number of KOs to be bigger than the previous value, and we need this to happen 10 unique times. Every time the current value is bigger than the previous value, the hit count will go up by one. The next frame, the 'delta' value will have increased to be the same as the current value, this ensures that after every kill, the KO counter will go up by one, and the hit count will go up by one. **LIMITATION**: if the number of KOs goes up by two in the same frame, the hit count will only go up by one. It's a slight flaw that does happen a little more often than expected... it's not so accurate but it's a fairly close estimate to your number of kills.

3. reset all our progress, if the **weapon type** is different than the last known weapon type.

4. reset **all** our progress, if the player is no longer carrying a weapon.

### Using Add Source and Deltas for Collectibles

In these examples are a couple simple ways one can utilize the Add Source flag in their achievement logic.

First, we'll look at an achievement from [Suikoden (PlayStation)](https://retroachievements.org/game/11255) entitled [Treasure Hunter - Dragon Knights' Domain](http://retroachievements.org/Achievement/80100):

**Addresses Used**

- `0x1b8244`: bit0-bit4 are treasures in Soniere, bit5 is a treasure at the Northern Checkpoint, and bit6-bit7 are treasures at the Dragon Den.
- `0x1b8245`: bit0 is a treasure at the Dragon Den, bit1-bit5 are treasures at Seek Valley, and bit6-7 are treasures in Kalekka.
- `0x1b824b`: bit0-bit1 are treasures at the Village of the Hidden Rune, bit2 is unused, bit3-4 are treasures at the Dragon Knights' Fortress, bit5-6 are treasures in Teien, and bit7 is a treasure at Luiken's House. 

![addsource-example](/development/images/addsource-example.png)

??? "View Syntax"

    A:d0xS1b8244_A:d0xT1b8244_A:d0xM1b8245_A:d0xN1b8245_A:d0xO1b8245_A:d0xP1b8245_A:d0xQ1b8245_A:d0xR1b8245_
    A:d0xP1b824b_d0xQ1b824b=9_A:0xS1b8244_A:0xT1b8244_A:0xM1b8245_A:0xN1b8245_A:0xO1b8245_A:0xP1b8245_A:0xQ1b8245_
    A:0xR1b8245_A:0xP1b824b_M:0xQ1b824b=10

This particular achievement only requires treasures from Dragon Knights' Fortress, Dragon Den, and Seek Valley; therefore, we only need bit6-7 from `0x1b8244`, bit0-bit5 from `0x1b8245`, and bit3-bit4 from `0x1b824b`. 

**Logic Breakdown**

- There are two groups of ten conditions with the main differences being the Delta type and the total. This is to ensure that the player goes from nine of these treasures obtained to having all ten of these treasures obtained. *Note: Remember to use hexadecimal for Add Source totals!* 
- Since we're using bitflags here, the totals for individual conditions will only ever be 0x00 or 0x01. Obviously, we want them all to be 0x01 for the trigger, but we don't want someone to get the achievement simply by loading a save with all ten treasures already found.
- The trigger is the first frame that the player goes from nine to ten treasures obtained. This is to help prevent the achievement from triggering when it's not supposed to.
- The Measured flag is on the last condition so the player can check how far they are from their goal. If they have eight out of ten treasures, the achievement will show that it is 80% complete in the overlay (RAEmus) or achievement menu (RetroArch). 

This method is mostly handy for when the totals between the Delta-type and Mem-type only have a difference of 0x01, but it can be used in various types of achievements: collectibles that are only obtainable one-at-a-time, map completion (such as dungeon-crawlers with viewable maps that get revealed as you enter new areas), learnable skills, completing a certain number of side missions, and many others. 


### Circumvent the Problem of a Counter Incrementing Twice in the Same Frame

In this example you'll see how to circumvent the problem of a counter incrementing twice in the same frame by combining [SubSource](SubSource-Flag) and [AddHits](AddHits-and-SubHits-Flag).

In the Game Boy Advance library there's a Christmas platformer game called [Santa Claus Jr. Advance](http://retroachievements.org/Game/7152). There are some achievements for collecting all candy canes in each one of the bonus stages.

Such achievements were supposed to be quite simple, like this:

ID | Special? | Memory   | Cmp | Type  | Mem/Val | Hits
---|----------|----------|-----|-------|---------|-----
 1 |          | 0xCANDIES| !=  | Delta |0xCANDIES| (N)
 2 | ResetIf  | 0xSTAGE  | !=  | Value | 0xBONUS |

This translates into "check if the candy canes counter changed `N` times in the bonus stage".

**Note**: we're using `0xCANDIES != Delta 0xCANDIES` (using `!=`, and not `>`) cause when the player has 99 candies and collect one more, the counter goes to zero.

However, there is an aspect in this game (and many others) where if the player collect 2 candy canes simultaneously the counter is increased by 2 in the same frame. When it happens the hit counter is increased by one while the candy counter is increased by two. This, obviously, ruins the logic used above.

In order to circumvent this issue we have to use that technique of [using `SubSource` to count specific increments](SubSource-Flag#using-subsource-to-count-specific-increments) combined with the [`AddHits` flag](AddHits-and-SubHits-Flag).

Let's take a look at the achievement logic and then we'll see the explanation:

**Addresses**

* `0x80dc`: Candy Canes counter.
* `0x809c`: Stage ID.

So now the structure of the achievement is going to be like this:

![](/development/images/circumvent1.png)

**Conditions**

1. Together with condition 2, is a trick used to check if `0xCANDIES - Delta 0xCANDIES = 2`. In other words, the candy counter was incremented by two.

2. Used together with condition 1 (as explained above) and 3. As explained in [its respective page](AddHits-and-SubHits-Flag), when the `AddHits` condition is true, the hit counter in the next condition is incremented. Therefore, in our example here, when condition 2 is true, the hitcounter in condition 3 is incremented.

3. Count when the candy counter changes.

4. Reset the counter if not in the Bonus stage.

All these conditions could be translated as "while in the bonus stage, trigger the achievement if the candy counter changes 99 times, and if the candy counter is incremented by 2 in the same frame, count an extra change in the candy counter."

So, now it is 100% solved, right? Well, actually, almost. There is still a very minor exception. Remember it was said before that `!=` was being used instead of `>` because `when the player has 99 candies and collect one more, the counter goes to zero`?

This means that, if we get two canes in the same frame (which is already rare), there's a very small possibility that this change will be from `98 -> 00` or from `99 -> 01`. In these only two cases our code won't work, because `00 - 98` is not 2, it is `-98`. Same thing for `01 - 99`, it is not 2, it is also `-98`.

Despite being a very unlikely possibility, we should treat this case too. So we're gonna add two more requirements to the code, and it will end up looking like this:

![](/development/images/circumvent2.png)

It is the same as before, with the only changes being lines 3 and 4, which represents an extra `SubSource + Add Hits` to check if `0xCANDIES - Delta 0xCANDIES = -98`, only to take care of this very minor exception just mentioned.

And now it is solved!

- `note: need to add something about how the toolkit still uses hex even if the value is in BCD`

### Creating a Timer with Reset If hits based on the speed of the game

In this example you will learn how to create an ingame Timer based on the framerate speed of the game.

Every game has an address which is constantly increasing, it functions like a engine in a car which is constantly moving despite what you do and starts as soon you start the game, the game itself is your car and some cars are faster than others.

> Please note that PAL Games (50hz) have a lower framerate than NTSC Games (60hz) and aren't compatible with this method. It is recommended to create every Timer based on the NTSC version of the game, unless PAL version is the only version existing and there is no NTSC Patch available.

**Addresses**

- `0x19`: Demo Mode: `01`=Active, `00`=Inactive
- `0x1a`: Game Engine (speed based on framerate)
- `0x25`: Game Paused: `01`=Yes. `00`=No
- `0x2c`: Game Progression: `03`=Before Stage starts, `04`=Stage started, `08`=Stage finished
- `0x30`: Stage ID (in this example, Stage 1)

![Contra-Timer](/development/images/contra-timer.jpg)

Link to Cheevo: [Contra Speedrun](https://retroachievements.org/achievement/65443)

YouTube: [ResetIfHits Demo: Contra Stage 1 60 seconds Speedrun ](https://youtu.be/6PpdG04tM4s)

**Conditions**

1. Activates the 'Hit' when entering a Stage (`03`only appears once in each Stage).

2. Triggers when a Stage has been finished.

3. Current Stage (in this example, Stage 1).

4. Pauses if the game is 'Paused' (Stops the timer).

5. Resets if `60` seconds `3600` Hits are reached. `1` second = `60Hits` (NTSC 60fps), `50Hits` (PAL 50fps).

6. Resets if `Demo Mode` is active.

7. Resets timer when entering a new stage.

## See Also
  - Making Tutorial Videos