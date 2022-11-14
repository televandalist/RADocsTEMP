In the Achievement Editor, the field on the far right side is Hit Count.

![image](/development/images/hitcounts.png)


The default is Zero, which means the condition must be true for the achievement to trigger.

If you set a target hit count, like 5, it means the condition must be true for at least that many frames, and once that hit count target is met, it doesn't need to be met again at any other time.

**PLEASE NOTE**: if a condition has a non-zero hit count, and reaches the number required, this condition is no longer tested. It  remains true, **UNLESS** you have a [`ResetIf`](/development/resetif/), which we will discuss below.

Conditions with [`Reset If`](/development/resetif/) and [`PauseIf`](/development/pauseif/) flags can also have hits. Follow the links for details.

In the [Achievement Creation Tutorials](/development/achievement-creation-tutorials/) section there are two examples good examples:

- [Using Hit Counts as a Timer](/development/achievement-creation-tutorials#using-hit-counts-as-a-timer)
- [Using Delta Values and Hit Counts to Detect an Increment](/development/achievement-creation-tutorials#using-delta-values-and-hit-counts-to-detect-an-increment)

### Effect of Resetting the Emulator

When the emulator is reset, all hits are immediately zeroed out and the achievement is set back to Waiting. However, an emulator reset does not clear out memory, so it's possible for the hits to reaccumulate before the game reinitializes the memory. As such, you should not rely on the hits being cleared out by the emulator reset.

Similarly, when the emulator first "powers on", the state of memory is not guaranteed to be consistent as true hardware does not initialize its memory. Instead, the software sets some initial state when it claims portions of memory. Some games actually rely on the random nature of the uninitialized memory to seed their random number generators.

For both cases, you should have an explicit reset for some piece of knowable logic, like the player being on the title screen.