![radocslogo](images/radocslogo.png)

Welcome to the NEW [RetroAchievements](https://www.retroachievements.org) documentation!

!!! attention "Under Construction!"
    The docs are undergoing a much needed overhaul and I only put this here to test this thing out!

# RADocsTEMP

Welcome!

This repo is dedicated to coordinating a MASSIVE overhaul to the RetroAchievements documentation: https://docs.retroachievements.org/ There are many pages and/or sections of the current docs that are outdated or no longer relevant. The way it has been setup in the past: updates are made to the wiki, which in turn are deployed to the docs subdomain. However, when deploying, we do not see what changes were actually made. We have to cross our fingers and hope nobody screwed something up. Also, the format rarely looks as it should according to the wiki. For example: bullet lists don't have automatic line breaks so they have to be added manually. As you can probably imagine, this has the potential to get very nasty and makes keeping any sort of accurate changelog very frustrating, which is why that workflow absolutely must go. 

My proposal was to start from scratch, update, reorganize, expand, and clarify with an entirely new workflow:
1. Clone the docs repository (this one, for now).
2. Set up mkdocs (https://www.mkdocs.org/) to work with that repository. 
3. Edit the Markdown files locally, which can be previewed in a local instance, and save changes.
4. Submit a Pull Request to merge your changes with the main repository. 

So yes, making the actual edits will require some basic know-how with GitHub. If you're willing to learn, it isn't that difficult. If that is not for you, no worries, there will be other ways you can contribute to this project.

-------------------------

These are the biggest objectives in this overhaul:

1. Get rid of everything that is no longer relevant. RAGens? 400-point cap? Believe it or not, there are still mentions of these lurking about! 

2. Update any documentation that needs to be updated. Some rules/guidelines are out of date. Keep in mind we are not creating or revising policies here. If you disagree with a rule, this is not the place to discuss it.

3. Update images, gifs, etc. that show older versions of the toolkit, gameplay of achievements popping, etc., the site, etc. The current docs host the images in an "Issues" thread, which is not ideal at all. With the new workflow, they will be within the repo itself. No links will need to be changed; only the files themselves.

4. Completely recategorize so it's not simply "General" and "Developer" docs. 

5. Create a thorough collection of achievement logic examples/breakdowns. This is so very long overdue.

6. Clarify and simplify as much as we can. Is there are page somewhere with five paragraphs that just never seem to get to the point? Can it be rewritten to be a single paragraph? By all means, do it. 


-------------------------

The contents of this repo as of July 2022 are a bit of a mess. Most of the existing RADocs pages have been transferred here, but nothing has been organized or optimized yet. There are lots of broken links, stuff that doesn't make sense, placeholders, etc. The time I've spent working on the overhaul so far has been spent getting familiar with mkdocs + material themes, etc. Things are going to start moving quickly here. :) - tele

-------------------------

For community guidelines, you must know the [RetroAchievements Manifesto](/ramanifesto/) and adhere the [User's Code of Conduct](user-coc).

If you're looking for docs about creating achievements, check our [Developer docs](/developers/home/) section.

We encourage all community members to join our [Discord Server](https://discord.gg/dq2E4hE), we use this for most communication.

The complete list of pages is on the sidebar, but here's a brief description of some of them:

- [FAQ](FAQ): the Frequently Asked Questions (like [which RetroArch core should I use?](http://docs.retroachievements.org/FAQ/#which-retroarch-core-should-i-use)).

- [Global Leaderboard and Achievement Hunting Rules](Global-Leaderboard-and-Achievement-Hunting-Rules): explains the rules for the Global Leaderboard, what's the Untracked status, what can be considered cheating, etc.

- [Downloads](Downloads): our alternative downloads page.

- [Free Games](/games/homebrews): games that are completely and legally free download and play on your emulators.

- [Events](Events): learn about the various community events that take place at RetroAchievements.

- [My game is not loading achievements](My-game-is-not-loading-achievements): what you have to do when your game isn't loading achievements.

- [System X wen](System-X-wen): Something meleu snuck in one day.

- [Why you shouldn't use the load state feature](Why-you-shouldn't-use-the-load-state-feature): why you should expect to have issues if you use save/load state while playing.

- [A message for Achievement Hunters and Completionists about revisions](A-message-for-Achievement-Hunters-and-Completionists-about-revisions): why you shouldn't be frustrated when a revision on an achievement set is made.

- [How to contribute if you are not a developer](How-to-contribute-if-you-are-not-a-developer): if you don't know how to develop achievements, there are many other ways to contribute with the community.

You can help to improve these docs by editing/creating the pages at [RetroAchievements wiki](https://github.com/RetroAchievements/docs/wiki)