# Patches for UNIBIOS 4.0

- UNIBIOS created by [Razoola](http://unibios.free.fr)
- Initial patch by [ArcadeTV](https://github.com/ArcadeTV/neogeo-menu)
- Multicart by [Vortex](https://github.com/xvortex/VTXCart)
- PICKnMIX for Vortex carts patch by [zardam](https://github.com/zardam)

## Patching

1. Obtain the [UNIBIOS 4.0 ROM](http://unibios.free.fr/download/uni-bios-40.zip).
2. Use a patcher that can use IPS files to patch the ROM. I used Lunar IPS to create and patch bios files successfully. 

Notes from zardam's original repo, all of which still apply to both patches below.
This patch enables PICKnMIX feature for a custom Vortex cart, with some limitations:
- Works on MVS only (backup RAM used to store soft dips).
- No high score save.
- Tested on a MV1A only.
- Game list (titles and order) is hardcoded. The custom Vortex cart must have been created with this one: [gameslist_2024.txt](gameslist_2024.txt).
- Use at your own risk!

## [uni-bios-leon-autoPnM.ips](uni-bios-leon-autoPnM.ips)

With this patch, the bios autoboots PICKnMIX, even with a normal game cartridge.  Tap A to advance forward by one title, Tap B to back up one title.  Hold A or B to open the full game list.  Use the joystick to change titles (Up/Down moves by one title, Left/Right moves by four titles), select a game by releasing A or B.  If left alone it will cycle all attract modes randomly.  King of the Monsters is excluded from random attract mode when Hard DIP #7 (Free Play) is enabled because the game will default to the Start Compulsion screen and does not advance away from this title.  The standard Vortex cart menu is not accessible with this patch.  The Eye of Typhoon, Xeno Crisis, and 240P Test Suite are not accessible with this patch.

## [uni-bios-leon-exitPnM.ips](uni-bios-leon-exitPnM.ips)

With this patch, the bios does not autoboot PICKnMIX.  When powering up the MVS board or during a soft reset using the Unibios In Game Menu, hold 1P Start to enable PICKnMIX.  Once enabled it will behave the same as the patch above.  Once in PICKnMIX, during a soft reset, hold 1P B Button and the bios will return to the standard Vortex cart menu.  All titles can be selected from this menu including The Eye of Typhoon, Xeno Crisis, and 240P Test Suite.  
