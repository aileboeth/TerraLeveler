# TerraLeveler

**English** | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Русский](README.ru.md) | [Português (Brasil)](README.pt-BR.md)

TerraLeveler is a client-side Fabric mod for Minecraft. In survival mode it takes control of your own player and levels an area to a target height (a rectangle you select, or a whole island), or lights up an area with torches. It only uses normal walking, mining, placing and container actions, and you can pause, resume or stop it at any time.

> The in-game interface (settings screen and chat messages) is currently available in Chinese only.

## Features

### Terrain leveling

- **Selection:** hold a plain apple, left-click the first corner and right-click the opposite corner. Or turn on island auto-detection: starting from the land you stand on, TerraLeveler finds the whole island by the continuous water around it. Large islands are worked on section by section.
- Removes every block above the target height and lays a single dirt / grass surface at the target height. Caves and fluids below the surface are not filled in.
- Finds its own paths. When it needs to reach high places it builds temporary scaffolding or pillars and removes them when the job is finished. The number of scaffold blocks is limited by a scaffold budget and recorded in a local ledger, so leftover scaffolding can still be cleaned up after you rejoin the world.
- Handles fluids: fills water above the target height, and first tries to find and block sources flowing in from outside the selection.
- Lands with a water bucket when coming down from a height, if you carry one.
- Protects containers and block entities (on by default): it pauses and reports the position when it reaches a chest, shulker box, furnace or similar block.

### Area lighting

- Select two corners of a 3D area with the apple. TerraLeveler places torches on every placeable floor whose block light is at or below a threshold (sky light is ignored). Torches can be taken from shulker boxes in your inventory.

### Both modes

- Switches tools when durability reaches a reserve value, and can optionally take replacement tools from shulker boxes with a chosen name ("tool boxes").
- When collected materials such as dirt go over a limit, stores the surplus in a shulker box in your inventory and takes it back out when the surface needs more (the box is opened through Quick Shulker, so no screen pops up).
- Fights back against mobs that attack you, eats automatically, escapes from water or lava, and pauses when health is low, then continues after recovering.
- Clears ordinary animals that block the way. Villagers, golems, tamed pets and horses, and named or leashed animals are never attacked; it walks around them or waits.
- Shows the current state and a progress percentage on screen. When it pauses it tells you why in chat, and plays a sound when you need to step in.
- Optional diagnostic log for troubleshooting.

## Downloads

Builds are on the [Releases](https://github.com/aileboeth-web/TerraLeveler/releases) page. Both versions have the same features.

| Minecraft | TerraLeveler | Source branch |
|---|---|---|
| 26.3 | 0.9.25+26.3 | `mc-26.3` |
| 26.1.2 | 0.9.24 | `main` |

## Requirements

| | Minecraft 26.3 | Minecraft 26.1.2 |
|---|---|---|
| Fabric Loader | 0.19.5 or newer | 0.19.3 or newer |
| Java | 25 or newer | 25 or newer |
| [Fabric API](https://github.com/FabricMC/fabric) | Required (built against 0.163.0+26.3) | Required (built against 0.154.2+26.1.2) |
| [MaLiLib](https://github.com/maruohon/malilib) | Required, 0.30.2 or newer (settings screen) | Required, 0.28.6 or newer |
| [Quick Shulker](https://github.com/MoRanpcy/quickshulker) | Required, 26.3 build (tested with 3.1.1-26.3) | Required, 26.1.2 build |
| [Mod Menu](https://github.com/TerraformersMC/ModMenu) | Optional, adds a "Config" button to the mod list | Optional |

TerraLeveler itself only needs to be installed on the client. On a multiplayer server, the shulker box features also need Quick Shulker on the server. Without it, surplus materials are dropped, and when dirt runs short TerraLeveler digs dirt above the target height inside the selection instead.

## Installation

1. Install Fabric Loader for your Minecraft version.
2. Put the TerraLeveler JAR for that version and the required mods from the table above into the `mods` folder of your game directory.
3. Start the game.

## Usage

### Opening the settings

- Open the MaLiLib configuration menu (MaLiLib's default hotkey is `A + C`) and choose TerraLeveler at the top, or
- click the "Config" button for TerraLeveler in Mod Menu's mod list.

Choose the work mode (terrain leveling or area lighting) and adjust the options there. Changes are saved immediately.

### Binding hotkeys

TerraLeveler has **no hotkeys bound by default**. Bind them in the settings before first use:

| Hotkey | What it does |
|---|---|
| Start / stop | Starts a job when idle; stops it while running or paused |
| Pause / resume | Pauses or continues the current job |
| Record target height | Records the height of the full block under your feet as the target ground level (you can also type the Y value in the settings) |
| Record kept item | Adds the item in your main hand to the custom keep list, or removes it; items on the list are never thrown away |

Chat messages show the keys you actually bound.

### Leveling a rectangle

1. Choose the terrain leveling mode in the settings.
2. Stand at the ground height you want and press "Record target height", or type the target Y in the settings.
3. Hold a plain apple in your main hand, left-click one corner and right-click the opposite corner.
4. Press "Start / stop".

### Leveling a whole island

1. Turn on island auto-detection in the settings, and adjust the related options as needed (shoreline margin, whether to level inland ponds, and so on).
2. Record the target height, stand on the island and press "Start / stop". The first press shows a preview of the detected island; press again to confirm and start.

While island mode is on, apple corners are ignored and the detected island is used instead.

### Lighting an area

1. Choose the area lighting mode in the settings.
2. Set the two corners of the 3D area with the apple (left and right click), then press "Start / stop".

### File locations

All files are inside the game directory (`.minecraft/versions/<version name>/` if your launcher keeps a separate folder per version):

- `config/terraleveler.json`: settings
- `config/terraleveler-scaffold-ledgers.json`: temporary scaffolding ledger (do not clear it by hand, or leftover scaffolding can no longer be removed automatically)
- `config/terraleveler-island-survey/`: terrain data recorded during island detection
- `logs/terraleveler-diagnostic.log`: diagnostic log (turned on and off with the diagnostic log option; its description in the settings shows the full path on your computer)

When you upgrade from the old name WETA (WorldEater Trench Assistant), the old `weta.json` and related files are copied to the new names on first start. Remove the old `worldeater-trench-assistant-*.jar` from `mods`, or both mods will run at the same time.

### Things to know

- Automatic building turns the camera, moves and breaks blocks very often. Servers with anti-cheat may flag this. Check the server rules first.
- While a job runs, plain apples are kept for selecting areas and are never eaten.
- Moving manually during a job counts as taking over, and the job pauses.

## Building from source

You need JDK 25. Check out the branch for your Minecraft version (`main` for 26.1.2, `mc-26.3` for 26.3), then run in the project root:

```bash
./gradlew directTest build -x test
```

On Windows use `gradlew.bat directTest build -x test`. The mod JAR is written to `build/libs/terraleveler-<version>.jar` (the `-sources.jar` next to it contains the source code).

`directTest` first initializes Minecraft's block and item registries and then runs all tests with the JUnit Platform Console Launcher. Gradle's standard `test` task skips that step, so some tests fail with `Not bootstrapped`; that is why the build skips it with `-x test`.

Project layout:

```text
src/client/java/      client source code (cn.terraleveler)
src/client/resources/ Mixin configuration
src/main/resources/   fabric.mod.json and icon
src/test/java/        unit tests
libs/                 compile-only dependency (Mod Menu; not bundled into the mod)
tools/Make-Icon.ps1   PowerShell script that generates the mod icon
```

The version number is set by `mod_version` in `gradle.properties`.

## License

TerraLeveler is released under the [MIT License](LICENSE), Copyright (c) 2026 cys.

Third-party components:

- The Mod Menu JAR in `libs/` (`modmenu-21.0.0.jar` on `mc-26.3`, `modmenu-18.0.0-beta.1.jar` on `main`) is [Mod Menu](https://github.com/TerraformersMC/ModMenu) by TerraformersMC, MIT License (the license text is included in the JAR as `LICENSE_modmenu`). It is only used to compile the optional Mod Menu integration and is not included in the TerraLeveler release JAR.
- Fabric API (Apache-2.0), MaLiLib (LGPLv3) and Quick Shulker (MIT) are runtime dependencies installed by players themselves; they are not distributed with this project.

See [CHANGELOG.md](CHANGELOG.md) for the version history (written in Chinese).
