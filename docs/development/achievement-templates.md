## **WARNING: EVERY GAME IS DIFFERENT!**

Here you'll see examples of some typical achievements. You can use them as inspiration to create your own achievement. But keep in mind the following:

**EVERY GAME IS DIFFERENT! The memory has a different behavior from game to game.**


So do **NOT** take these templates as a rule. They are here just for educational purposes.


In these examples we use the following convention **0xLEVEL** is the memory address with the level ID; **0xLIFE** is the address used for the character life; **0xTIME** for time, **0xITEM** for getting an item, etc...


## Collecting an Item N times

There are some situations where you want to award an achievement for collecting an item (like a coin or a ring) N times. You'll need to find in the memory the address responsible to count how much of the item you have. Once you have the address, this logic usually does the job:

ID | Special? | Memory   | Cmp | Type  | Mem/Val | Hits
---|----------|----------|-----|-------|---------|-----
 1 |          | 0xCOUNT  | >   | Delta | 0xCOUNT | (N)

But you most likely will want to be more specific, for example "get item N times without dying". Then you should use another condition with a `ResetIf`, like this:

ID | Special? | Memory   | Cmp | Type  | Mem/Val | Hits
---|----------|----------|-----|-------|---------|-----
 1 |          | 0xCOUNT  | >   | Delta | 0xCOUNT | (N)
 2 | ResetIf  | 0xLIVES  | <   | Delta | 0xLIVES |
 
The `ResetIf` condition could be "while in level X", "without using a bomb", etc.


## Finish Level N

In this example we want to award when the player finish the level `N` and goes to level `N+1`.

ID | Special? | Memory   | Cmp | Type  | Mem/Val | Hits
---|----------|----------|-----|-------|---------|-----
 1 |          | 0xLEVEL  | =   | Value | N       | (1)
 2 |          | 0xLEVEL  | =   | Value | N+1     |
 3 |          | 0xLEVEL  | >   | Delta | 0xLEVEL |
 4 | ResetIf  | 0xLEVEL  | =   | Value | TITLE   |

**Requirements**

- 1: On level `N` at least one time
- 2: Currently at level `N+1`
- 3: The level has been increased
- 4: Reset the hit counter when back to title screen

The value **0xTITLE** means "at game's title screen". You need to `ResetIf` going to the title screen to avoid the awarding at a wrong time.

Here is an example of game flow that could make the achievement trigger at a wrong time if it wasn't for that ResetIf:

1. Start the game and reach level 2 (this make the hit counter goes to 1)
2. Get a game over while on level 2
3. Go back to the title screen
4. Use a password for level 3

If not using the ResetIf we will have these conditions:

1. Hit level 2: TRUE
2. Current level = level 3: TRUE
3. Level increased (from title/password screen to level 3): TRUE

And it would be enough to trigger the cheevo (at a wrong time). That's why we're using the `ResetIf` in this example.


## Finish Level N before Time reaches T

In this example we consider a game where the time decreases (e.g.: Super Mario Bros). Adapt it accordingly the time on your game has a different behavior.

We want to award if the player finishes the level `N` while time is greater than `T`.

ID | Special? | Memory   | Cmp | Type  | Mem/Val | Hits
---|----------|----------|-----|-------|---------|-----
 1 |          | 0xLEVEL  | =   | Value | N       | (1)
 2 |          | 0xLEVEL  | =   | Value | N+1     |
 3 |          | 0xLEVEL  | >   | Delta | 0xLEVEL |
 4 | ResetIf  | 0xLEVEL  | =   | Value | TITLE   |
 5 |          | 0xTIME   | >=  | Value | T       |

**Requirements**

Requirements 1-4 are the same as [Finish Level N](#finish-level-n) template.

- 5: timer is greater than `T`.

**Keep in mind that besides knowing how the time behaves in game you also need to research how it behaves in memory.**


## Finish Level N without Dying (or getting hit, using a weapon, etc.)

ID | Special? | Memory   | Cmp | Type  | Mem/Val | Hits
---|----------|----------|-----|-------|---------|-----
 1 |          | 0xLEVEL  | =   | Value | N       | (1)
 2 |          | 0xLEVEL  | =   | Value | N+1     |
 3 |          | 0xLEVEL  | >   | Delta | 0xLEVEL |
 4 | ResetIf  | 0xLEVEL  | =   | Value | TITLE   |
 5 |          | 0xSCREEN | =   | Value |LVL_N_INTRO| (1)
 6 | ResetIf  | 0xLIFE   | <   | Delta | 0xLIFE  |

**Requirements**

Requirements 1-4 are the same as [Finish Level N](#finish-level-n) template.

- 5: a checkpoint to represent the point from where the player is suposed to start the chalenge of not losing a life. If the game has a level intro screen, it can be a good checkpoint.
- 6: reset hit count if life decreased.

The requirement 6 can also be used to reset hit count if a weapon was used, damage taken, or anything else that you want the player to NOT do.



## Finish Level N with Item

ID | Special? | Memory   | Cmp | Type  | Mem/Val | Hits
---|----------|----------|-----|-------|---------|-----
 1 |          | 0xLEVEL  | =   | Value | N       | (1)
 2 |          | 0xLEVEL  | =   | Value | N+1     |
 3 |          | 0xLEVEL  | >   | Delta | 0xLEVEL |
 4 | ResetIf  | 0xLEVEL  | =   | Value | TITLE   |
 5 |          | 0xITEM   | =   | Value | TRUE    |

**Requirements**

Requirements 1-4 are the same as [Finish Level N](#finish-level-n) template.

- 5: the player have the item


## Collect an Item in a specific Level

This template is for battery save or password protection for items. It avoids awarding "get item X" by loading to where player already has the item. It checks that an item is collected in the level/room ID it is supposed to be collected, and only allows it be earned at that time.

ID | Special? | Memory   | Cmp | Type  | Mem/Val      | Hits
---|----------|----------|-----|-------|--------------|-----
 1 |          | 0xITEM   | =   | Value | FALSE        | (1)
 2 |          | 0xITEM   | =   | Value | TRUE         |
 3 | ResetIf  | 0xLEVEL  | !=  | Value | collect level|


**Requirements**

- 1: Do not have the item when entered the collect level, the hit is a checkpoint so 1&2 can both be true at once.
- 2: Have the item
- 3: Reset hit counter if in a level different than the one where the item must be obtained


Requirements 1 and 3 together mean "arrived the level/Room ID without the item".

Even if the player loads a savestate and goes to the required level they will not be able to add hits to condition 1, thus they can't get it except in normal gameplay.  

It does not necessarily have to be level/Room ID. There are other ways to approach this problem, for example a unique Mem/Val that only occurs on collection. Etc.


## Collected 100% of Something

This is limited battery save /password protection for when a player will collect 100% of something like clearing each stage in Super Mario world, or getting a 100% collection rate in Super Metroid. It's necessary so that a player cannot just load a save at 100% and get the achievement for free. (As usual there are other ways to approach this problem too.)

ID | Special? | Type | Memory   | Cmp | Type  | Mem/Val      | Hits
---|----------|------|----------|-----|-------|--------------|-----
 1 |          | Delta| 0xCollectPercent  | <  | Value | 100% value   |
 2 |          | Mem  | 0xCollectPercent  | =  | Value | 100% value   |
 3 | PauseIf  | Mem  |0xPlayerState | !=  | Value | Specific mode/point in game where % is increased|

Using the correct address value for condition 3 is especially important. You need to find an address that represents a unique time in the game where this percent increases. You'd not want the achievement to trigger when the player is loading their in game save file, which means this achievement must be paused at that time.

**Example**: In Super Mario World this change happens while the player sees the world map after completing a stage.

**Note:** This is similar in behavior and result to [Collect an Item in a specific Level](#collect-an-item-in-a-specific-level).


## Circumvent the Problem of a Counter Incrementing Twice in the Same Frame

In the [Collecting an Item N times](#collecting-an-item-n-times) we are counting how many times the counter goes up. But in some games there are situations where the counter goes up twice in the same frame, and the hit counter is incremented only by one. This behavior, obviously, ruins our logic. We're going to see a way to circumvent this issue.

The technique used here relies on two other ones:

- [using `SubSource` to count specific increments](/development/subsource#using-subsource-to-count-increments)
- [`AddHits` Flag](/development/addhits-subhits/)

Here's the trick:

ID | Special? | Type | Memory   | Cmp | Type  | Mem/Val | Hits
---|----------|------|----------|-----|-------|---------|-----
 1 | SubSource| Delta| 0xCOUNT  |     |       |         |
 2 | AddHits  | Mem  | 0xCOUNT  | =   | Value | 0x02    |
 3 |          | Mem  | 0xCOUNT  | >   | Delta | 0xCOUNT | (N)
 4 | ResetIf  | Mem  | 0xLIVES  | <   | Delta | 0xLIVES |

It can looks a bit confusing at a first sight, but maybe using a real example it can be more clear. Check the [Circumvent the Problem of a Counter Incrementing Twice in the Same Frame](/development/achievement-creation-tutorials#circumvent-the-problem-of-a-counter-incrementing-twice-in-the-same-frame).


## Check for a specific value changing to another specific value ten times

In this example we want to detect a value changing from `V1` to `V2` ten times:

ID | Special? | Type | Memory   | Cmp | Type  | Mem/Val      | Hits
---|----------|------|----------|-----|-------|--------------|-----
 1 | AndNext  | Delta| 0xADDRESS| =   | Value | 0xV1         | 
 2 |          | Mem  | 0xADDRESS| =   | Value | 0xV2         | (10)

**Requirements**

- 1: If value in `0xADDRESS` in the previous frame is `0xV1`
- 2: AND If the current value in `0xADDRESS` is `0xV2`, increases the hitcount (up to 10).


## Conditional Resets
Conditional resets can be used for many things.

Lets say you want to have a reset if a player enters a certain X and Y zone of a level:

**CORE**  

- The Core is whatever condition(s) you need for your achievement to be true. It can also include normal reset behavior.

**ALT1**

ID | Special? | Type | Memory     | Cmp | Type  | Mem/Val      
---|----------|------|------------|-----|-------|-------------
 1 | ResetIf  | Mem  | 0xLEVEL    | =   | Value | LEVELID     
 2 | PauseIf  | Mem  | 0xX-COORDS | >   | Value | RESET-X-ZONE
 3 | PauseIf  | Mem  | 0xX-COORDS | <   | Value | RESET-X-ZONE
 4 | PauseIf  | Mem  | 0xY-COORDS | >   | Value | RESET-Y-ZONE
 5 | PauseIf  | Mem  | 0xY-COORDS | <   | Value | RESET-Y-ZONE

- The reset will only happen if all of the Pauseif conditions are not true.
- The pause is local to the alt but the reset resets the entire achievement.

**ALT2**

ID | Special? | Type | Memory | Cmp | Type  | Mem/Val 
---|----------|------|--------|-----|-------|---------
 1 |          | Mem  |    0x1 | =   | Mem   |     0x1 

- Any true condition. (to satisfy alt behavior having an always true alt is needed)

- **Note:** You can use multiple conditional resets, each one in their own alt group to have far greater control of reset behavior.