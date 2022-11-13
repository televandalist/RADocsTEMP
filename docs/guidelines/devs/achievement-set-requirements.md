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
	  *See also*: [Achievement Templates](/development/achievement-templates/) and [Achievement Creation Tutorials](/development/achievement-creation-tutorials/) for some well known protection techniques.

### Recommended, but not required

1. Basic [Rich Presence](/development/rich-presence/).
2. Leaderboards for scores and time challenges.
3. Missable achievements flagged, especially for RPGs and long games. 
    - Use `[m]` in the end of achievement's title to flag it as missable.
4. An achievement guide. Guides can be created and posted [here](https://github.com/RetroAchievements/guides/wiki). 
5. For games with text-triggered achievements (especially RPGs) it's recommend to find an event flag instead of hooking onto text or text ID. Text presentation varies between regional versions making multi-region support difficult.

### Tools to Help you Succeed

We have a [roadmap](/development/set-development-roadmap/) you can use as a guideline to create a good achievement set.  
We also have an [achievement design guide](/development/design/) on how to design good achievements, not the technical side but the conceptual. Creating a balanced set is one of the most difficult aspects of development, we have a [set balance guide](/development/difficulty-scale-and-balance/) which will help you in thinking about how to create a set that flows.

It is preferable and recommended to work on one set at a time. But if you have more, be open for a teamwork or even delegate the set creation if another dev contacts you.

## Code Notes

Leave accurate code notes for each address you use for achievement conditions. This helps you and others maintain the set, keeping it free of bugs.

You're free to add any code notes you discover to any set without declaring intentions to work on the game. Just be careful to not delete previous notes added by someone else.

## Scoring

There is no set point cap. When scoring achievements match your scores to one of these 5 tiers.

-   0-5 Easy / Minor Significance  
-   10 Medium / Intermediate Significance  
-   25 Hard / Major Significance  
-   50 Very Hard / Completion Level Significance  
-   100 "Impossible" (Typically for bonus sets)  

There are other [factors](#factors-to-consider-while-scoring-achievements) you should consider as well, such as achievement spread and game length.

Scoring from set to set will never perfectly match up, but this scoring system allows the points earned to more closely match skill and effort.

### Exceptions
Some games may come up as exceptions to the normal scoring tiers and will be listed here.
- Picross and Sudoku achievements fall under a special scoring category as follows based on difficulty:
Easy - 1 point,
Medium - 2-3 points,
Hard - 4-5 points
- Picross 3D is an exception to this rule and is scored normally
- Further exceptions can be requested by Code Reviewers and/or Admins on a case by case basis

### Rescoring

Up until June 2019, RetroAchievements had a 400-point cap per set, with no restrictions on individual achievements. The set cap was removed to put less focus on set totals and more on the achievements themselves. This initiative was also meant to eliminate the misconception that a set worth 400 points is a "complete" set. 

As with revisions and aesthetic changes, a rescore typically requires community approval. You can find more information on rescores [here](/guidelines/revision-guidelines/#rescores).

### Factors to Consider While Scoring Achievements

#### Difficulty

Consider for the whole set:

- What percent of players earned the achievement?
- How hard were the achievements for you?
- What is the current score compared to others achievements?
- How much time, effort and practice does it take to learn the necessary skills to complete the achievement, game and entire set?

#### Significance

How important is the achievement to the game?

- Beating the game is major significance.
- Defeating a boss is intermediate significance.
- Collecting a powerup is minor significance.

#### Achievement Spread

Imagine you had two versions of the same set, with the same difficulty:

- If the set has many similar achievements they should each be scored lower.
- If it has few they should be scored higher.

#### Game Length

- For long games achievements should be scored somewhat higher than short games.
- RPGs are often much longer than other genres. Game length should be a factor in scoring but is lesser than the other three.

[Examples](https://retroachievements.org/viewtopic.php?t=9050&c=47755).