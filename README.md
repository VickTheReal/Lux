# Lux
Semi-recreation of early versions of Amnesia: The Dark Descent

## Key changes:
- Restored climbing mechanic
- Restored pickaxe (MUST HAVE ANIMATION FILES IN THE HAND MODEL FOR MELEE)
- Restored old inventory UI
- Restored completion counter (slightly janky, prone to errors)
- Minor restorations to visual and sound effects, such as sanity damage effects, enemy staring effects, darkness effects and sound, etc.
- Features a very unfinished and partially tested total conversion. Serves mostly as a repository for custom assets and maps as well as for carrying the necessary game.cfg file to run the game

## Guide to install:

- Download the source code
- Copy the Lux.exe file into your Amnesia directory
- Copy the game_lux folder into the Amnesia directory
- Run the game through Lux.exe, or run the experimental game_lux total conversion through the .bat file within
- Optionally if you're playing through Lux.exe, backup your game.cfg file on the config folder and replace it with the one on game_lux/config

Note that the Lux.exe is 32 bits. Building a fresh .exe in 64 bits is just like with Amnesia64.

## Notes:

- Warning, game_lux is a very unfinished and buggy total conversion. The most fatal issue upon testing, the pickaxe doesn't seem to work. If you'd like to play around with the pickaxe, at the very least make a backup of the original models folder in Amnesia's directory and replace it with the one in game_lux. Also make sure to copy the pickaxe item itself from the entities folder into the normal directory, that doesn't require replacing anything. Overall, though, game_lux serves mostly to transport the assets I've used in making this.
- Custom stories are, overall, still playable in Lux.exe. However, two key changes have been made:
- Firstly, the restored QUEST COMPLETED message needs a Quest_EXAMPLE_Name string file for every quest now. For example, the vanilla Quest_00Trail_Text, "Follow the liquid trail and find its source.", would now need a Quest_00Trail_Name, which could look something like "Trail - Old Archives".
- Secondly, all map files now need the before-obsolete "SetNumberOfQuestsInMap(int alNumberOfQuests);" function on "void OnStart();" so that the completion counter may work properly. "int alNumberOfQuests" is the number of "void CompleteQuest(...);" functions on the map, but this is still slightly untested and possibly buggy (though the completion counter in itself is still slightly buggy). On maps that may have multiple ways of completing a quest, and such ways may be activated twice, this function may be tricky to adjust and fit on the map.
- The pickaxe depends on animation files for melee weapons being assigned to the hand model entity for it to work. To be precise, it needs "Melee_Idle", "Melee_Draw", "Melee_Holster", "Melee_Charge", "Melee_Swing" and "Melee_SwingCharge" animations. I currently use the vanilla lantern animations as placeholders, but anyone may attempt to make animations for the hand model. If anyone is willing to make them, I desire for the Penumbra pickaxe animations to be recreated so that I may replace the currently distributed placeholder animations in this repository.

## Credits:

- Buzer2020 for Amnesia64, Frictional Games for the source code as a whole
- Penumbra: Necrologue team for the Infected entity
- Lester79 on ModDB for the paraffin lantern model
- The Frictional Games Discord server for a lot of help
