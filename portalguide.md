---
layout: default
title: My Markdown File
---

Welcome! This is an extensive guide to speedrunning Portal!
Here you'll find everything you need on your speedrunning journey, from the basics of setting up the game, to the most advanced strategies a runner can learn.

If you're new to this, read through the [Setup Guide.](#Setup)

Otherwise, jump ahead to the tutorials:

[Glitchless](#glitchless) - [Inbounds No SLA](#inbounds-no-sla) - [Inbounds](#inbounds) - [Out of Bounds](#out-of-bounds)



## Setup
The most important step for setup is installing the right version of the game for speedrunning.
If you want to run glitchless, the Steam version of the game is completely fine, although you'll have to manually install any additional software or resources. If you're running any other category, you'll want to use **Source Unpack**. 

Source unpack is a package including a stand-alone copy of build 5135, an older version of the game that makes certain glitches significantly easier. Source unpack comes with everything you need pre-installed, so it's as simple as downloading the package, unzipping it, and running it.
In order to use Source Unpack, you must own Portal on Steam, and Steam must be running.

**You can download Source Unpack from [here](https://sourceunpack.gameabusefastcomplete.com/). Pick the server (Europe/US/Asia) that is closest to you.**

### Installing Livesplit
Livesplit is the software we use to time runs as they're performed. It's the timer you see in the corner of runs.

#### 1. Download Livesplit and Splits File
Livesplit isn't a Portal-specific piece of software, so it's not included with Source Unpack. You'll need to download the latest version of livesplit from [the livesplit website.](https://livesplit.org/downloads/) Once you have it, you'll also need a splits file for Portal, which you can get [here](https://www.speedrun.com/portal/resources/bx1fa). 

#### 2. Configure Splits
Open the splits file in livesplit, and you should have a list of chambers from 00/01 through to e02, though they aren't all shown at once by default.

Right click and press edit splits. This will bring up a menu where you can configure a few things about your splits file.

#### 3. Setting the Category
Towards the top, there's a "Run Category" text box. Change this to match the category you plan on running. If you're planning on running multiple categories, you'll need to have multiple splits files.

#### 4. Enabling the Auto-Splitter
While you're on this screen, you can confirm you have Sourcesplit. Sourcesplit is an *auto-splitter*, meaning it will automatically start and stop the timer, as well as removing any load times from your run, to keep it fair between different computers. It should install itself automatically, but it's good to check.

Towards the top of the edit splits window, livesplit should say "Game Time and Auto Splitting are available. (By Fatalis and 2838)". If the button beside that says "Deactivate", the auto-splitter is loaded and ready! If it says "Activate", click it to activate auto-splitting. There's a bunch of settings you can play around with in sourcesplit, but the defaults are fine for running the main categories.
To make sure the auto-splitter is working, open Portal and start a new game. The timer should start ticking as soon as your crosshair appears.

#### 5. Set comparison
Finally, close out of the edit splits menu and right click on livesplit, hover over the "Compare Against" option, and ensure that "Game Time" is selected at the bottom. Sourcesplit should set this automatically, but it's a good idea to double check.

We do this because livesplit tracks two types of time, your time without loads (game time) and your time with loads (real time). For the leaderboard, we only care about game time (or "load removed time" on speedrun.com) but you can additionally include the real time (called "real time attack" on speedrun.com).

And that's all for setting up livesplit! Right click and save your splits! 

**If you installed Source Unpack, skip ahead to the [Binds and Configuration](#binds-and-configuration) section!**

### Demo Recording
(**Reminder: you can skip this section if you are using source unpack**)

Demos are a built-in feature of Portal and other Source engine games. They're effectively "replay" files that you can record and play back from within the game. Demos are the gold standard for recording speedruns, as they give the speedrun.com verifiers the ability to inspect your run to a much greater extent than with a video recording.

The default demo recording commands don't let us use quicksaves, and also just dump all the recorded demos in the install folder, so instead we use a custom plugin that manages demo recording.

You'll need to install this plugin. If you're on the steam version of the game, download the `speedrun_demorecord-2013.dll` file. If you're on an older version for whatever reason then you'll instead want the `speedrun_demorecord-2007.dll` file. The 2006 version is only for recording demos in old versions of Half-Life 2.

Once this is downloaded, navigate to your Portal install folder. On steam, this can be done by right-clicking on Portal in the games library, clicking on "Properties", going to the "Installed Files" tab and clicking on the "Browse..." button. I'd recommend pinning this folder to quick access in File Explorer, so you can get back to it later.

You'll want to place the dll file you downloaded in the `Portal/portal/` folder. Note that there are *two* levels of Portal folders here. The dll needs to be placed in the innermost one, the same folder that contains `gameinfo.txt`.

**Note for 3420 And Older Builds**

On older builds of Portal, plugins must be placed in the `Portal/bin/` folder rather than the `Portal/portal/` folder.

Once you've done that, you can load the plugin in-game via the developer console, but doing that every time would be a pain. Instead, we're going to setup an autoexec that will load it for us.

#### Adding to autoexec
Open the `Portal/portal/cfg/` folder. There'll be a number of .cfg files here. If there's already an `autoexec.cfg` file, great! If not, you'll need to create a new text document and name it `autoexec.cfg`. Make sure that filename extensions are enabled, or Windows will sneakily give your file the name `autoexec.cfg.txt`. If the existing files don't show `.cfg`, do a web search on how to display file extensions in Windows explorer for your respective version of Windows.

Edit the `autoexec.cfg` file. Each line in this file is a console command that will be executed every time the game starts. This is where we're going to load our plugin.

Add a line with `plugin_load speedrun_demorecord-20xx`, adjusting the `20xx` to match the version of the plugin you downloaded.
I also recommend setting up a custom demo folder here, as otherwise the plugin will fill your `portal` folder with demos.
Add the line `speedrun_dir ./demos/`. This will instead put all the created demo folders in `Portal/portal/demos/`, which will be much neater.

Now, every time you open the game, the plugin will be loaded and configured correctly.

### Vault Save
(**Reminder: you can skip this section if you are using source unpack**)

The start of Portal involves a minute-long cutscene in which the player is free to mess around, but can't do anything to speed it up. 
In the interest of maintaining their sanity, Portal runners typically start their runs by loading a save towards the end of this cutscene. Specifically, they load a save that starts exactly 53.025 seconds into the run, and the same amount of time is added on by the auto-splitter.
This save can be downloaded from [here.](https://www.speedrun.com/portal/resources/2e631)

**This is the *only* save that is permitted, making your own is *not* allowed.**

You need to extract the `.sav` file from the `.7z` archive. For this, I recommend [7zip.](https://www.7-zip.org/)

To install it, place it in the `Portal/portal/save` folder. On older versions, `save` might instead be `SAVE`, but the process is no different.

How to actually use the save is covered in the [Performing a Run](#performing-a-run) section.

### Binds and Configuration
While it's possible to complete speedruns with the default binds, there's a number of very helpful additional binds that will be listed here.

These binds are provided as console commands. To run console commands from in-game, first ensure the console is enabled by going to Settings>Keyboard>Advanced and checking the "Enable developer console" box. Now, you should be able to use the backtick/tilde key (\`/~), next to 1 on most keyboards, to open the console. If you can't find this key, or just don't have it, you can bind it to something else in the keyboard settings. One of the function keys is a suitable choice.

Once you have the console, you can use the commands below.

`<key>` represents the key you want to bind the function to. Replace it with the key you want (i.e. `bind <key>` becomes `bind q` or `bind ctrl`).

Any instances of `A|B` mean that you can put A *or* B. If you want both, make two separate binds.

- `bind mwheelup +jump` & `bind mwheeldown +jump`
	- Binds the scroll wheel (up and down respectively) to a jump input. 
	- Required for performing optimal movement in all categories.
- `bind <key> "save quick"` & `bind <key> "load quick"`
	- Sets your quicksave and quickload keys. Can also be done through the menu.
- `bind <key> "load quick01"`
	- Loads the second most recent quicksave. Useful for when you save at a bad time.
- `bind <key> "save glitch; load glitch"`
	- Make a save and load it at the same time. Very important for Inbounds and Out of Bounds speedruns.
	- Note: "glitch" is just the name of the save. You could use any name.
- `bind <key> "load glitch"`
	- Reloads the save in the above command. Useful in the event of a mistake.
- `bind <key> toggle_duck`
	- A key that toggles your duck state, as opposed to normally needing to hold it down. Useful for certain glitches in Inbounds and Inbounds No SLA, as well as for movement in all categories except Glitchless.
- `bind <key> sv_player_funnel_into_portals 0|1`
	- Using 1 will enable portal-funneling, 0 will disable it. Having a bind for both is recommended.


There's a few other useful commands you may want, but aren't worth binding. Instead, run these via the console or append these to the end of your `autoexec.cfg` file (Refer to the [Adding to Autoexec](#adding-to-autoexec) section if you didn't install the demo recorder manually.).

- `cl_showpos 0|1` - Shows your position and angle in the top right corner.
- `cl_showfps 0|1` - Shows your frames per second.
- `net_graph 0|1` - Shows some data about the game, including frames per second

### Performing a Run
Now that you've setup all your binds and know how to use the developer console, you can perform your first run.
There's a minute long cutscene at the start of Portal, but we're going to skip over that by loading the vault save.
Open the developer console and run `speedrun_save vault`. This will tell the demo recorder that you want to start your run by loading that save. You may wish to add this to your `autoexec.cfg`.

Now, run `speedrun_start` to load the save and start your run. If you want, you can add this as a bind. Livesplit should pick up on the fact that you loaded the vault save and automatically start at 53 seconds. From here, you can perform your first run. Feel free to just run through the game once with the timer running, to get a feel for it, but it's best to go through all the beginner tutorials for your chosen category and learn some strats before submitting a run to the leaderboards. It's also a good idea to read over the [Submitting a Run](#submitting-a-run) section so you know what you have to do during the run in order for it to be accepted.

Once you've defeated Glados (and the neurotoxin starts circling up), you need to run `speedrun_stop` in the console in order to lock in the demos for the run. It is **very important** that you don't forget this step, as you can easily have your demos corrupted if you don't. The best time to do this is straight after Glados dies. You can unpause and watch the rest of the ending cutscene if you want, but it's best to stop the demos straight away.


### Submitting a Run
In order for your run to be accepted, it must follow the rules of the category you're submitting to. You can see the rules for a given category by clicking the "Show Rules" button on the [speedrun.com leaderboard.](https://www.speedrun.com/portal)

All Portal runs require proof in the form of either demos, or a live video recording.
For a live recording to be valid, it has to include game audio and show the livesplit timer the whole time. The best software for recording runs is [OBS.](https://obsproject.com/)

Demos will always be valid, **so long as you did not pause**. Pauses are timed in Portal, and demos don't record how long the player paused for. For this reason, if you pause during your run for any reason, you need to provide a live recording.

To submit with video, upload it to a video-sharing service such as youtube. Whatever service you use must provide permanent hosting. Add a publicly accessible link in the video field when submitting.

To submit with demos, upload them to a file-sharing service such as google drive. Whatever service you use must provide permanent hosting. Add a publicly accessible link in the *description* when submitting.

With that, you now know everything you need in order to speedrun Portal. All that's left now is to learn the strats and practice, practice, practice.

# Glitchless
Routes are assigned a color based on their difficulty. 
If you're just learning the game, follow the beginner ![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") routes. 

Intermediate ![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") routes are a little harder, but often much faster.

Advanced ![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") routes are quite difficult, but save more time. Advanced routes are *usually* the fastest for a given map.

Expert ![expert](https://placehold.co/15x15/f70c27/f70c27.png "Expert Route") routes are extremely difficult, and are generally only used when going for top times.

Implement these into your runs at your own pace. As you improve, harder routes will become more accessible.

## 00/01
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner](https://youtu.be/xy7ZljG3EKs) - The intended route through the first two chambers.
## 02/03
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner](https://youtu.be/tBySUCHNrWY) - Shows strats for both 02 and 03, including pre-fizzle in 02.
## 04/05
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner](https://youtu.be/leQhYPgO59k) - Showing a few different options for 04 as well as the most consistent way for doing chamber 05.
## 06/07
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner](https://www.youtube.com/watch?v=fd_fumnU5Zo) - Shows beginner options for both chambers as well as optimizations.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [06 Overhead and Fast 07](https://youtu.be/8G1b6adkD2A) - Each save a small amount of time, but are useful for top level runs.
## 08
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Block Jump](https://www.youtube.com/watch?v=H7re62Wj554&t=23s) - A jump on some level geometry to skip the orb puzzle.
## 09
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Portal Peek](https://www.youtube.com/watch?v=3_XVx5Vynho) - Simple route that avoids walking to the cube.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Peek Under Cube + Cubethrow](https://www.youtube.com/watch?v=njiGFEMG_1Q) - Slightly harder variant of the portal peek route.
## 10
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Flings](https://www.youtube.com/watch?v=yvEexX-VST4) - Basic flings, nothing special. *Having portal funnelling on helps with the last fling.*

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Portal Stand](https://www.youtube.com/watch?v=a31n-7eW3Ng) - A little tricky, skips the first fling.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Jump Fling](https://youtu.be/OefwOTRppi0) - More precise final fling that can save up to 2 seconds.
## 11/12
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner](https://youtu.be/SwINkfSq4XQ) - Beginner friendly methods for competing chambers 11 & 12.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Optimizations](https://youtu.be/BAdDgQY1c_Y) - Faster but more difficult routes for 11 & 12. More info on 12 cube throw can be found [here.](https://www.youtube.com/watch?v=e8yi9FCgGCA)

![expert](https://placehold.co/15x15/f70c27/f70c27.png "Expert Route") - [Funtitled Strafe](https://www.youtube.com/watch?v=mBM1O3aHi2s) - Very difficult strafe that saves 4-5 seconds over the standard route.

## 13
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner](https://www.youtube.com/watch?v=eGGsb0l8uNo) - Shows a few options for completing Chamber 13.

## 14
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Fling](https://youtu.be/EbesgW49pdU) - Slightly tricky fling to the end of the chamber.

![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Backup](https://www.youtube.com/watch?v=YdTlfI6XuQ0) - Should be used if you fail the fling.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Reportal](https://youtu.be/Vlwk0UU_7bI) - Slightly faster than the fling, saves less than a second but isn't too hard.
## 15
![#All](https://placehold.co/15x15/FFFFFF/FFFFFF.png) - [All Skill Levels](https://youtu.be/HZl43JqFqiI) - Video goes over all routes for chamber 15.

## 16
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner](https://www.youtube.com/watch?v=8mn6cBKV1oY) - Slow but easy route in case you struggle with the harder strats.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Spiderman](https://youtu.be/AAdxY15XqUQ) - Fastest route through chamber 16.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Spiderman Optimizations](https://www.youtube.com/watch?v=nbqJMPVyRrk) - Small optimizations to the spiderman route.

## 17
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner Camera Stack](https://youtu.be/kzku2hO9Fog) - A simple way to skip the orb puzzles.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Optimized Camera Stack](https://www.youtube.com/watch?v=4LVfo3lV38I) - Fastest way to do camera stack.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Chillino Fling](https://youtu.be/PzgOzpOgJ54) - Fling that requires some tight aiming, but is quite a lot faster than camera stack (and less random).

## 18
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Camera Door Wedge](https://youtu.be/kzku2hO9Fog) - Use a camera to wedge a door open, skipping most of the puzzle. Portal funneling makes the last room much easier.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Reportals](https://youtu.be/Dd18VMnZT08) - Difficult reportals that save 3.5 seconds.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Overhead Strafes](https://www.youtube.com/watch?v=UJbW52KapL4) - Reasonably difficult optimisations that can save 1-2s.

## 19
![#All](https://placehold.co/15x15/FFFFFF/FFFFFF.png) - [Spiderman (All Skill Levels)](https://youtu.be/5FFDigrNDDM) - Video goes over all routes for chamber 19.

## Escape 00
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner](https://www.youtube.com/watch?v=ycj-WnJzX5A) - Basic route that is fairly easy to perform.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Pistons](https://www.youtube.com/watch?v=G6J4lYs0iWg) - More difficult route.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Advanced Optimizations](https://youtu.be/4FLtd3ktfic) - Several optimizations, such as Mikael's shot.

## Escape 01
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner](https://www.youtube.com/watch?v=mLElIeb6JnQ) - Beginner route that makes use of the Turret Flippy Skippy Tricky Flicky Wingy Swingy Thingy.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Flippy Skippy Skip](https://www.youtube.com/watch?v=TXauQifcDJQ) - Very challenging but fast optimisation for the flippy skippy trick. Saves a lot of time and provides the portal for the turret glass break.
## Escape 02
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner](https://youtu.be/f7oqD5BGhBs) - The GLaDOS fight will take a little practice, standing in the correct spot before the rocket turret comes out is very important.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Catwalk Skip & Fast Glados](https://www.youtube.com/watch?v=zy1dACjHHHQ) - Skips the long flings and walk along the catwalk, as well as a faster version of the Glados fight.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Advanced Optimizations](https://youtu.be/tgPJ-WQUr5U) - Multiple optimizations throughout e02 that each save a small amount of time, but are invaluable at the highest level.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Fast Rocket Turret](https://youtu.be/DP2R-IgP5XA) - Faster approach to Glados that saves 1.5s per core. Easy on the first core, extremely difficult for the other two. For red core, see [here.](https://youtu.be/i9pTDp0MEWE)



# Inbounds No SLA
Routes are assigned a color based on their difficulty. 
If you're just learning the game, follow the beginner ![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") routes. 

Intermediate ![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") routes are a little harder, but often much faster.

Advanced ![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") routes are quite difficult, but save more time. Advanced routes are *usually* the fastest for a given map.

Expert ![expert](https://placehold.co/15x15/f70c27/f70c27.png "Expert Route") routes are extremely difficult, and are generally only used when going for top times.

Implement these into your runs at your own pace. As you improve, harder routes will become more accessible.

**Note: There are two subcategories for Inbounds No SLA. Some routes are *Unrestricted only*, meaning they cannot be used in Inbounds No SLA Legacy. All routes listed can be used in Inbounds No SLA Unrestricted**

## 00/01
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Intended](https://youtu.be/_8CkCPzXMOA) - The intended route that is used from beginner runs all the way to advanced runs.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [No SLA Vault Skip](https://youtu.be/_8CkCPzXMOA) - **Unrestricted only** - Extremely inconsistent skip that saves over 50 seconds if performed correctly.

## 02/03
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Intended](https://www.youtube.com/watch?v=RSieOgEAwLY) - The intended route through the chamber.

## 04/05
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Optimized Route](https://youtu.be/muEzNmtAHlU) - A quick way to execute the intended solutions to the chambers.

## 06/07
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Skips](https://www.youtube.com/watch?v=I9iZgt3Dwo0) - Shows multiple routes for 06 and 07, including fast 07 and a few optimizations.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [06 Camera Launch](https://youtu.be/HlLdbvqHJzY) - Preserves a camera from 05 in order to skip using the portal in 06.

## 08
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Block Jump](https://www.youtube.com/watch?v=H7re62Wj554) - A jump on some level geometry to skip the orb puzzle.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - ABH Over Goo - A difficult ABH sequence that saves 2-3 seconds over block jump. A few methods are listed:
- [Circle Strafe Over Goo](https://www.youtube.com/watch?v=WEjFAkwkwKs)
- [Crisper's Over Goo](https://www.youtube.com/watch?v=JZ8eI-wdW5E)
- [Adamantite's Over Goo](https://www.youtube.com/watch?v=_dtT9HZmVdo)

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [PDI Over Goo](https://www.youtube.com/watch?v=Pcxr9HkPi_A) - A much harder optimization to ABH Over Goo that saves an additional second.

## 09
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Under Door](https://youtu.be/SeLW8dgJLg0) - Simple route that uses a shot under the door to skip the puzzle.

## 10
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Flings](https://youtu.be/9z6VfuJ9kT8) - Basic flings, nothing special. *Having portal funnelling on helps with the last fling.*

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Doorlaunch](https://www.youtube.com/watch?v=RgDVasBC2jo) - Very difficult and inconsistent strat that skips the ending fling, saving 5-6 seconds.

## 11/12
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner](https://youtu.be/t10J7PSME7w) - Very simple route. Move on to the Triple Edge Glitch once you're comfortable with the game, as it's much faster.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Triple Edge Glitch](https://youtu.be/T_ZgIibUafI) - Uses an edge glitch to skip the elevator between 11 and 12, saving 15-20 seconds.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [AFH Start](https://youtu.be/3XxnWwlVykA) - Uses an AFH out of the starting elevator to get to the portalgun faster.

## 13
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Cube Throw](https://youtu.be/x39hmpQG6Is) - Throwing the cube fast can be a bit annoying, but otherwise it shouldn’t be too difficult.

## 14
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Double Fling](https://youtu.be/EbesgW49pdU) - Slightly tricky fling to the end of the chamber.

![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Backup](https://www.youtube.com/watch?v=YdTlfI6XuQ0) - Should be used if you fail the fling.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Reportal](https://youtu.be/Vlwk0UU_7bI) - Slightly faster than the fling, saves less than a second but isn't too hard.

## 15
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Observation Room Bumps](https://youtu.be/o9zooS4dqy8) - Uses portal bumps to skip the orb puzzle.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Quantum Crouch](https://www.youtube.com/watch?v=hxyz7o-J65A) - Uses QQC to save a few seconds.

## 16
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Portal Bumps](https://youtu.be/sfJAlvMw734) - Uses portal bumps to skip the start cutscene and most of the chamber.

## 17
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Portal Bump](https://youtu.be/plfNytkCs-w) - Uses a portal bump to skip solving any of the orb puzzles.

![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Seam shot](https://youtu.be/AwZCE1JPoLI) - Uses a seam shot at the start of the chamber to skip the hallways. Showpos Pos: ~1584 ~384.05 Ang: ~89 ~-4.4

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Vertical Angle Glitch](https://youtu.be/jZobqM3Wac0) - **Unrestricted Only** - Uses precise angles to perform a VAG (Vertical Angle Glitch) and warp straight to the elevator. *For the QCE, start your uncrouch right before you shoot.*

## 18
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Double Edge Glitch](https://youtu.be/dra4RTn-F2k) - Uses back to back edge glitches to skip to the ending room. A little tricky, but about 20 years faster than any other route.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Lasagna Launch](https://youtu.be/_iW7FczTcs4) - A tasty strat that uses a pause boost on a camera to save about 8 seconds by skipping the ending flings. **All runs using this strategy must be submitted with a live recording.**


## 19
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Short LAG](https://youtu.be/Rsz9z4DawYQ) - An easy LAG that gets you to the room above the fire pit. [Here](https://www.youtube.com/watch?v=9MQdHqlgprE) is an alternative to the edge glitch if you are having trouble with it.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Loch Ness Monster](https://youtu.be/MjwnD5K2lkQ) - A faster LAG route that warps you into some goo you have to swim out of (hence the name). A replacement for the single LAG that leads nicely into double LAG.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Double LAG](https://www.youtube.com/watch?v=CgPd65CZAR4) - Uses edge glitches and portal peeks to set up a second LAG that takes you straight to the end. Use the [other double lag video](https://youtu.be/MjwnD5K2lkQ?t=272) as well to understand how the second LAG works.

## Escape 00
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner](https://youtu.be/QR3saaE-pTo) - Basic route that is fairly easy to perform.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Pistons](https://youtu.be/LyygkRe6yl8) - Faster route that is more difficult to perform.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Mikael's Route](https://youtu.be/n5usLjjxIv8) - Very difficult route that requires good movement, precise and quick portal shooting.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Pistonless](https://youtu.be/i8iRjAHysNw) - Uses an edgeglitch teleport to skip the entire piston hallway room. Optimally saves 3-4 seconds over Mikael’s shot.

## Escape 01
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner](https://youtu.be/wfdPf6eh7v4) - Route for new runners.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Flippy Skippy Skip](https://youtu.be/Frjz4nKnwuc) - Difficult optimization for the beginner route. Also the best named strat of all time.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Angle Glitch Save Glitch](https://www.youtube.com/watch?v=TXauQifcDJQ) - **Unrestricted Only** - Uses a modified version of save glitch called AGSG which doesn’t require loading to do a series of precise shots to get to the end of the level.

## Escape 02
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Flings + Turret Kill Glados](https://youtu.be/fubeSk_UlpU) - Simple flings from start to finish, nothing too difficult. Skips the GLaDOS dialogue using a turret. Uses the incinerator to destroy the cores, just like in a normal playthrough.

![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Corefall Skip](https://youtu.be/fubeSk_UlpU) - Uses an edge glitch to destroy the cores without them having to fall out of your portal into the incinerator.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Catwalk Skip](https://youtu.be/rEsFwwdaDKc) - Skips the long flings and the ABH on the bridge to get to the door as fast as possible.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [AAG](https://youtu.be/vHT_lqLnlEk) - Uses a fling and an AAG to teleport into Glados' chamber, bringing a turret with you.

![expert](https://placehold.co/15x15/f70c27/f70c27.png "Expert Route") - [Preturret](https://youtu.be/41DOh1-ptVU) - Does the AAG before the turrets drop, allowing them to drop directly into the Glados room. Extremely precise and very little time to set up. Saves about 3 seconds over Single AAG.


# Inbounds
Routes are assigned a color based on their difficulty. 
If you're just learning the game, follow the beginner ![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") routes. 

Intermediate ![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") routes are a little harder, but often much faster.

Advanced ![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") routes are quite difficult, but save more time. Advanced routes are *usually* the fastest for a given map.

Expert ![expert](https://placehold.co/15x15/f70c27/f70c27.png "Expert Route") routes are extremely difficult, and are generally only used when going for top times.

Implement these into your runs at your own pace. As you improve, harder routes will become more accessible.

## 00/01
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Intended](https://youtu.be/_8CkCPzXMOA) - The intended route that is used from beginner runs all the way to advanced runs.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Vault Skip](https://youtu.be/CFMG-a2vzqM) - Strategy that uses the radio to clip out of the vault well before the portal opens. Saves over 50 seconds if performed well.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Button Save Glitch](https://youtu.be/6EtIcAK2Yz8) - This is a very timing intensive strat that can reward you with 14 seconds of time save at the start of a run.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Fast Vault Skip](https://youtu.be/NbnGAHJvDnI) - Using a more precise setup and tight Save/Load timing, this strat saves up to 4 seconds over Vault Skip.

## 02/03
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Intended](https://www.youtube.com/watch?v=RSieOgEAwLY) - The intended route through the chamber.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Vault Skip](https://youtu.be/u9I0BtZtvuc) - Uses a save glitch to skip the 02 to 03 elevator. Saves around 10 seconds.

## 04/05
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Save Glitch](https://youtu.be/Uz28Saq8oy0) - Uses a save glitch to skip solving the puzzles in 04 and 05.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [04 VWW/Chungus Skip](https://www.youtube.com/watch?v=yw-MNguvc5c) - Uses an inbounds VWW to skip part of the elevator ride, can save 5s over the basic route.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [06 Infront](https://youtu.be/eG-12qeV8ls) - Utilizes the wait time in 05 to set up a save glitch and Inbounds VWW, allowing you to begin 06 in front of the elevator. Optimally saves 1.5 seconds. If the ABH to the fizzler is difficult, an alternate method to get to there can be found [here](https://youtu.be/BW4vBgqvV7I?si=RM3CSn9PLcjZEZmk).

![expert](https://placehold.co/15x15/f70c27/f70c27.png "Expert Route") - [04 Elevator Skip](https://youtu.be/Q189NzN22Sc) - A long, extremely difficult strat that involves a preserved save glitch from Chamber 03. Can save up to 6 seconds over 04 VWW if executed perfectly.

## 06/07
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Skips](https://www.youtube.com/watch?v=I9iZgt3Dwo0) - Shows multiple routes for 06 and 07, including fast 07 and a few optimizations.

## 08
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Block Jump](https://www.youtube.com/watch?v=H7re62Wj554) - A jump on some level geometry to skip the orb puzzle.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - ABH Over Goo - A difficult ABH sequence that saves 2-3 seconds over block jump. A few methods are listed:
- [Circle Strafe Over Goo](https://www.youtube.com/watch?v=WEjFAkwkwKs)
- [Crisper's Over Goo](https://www.youtube.com/watch?v=JZ8eI-wdW5E)
- [Adamantite's Over Goo](https://www.youtube.com/watch?v=_dtT9HZmVdo)

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [PDI Over Goo](https://www.youtube.com/watch?v=Pcxr9HkPi_A) - A much harder optimization to ABH Over Goo that saves an additional second.

## 09
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Under Door](https://youtu.be/SeLW8dgJLg0) - Simple route that uses a shot under the door to skip the puzzle.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Save Delay](https://www.youtube.com/watch?v=orGlVBUCvgY) - Saves 1-2 seconds over the standard method if done perfectly, but the saveload timing can take a bit to get used to.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Early Activation](https://youtu.be/c6K3wP8sKp4) - Saves around 3 seconds by using the save delay method to hit the triggers for the elevator in a different order, making it start going up earlier and keeping the doors open for the start of 10.


## 10
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Flings](https://youtu.be/9z6VfuJ9kT8) - Basic flings, nothing special. *Having portal funnelling on helps with the last fling.*

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Doorlaunch](https://www.youtube.com/watch?v=RgDVasBC2jo) - Very difficult and inconsistent strat that skips the ending fling, saving 5-6 seconds.

## 11/12
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner](https://youtu.be/t10J7PSME7w) - Very simple route. Move on to the Triple Edge Glitch or Softwall Save Glitch once you're comfortable with the game, as they're much faster.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Triple Edge Glitch](https://youtu.be/T_ZgIibUafI) - Uses an edge glitch to skip the elevator between 11 and 12, saving 15-20 seconds over the beginner route.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Softwall Save Glitch](https://youtu.be/WgC0xdzpE5k) - Uses a save glitch to skip the entirety of chamber 12. Optimally saves 7 seconds over the triple edge glitch.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [AFH Start](https://youtu.be/3XxnWwlVykA) - Uses an AFH out of the starting elevator to get to the portalgun faster.

![expert](https://placehold.co/15x15/f70c27/f70c27.png "Expert Route") - [13 Infront](https://www.youtube.com/watch?v=BjPyZUqymok) - Difficult save glitch that is under time pressure. Saves 2-3 seconds over softwall save glitch.

## 13
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Cube Throw](https://youtu.be/x39hmpQG6Is) - Throwing the cube fast can be a bit annoying, but otherwise it shouldn’t be too difficult.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Save Glitch](https://youtu.be/vNUVbdKAtwM) - A very simple save glitch to skip to the end of the chamber. Saves a couple of seconds over the beginner route.


## 14
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Double Fling](https://youtu.be/EbesgW49pdU) - Slightly tricky fling to the end of the chamber.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Traveling Portal Wrong Warp](https://youtu.be/vNUVbdKAtwM) - Somewhat difficult save glitch that sets up for a TPWW in 15. Loses roughly 2 seconds over Reportal but gains it back and more in 15. An optimization for this route can be found at the beginning of the [IUE](https://youtu.be/vXuMqID4kuA) tutorial.

## 15
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Long Save Glitch](https://youtu.be/Y35sDj01rjM) - An involved save glitch to make it to the end room.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Quantum Crouch](https://www.youtube.com/watch?v=hxyz7o-J65A) - Uses QQC to save a few seconds.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Traveling Portal Wrong Warp](https://youtu.be/gg3zllMZW0Q?t=305) - Part 2 of TPWW. A simple fling or AFH to the end, saves 8-9 seconds over Early Save Glitch depending on which ending you do, making the net gain of TPWW 6-7 seconds.

![expert](https://placehold.co/15x15/f70c27/f70c27.png "Expert Route") - [Inbounds Under Elevator](https://youtu.be/vXuMqID4kuA) - A 3 part route between chambers 15-17 involving several TPWWs and Load Glitches. Optimally saves ~5 seconds, but is extremely difficult.

## 16
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Save Glitch](https://youtu.be/uBy5VJEzVGQ) - A short save glitch to get to the end. There's also a [3-shot method](https://youtu.be/U9CvD4VrJug), which is applicable for Turretless.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Turretless](https://www.youtube.com/watch?v=tqnpvtxUcIg) - A very difficult route that preserves save glitch state through Chamber 17 and 18 saving around 26 seconds in total.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Turretless Infront](https://youtu.be/W1eO5mmhyAQ) - An improvement to Turretless that saves 2-3s and is similar in difficulty.

![expert](https://placehold.co/15x15/f70c27/f70c27.png "Expert Route") - [Inbounds Under Elevator](https://youtu.be/vXuMqID4kuA?t=180) - The second part of IUE, continued from chamber 15.

## 17
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Portal Bump](https://youtu.be/plfNytkCs-w) - Uses a portal bump to skip solving any of the orb puzzles.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Vertical Angle Glitch](https://youtu.be/jZobqM3Wac0) - **Unrestricted Only** - Uses precise angles to perform a VAG (Vertical Angle Glitch) and warp straight to the elevator. *For the QCE, start your uncrouch right before you shoot.*

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Turretless](https://youtu.be/tqnpvtxUcIg?t=151) - Turretless, continued.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Turretless](https://youtu.be/VoHnlvQOlbY) - An improvement to Turretless that saves an additional second or so, but is notably easier to preserve save glitch into 18 with.

![expert](https://placehold.co/15x15/f70c27/f70c27.png "Expert Route") - [Inbounds Under Elevator](https://youtu.be/vXuMqID4kuA?t=290) - The final part of IUE. Finishes in the same way as Turretless, including the preserve into 18.

## 18
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Dacciox's Save Glitch](https://www.youtube.com/watch?v=8Lda5YeLGMI) - Save glitch to the end of the chamber.

![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Crisper's Save Glitch](https://youtu.be/q8m9LNNpbTU) - Save glitch to the end of the chamber.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Elevator Save Glitch](https://youtu.be/tqnpvtxUcIg?t=609) - Requires a save glitch preserve, either from Turretless or IUE.

## 19
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Short LAG](https://youtu.be/Rsz9z4DawYQ) - An easy LAG that gets you to the room above the fire pit. [Here](https://www.youtube.com/watch?v=9MQdHqlgprE) is an alternative to the edge glitch if you are having trouble with it.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Loch Ness Monster](https://youtu.be/MjwnD5K2lkQ) - A faster LAG route that warps you into some goo you have to swim out of (hence the name). A replacement for the single LAG that leads nicely into double LAG.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Save Glitch](https://www.youtube.com/watch?v=lTrjLb0xEgw) - A save glitch after Loch Ness that saves a substantial amount of time.

## Escape 00
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner](https://youtu.be/QR3saaE-pTo) - Basic route that is fairly easy to perform.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Pistons](https://youtu.be/LyygkRe6yl8) - Faster route that is more difficult to perform.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Save Glitch](https://youtu.be/k0Kba0Xy_G4) - Save glitch with a very precise shot that saves several seconds over other routes.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Ethan's Save Glitch](https://youtu.be/VqS4MaWGT28) - Alternate save glitch than can be about a second faster. Also makes the precise shot a little easier.

## Escape 01
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Beginner](https://youtu.be/wfdPf6eh7v4) - Route for new runners.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Static Save Glitch](https://www.youtube.com/watch?v=9ETqPbTVwXc) - Save glitch to skip to the end of e01. Same speed as route 4, pick your favourite.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Route 4](https://youtu.be/aib6hO7MJos) - [Alternate lineups](https://youtu.be/Oyihh0rjBnA) - Save glitch to skip to the end of e01. Same speed as static SG, pick your favourite.

## Escape 02
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Flings + Turret Kill Glados](https://youtu.be/fubeSk_UlpU) - Simple flings from start to finish, nothing too difficult. Skips the GLaDOS dialogue using a turret. Uses the incinerator to destroy the cores, just like in a normal playthrough.

![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Corefall Skip](https://youtu.be/fubeSk_UlpU) - Uses an edge glitch to destroy the cores without them having to fall out of your portal into the incinerator.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Catwalk Skip](https://youtu.be/rEsFwwdaDKc) - Skips the long flings and the ABH on the bridge to get to the door as fast as possible.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [AAG](https://youtu.be/vHT_lqLnlEk) - Uses a fling and an AAG to teleport into Glados' chamber, bringing a turret with you.

![expert](https://placehold.co/15x15/f70c27/f70c27.png "Expert Route") - [Preturret](https://youtu.be/41DOh1-ptVU) - Does the AAG before the turrets finish lowering, allowing them to drop directly into the Glados room. Extremely precise and very little time to set up. Saves about 3 seconds over regular AAG.

# Out of Bounds

## 00/01
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Intended](https://youtu.be/_8CkCPzXMOA) - The intended route that is used from beginner runs all the way to advanced runs.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Vault Skip](https://youtu.be/CFMG-a2vzqM) - Strategy that uses the radio to clip out of the vault well before the portal opens. Saves over 50 seconds if performed well.

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [Button Save Glitch](https://youtu.be/6EtIcAK2Yz8) - This is a very timing intensive strat that can reward you with 14 seconds of time save at the start of a run.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Fast Vault Skip](https://youtu.be/NbnGAHJvDnI) - Using a more precise setup and tight Save/Load timing, this strat saves up to 4 seconds over Vault Skip.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Egg + 02 Skip](https://youtu.be/Gn4NrxAydAE) - Only possible on older builds (4104 or earlier). Fastest route when paired with vault skip.

## 02/03
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Save Glitch](https://youtu.be/YBzFV1yr4og) - Simple save glitch to end.

![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Under Elevator + New Game](https://www.youtube.com/watch?v=QTb8TxCiHqE) - Simple save glitch to get under the elevator that uses the new game feature to get up to 04. **You must record video to use this since it requires pausing and you also have to use "sv_unlockedchapters 0" every time you reset.**

![intermediate](https://placehold.co/15x15/FF8411/FF8411.png "Intermediate Route") - [04 Infront](https://youtu.be/ytzPJrgGQrI) - Starts 04 in front of the elevator, saving around a second.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Seamshot + 04 Infront + SG Preserve](https://youtu.be/pDFy0JT4xB0) - Using a Viewsnap to skip needing the save glitch to get out of bounds. Optimally saves just over a second compared to the save glitch. The falling save glitch is interchangeable with the VWW used above.
*Viewsnap sensitivity: 5446.7218*

## 04/05
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Save Glitch](https://youtu.be/Z1XfVqrsWFA) - [Alternate Version](https://youtu.be/VN2CwNrcWJA) - Simple save glitch to end. Two options are linked.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [06 Infront](https://youtu.be/wICkzexuX3w) - Multiple save glitches to get you in front of the elevator in 06.

## 06/07
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Save Glitch](https://youtu.be/D-PwpRJB-gM) - Very precise but simple shot set up in the previous chamber.
*Showpos coordinates: -72.60 164.56*

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [08 Infront w/ Quantum Crouch](https://youtu.be/Z9Smd_IAJg4) - A modified seamshot, followed by a very hard chain of actions to get you in front of the elevator in 08.
*Showpos coordinates: -66.80 168.77*

## 08
![beginner](https://placehold.co/15x15/2DD000/2DD000.png "Beginner Route") - [Block Jump](https://www.youtube.com/watch?v=H7re62Wj554) - A jump on some level geometry to skip the orb puzzle.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - ABH Over Goo - A difficult ABH sequence that saves 2-3 seconds over block jump. A few methods are listed:
- [Circle Strafe Over Goo](https://www.youtube.com/watch?v=WEjFAkwkwKs)
- [Crisper's Over Goo](https://www.youtube.com/watch?v=JZ8eI-wdW5E)
- [Adamantite's Over Goo](https://www.youtube.com/watch?v=_dtT9HZmVdo)

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [PDI Over Goo](https://www.youtube.com/watch?v=Pcxr9HkPi_A) - A much harder optimization to ABH Over Goo that saves an additional second.

![advanced](https://placehold.co/15x15/BA68C8/BA68C8.png "Advanced Route") - [Infront Over Goo](https://youtu.be/Z9Smd_IAJg4?t=495) - Performing ABH over goo starting in front of the elevator. Saves a second or two over regular over goo and can be combined with PDI.

## 09

## 10

## 11/12

## 13

## 14

## 15

## 16

## 17

## 18

## 19

## Escape 00

## Escape 01

## Escape 02