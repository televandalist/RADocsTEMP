### Every Achievement Set MUST Have

Not abiding by the following guidelines can result in the achievements being demoted until the requirements are met:

1. Content covering up to completion so long as the game can be beaten. Whether it be defeating the final boss, completing a first loop, or completing all puzzles, achievement sets that do not cover at least beating the game are deemed unfinished and therefore subject to demotion. **Arcade-style games where the focus is on high scores (such as Pac-Man and Crystal Castles) are exempt from this rule.**
2. Each achievement must have a badge. They do not need to be distinct from each other, but do not leave them blank.
3. Game information (Developer, Publisher, Genre, and Release Date) filled in on the website.
4. Game images (Game Icon, Title Screen, Screenshot, and Box Art).
  - An exception to having no box art is if the game does not have official box art. If this is the case, you can either make one from a template or link it to the [hub for missing box art](https://retroachievements.org/game/10214).
5. **Protection** for situations where the players can get achievements without effort, such as:
  - Demo mode
  - In-game cheat codes
  - Battery saves
  - Passwords
  *See also*: [Achievement Templates](/developers/achievement-templates) and [Real Examples](/developers/real-examples) for some well known protection techniques.

### Recommended, but not required

1. Basic [Rich Presence](Rich-Presence) (only available for full-devs).
2. Leaderboards for scores and time challenges (only available for full-devs).
3. Missable achievements flagged, especially for RPGs and long games. 
    - Use `[m]` in the end of achievement's title to flag it as missable.
4. An achievement guide. Guides can be created and posted [here](https://github.com/RetroAchievements/guides/wiki). 
5. For games with text-triggered achievements (especially RPGs) it's recommend to find an event flag instead of hooking onto text or text ID. Text presentation varies between regional versions making multi-region support difficult.

### Tools to Help you Succeed

We have a [roadmap](Set-Development-Roadmap) you can use as a guideline to create a good achievement set.  
We also have an [achievement design guide](Achievement-Design) on how to design good achievements, not the technical side but the conceptual. Creating a balanced set is one of the most difficult aspects of development, we have a [set balance guide](Difficulty-Scale-and-Balance) which will help you in thinking about how to create a set that flows.

It is preferable and recommended to work on one set at a time. But if you have more, be open for a teamwork or even delegate the set creation if another dev contacts you.

## Code Notes

Leave accurate code notes for each address you use for achievement conditions. This helps you and others maintain the set, keeping it free of bugs.

You're free to add any code notes you discover to any set without declaring intentions to work on the game. Just be careful to not delete previous notes added by someone else.