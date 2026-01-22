# DOOM (1993) Presets Package
This is a personal repository, and its contents are intended to help you and/or my future self set up DOOM (1993) mods and IWADs to run with DoomRunner via Steam. It includes all the necessary folder structure and custom configuration files to get them working.

It **DOES NOT INCLUDE** DoomRunner, source ports, or any mod files! The provided `file_info_cache.json` and `options.json` files are preconfigured with the necessary folder paths for a few IWADs/Mods.

Below is a step-by-step tutorial on how to get DoomRunner to work with the Steam version of [DOOM + DOOM II](https://store.steampowered.com/app/2280/DOOM__DOOM_II/).

## Setting up DoomRunner to launch via Steam
1. Download [DoomRunner](https://github.com/Youda008/DoomRunner/).
2. On Steam, right click `DOOM + DOOM II > Manage > Browse local files`, create a folder named "DoomRunner" and extract `DoomRunner.exe` into it.
3. Download the contents of this repository and place them inside of DoomRunner's folder from the previous step.
4. Download your source port of choice, open the `Sourceports` folder of this repository, create a new folder named after the source port and extract its files inside of it.
	* I personally recommend [UZDoom](https://zdoom.org/downloads) or [DSDA-Doom](https://github.com/kraflab/dsda-doom), but you're free to use any source port you like.
5. Grab the `.wad` files from the DOOM + DOOM II installation folder (inside of "base" or "rerelease") and place them inside of the IWADs folder.
    * Alternatively, you can use [Freedoom](https://freedoom.github.io/download.html).
6. On Steam, right click `DOOM + DOOM II > Properties... > General > Launch Options` and type the following command:
```
"PATH_TO_DOOM'S_FOLDER\DoomRunner\DoomRunner.exe" %command%
```
Replace `PATH_TO_DOOM'S_FOLDER` with the complete path to DOOM + DOOM II's folder from Step 2, and that's it! DoomRunner has been set up to work when launched via Steam. Now let's start configuring it to launch your IWADs and mods.

If you'd like to use the provided `file_info_cache.json` and `options.json` files, follow [these steps](#using-my-own-doomrunner-json-config-file) instead.

## Setting up DoomRunner and creating your own presets
DoomRunner uses presets to store all the necessary configuration for each mod/WAD in a JSON file. If you want to create your own, follow these steps:

### DoomRunner configuration
1. On the top left of DoomRunner, click `Menu > Initial setup`:
    * In the `Add your Doom engines` section, select the EXE of the source port of your choosing, then give it a name in the next screen.
    * In the `Config directory` section, select the folder where you want to store your source port's configuration files.
    * In the `Data directory` section, select the folder where you want to store your save and demo files.
    * In the `Engine family` section, select the correct engine family of your source port. If you're using a fork, check which engine it was forked from.
    * Hit `OK` once you're done.
2. In `Directory with community map packs`, select the folder you're using to store your megawads. (If you're using my folder structure, it's `IWADs/Megawads`)
3. In `Locate your IWADs`, select "Auto-update IWAD list from directory" then pick the folder you're using to store DOOM's .wad files. (If you're using my folder structure, it's `IWADs`)
4. Hit `Done`.

### Preset creation
1. On the left-hand side, click the plus icon under the "Create preset" section and give it a name.
2. In the `Select engine` section, pick the engine you've setup previously.
3. In the `Select IWAD` section, pick the IWAD of the game you want to play. If you're creating a mod preset, select the IWAD specified by the mod's author.
4. In the `Select map pack` section, pick the megawad files you wish to play. If it needs multiple files, you can hold CTRL to pick them in the correct order.
5. OPTIONAL: In the `Selection config` section, pick the .ini or .cfg configuration file of the source port you're using.
6. In the `Add mods` section, add your mod files. If they need to be loaded in a specific order, you can drag them up and down in the list.
7. In the `Additional arguments (preset)` section, add any additional arguments you want to use for that specific preset, like compatibility level, for example. Remember to use arguments recognized by the source port you're using!
    * If you're using UZDoom with the .ini files I've provided, and you want a pure vanilla experience, I recommend using: `+dmflags 4259840 +compatmode 2 +vid_rendermode 0`. These will set the Compatibility Flags to "Doom (strict)", disable freelook, jump, and crouch, and set the renderer to the Doom Software Renderer.
8. Hit `Launch` and enjoy!

## Using my own DoomRunner JSON config file
> [!NOTE]
> This section assumes that you've setup the folders EXACTLY as it is in the repository, you're using the exact same source ports and that you have a basic understanding of JSON files.

I've included the generated `file_info_cache.json` and `options.json` files which have all of my presets already set up and ready to go. To use them, you'll have to make a few edits.

### file_info_cache.json
This file contains source port information. It's setup to use UZDoom and DSDA-Doom. Edit the file and replace `G:\SteamLibrary\steamapps\common\Ultimate Doom` with the corresponding DOOM + DOOM II's installation folder in your system. Also adjust your source port paths accordingly.

### options.json
This file contains preset information. It's a bit more complex than `file_info_cache.json`. A few keys to look out for are:
* config_dir
* data_dir
* mods
* selected_IWAD
* selected_config
* selected_engine
* selected_mappacks

These contain relative paths to the corresponding files for each preset. Adjust accordingly.

**REMINDER:** If you choose to replace these files with an updated version from the most recent push, YOU WILL LOSE ALL PRESETS THAT YOU'VE CREATED YOURSELF! I recommend creating a backup, just in case something goes wrong with your files.

## Mods and Megawads
Below is a list of mods that I enjoy:
* [Ashes: 2063 - Episode One](https://www.moddb.com/mods/ashes-2063/downloads)
* [Ashes: Afterglow - Episode Two](https://www.moddb.com/mods/ashes-2063/downloads)
* [Brutal Doom](https://www.moddb.com/mods/brutal-doom)
    * [Brutal Doom Platinum](https://github.com/EmeraldCoasttt/BrutalDoomPlatinum)
	* [Extermination Day](https://www.moddb.com/mods/brutal-doom/forum/thread/extermination-day-beta-001-download)
* [Brutal Doom 64](https://www.moddb.com/mods/brutal-doom-64)
	* [v2.5 Patch](https://www.moddb.com/mods/brutal-doom-64/addons/brutal-doom-64-v2-patched)
	* [DOOM 64 ULTIMATE MUSIC PACK](https://www.moddb.com/mods/brutal-doom-64/addons/the-doom-64-ultimate-music-pack)
* [Brutal Heretic RPG](https://nzdoom.net/showthread.php?tid=3)
* [Brutal Hexen RPG](https://nzdoom.net/showthread.php?tid=2)
* [Brutal Wolfenstein](https://www.moddb.com/mods/brutal-wolfenstein-3d)
* [Doom 64: Retribution](https://www.moddb.com/mods/doom-64-retribution)
* [Embers of Armageddon](https://www.moddb.com/mods/embers-of-armageddon)
* [Lambda](https://www.moddb.com/mods/lambda-for-doom-and-d00m-2)
* [Live Through Doom](https://discord.gg/sAE7jDT)
* [My House](https://www.doomworld.com/forum/topic/134292-myhousewad/)
* [Project Brutality](https://github.com/pa1nki113r/Project_Brutality)
* [Siren](https://www.moddb.com/mods/siren-doom-tc)
* [Wolfenstein 3D TC](https://www.afadoomer.com/wolf3d/downloads.html)

Below is a list of wads/megawads that I enjoy:
* [Ancient Aliens](https://www.doomworld.com/idgames/levels/doom2/Ports/megawads/aaliens)
* [AUGER;ZENITH](https://www.doomworld.com/idgames/levels/doom2/Ports/megawads/dbp37_augzen)
* [Back to Saturn X Episode 1: Get Out Of My Stations](https://www.doomworld.com/forum/topic/62529)
* [Back to Saturn X Episode 2: Tower In The Fountain Of Sparks](https://www.doomworld.com/forum/topic/69960)
* [Eviternity](https://www.doomworld.com/idgames/levels/doom2/Ports/megawads/eviternity)
* [Stardate 20X6](https://www.doomworld.com/idgames/levels/doom2/Ports/s-u/stardate)
* [Stardate 20X7](https://www.doomworld.com/idgames/levels/doom2/Ports/s-u/sd20x7)
* [Sunlust](https://www.doomworld.com/idgames/levels/doom2/Ports/megawads/sunlust)
* [Valiant](https://www.doomworld.com/idgames/levels/doom2/Ports/megawads/valiant)
* [SIGIL + SIGIL II](https://romero.com/sigil)

Below is a list of extra/optional mods that I enjoy:
* [Brutal Doom v21 Monsters Only](https://www.moddb.com/mods/brutal-doom/downloads/bdv21-monsters-only-version)
* [Brutal Doom 64 Monsters Only](https://www.moddb.com/mods/brutal-doom-64/addons/brutal-doom-64-monsters-gzdoom-only)
* [GZSprFix 2.0 (Revenant100's sprite fixes repacked for GZDoom)](https://forum.zdoom.org/viewtopic.php?t=74649)
* [Doom Metal Soundtrack Volume 5](https://www.moddb.com/mods/brutal-doom/downloads/doom-metal-soundtrack-mod-volume-5)
* [IDKFA Soundtrack](https://www.moddb.com/mods/brutal-doom/addons/idkfa-doom-soundtrack)
* [Hitmarkers](https://www.wad-archive.com/wad/782cb71865e196ea2e4c99b27eb7ce292d42f6b4)
* [ZMovement 3.2.1](https://forum.zdoom.org/viewtopic.php?t=65095)
* [Smooth Doom](https://www.doomworld.com/forum/topic/69451-smooth-doom-update-41420/)
* [Alternate Dark Ambient Music Pack](https://www.moddb.com/mods/brutal-doom/addons/alternate-dark-ambient-music-pack)
* [DoomGals Companion Mod](https://s20-tbl.itch.io/doomgals)
* [Plutonia MIDI Pack](https://www.doomworld.com/idgames/music/plutmidi)
	* [Plutonia MIDI Pack Metal Cover](https://mega.nz/#!rt9lWQ5S!KigeOsjGNqQntAc60HKLV95MloqhBIMjRUz0R2nDiNI)
* [Tilt++](https://forum.zdoom.org/viewtopic.php?t=55413)
* [HXRTC HUD Platinum](https://github.com/FelesNoctis/HXRTCHUD_Platinum)
* [Damage Indicator](https://www.moddb.com/mods/qol-power-trip/addons/damage-indicator1)
* [Bolognese Gore Mod](https://www.moddb.com/mods/brutal-doom/downloads/bolognese-gore-mod-v20)
* [Target Spy](https://github.com/mmaulwurff/target-spy)
