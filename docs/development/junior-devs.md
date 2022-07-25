*This info was taken from Carl's ?newjrdev command and needs to be adjusted for the docs*

# Junior Developers
Welcome to the Junior Developer channel! Here you can ask all the questions and get all the help you need to get started on becoming an achievement developer. It is recommended to read over [How to Become an Achievement Developer](https://docs.retroachievements.org/How-to-Become-an-Achievement-Developer/) before getting started.

With the addition of the Junior Developer site role you now access to some developer site features, more information on role permissions can be found [here](https://retroachievements.org/viewtopic.php?t=13332).

## Claiming a Set

In order to work on an achievement set you will need to make a claim on that games page using the new on site [claim system](https://retroachievements.org/viewtopic.php?t=17176). If the game page or forum topic does not exist, ping @Code-Reviewer and we will create it for you. As a Junior Developer you are only allowed to claim one set at a given time. When your code review is complete you are free to mark your claim as complete and claim another set.

Please let us know which set you are working on after claiming it.

## I Need Help with Something

General questions can be asked without needing to ping @code-reviewer.

If you need help with developer only tasks such as updating a games images, Leaderboards, Rich Presence, promoting/demoting achievements, resolving tickets, or linking/unlinking hashes, please ping @Code-Reviewer.

## My Set Is Done, Now What?

Ping the @Code-Reviewer role indicating that your set is complete and ready for to be reviewed. Your set will be added to the review backlog and will be marked with a :notepad_spiral:. The current review backlog can be found [here](https://docs.google.com/spreadsheets/d/e/2PACX-1vSl4tRG-wV1lxtb-2ZJYRoM0VLnQPYoQO1jOVRmb8TFWldFJGr7RrO6-I-c6rWK0XsZ1h5pJEOStjmQ/pubhtml?gid=1582422742&single=true). When your review is complete a code reviewer will reach out to you with your review evaluation. After the review has been completed the code-reviewer will promote your set to core so players can start earning your achievements.

Your set must meet the following criteria before it is ready for review:
 - All achievements must be promoted to unofficial.
 - All achievements must have valid points values. (0-5, 10, 25, 50, 100)
 - All achievements must have badges.
 - The game must have a icon.
 
 ## My Achievements Need To Be Updated, How Do I Update them?
 
 If your achievements are in unofficial you can modify them as you wish and commit the changes. If you achievements are in core you will need to ping @Code-Reviewer asking for the achievements to be demoted to unofficial so you can update them. After you have made the updates you can ping @Code-Reviewer asking for them to be promoted to core again.

Please include links to the achievements you need demoted/promoted. It makes the process much faster.

## How Long Does It Take To Become a Full Developer?

Typically only a few sets, but it will vary user to user. We evaluate each users ability to understand the toolkit features based on proficiencies which are outlined [here](https://retroachievements.org/viewtopic.php?t=10816). 

# Code Review

*This was taken from the old Code Reviwer's Checklist. Needs to be updated and worded to fit this page.*

This is a list of things that code reviewers usually check when someone submits a set to be reviewed.

## Code Notes

- [ ] Clearly written! [clear-code-notes](/development/images/clear-code-notes.png)

- [ ] For all addresses used in logic

- [ ] Describing appropriate values used where applicable


## Achievement Logic

- [ ] No achievements with only one condition.

- [ ] Demo mode protection (when applicable).

- [ ] Cheat codes protection (when applicable).

- [ ] No redundant logic (like `0xADDRESS = 1` and `ResetIf 0xADDRESS != 1`).

- [ ] Understanding the difference and the right use of PauseIf and ResetIf.

- [ ] On a "get 100 coins" like achievement, use `>= 100` rather than `= 100`.


## Achievement Design

- [ ] No [unwelcome concepts](https://github.com/RetroAchievements/docs/wiki/Developers-Code-of-Conduct#unwelcome-concepts).

- [ ] Achievements for "Finish level N" rather than "Reach level N+1".

- [ ] No "two for one" achievements (like one for defeating a boss and another one for getting the dropped item).