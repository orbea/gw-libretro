# gw-libretro

**gw-libretro** is a [libretro](http://www.libretro.com/) core that runs Game & Watch simulators.

test1

It runs simulators converted from source code for the games available at [MADrigal](http://www.madrigaldesign.it/sim/). Each simulator is converted with [pas2lua](https://github.com/leiradel/pas2lua), which was written specifically for this purpose, and uses [bstree](https://github.com/leiradel/bstree), which was also specifically written to obfuscate the generated Lua source code as per MADrigal's request.

The converted games are available at [libretro's buildbot site](http://bot.libretro.com/assets/cores/Handheld%20Electronic%20Game/). Unpack the zip and read the README.txt for instructions.

The [SNES controller](http://commons.wikimedia.org/wiki/File:SNES_controller.svg), the [hand cursor](https://commons.wikimedia.org/wiki/File:Pointing_hand_cursor_vector.svg), and the [Boxy Bold](http://opengameart.org/content/boxy-bold-font) font used in **gw-libretro** are released under the [CC0](http://creativecommons.org/publicdomain/zero/1.0/).

## Changelog
test new
test new1
test new2
test new3

### 1.4.0

* Removed the `constcast.cpp` aberration, the core is now pure C.
* Added the core version to `version.c.templ`.
* Exposed core version to Lua code (helps to add new features and fixes in a backwards compatible way):
  * `system.GW_VERSIONSTR`, a string containing the full version, i.e. `"1.4.0"`
  * `system.GW_VERSION`, a number containing the full version as `major << 16 | minor << 8 | patch`, i.e. `0x010400`
  * `system.GW_MAJOR`, `system.GW_MINOR`, and `system.GW_PATCH`
* Fixed Galaxy II, Motor Cross, and Tron throwing errors when used with previous versions of the core.

### 1.3

* Implemented a menu system to avoid weird button mappings. Now only the buttons used to play the game are mapped to the controller, all other buttons are accessed via the Select (cycle options) and Start (perform action) buttons.
* Added proper credits in the controller help overlay.
* Fixed sounds not looping in Galaxy II, Motor Cross, and Tron.
* Fixed the transparency settings of some images. It fixes some artifacts around the buttons and some backgrounds having the wrong color.
