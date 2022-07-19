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
  - Using Hit Counts as a timer
  - Using Delta Values and Hit Counts to Detect an Increment
  - Circumvent the Problem of a Counter Incrementing Twice in the Same Frame
    - `note: need to add something about how the toolkit still uses hex even if the value is in BCD`
  - Various types of chains
  - When to use Reset If or Pause If
  - When to use Delta or Prior
  - Using BitCount for collectables
  - Using Add Source with `Mem / Mem` comparisons
  - Creating a Timer with Reset If hits based on the speed of the game
  - Using `bit0` to include or exclude odd-numbered values

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
  - Syntax Table