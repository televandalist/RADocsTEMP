## Introduction

Rich Presence **(RP)** is brief overview of what active players are currently doing in their game. To have RP in a game you need a Rich Presence Script **(RPS)** which is created by Developers. The Script checks the player's game memory and as programmed reports the values of certain addresses with definitions assigned by the Developer such as which stage the player is on, how many lives they have, if the game is paused, what game mode they are playing, what the player has accomplished, etc. This information is reported back to the website. 

**Example of RP in action:**

![Example of RP in action](https://i.imgur.com/E5097sz.png)  


To see the RP live in a game click on the RetroAchievements menu in your emulator and then click on Rich Presence Monitor. A small window will show you your active RP. (Good for debugging)

![Rich Presence Monitor](https://i.imgur.com/XkCZoLG.png)

The best way to understand Rich Presence is to look at various examples in game, look at the addresses used and look at how the text is displayed in the Rich Presence Monitor and on site.

### How Does it work?

Every time a game is launched, it fetches the achievements in a 'patch' file for the ROM which details all the achievements and memory addresses (and leaderboards) that can be watched for. It will also request a Rich Presence Script for the currently loaded ROM. The emulator will report back to the website every 120 seconds. Similarly, every 120 seconds or so, the 'active players' box on the front page will refresh, detailing the last known activity of all active players. If there isn't a rich presence script given, the text will be 'earning achievements' if playing a game with achievements, 'playing [game]' if playing a game without achievements, or 'developing achievements' if the memory dialog is open and visible. 

The RPS for each game can be found under the development section on each game's page: 

![Dev click](https://i.imgur.com/sqxOjyL.png)

![RP shown](https://i.imgur.com/e7qoaNx.png)
 
## Example (Super Mario Bros.)

```
Format:Digit
FormatType=VALUE

Lookup:Mode
0=[Demo] 
2=[World Complete] 

Lookup:Paused
0x81=▌▌ 
0x80=▌▌ 
1=▌▌ 

Lookup:Star
5=🌟 
4=🌟 
3=🌟 
2=🌟 
1=🌟 

Lookup:Powerup
0=Small
1=Super
2=Fire

Lookup:Swimming
1= swimming

Lookup:Status
0= [Loading]
1= taking a vine warp
2= entering a warp pipe
3= entering a warp pipe
4= 🚩
5= [Stage Complete]
6= [Game Over]
7= [Entering Area]
9= growing
0xA= shrinking
0xB= 💀
0xC= powering up

Lookup:Quest
0x0=1st
0x1=2nd

Display:
@Mode(0xh770)@Paused(0xh776)@Star(0xM79f_0xN79f_0xo79f_0xP79f_0xQ79f_0xR79f)@Powerup(0xh0756) Mario in @Digit(0xh75f_v1)-@Digit(0xh75c_v1)@Swimming(0xh704)@Status(0xhe), 🚶:@Digit(0xh75a_v1), @Quest(0xh7fc) Quest
```
It breaks down into a series of Lookup objects, Format objects and one Display object. 

## Lookups 

Lookups are defined like this: 
```
Lookup:NameOfLookup
1=Text When 1
2=Text When 2
...
``` 
When a Display string references a Lookup, it's Value will be located in the table and the associated text will be displayed.

**NOTE**: Values in the Lookup should be in decimal. If you want to use hex values, include a `0x` prefix. (i.e. `0x12=Eighteen`)

You can also specify multiple values for a single text string:
```
1-5,10=Text When These Values
*=Text For All Other Values
```
In this example, the values 1, 2, 3, 4, 5, and 10 all map to the first text string.

Anything that doesn't match an item defined in the lookup table will return the text associated with `*`. If `*` does not appear in the lookup table, no text will be returned if a value doesn't have an entry.


## Format 

Format tables are defined like this:
```
Format:Score
FormatType=VALUE
```

Begin with `Format:`, then the name of the Format converter. On the next line, give `FormatType=`, then one of the following:

- `VALUE`: generic value, no leading zeroes. 
- `SCORE`/`POINTS`: generic value, padded with leading 0s to 6 digits.
- `TIME`/`FRAMES`: value describes the number of frames elapsed, and will be turned into 00:00.00 by multiplying by 100 (hundredths of a second) and dividing by 60 (frames per second). If your system runs at something other than 60 fps, you'll have to do the conversion yourself and use `MILLISECS`.
- `MILLISECS`: value describes the number of hundredths of a second elapsed, and will be turned into 00:00.00 
- `SECS`: value describes the number of seconds elapsed, and will be turned into 00:00 
- `MINUTES`: value describes the number of minutes elapsed, and will be turned into 0h00
- `SECS_AS_MINS`: value describes the number of seconds elapsed, and will be turned into 0h00


## Display

Display is a string that gets shown in the 'Active Players' box on the front page and the 'Last Seen In' section of the player's profile.

It is built by replacing any macros in the display string with text from a Lookup or formatted values from a Format converter. Each macro is identified by a single '@', which is followed by the name for the Lookup or Format (case sensitive!), and immediately after, in parenthesis, a value specifying what to send to that Lookup or Format object.

`Using @Powerup(0xh756)!` 

This means use the Lookup or Format that's called `Powerup`, and give it whatever 8-bit value is in the address 0x756. After converting, put the result in between "Using " and "!".

**NOTE**: Lookup/Format names are case sensitive and must exactly match the usage in the Display string: `@test(0x1234)` will not find `Format:Test`

**NOTE**: Lookup/Format definitions cannot contain spaces before or after the name. `@test(0x1234)` will not find `Format:test   ` or `Format:   test`

### Example Lookup Breakdown

- `@Mode(0xh770)` - Lookup for the address that shows if the game is in demo mode or a world has been completed.  
- `@Paused(0xh776)` - Lookup for the address that shows if the game is paused (3 values are used, two of them are for pausing and unpausing).  
- `@Star(0xM79f_0xN79f_0xo79f_0xP79f_0xQ79f_0xR79f)` - Lookup for the address of if Mario has Star invincibility. More on this later.  
- `@Powerup(0xh756)` - Lookup for the address that show if Mairo is Small, big or has fire power.  
- `Mario in` - Static text to string lookup and format objects together.  
- `@Digit(0xh75f_v1)` - `Digit` is a format object defined as a value. The address 0xh75f is the World minus 1 (because it it 0 based, as in it starts counting at 0). `_v1` Means + value 1. `_v+1` is also correct.  
- `-` - More static text to split World and Level. as in the hypen in World 1-1.  
- `@Digit(0xh75c_v1)` - Another use of the `Digit` format object. This time It's looking up the stage. World 1-X.  
- `@Swimming(0xh704)` - Lookup for the address that shows if the player is swimming.  
- `@Status(0xhe)` - Lookup for the address that shows Mario's status, such as going through pipes.  
- `, 🚶:` - More static text. 🚶 is a symbol for lives.  
- `@Digit(0xh75a_v1)` - Third use of the `Digit` format object. This time it's checking the player lives address.  
- `, ` - Static text.  
- `@Quest(0xh7fc)` A lookup to see if the player is in normal or on the 2nd quest, hardmode.  
- ` Quest` - Static Text.  

### Address size

To specify what size of address you are are checking there are various characters used. (capitalization is ignored)

- A 16bit address is default and has no character designation. At 0x10 the address is two bytes - 16 bits.
- An 8bit address's character is `h` (or `H`). At 0xh10 the address is one byte - 8 bits. `xxxx xxxx`  
- An upper4 address's character is `u` (or `U`). At 0xu10 the address is one nibble - 4 bits. `xxxx 0000`  
- A lower4 address's character is `l` (or `L`). At 0xl10 the address is one nibble - 4 bits. `0000 xxxx`  
- A bit0 address's character is `m` (or `M`). At 0xm10 the address is one bit, the lowest bit: `0000 000x`  
- A bit1 address's character is `n` (or `N`). At 0xn10 the address is one bit, the second bit: `0000 00x0`  
- A bit2 address's character is `o` (or `O`). At 0xo10 the address is one bit, the third bit: `0000 0x00`  
- A bit3 address's character is `p` (or `P`). At 0xp10 the address is one bit, the fourth bit: `0000 x000`  
- A bit4 address's character is `q` (or `Q`). At 0xq10 the address is one bit, the fifth bit: `000x 0000`  
- A bit5 address's character is `r` (or `R`). At 0xr10 the address is one bit, the sixth bit: `00x0 0000`  
- A bit6 address's character is `s` (or `S`). At 0xs10 the address is one bit, the seventh bit: `0x00 0000`  
- A bit7 address's character is `t` (or `T`). At 0xt10 the address is one bit, the top bit: `x000 0000`  
- A 32bit address's character is `x` (or `X`). At 0xx10 the address is four bytes and 32 bits.
- A 24bit address's character is `w` (or `W`). At 0xW10 the address three bytes and 24 bits.

Summarizing on a table:

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
24bit         | `0xW`  | `0xW123`
32bit         | `0xX`  | `0xX01234`

### Conditional Display Strings

```
Display:
?0x 000085=0?Title Screen
?0xT00007c=1?Custom Map in @Landscape(0xH00016c)
Playing Battle @Battle(0x 00007c*0.2) in @Landscape(0xH00016c)
```

The existing `Display:` marker is still used to indicate the start of the display block. If the next line starts with a question mark, it is considered to be a conditional display string. The portion of the line between the two question marks is the conditional clause. If the conditional clause evaluates true, then the remaining portion of the line is used as the display string. If it does not evaluate true, then processing proceeds to the next line. If it starts with a question mark, the same process repeats. If it does not start with a question mark, the entire line is used as the default display string.

**NOTE**: A default display string is required in case none of the conditional display strings match. If you only have conditional display strings, the script will appear to do nothing.

Looking at this example, if the 16-bit value at $0085 is 0, the display string is `Title Screen`. If not, the next line is examined. If the 7th bit of $007C is 1, the display string is `Custom Map in @Landscape(0xH00016c)`. If not, the final line does not have a conditional clause and is used.

Display strings associated with a conditional clause support all of the same syntax as the default display string. In this example, you can see the `@Landscape` lookup is used in both the conditional display string and the default display string. The lookup itself only has to be defined once.

The conditional phrase supports all of the previously mentioned address accessors as well as AND (_) and OR (S) logic. Note that OR clauses still require a 'core' group, [just like achievements](Alt-Groups).

* `?0xH1234=32_0xH2345=0?and example`

    if the 8-bit value at $1234 is 32 _and_ the 8-bit value at $2345 is 0, display `and example`

* `?0xH1234=32S0xH2345=1S0xH2345=2?or example`

    if the 8-bit value at $1234 is 32 _and_ the 8-bit value at $2345 is 1 _or_ 2, display `or example`

* `?0xH1234=32_0xH5678=33S0xH2345=1S0xH2345=2?and/or example`

    if the 8-bit value at $1234 is 32 _and_ the 8-bit value at $5678 is 33 _and_ the 8-bit value at $2345 is 1 _or_ 2, display `and/or example`

**Pro-tip:** Conditions can be created using the [achievement editor](Achievement-Logic-Features). Once you have your condition defined, use the `Copy Def` button to copy the achievement definition to the clipboard so you can paste it into the rich presence script.


## Binary Coded Decimal (BCD)

BCD is when the values are store in an address from as 0-9 (one digit) or 0-99 (two digits). Keep in mind that most often values are stored in hexidecimal, but sometime games will store them in this way and here's the best way to handle these addresses in your display.

BCD decoding treats each hex character as a decimal digit. If the memory inspector shows 86 (in hex), the result of BCD decoding the value would be 86 (in decimal).

For value objects you can use the BCD prefix, as in `b0xh1234`. This also works with [leaderboard values](Leaderboards#value-interpreter).
Note that you still need to specify the size of the BCD memory address. `b0x1234` reads a 16-bit value. `b0xh1234` reads an 8-bit value and `b0xX1234` reads a 32-bit value.
_NOTE_: Support for 16-bit and 32-bit BCD decoding is a feature of the 0.075 toolkit.

This is most commonly used for score and time, but often other types of display values.

## Limits

- 65,535 character limit for script  
- 255 character limit for what is displayed  
- Unicode characters are allowed, some use more characters than 1

## Tips and Tricks

- Comments can be added anywhere in the script. A double slash (`//`) indicates the remaining portion of the line should be ignored when processing the script. Note: comments still apply toward the script size limit.
- Lookup names can be as short as a single character if you need to squeeze in a few extra characters.
- Leading zeros can be removed from addresses (`0xh0001` can be shortened to `0xh1`).
- Turning all your values from hex into decimal will take up less characters.
- Unicode characters don't always "take up less space" they often take up to four system characters.
- Each `Lookup` or `Format` named mapping can be referenced multiple times with the same or different addresses. You can define a single `Format:Number FormatType=VALUE` instead of defining individual ones for Lives, Score, Level, etc.
- Putting spaces in your Lookups sometimes before or after can allow you to hide certain lookups when they are not needed, like how `@Pause`, `@Star`, `@Swimming`, and @Mode do. 


### Value Properties

When using lookup and format objects `@object()` it's possible to combine and perform calculations. Macro values support everything that [leaderboard values](Leaderboards#value) support, so you can use multiplication, addition, and even some logic to generate values that aren't directly available in memory.

**Example**
`@Score(0xh28*10_0xh29*1000_0xh26*100000) points` 

This means use the Lookup or Format `Score`, and give it the sum of:  
- the 8-bit value at 0x28 times 10, ADD  
- the 8-bit value at 0x29 times 1000, ADD  
- the 8-bit value at 0x26 times 100000  

## Unicode Standard Symbols
You can without doubt use these symbols in rich presence.

▌▌=Paused  
🔁=Continues  
⏰=In Game Time/Game Clock  
🔑=Keys  
💣=Bombs  
❤️ or ❤=In a game with hearts (e.g. Zelda)   
💰=Money  
🚩=Level/Stage   

While making Rich Presence devs need to be careful that they are communicating clearly. If you are using non-standard symbols they will make sense to you but could be entirely confusing to others. **When using non-standard symbols, check them with someone else** or a few people to see if the symbols you use make sense. If they don't, use better symbols, use text or use symbols alongside of text.

For custom unicode/emoji [ShapeCatcher](http://shapecatcher.com/) is an excellent resource, you can draw what you're looking for and an AI will find similar matches. Just be careful to not use unicode that *too obscure*, as they don't all display on all systems.

Take note of community display preference:
![image](https://user-images.githubusercontent.com/32706333/56547116-a65a7c80-6539-11e9-951c-83b4f9930b3e.png)

## Developing Rich Presence

The toolkit does not currently have an integrated Rich Presence editor, but you can test local changes before putting them on the server. Once you've started a game and the current Rich Presence has been downloaded from the server, you can find it in `RACache\Data\XXX-Rich.txt` where XXX is the game ID. 

The Rich Presence Monitor (openable from the RetroAchievments menu) reads this file and shows the current value every second while the window is open.

If you make changes to the `XXX-Rich.txt` file, and reselect the menu option, it will read the new changes and allow you to immediate test them without applying the changes to the server. Continue to make changes and reselect the menu option until the script is behaving as you expect, then copy the contents to the server page to make it available to everyone else.

**NOTE**: The `XXX-Rich.txt` file is overwritten with the current server data each time the game is opened. As long as you still have the file open in an editor, you can always save your changes over the updated file after reopening the game.

### Parse Errors

|Code|Enum|Description|
|----|----|-----------|
|-2|`INVALID_MEMORY_OPERAND`|A memory operand was expected and not found. Memory operands start with `0x`, then a size indicator. The most common causes of this are forgetting the `0x` or having an `_S` or `__` in the script.|
|-3|`INVALID_CONST_OPERAND`|A lookup key could not be evaluated. The most common cause of this is using hex without the `0x` prefix. This may also occur on older versions of RetroArch when using CSV or range keys for lookups.|
|-6|`INVALID_OPERATOR`|An unknown operator was encountered. The most common cause of this is using `!` instead of `!=`|
|-16|`MISSING_VALUE`|A macro was encountered without providing a value (i.e. `@Points` instead of `@Points(0xh1234)`)|
|-18|`MISSING_DISPLAY_STRING`|The rich presence script did not contain a `Display:` element, or contained only conditional display strings|
|-20|`RC_INVALID_VALUE_FLAG`|A non-combining flag is used in a non-trigger context. Combining flags are AddSource, SubSource, AddHits, AddAddress and AndNext.

Additionally, if you see `[Unknown macro]`, that means the macro name could not be resolved. For example `@Points(0xh1234)` without defining `Format:Points` would generate `[Unknown macro]Points(0xh1234)`.

This issue happens sometimes when a Rich Presence is created in the `<GameID>-Rich.txt` file in the `RACache>Data` folder. In this case the issue can be fixed by adding an empty line at the start of the file.