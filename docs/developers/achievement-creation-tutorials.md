[Intro](#intro)<br>

[Basics](#basics)<br>

[Achievement Editor](#achievement-editor)<br>
- [Flags](#flags)<br>
- [Types](#types)<br>
- [Sizes](#sizes)<br>
- [General Comparisons](#general-comparisons)<br>
- [Flag Specific Comparisons](#flag-specific-comparisons)<br>
- [Other Toolkit Features](#other-toolkit-features)<br>

[Protections](#protections)<br>

[Logic Tips and Tricks](#logic-tips-and-tricks)<br>

[Lesser-Known Features](#lesser--known-features)<br>

[Workflow Tips](#workflow-tips)<br>

[Things To Avoid and Why](#things-to-avoid-and-why)<br>

[See Also](#see-also)

## Intro
Page is heavily WIP, but the goal is to provide extensive documentation to cover every aspect of set development from start to finish. Will probably end up merging the "Real Examples" into this section somehow. Each flag, type, size, comparison, etc. will have its own page. Will also include several tips n' tricks, case studies, etc. 

## Basics
  - Adding Games to the Database
    - Everything you ever wanted to know (but were too scared to ask) about hashes
    - Patch Guide
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
  - Password Protection
  - Cheat Protection
  - Multiplayer Protection
  - Other
    - Dipswitch
    - BIOS (PlayStation and Saturn)

## Logic Tips and Tricks
  - Checkpoints hits
  - Pause Locks
  - Using Hit Counts as a timer
  - Using Delta Values and Hit Counts to Detect an Increment
  - Circumvent the Problem of a Counter Incrementing Twice in the Same Frame
  - Various types of chains
  - When to use Reset If or Pause If
  - When to use Delta or Prior
  - Using BitCount for collectables
  - Using Add Source with `Mem / Mem` comparisons
  - Creating a Timer with Reset If hits based on the speed of the game

## Lesser-Known Features
  - Double-Clicking bitflags while in 8-bit view
  - Right-Clicking addresses in the editor to jump to them in the Memory Inspector (also works with offsets to jump to the current address)
  - Highlighting conditions and holding CTRL while clicking to change a field in multiple conditions at once

## Workflow Tips
  - Using Google Sheets and Notepad++
  - Editing local file

## Things to Avoid and Why
  - Redundant Reset Ifs
  - Single-Condition achievements
  - Text-Based addresses

## See Also
  - Point Distribution
  - Badge Creation
  - Rich Presence
  - Leaderboards
  - RATools
  - Making Tutorial Videos