## BBS 0.3

This update features refactored quest chains, multiple UX features and tweaks. **This update contains breaking changes!**

The list of breaking changes:

* Keyframe paths in animation panel were changed, so some (if not all) keyframes that worked in 0.2 would stop working
* Trigger world object's hitbox anchor was changed to middle XZ and bottom Y, so any trigger objects would need to be shifted by (0.5, 0, 0.5)

The list of changes:

* Added schematic importer (Centryfuga): here is how it works, if you would place a .schematic file into `game/config/structures/`, it would appear in the load structures list with `.schematic` suffix, load it, and it will open an overlay where you can adjust the blocks. Once you're done configuring, close the overlay panel, and the structure would appear. Make sure to save it!
* Added new forms:
    * `bbs:block` a form that renders a single block variant
    * `bbs:structure` a form that renders saved structure (schematic structures have to be saved first)
* Added basic crash report saving mechanism: if the engine crashes, a window should popup that would offering opening crash logs folder, copy crash log to the copy-paste buffer, and just close
* Added new global triggers in Game Settings:
    * `Player: clicked mouse` gets triggered when player presses or releases a mouse button
    * `UI: open menu` gets triggered when app opens a UI menu (The Bendy)
    * `UI: open menu` gets triggered when a UI menu gets closed (The Bendy)
* Added scripting methods:
    * `IScriptEntity.getForm()` returns a direct reference to entity's form (or `null` if it doesn't have one)
    * `IScriptWorld.getEntityByUUID(String)` returns an entity found in the world by given UUID
    * `IScriptWorlds.loadAt(String, double, double, double, float, float)` to spawn player at desired coordinates
* Added arc tool to the world editor (Centryfuga)
* Added open blocks panel keybind to world editor (`O` is default key) (Centryfuga)
* Added basic quest HUD renderer
* Added basic quest tracker in player's inventory menu
* Added `launch.bat`/`launch.sh` (depending on the OS) scripts to distribution
* Added space + left click to move camera as an alternative to middle mouse button (FreakZillA8)
* Added hitbox size option to trigger world object
* Added change tile sets button to world add and edit overlays
* Changed logging system: logs will no longer be save near `launcher.jar` but rather in `game/logs/`. `launcher.log` is the latest log, while the logs with date filenames are previous logs.
* Changed font line word wrapping threshold to 12 symbols
* Changed quest chains: a separate chain is a list of quests that needed to be completed in order, unnecessary options like allow retake and auto accept were removed
* Changed right clicking an entity in REPL world panel pasting `.getEntityByUUID()` snippet instead of direct reference
* Fixed animated models rendered rotated groups incorrectly (Hrymka)
* Fixed form body parts are not considered for equality resulting in selecting incorrect form in the form list menu
* Fixed crash when clicking on non model morphs in animation panel (Kirkus)
* Fixed exponential interpolations having a rough end (because the range of original formulas were 0.001..1 instead of 0..1)
* Fixed mouse clicking in REPL panel will insert code bits even when it shouldn't (Kirkus)
* Fixed a couple of scripting docs documentation issues
* Fixed a crash when there are extra non .jar files in dependencies (Joziah3)
* Fixed memory leak with chalkboard upon window resize (Just Jory)
* Fixed GUI flickering when changing GUI scale by dragging (Just Jory)
* Fixed picking a form with body parts won't add its body parts to the tree list
* Fixed edit metadata and convert world overlays wrongly display warnings about empty world ID
* Fixed non-existent entity/object still being present in the list after it was removed
* Fixed trigger objects hotkey HUD tooltips are visible during camera playback (Kirkus)
* Improved animation panel:
    * Added ability to keyframe color and transform properties
    * Changed the paths for body parts
    * Moved keyframe list was moved to an overlay panel
    * Removed pick/edit keybinds for form picking/editing (to avoid triggering them when vertically navigating by `Q` and `E`)
* Improved langauge string editor:
    * Added context menu option to keys to allow mark keys as completed (in case translation isn't needed)
    * Added feature to add supported langauges without hardcode: create a file `game/assets/lang_editor/languages.json`, and the object's key is the language ID and the value is display label, so adding `{"es_ES": "Español (es_ES)"}` to the file will add Spanish to the list of languages
* Improved crafting table panel:
    * Added solid black background and right click animation to the recipe list
    * Moved title and craft button labels under settings (gear icon)
* Improved tile set editor:
    * Added context menu to UV editor to jumpt to currently selected UV region (Joziah3)
    * Added block tint option (Joziah3)
    * Added replace block model button to the list overlay (Joziah3)
    * Added copy/paste block model context menu items to the list overlay
* Removed camera sync mode, now camera clips are edited by just enabling flight mode

## BBS 0.2

This update features support for localization of some European languages, bug fixes, and some nice tweaks. Special thanks goes to Draacoun, Kirkus, Noozy and Rebane!

**IMPORTANT**: new default tile set atlas (`assets:textures/default_atlas.png`) was added, so in the future, the old default atlas texture (`assets:textures/atlas.png`) will be removed! 

* Added font rendering support of letters from: Portuguese, Russian, Ukrainian, French, German, Spanish, Italian, Swedish, Norwegian, Dutch, Danish and Chinese (thanks to [zpix-pixel-font](https://github.com/SolidZORO/zpix-pixel-font) and Chunk7 for introducing it to me)
* Added Russian (by Kirkus) and Ukrainian (by Kirkus) languages
* Added font rendering formatting codes wave (§w, stacking increases vertical amplitude), shake (§s, stacking increases distance of shake) and rainbow (§n, stacking changes per letter rainbow colors or per entire text fragment) (Centryfuga)
* Added language editor in utility panel (F6) that allows to edit current language's strings (it's userful mostly for translators)
* Added walking camera mode in world menu (Ctrl + B) (Centryfuga)
* Added application icons (Windows and Linux) (Kirkus)
* Added v-sync and frame rate options to App configurations (Protoxy)
* Added feature to connect two nodes by dragging on connection line (Пивовар)
* Added atlas texture picker to tile set editor
* Added tab keybind to toggle between panels in world menu (Kirkus)
* Added `bbs.camera.lock()`, `bbs.camera.isLocked()`, `bbs.camera.set(x, y, z, yaw, pitch, roll, fov)` and `bbs.camera.unlock()` scripting methods to lock and unlock camera
* Added `bbs.animations.play(id)`, `bbs.animations.isPlaying(id)` and `bbs.animations.stop(id)` scripting methods to play and stop animations
* Added FOV options to player data and BBS' engine options
* Added **Animation** and **HUD scene** trigger blocks
* Added form hitbox options
* Added new texture atlas and default tile set (upon first world creation)
* Changed list icon in HUD scenes panel to an appropriate icon (The Bendy)
* Changed buttons, toggles and labels text get shortened with ... if it's too long
* Fixed title in block model factory panel
* Fixed crash when using inventory during scene recording (Kirkus)
* Fixed morph menu in the scenes panel is covered by icon bar (The Bendy and Maysvoch)
* Fixed JSON parser not treating correctly backslashes at the end of the string
* Fixed crashing when a model is empty or has incorrect data format
* Fixed trigger objects could be accessed from anywhere
* Fixed default model texture isn't being picked when picking a texture
* Fixed multi-link based textures appear black with block atlas (due to mipmapping)
* Fixed dialogue labels don't get correctly when they have new line(s) (Пивовар)
* Fixed objectives not being created (Kirkus)
* Fixed actors falling when switching to flight mode
* Fixed blocks placement isn't prioritized (when other chunks are loaded, they are not being updated first)
* Fixed plant block model's texture being stretched
* Fixed form and texture picker panels could've been opened multiple times atop each other (Kirkus)
* Improved forms by rewriting their properties to be separate objects (which also support tweening/transitioning)
* Improved baked AO which elimited dark shading from the sides of blocks (thanks to [0fps article](https://0fps.net/2013/07/03/ambient-occlusion-for-minecraft-like-worlds/))
* Moved REPL panel to world menu

## BBS 0.1.1

Quick patch fix to make it a little bit more stable.

* Added JSON options to specify texture atlas for tile sets
* Added warning when World ID is empty in create world overlay panel (Janetyqua)
* Added warning when generator options are not filled in (meepstertron)
* Added warning when removing a block model in the tile set editor
* Added `RegisterTriggersEvent` for modders to register custom global triggers (TorayLife)
* Added framebuffer toggle in App's settings to disable rendering with framebuffer (it may help with Intel graphics cards 🤞)
* Added first person player data option
* Added jump player data options (toggle jump altogether or limit to jumping only when being on the ground)
* Changed region shapes' volumes rendered as thick lines
* Fixed `min-games` to `mini-games` in the welcome menu (Kyttu)
* Fixed video recording not working when `ffmpeg` is setup (meepstertron)
* Fixed extra blank context menu items in trigger and condition menus
* Fixed a pixel gets drawn in top left corner in the texture editor due to division by `0`
* Fixed missing UI strings (resume button)
* Fixed Max stacks field had wrong label (item's display name) (TheBendy)
* Fixed player data not updating
* Fixed chalkboard passing mouse wheel scroll events
* Fixed letter box and center lines not correctly aligned when letter box is enabled
* Fixed empty UI keys (now all missing UI keys will display as the corresponding UI key)
* Fixed crashing when removing a body part from form editor
* Fixed items not being updated after editing
* Fixed extrude tool not having a keybind (its keybind now is `Shift + 0`)
* Fixed backspace, delete and enter/return are not repeating in the textarea/script editor
* Fixed world objects' debug not rendering (i.e. the proper size of hitboxes and region's shape areas)
* Fixed actors not disappearing after camera was played
* Fixed buttons in data panels crashing BBS due to not selected data entry (TheBendy)
* Fixed chunks not being updated when moving the camera (Janetyqua)
* Fixed folders appearing in the pick data lists (Centryfuga)
* Moved HUD scene's input fields into options :gear: (TheBendy)
* Removed buttons under `Configuration > BBS > Data` (TheBendy)
* Removed flat scrollbar option (TheBendy)
