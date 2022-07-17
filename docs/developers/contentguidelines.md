## Basic Achievement Design Guidelines

### Unwelcome Concepts

You can (and should) be as creative as you can, but there are some concepts that are **NOT** welcome for achievements, such as:

1. Require Glitches/Bugs<sup>1</sup> (acceptable in [Bonus sets](Bonus-Sets)). 
2. Require two players (acceptable in "Multi" sets).
3. Require perfection all game (**maybe** acceptable in [Bonus Sets](Bonus-Sets)).
4. Dying (simply), or playing bad without any purpose (acceptable for extra content like special cutscene).
5. NSFW content in text or image.
6. Achievements popping frequently with little effort from the player (including multiple achievements for doing the same task, such as one for beating a boss and another one for getting the item left by the boss, etc.)
7. Achievements obtainable with zero effort for no meaningful purpose (example: start the game as character X, collect one coin, watch a video). It's acceptable if there's something fun/historical/interesting you want to address.
8. Require excessive repetitive grinding, such as reaching level 99 in an RPG, for no meaningful purpose (**maybe** acceptable in [Bonus Sets](Bonus-Sets)).
9. Rely entirely on randomness, especially when there are extremely low odds. However, for games where the randomness is a major aspect, it may be appropriate.
10. "Secret Achievements", where the players have no indication of what they're going after. If you want to prevent spoilers give at least a clue on the Achievement Title/Description. Otherwise the players will start to search on web or mess with Achievement Editor/Memory Inspector, and in the process they can stumble across even worse spoilers.
11. Sets for games that lack gameplay (videos, music visualizers, jukeboxes, etc.) won't be accepted without explicit approval. Approval will be handled via a vote by the QATeam on the Discord server, and requires implementation of sufficiently creative concepts. Book sets are still allowed, but must be worth 0 points. Example: SporyTike's GBA Video Series was presented with the idea to include a leaderboard quiz at the end of each episode. This unique plan involved gameplay past pressing start and was approved.
12. Sets for compilations featuring games that share the same console as the compilation. An example of this is 6-Pak for Genesis/Mega Drive, which contains six Genesis/Mega Drive games.
13. Prototypes/Beta sets if there is no discernible unique content from the main game. (This is just an extension of the demo rule).

<sup>1</sup> Glitches/Bugs are errors within a game's code which often cause unintended behavior. Examples are memory overflow, incorrectly loaded levels, and clipping into objects.

**Note**: With every rule, there are exceptions. This is especially true with unwelcome concepts. All unwelcome concepts have some wiggle room, so when in doubt, consult with the admin team.

### Every Achievement Set MUST Have

- All game page information filled out, and game images uploaded (if you're not a full-dev, send the images to the code-reviewers).
- Game Badges for each achievement (they don't need to be distinct from each other, just don't leave them blank).
- Content covering up to completion so long as the game can be beaten. Whether it be defeating the final boss, completing a first loop, or completing all puzzles, achievement sets that do not cover at least beating the game are deemed unfinished and therefore subject to demotion. **Arcade-style games where the focus is on high scores (such as Pac-Man and Crystal Castles) are exempt from this rule.**

**Protection** for situations where the players can get achievements without effort, such as:

1. Demo mode;
2. In-game cheat codes;
3. Battery saves;
4. Passwords.

**See also**: [Achievement Templates](Achievement-Templates) and [Real Examples](Real-Examples) for some well known protection techniques.


### Recommended but not required

- Basic [Rich Presence](Rich-Presence) (only available for full-devs).
- Leaderboards for scores and time challenges (only available for full-devs).
- Missable achievements flagged, especially for RPGs and long games. 
    - Use `[m]` in the end of achievement's title to flag it as missable.
- An achievement guide. Guides can be created and posted [here](https://github.com/RetroAchievements/guides/wiki). 
- For games with text-triggered achievements (especially RPGs) it's recommend to find an event flag instead of hooking onto text or text ID. Text presentation varies between regional versions making multi-region support difficult.


### Achievement Scoring

When [scoring](Achievement-Scoring) achievements match your scores to one of these 5 tiers. There is no achievement set point cap. 

-   0-5 Easy / Minor Significance  
-   10 Medium / Intermediate Significance  
-   25 Hard / Major Significance  
-   50 Very Hard / Completion Level Significance  
-   100 Sadistic (Typically for bonus sets)  

When scoring there are other [factors to be considered](Achievement-Scoring#factors-to-consider-while-scoring-achievements), such as achievement spread and game length.

### Tools to Help you Succeed

We have a [roadmap](Set-Development-Roadmap) you can use as a guideline to create a good achievement set.  
We also have an [achievement design guide](Achievement-Design) on how to design good achievements, not the technical side but the conceptual. Creating a balanced set is one of the most difficult aspects of development, we have a [set balance guide](Difficulty-Scale-and-Balance) which will help you in thinking about how to create a set that flows.

It is preferable and recommended to work on one set at a time. But if you have more, be open for a teamwork or even delegate the set creation if another dev contacts you.

## Revisions - Working on Sets with Existing Achievements

Revisions, as in working on a set that has existing achievements typically requires community approval by presenting your plan in the forum and in the **#revision-voting** channel in Discord. Not all changes need approval. See [Achievement Set Revisions](Achievement-Set-Revisions) for details.


## Code Notes

Leave accurate code notes for each address you use for achievement conditions. This helps you and others maintain the set, keeping it free of bugs.

You're free to add any code notes you discover to any set without declaring intentions to work on the game. Just be careful to not delete previous notes added by someone else.
