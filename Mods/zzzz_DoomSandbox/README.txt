DoomSandbox
===========

Owns Sandbox Options UI for Doom Survival.

Live worksheets (edit → full game restart):
  Config/sandbox_options.txt       option tabs, ladders, locked rules
  Config/sandbox_difficulties.txt  Difficulty presets (names, icons, ratings, values)

Rules (sandbox_options.txt):
  - Delete a row = remove that option from the UI
  - Change Name/Default/Choices/Does = rewrite that option
  - Add a row / TAB = add option / tab
  - Exactly ONE choice = forced/locked (shown under Locked tabs)
  - Never/10000 is valid for day-interval options (trader/vending reset forever)

Difficulty presets (sandbox_difficulties.txt):
  - One DIFFICULTY block per preset under the Difficulty group
  - Icon paths like #@modfolder:UIAtlases/doomguy_4.png (auto-normalized)
  - Blank option value = use worksheet Default
  - Values must match Choices (short forms like "Default" match "Default (100%)")

Custom / User preset art:
  UIAtlases/Doom_CustomSandboxImage.jpg

Restart after config or DLL changes.

Source:
  c:\GitHub\7D2D-Mods\00_DLL-Projects\Projects\DLL_DoomSandbox
