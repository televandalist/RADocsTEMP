In this example you'll see how hit counts can be used as a timer and award an achievement if a condition is true for 10 seconds.

Let's see how [Super Hang-On (Mega Drive)](http://retroachievements.org/Game/16)'s achievement [Speed Freak - Maintain at least 300kph for 10 seconds](http://retroachievements.org/Achievement/71) looks like in Achievement Editor dialog:

**Addresses**

- `0x0055a`: is the speed.
- `0x0c757`: is 0x00 when the game is unpaused.

![speedfreak-example](/developers/realexamples/images-realexamples/speedfreak-example.png)

In this achievement, we wish for there to be a fact or condition that is true 600 times consecutively. The reason for this is that the genesis is locked into processing 60 frames of logic per second (NTSC at least?). And the fact we're looking for is "speed is over 300". Also, we want the player to keep the speed above 300 without pausing the game.


**Conditions**

1. player's speed is above 300 for 600 frames (or 10 seconds have passed).

2. reset the hit counter if speed is under 300.

3. reset the hit counter if the player pause the game.