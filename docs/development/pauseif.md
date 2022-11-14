The `PauseIf` can be chosen in the Flag column of the Achievement Editor.

While true, the `PauseIf` pauses activity for most conditions **in the same group**. It *does not* pause conditions in other groups (more about [Alt Groups](/development/alt-groups/) below).

**Note**: Keep in mind that `PauseIf` has priority over a `ResetIf` condition! In other words **`ResetIf` won't work while a `PauseIf` is active in the same group**.

The `PauseIf` is usually used to prevent hit counts from going up during a specific situation (like when the game is paused). It's used when you want to keep previously earned hit count, but don't want to increment it or reset it while something else is going on.

**Also Note**: A `ResetNextIf` condition attached to the active `PauseIf` condition is _not_ paused. However, a `ResetNextIf` outside of the active `PauseIf` does get paused. This is the only case where a condition inside a paused group can still work. `ResetNextIf` attached to a `PauseIf` is useful for resetting a `PauseIf` with hit counts (see below) to unpause a group without resetting hit counts elsewhere in the group.

## `PauseIf` with hit counts

A `PauseIf` condition with a hit count target will only trigger when the hit count target is met. Once the hit count target is met, the group **remains paused until a `ResetNextIf` condition attached to the active `PauseIf` condition is true**, or **until a `ResetIf` condition in *another* group is true**, or until the game is reset. A `PauseIf` without a hit count will unpause when the condition is no longer true.
