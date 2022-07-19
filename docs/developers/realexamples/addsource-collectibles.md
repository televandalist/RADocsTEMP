In these examples are a couple simple ways one can utilize the Add Source flag in their achievement logic.

First, we'll look at an achievement from [Suikoden (PlayStation)](https://retroachievements.org/game/11255) entitled [Treasure Hunter - Dragon Knights' Domain](http://retroachievements.org/Achievement/80100):

**Addresses Used**

- `0x1b8244`: bit0-bit4 are treasures in Soniere, bit5 is a treasure at the Northern Checkpoint, and bit6-bit7 are treasures at the Dragon Den.
- `0x1b8245`: bit0 is a treasure at the Dragon Den, bit1-bit5 are treasures at Seek Valley, and bit6-7 are treasures in Kalekka.
- `0x1b824b`: bit0-bit1 are treasures at the Village of the Hidden Rune, bit2 is unused, bit3-4 are treasures at the Dragon Knights' Fortress, bit5-6 are treasures in Teien, and bit7 is a treasure at Luiken's House. 

![addsource-example1](https://u.cubeupload.com/televandalist/docssuikotreasure.png)

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

