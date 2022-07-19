Currently Leaderboards can be edited by developers on the website. It's a pretty hefty interface and a difficult job to get a leaderboard working just right. It genuinely takes some care and attention to get a good leaderboard working, so in this doc we'll try to understand how it works.

## Overview

This is how a game's Leaderboard List looks like on the website:

![leaderboard_list](/developers/images-leaderboards/leaderboard-list.png)

In the center you can see every already made Leaderboard, and in the right column you can see the **Code Notes** for the game. The Code Notes are here to help with some conditions we'll see below.

Here's a brief explanation of each field of a single Leaderboard:

- **Title**: the leaderboard's title.
- **Description**: the leaderboard's description.
- **Format**: specifies how the value should be displayed.
- **"LowerIsBetter" checkbox**: determines how the list should be sorted. When checked, lower value appear as higher ranks in the leaderboard. Time-based leaderboards usually honor faster times (lower), whereas score-based leaderboards favor higher values.
- **Start**: start conditions, aka **STA**.
- **Cancel**: cancel conditions, aka **CAN**.
- **Submit**: submit conditions, aka **SUB**.
- **Value**: a value interpreter, aka **VAL**.

**Note**: A valid leaderboard MUST have all four of these conditions, even if they're set to always be true (`1=1`) or always be false (`0=1`).

Those last 4 fields are really important and *LOTS* of care must be taken over the entry of any characters into these strings. That's why they deserve a further explanation:

The **Start** (**STA**) condition is a series of values, like an achievement, that must be true in order to start looking for a leaderboard submission. 

If a **Cancel** (**CAN**) condition is true, then it will cancel the leaderboard and no score will be submitted. NOTE: Cancel is given priority over Start. If both become true in the same frame, the leaderboard will not start.

If the **Submit** (**SUB**) condition is true, then the leaderboard score will be submitted. NOTE: Cancel is given priority over Submit. If both become true in the same frame, the score will not be submitted.

Finally, the **Value** (**VAL**) is a special case, and will be taken from memory using the formula stated in the memory box. This is the score that gets displayed while the leaderboard is active, and the value that's submitted if **SUB** is true.

NOTE: Once an active leaderboard is cancelled or submitted, it cannot be reactivated until the **Start** condition becomes false, then true again. This prevents the leaderboard from immediately reactivating after submission/cancel.

**Pro-tip:** **STA**, **CAN**, and **SUB** support all logic available in the [achievement editor](Achievement-Logic-Features). The easiest way to make sure you get them written correctly is to create local achievements that capture the events, then use the `Copy Def` button to copy the achievement definition to the clipboard so you can paste it into the editor on the website.

## Address Format

The memory addresses for STA/CAN/SUB/VAL have the following format:

location/size | prefix (the letters can be in lower case) | example
:------------:|:-----------------------------------------:|:---------:
bit0          | `0xM`  | `0xM01234`
bit1          | `0xN`  | `0xN01234`
bit2          | `0xO`  | `0xO01234`
bit3          | `0xP`  | `0xP01234`
bit4          | `0xQ`  | `0xQ01234`
bit5          | `0xR`  | `0xR01234`
bit6          | `0xS`  | `0xS01234`
bit7          | `0xT`  | `0xT01234`
Lower4        | `0xL`  | `0xL01234`
Upper4        | `0xU`  | `0xU01234`
8bit          | `0xH`  | `0xH01234`
16bit         | `0x`   | `0x01234`
24bit         | `0xW`  | `0xW01234`
32bit         | `0xX`  | `0xX01234`

## Example

The best place to start is to look at one of the existing leaderboards [https://retroachievements.org/leaderboardList.php](https://retroachievements.org/leaderboardList.php) and break it down to see how it works. We're going to use the [Green Hill Act 1 (Sonic the Hedgehog) Leaderboard](https://retroachievements.org/leaderboardinfo.php?i=2) for this purpose. Then let's see how it looks:

![new_leaderboard2](/developers/images-leaderboards/new-leaderboard.png)

The **Title/Description** fields are quite obvious.

The **Type** is "Time (Frames)". The value we're tracking updates once a frame, and the Genesis runs at 60 frames per second. (see not below for systems that run at other speeds)

The **Lower Is Better** flag is checked, then the one who makes the shortest time will be the #1.

Now we're going to break down the most important parts.

### Start Conditions

**STA**: `0xfe10=h0000_0xhf601=h0c_d0xhf601!=h0c_0xfff0=0`

- `0xfe10=h0000`: If 16-bit RAM address 0xfe10 is equivalent to hex 0000,
- `_`: AND,
- `0xhf601=h0c`: If 8-bit RAM address 0xf601 is equivalent to hex 0c,
- `_`: AND,
- `d0xhf601!=h0c`: If the previous 8-bit RAM address 0xf601 is NOT equivalent to hex 0c,
- `_`: AND,
- `0xfff0=0` If 16-bit RAM address 0xfff0 is equivalent to 0.

This might seem daunting, because we don't know what these addresses mean. That's why the **Code Notes** in the right column are pretty handy! You can see how these addresses are labelled in memory. In our example we have:

- `0xfe10` is the level, and is expected to be `0` (the first level).
- `0xf601` is an 8-bit memory address, and we use the prefix `0xh` instead of `0x` to signify this. The `0xf601` is the screen mode. The second and third parts of the start statement are saying "the current mode should be *ingame* (`0c`), and the mode on the previous frame should NOT be *ingame*". **Note**: that `d` prefix on the address represents delta, or "the previous frame's value". **Summing up:** trigger this if we've JUST arrived in a level (the start of the level, when we want to start testing their time).
- Finally we also expect `0xfff0` to be equivalent to `0`, because this address is used for demo mode, and we don't want to award a leaderboard entry when the demo is active!

**Tip**: the most common mistake when creating leaderboards is forgetting the `h` when trying to reference an 8-bit memory address.

**Note**: You can use HitCounts in the Start/Submit/Cancel triggers, but you are responsible for resetting them. These triggers are evaluated every frame, and the state of the leaderboard is dependent on which ones are true. As such, the HitCount will increment even when the leaderboard is not active unless you have an explicit ResetIf condition.

### Cancel Conditions

**CAN**: `0xhfe13<d0xhfe13`

- 0xfe13 is the number of lives.

The cancel section checks if the player's LIVES counter ever becomes lower. Literally, it says "Cancel if the CURRENT value at 0xfe13 is less than the PREVIOUS value at 0xfe13". We want to do this because you could reach the final checkpoint and run out of time, resetting your timer to 0:00. We don't want to allow this, because it's not the correct way of completing the level. So if the player dies, we reset their leaderboard progress. Finally, if you connect two cancel conditions with `s`, the leaderboard will cancel when either one of them are true.

### Submit Conditions

**SUB**: `0xf7cc!=0_d0xf7cc=0`

- 0xf7cc is the endlevel flag, non-interactive.

The submit section checks if the current frame has the 'endlevel' flag set to true (or `!=0`, 'nonzero'), and the previous frame (delta) has it set to false (or `=0`, 'zero'). This suggests that the player has reached the end of the level, and has proven to be a fairly sturdy benchmark.

**Tip**: it can be useful to watch these values in memory to see how they perform, and what sort of values they end up at in different circumstances.


### Value

Finally, value. Once the player has reached the start condition, they will be shown a popup which remains on-screen, showing their progress so far. If it's a time leaderboard, it will be a clock, and if it's a score, it will just be the value. If they fulfill the cancel condition, they will be told that they have failed, and the popup will be removed. If they successfully reach the submit condition, the current value will be taken and submitted as their score, and on successful submission, an in game popup will inform the player of the leaderboard so far, and their position in the leaderboard.

**NOTE**: The value calculation is performed using 32-bit signed integers. As such, the maximum value is 2147483647 and the minimum value is -2147483648. Values above the maximum will wrap around and register as very negative numbers. 

The value condition is special in a few ways. It is evaluated constantly and shown on-screen all the time when the leaderboard is active. 

There is also a symbol which only works in this field. Connecting two value conditions with `$` will cause only the one with the highest value to be used.

Many games use [Binary Coded Decimal](Rich-Presence#binary-coded-decimal-bcd) to encode scores. You can have the runtime decode BCD values by putting a `b` prefix in front of the memory reference (i.e. `b0xW1234`)

#### Value from Measured

Starting with the 0.77 DLL (and RetroArch 1.8.2), you can use the Measured flag to generate a Value. This supports all logic supported by the achievement editor, but every condition must have a flag that somehow influences the Measured value (i.e. AddSource, AddAddress).

**VAL**: `A:0xhfe24_A:0xhfe25*60_M:0xhfe22*3600`

The example provided above reads:
```
AddSource 8-bit 0xfe24
AddSource 8-bit 0xfe25 * Value 60
Measured  8-bit 0xfe22 * Value 3600
```

The addresses represent frames, seconds, and minutes respectively, and are individually multiplied and then added together to create a total number of frames that can be submitted to the database.

#### Value from HitCount

Sometimes you want to count the number of times something happens and submit that as the value. You can also do this using Measured syntax. Just add a comparison to your final condition. Do not include an explicit Hit target, or that will be the maximum value that can be submitted.

The HitCount on the condition will automatically be set to 0 when the leaderboard starts, and the HitCount will be submitted as the Value when the leaderboard submit trigger activates. You can use PauseIf and ResetIf within the Value conditions to further control the behavior.

For example:
```
M:0xH1234!=d0xH1234
```
Would submit the number of times the byte at $1234 changed while the leaderboard was active.
```
N:0xH1234!=20_M:0xH1234!=d0xH1234
```
Would submit the number of times the byte at $1234 changed to something other than 20 while the leaderboard was active.

#### Legacy Syntax:

**VAL**: `0xhfe24*1_0xhfe25*60_0xhfe22*3600`

Before the introduction of the Measured flag, Values were written using their own syntax. Some people still prefer this syntax as it's generally easier to do by hand. A legacy value is the sum of a collection of memory values multiplied by modifiers.

`address*modifier` (address times modifier)

The `_` underscore operator separates the individual values and acts as 'plus'. So the example above represents:

```
8-bit 0xfe24 times 1, PLUS
8-bit 0xfe25 times 60, PLUS
8-bit 0xfe22 times 3600
```

The addresses represent frames, seconds, and minutes respectively, and are individually multiplied and then added together to create a total number of frames that can be submitted to the database.

To add a constant, use `_vN` where N is the constant in decimal (i.e. `_v10`) will add 10 to the result. You can also use negative values for N (i.e. `_v-10` will subtract 10 from the result.

**Tip**: modifier can be a non-integer value, so if you need to divide by two, you can multiply by 0.5: `0xhfe24*0.5`

### Value Format

'Format' can be any of the available [formats](Rich-Presence#format), but the editor currently only provides **Score**, **Time (Frames)**, **Time (Milliseconds)** and **Value**. **Time (Frames)** is the most common one, and represents a time derived from a value that increments every frame. It does this by multiplying by 100 (to convert to hundredths of a second) and dividing by 60 (the number of frames per second).

**NOTE**: If you're using a system that doesn't run at 60Hz, you have to use "Time (millisecs)" and multiply by some value to do the conversion yourself (50Hz = `*2` [100/50], 60Hz = `*1.666666` [100/60], 75Hz =`*1.333333` [100/75]).

**NOTE**: **Time (Milliseconds)** is actually hundredths of a second, not thousandths of a second. i.e. a Value of 6234 would be 62.34 seconds, not 6.234 seconds.


## Further help

There are unfortunately *MANY* ways to get this process wrong, so if you are having any trouble feel free to ask for help in our [Discord server](https://discord.gg/dq2E4hE).

If you want to practice, it's highly recommended to create your own leaderboard and attempting something on a new game, rather than using an existing leaderboard.

Please remember that these files are pulled directly into someone's game if they decide to play it, and a badly formed memory address or string could cause their emulator to crash, so please test your leaderboard code!
