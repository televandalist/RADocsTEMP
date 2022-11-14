### Memory sizes

Size          | Prefix | Example   |
:------------:|:------:|:---------:|
Bit0          | `0xM`  | `0xM01234`
Bit1          | `0xN`  | `0xN01234`
Bit2          | `0xO`  | `0xO01234`
Bit3          | `0xP`  | `0xP01234`
Bit4          | `0xQ`  | `0xQ01234`
Bit5          | `0xR`  | `0xR01234`
Bit6          | `0xS`  | `0xS01234`
Bit7          | `0xT`  | `0xT01234`
Lower4        | `0xL`  | `0xL01234`
Upper4        | `0xU`  | `0xU01234`
8bit          | `0xH`  | `0xH01234`
16bit         | `0x `  | `0x 01234`
24bit         | `0xW`  | `0xW01234`
32bit         | `0xX`  | `0xX01234`
16bit BE      | `0xI`  | `0xI01234`
24bit BE      | `0xJ`  | `0xJ01234`
32bit BE      | `0xG`  | `0xG01234`
[BitCount](/development/bitcount-size/) | `0xK`  | `0xK01234`
Float         | `fF`   | `fF01234`
MBF32         | `fM`   | `fM01234`

### Prefixes

Modifier | Prefix | Example |
:-------:|:------:|:-------:|
[Delta](/development/delta-values/) | `d` | `d0xH1234`
[Prior](/development/prior-values/) | `p` | `p0xH1234`
[BCD](/development/value-definition#binary-coded-decimal) | `b` | `b0xH1234`
[Invert](/development/value-definition#binary-inversion) | `~` | `~0xH1234`

### Logical Flags

Flag | Prefix | Example   |
:---:|:------:|:---------:|
[ResetIf](/development/resetif/) | `R:` | `R:0xH1234=1`
[ResetNextIf](/development/resetnextif/) | `Z:` | `Z:0xH1234=1`
[PauseIf](/development/pauseif/) | `P:` | `P:0xH1234=1`
[AndNext](/development/andnext-ornext/) | `N:` | `N:0xH1234=1`
[OrNext](/development/andnext-ornext/) | `O:` | `O:0xH1234=1`
[AddSource](/development/addsource/) | `A:` | `A:0xH1234=1`
[SubSource](/development/subsource/) | `B:` | `B:0xH1234=1`
[AddHits](/development/addhits-subhits/) | `C:` | `C:0xH1234=1`
[SubHits](/development/addhits-subhits/) | `D:` | `D:0xH1234=1`
[AddAddress](/development/addaddress/) | `I:` | `I:0xH1234=1`
[Measured](/development/measured/) | `M:` | `M:0xH1234=1`
[Measured%](/development/measured/) | `G:` | `G:0xH1234=1`
[MeasuredIf](/development/measured/) | `Q:` | `Q:0xH1234=1`
[Trigger](/development/trigger/) | `T:` | `T:0xH1234=1`