## BBS 0.2

This update is features support for localization of some European languages, bug fixes, and some nice tweaks. Special thanks goes to Draacoun, Kirkus, Noozy and Rebane!

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
