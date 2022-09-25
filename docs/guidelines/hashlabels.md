

Every ROM that is linked to an achievement set should be clearly identified and labeled. These labels help players know which versions of a game are compatible as well as if there are any translation patches, bug fixes, cosmetic hacks, quality of life hacks, etc. that they can use. 

## Info for Linked Hashes
- RA Hash: Check [Game Identification](/games/game-identification/) to learn more about these. These appear in `Manage Hashes` automatically.
- Filename - Filename should be entered as the description. These are typically automatic, but may need some adjustments.
- Labels - You can use the labels listed below by using the filename of the image (no extension).

## Images

|Image|Label to Use|Note|
|---|---|---|
|![main-label](https://retroachievements.org/Images/labels/main.png)|`main`|Sometimes used to show the primary ROM used by the set developer(s)|
|![RAPatches](https://retroachievements.org/Images/labels/rapatches.png)|`rapatches`|Used when the hash requires a patch hosted on RAPatches|
|![no-intro-label](https://retroachievements.org/Images/labels/nointro.png)|`nointro`|The most common for cartridge-based games|
|![redump-label](https://retroachievements.org/Images/labels/redump.png)|`redump`|The most common for disc-based games|
|![tosec-label](https://retroachievements.org/Images/labels/tosec.png)|`tosec`|
|![fb-neo-label](https://retroachievements.org/Images/labels/fbneo.png)|`fbneo`|Mostly used for Arcade|
|![clean-cpc](https://retroachievements.org/Images/labels/cleancpc.png)|`cleancpc`|Amstrad preservation project|
|![4am-crack](https://retroachievements.org/Images/labels/4amcrack.png)|`4amcrack`|Used for Apple II|
|![neo-kobe-label](https://retroachievements.org/Images/labels/neokobe.png)|`neokobe`|Mostly for PC-8001 and PC-8801|
|![homebrew](https://retroachievements.org/Images/labels/homebrew.png)|`homebrew`|Used for, you guessed it: Homebrews!|
|![atari-age-label](https://retroachievements.org/Images/labels/atariage.png)|`atariage`|Popular site for Homebrews|
|![itch-io-label](https://retroachievements.org/Images/labels/itchio.png)|`itchio`|Popular site for Homebrews|
|![msu-1-label](https://retroachievements.org/Images/labels/msu1.png)|`msu1`|Used to mark SNES ROMs with MSU-1 patches|
|![snes-mini](https://retroachievements.org/Images/labels/snesmini.png)|`snesmini`|
|![project-egg-label](https://retroachievements.org/Images/labels/egg.png)|`egg`|ROMs purchased from Project Egg, typically Japanese PC games.|
|![steam-label](https://retroachievements.org/Images/labels/steam.png)|`steam`|ROMs purchased from Steam.
|![mamesl-label](https://retroachievements.org/Images/labels/mamesl.png)|`mamesl`|MAME Software List
|![smwcentral-label](https://retroachievements.org/Images/labels/smwcentral.png)|`smwcentral`|Popular repository for Super Mario World hacks.|
|![rhdn-label](https://retroachievements.org/Images/labels/rhdn.png)|`rndn`|Popular repository for ROM hacks|
|![goodtools-label](https://retroachievements.org/Images/labels/goodtools.png)|`goodtools`|
|![nongood-label](https://retroachievements.org/Images/labels/nongood.png)|`nongood`|
|![offline-list-label](https://retroachievements.org/Images/labels/offlinelist.png)|`offlinelist`|


## Examples

### Deja Vu (NES)

![dejavu-hash-label](/guidelines/images/managehashes-dejavu.png)

- The first hash is the USA version of the game with an Uncensored patch applied to it. The full text of the description is `Deja Vu (USA) (Uncensored) (v1.0) (usertheloset).nes`, which follows the RAPatches naming scheme. The labels used are `nointro` and `rapatches`.
- The second hash is the No Intro-verified USA version of the game.
- The third hash is the No Intro-verified Japanese version of the game.

To see how this will look for the majority of users, go to the game entry page and click on "Linked Hashes."
![dejavu-links](/guidelines/images/links-dejavu.png)

As you can see below, `nointro` became ![no-intro-label](https://retroachievements.org/Images/labels/nointro.png) and `rapatches` became ![rapatches-label](https://retroachievements.org/Images/labels/rapatches.png).
![dejavu-linked-hashes](/guidelines/images/linkedhashes-dejavu.png)

### Suikoden (PlayStation)

We'll skip the manage hashes example for this one. Let's go straight to "Linked Hashes" on the game entry page:
![suikoden-links](/guidelines/images/links-suikoden.png)

The hashes labeled with `redump`, `rhdn`, and `rapatches` require patches that are available on both romhacking.net and in the RAPatches repository.
![suikoden-linked-hashes](/guidelines/images/linkedhashes-suikoden.png)


## Linking to Patches
- The first post of a game's forum topic is the best place to include links to patches required.
- These do not need to follow a specific format, but the information must be clear.
- Here is one example of how to format the text in the forum: 

=== "Input Text"
    ```
    [b]Suikoden (Europe) (De) (v1.01) (Twisted Phoenix Game Translation)[/b]
    [b]Suikoden (Europe) + [url=https://www.romhacking.net/translations/5736/]German Patch[/url][/b] [img=Images/labels/rhdn.png]
    or
    [b]Suikoden (Europe) + [url=https://github.com/RetroAchievements/RAPatches/raw/main/PS1/Translation/German/11255-Suikoden-GermanTranslation.7z]German Patch[/url][/b] [img=Images/labels/rapatches.png]
    [i]RA Checksum: [/i]f0c5ec0696aa2ec2d6e5b731fbe07491
    ```
=== "Result"
    ![suikoden-forum-label-01](/guidelines/images/forum-label-01-suikoden.png)

- A second example:
=== "Input Text"
    ```
    [img=Images/labels/rapatches.png] [img=Images/labels/rhdn.png]
    Download the patch from RHDN [url=https://www.romhacking.net/translations/5736/]here[/url].
    RAPatches Mirror [url=https://github.com/RetroAchievements/RAPatches/raw/main/PS1/Translation/German/11255-Suikoden-GermanTranslation.7z]here[/url].
    ```
=== "Result"
    ![suikoden-forum-label-02](/guidelines/images/forum-label-02-suikoden.png)

