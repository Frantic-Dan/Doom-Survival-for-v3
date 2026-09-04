================================================================ 
==                              == 
==          POI Scourge Mod (LITE) V1.5          == 
==             Map Tracker & Completionist Tool             == 
==                              ==
================================================================

Thank you for downloading POI Scourge Lite! This version is designed for players who want the completionist tracking features of the original mod without the added economy, items, or difficulty mechanics.

This mod automatically tracks your progress through the world, marking cleared locations on your map, revealing uncleared locations, and providing detailed statistics on your conquest of the wasteland. It is lightweight and designed for maximum compatibility.

--- TABLE OF CONTENTS ---

1. Installation
2. Core Features
3. Configuration (Settings.xml)
4. Console Commands
5. Lite Version Notes
6. Change Log

--- 1. INSTALLATION ---

1. Navigate to your 7 Days to Die installation folder.
2. If it does not already exist, create a folder named 'Mods' (case-sensitive).
3. Place the entire 'POIScourgeLite' folder (the one containing this readme) inside the Mods folder.
   Your folder structure should look like this: .../7 Days To Die/Mods/POIScourgeLite/

Your mod is now installed and will be active the next time you launch the game.

Note: This mod must be installed on both the Server and the Client for the map markers to sync correctly.

--- 2. CORE FEATURES ---

== Dynamic Map Marking (Cleared & Uncleared) ==
- Cleared POIs: When you eliminate every zombie within a Point of Interest (POI), the location is legally considered "Scourged." A permanent colored checkmark is immediately added to your map at that location.
- Uncleared POIs: As you explore the map, uncleared POIs can now be marked with a configurable icon (default is a gray question mark) so you know exactly where to go next.
- Markers are color-coded based on the POI Tier (Difficulty) so you can see at a glance which areas you have conquered and which remain.

== POI Scourge Progress Panel ==
A new information panel is added to your Map Screen (top-left corner).
- Displays the current biome you are standing in.
- Lists the total number of POIs in that biome, separated by Tier.
- Tracks exactly how many you have cleared vs. the total available (e.g., "Tier 5: 2 / 10").
- Shows a "World Total" summary at the bottom.
- Map Marker Toggles: Four buttons at the bottom of the panel allow you to instantly Show or Hide "Cleared" and "Uncleared" map markers on the fly.
- Toggleable Panel: You can click the "OPEN/CLOSE" buttons on the panel header to hide the stats if you need to see the map underneath. The mod remembers your choice between sessions.

--- 3. CONFIGURATION (SETTINGS.XML) ---
The mod generates a 'Settings.xml' file in its folder the first time you run the game. You can edit this file to customize the visuals.

IMPORTANT: Restart the game after editing this file.

== UI Settings ==
- ShowMapStatsPanel: (true/false) Completely enables or disables the POI Progress Panel on the map screen.
- ShowChatMessages: (true/false) If set to true, a global chat message will announce when a player clears a POI. Default is false.

== Map Marker Customization ==
You can change the hex color codes and the map icon (sprite) for each POI Tier (0-6) for both Cleared and Uncleared POIs.
- MarkerTextPrefix: Adds text next to the map icon (e.g., Setting this to "T" will label markers "T1", "T2", etc. Leave blank for no text).
- SpriteTierX / UnclearedSpriteTierX: Change the icon used on the map (e.g., "ui_game_symbol_check", "ui_game_symbol_skull", "ui_game_symbol_quest").
- ColorTierX / UnclearedColorTierX: Change the hex color code for that specific tier marker. Example: <ColorTier5>#FFA500</ColorTier5> (Orange).
- ShowUnclearedMapMarkers: (true/false) Enables or disables the uncleared fog-of-war markers.
- ShowUnclearedTier0: (true/false) If true, includes Tier 0 POIs (remnants, filler houses) in uncleared markers.

--- 4. CONSOLE COMMANDS ---
Open the console by pressing F1.

psc_info
Shows the status of the current POI (Total Volumes, Active Volumes, Living Zombies). Useful if you think a POI is bugged or if you can't find the last zombie.

poiscourgecomplete (Alias: psc)
Force-marks the current POI as cleared. Use this if a zombie falls through the world or glitches out, allowing you to get your checkmark.

psc_resetPOI
Resets the status of the current POI, removing the map marker for all players and reapplying the "Uncleared" marker. Use this if you want to re-run a POI or if a marker was placed incorrectly.

psc_stats
Dumps the raw calculated World Statistics to the console log (Total POIs per biome per tier).

psc_clearalldata_confirm
deletes all data for the Scourge Cleared POI's and Scourge Tokens.  This command is intended to fix an error where data from previous worlds would appear on a new map.  Very destructive so use cautiously. 

--- 5. LITE VERSION NOTES ---
This version differs from the Full Release in the following ways:
- No Items: Scourge Tokens, Bundles, and Exchange Stations are removed.
- No Quests: The tutorial and infestation quests are removed.
- No Trader Progression: Trader tier points are not awarded for POI clears.
- No Mechanics: The "Infestation Beacon" and "Stuck Timer" features are removed.
- Optional Chat: Chat messages are disabled by default but can be enabled in Settings.xml.
- Compatibility: Harmony patches have been reduced to the absolute minimum required for tracking, making this version highly compatible with overhauls.

--- 6. CHANGE LOG ---

Change Log 1.5.1
1.  recompiled mod with updated files from 7 days to die Game Version 3.1 Experimental


Change Log V1.5
1. Game Version 3.0 changes to vanilla assembly-CSharp made it so that we had to rework:  EntityTrader, TileEntity, Prefab, SleeperVolume, GameManager.
2. Localization.txt rework and file type changed to csv
3. changed panel to rect naming in windows.xml
4. changed config folder names to new 3.0 standards
5. corrected issue where cleared map information was carried over to new map
6. added console command to clear map data.  use this carefully it will erase all your cleared POI data.  psc_clearalldata_confirm is the command to clear all stored data


V1.4 Update:
- Performance Fix: Fixed a severe lag bug on Dedicated Servers where every zombie kill would continually trigger POI completion checks if the player was standing inside an already-cleared POI.
- New Feature: Added Uncleared POI map markers to track unvisited locations (reveals as you explore).
- New Feature: Added visibility toggle buttons to the Map Progress Panel. You can now instantly hide or show Cleared/Uncleared map markers directly from the UI.
- Customization: Settings.xml now allows for full customization of map Sprites (icons) and allows a custom text prefix (e.g., "T1") to be added to markers.

V1.3 Update:
- Multiplayer Sync Overhaul: Implemented a robust signal system. Markers now sync instantly between Host and Client without needing to relog.
- Tier 6 Support: Added tracking and color settings for Tier 6 POIs.
- New Command: Added 'psc_resetPOI' to reset a POI's status and remove markers.
- New Settings: Added 'ShowChatMessages' to Settings.xml (Default: false).

V1.0 - V1.2 (Legacy):
- Added "POI Scourge Progress" UI to the Map Screen.
- Added persistence for Open/Close state of the Map UI.
- Implemented offset saving to ensure Tier 0 POI markers persist after logging out.
- Added console commands for debugging and forced completion.