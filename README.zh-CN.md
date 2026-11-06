# TerraLeveler

[English](README.md) | **简体中文** | [繁體中文](README.zh-TW.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Русский](README.ru.md) | [Português (Brasil)](README.pt-BR.md)

TerraLeveler 是一个 Minecraft Fabric **客户端**模组。它在生存模式下控制你自己的玩家，把一片区域平整到指定高度（自己框选的矩形，或者整座岛），或者给一个区域补上火把照明。它只用正常的走路、挖掘、放置和开箱操作，可以随时暂停、恢复和停止。

> 游戏内界面（设置界面和聊天提示）目前只有中文。

## 功能

### 平地机

- **选区：**手拿普通苹果，左键设角点一、右键设角点二；或者开启“自动识别岛屿范围”，以玩家所在陆地为起点，按周围连续的水面识别整座岛。大岛会分区施工。
- 挖掉目标高度以上的所有方块，在目标高度铺一层泥土 / 草方块地表。地表以下的空洞和流体不会被填满。
- 自动寻路。需要到达高处时搭临时脚手或临时柱子，施工结束后回收。脚手数量受“脚手预算”限制，并记录在本地账本里，重进世界后仍能回收遗留的脚手。
- 处理流体：填掉目标高度以上的水，并尽量先找到、堵住从选区外流进来的源头。
- 背包里有水桶时，从高处下来会用水桶落地。
- “保护容器和方块实体”（默认开启）：遇到箱子、潜影盒、熔炉等方块时暂停并报告坐标。

### 区域照明

- 用苹果选两个角点框出一个三维区域，在方块光不高于阈值的所有可放置地面上放火把（不看天空光）。火把可以从背包里的潜影盒取出。

### 两种模式通用

- 工具耐久降到保护值时换工具；可选从指定名称的潜影盒（“工具盒”）里取替换工具。
- 挖到的泥土等材料超过上限时，把多出来的存进背包里的潜影盒，铺地表缺料时再取出（通过 Quick Shulker 开盒，不会弹出界面）。
- 反击攻击你的怪物、自动进食、掉进水或岩浆后自救；血量过低时暂停，回血后继续。
- 清除挡路的普通动物。村民、傀儡、驯服的宠物和马、改过名或拴着的动物不会被攻击，会绕开或等它走开。
- 屏幕上显示当前状态和进度百分比；暂停时在聊天栏说明原因，需要你处理时有提示音。
- 可选的诊断日志，方便排查问题。

## 下载

在 [Releases](https://github.com/aileboeth-web/TerraLeveler/releases) 页面下载。两个版本功能相同。

| Minecraft | TerraLeveler | 源码分支 |
|---|---|---|
| 26.3 | 0.9.25+26.3 | `mc-26.3` |
| 26.1.2 | 0.9.24 | `main` |

## 运行要求

| | Minecraft 26.3 | Minecraft 26.1.2 |
|---|---|---|
| Fabric Loader | 0.19.5 或更高 | 0.19.3 或更高 |
| Java | 25 或更高 | 25 或更高 |
| [Fabric API](https://github.com/FabricMC/fabric) | 必需（开发时使用 0.163.0+26.3） | 必需（开发时使用 0.154.2+26.1.2） |
| [MaLiLib](https://github.com/maruohon/malilib) | 必需，0.30.2 或更高（设置界面） | 必需，0.28.6 或更高 |
| [Quick Shulker](https://github.com/MoRanpcy/quickshulker) | 必需，26.3 版（测试用 3.1.1-26.3） | 必需，26.1.2 版 |
| [Mod Menu](https://github.com/TerraformersMC/ModMenu) | 可选，在模组列表里提供“配置”按钮 | 可选 |

TerraLeveler 本身只需要装在客户端。联机时如果要用潜影盒相关功能，服务器也需要安装 Quick Shulker；服务器没有时，多余的材料会直接丢弃，缺土时改为挖选区内高于目标高度的土来补充。

## 安装

1. 安装对应 Minecraft 版本的 Fabric Loader。
2. 把该版本的 TerraLeveler JAR 和上表中的必需前置放进游戏目录的 `mods` 文件夹。
3. 启动游戏。

## 使用

### 打开设置

- 打开 MaLiLib 的配置菜单（MaLiLib 默认快捷键 `A + C`），在顶部选择 TerraLeveler；
- 或者在 Mod Menu 的模组列表里点 TerraLeveler 的“配置”按钮。

在设置里选择工作模式（平地机 / 区域照明）并调整各项参数，改动会立即保存。

### 绑定快捷键

TerraLeveler 的快捷键**默认全部不绑定**，第一次使用前请在设置里绑定：

| 快捷键 | 作用 |
|---|---|
| 开始 / 停止施工 | 空闲时开始；施工中或暂停中停止 |
| 暂停 / 恢复 | 暂停或继续当前施工 |
| 记录平地目标高度 | 把脚下完整方块的高度记为目标地面高度（也可以在设置里直接填写 Y） |
| 记录保留物品 | 把主手物品加入或移出自定义保留清单，清单里的物品不会被丢弃 |

聊天提示里会显示你实际绑定的按键。

### 平地（矩形选区）

1. 在设置里选择“平地机”模式。
2. 站到想要的地面高度上，按“记录平地目标高度”，或在设置里填写目标 Y。
3. 主手拿普通苹果，左键点一个角，右键点对角。
4. 按“开始 / 停止施工”。

### 平地（整座岛）

1. 在设置里开启“自动识别岛屿范围”，按需要调整岸线保留、是否铺平岛内水塘等选项。
2. 记录目标高度后站在岛上，按“开始 / 停止施工”：第一次按显示识别结果预览，再按一次确认开工。

开启岛屿模式时苹果选点不起作用，以识别出的岛屿范围为准。

### 区域照明

1. 在设置里选择“区域照明”模式。
2. 用苹果左右键设置三维区域的两个角点，按“开始 / 停止施工”。

### 文件位置

以下文件都在游戏目录下（启动器开启版本隔离时为 `.minecraft/versions/<版本名>/`）：

- `config/terraleveler.json`：设置
- `config/terraleveler-scaffold-ledgers.json`：临时脚手账本（请勿手动清空，否则遗留的脚手无法自动回收）
- `config/terraleveler-island-survey/`：岛屿识别时记录的地形数据
- `logs/terraleveler-diagnostic.log`：诊断日志（用设置里的“诊断日志”开关控制；该项的说明会显示本机的完整路径）

从旧名称 WETA（WorldEater Trench Assistant）升级时，旧的 `weta.json` 等文件会在首次启动时自动复制为新名称。请删除 `mods` 里旧的 `worldeater-trench-assistant-*.jar`，否则新旧两个模组会同时运行。

### 注意事项

- 自动施工会频繁转动视角、移动和破坏方块，在开启反作弊的服务器上可能被判定违规，请先确认服务器规则。
- 施工时普通苹果保留给选区使用，不会被自动吃掉。
- 施工过程中手动移动会被视为人工接管，施工随即暂停。

## 从源码构建

需要 JDK 25。先切换到对应 Minecraft 版本的分支（26.1.2 用 `main`，26.3 用 `mc-26.3`），然后在项目根目录运行：

```bash
./gradlew directTest build -x test
```

Windows 下使用 `gradlew.bat directTest build -x test`。生成的模组 JAR 位于 `build/libs/terraleveler-<版本>.jar`（同目录下的 `-sources.jar` 是源码包）。

`directTest` 先初始化 Minecraft 的方块和物品注册表，再用 JUnit Platform Console Launcher 运行全部测试。Gradle 标准的 `test` 任务不做这一步，部分测试会因 `Not bootstrapped` 失败，所以构建时用 `-x test` 跳过它。

项目结构：

```text
src/client/java/      客户端源码（cn.terraleveler）
src/client/resources/ Mixin 配置
src/main/resources/   fabric.mod.json 与图标
src/test/java/        单元测试
libs/                 编译期依赖（Mod Menu，仅编译使用，不打包进模组）
tools/Make-Icon.ps1   生成模组图标的 PowerShell 脚本
```

版本号在 `gradle.properties` 的 `mod_version` 中设置。

## 许可证

TerraLeveler 以 [MIT 许可证](LICENSE) 发布，Copyright (c) 2026 cys。

第三方组件：

- `libs/` 中的 Mod Menu JAR（`mc-26.3` 分支为 `modmenu-21.0.0.jar`，`main` 分支为 `modmenu-18.0.0-beta.1.jar`）是 TerraformersMC 的 [Mod Menu](https://github.com/TerraformersMC/ModMenu)，MIT 许可证（许可证文本包含在该 JAR 内的 `LICENSE_modmenu`）。它仅用于编译可选的 Mod Menu 集成，不包含在 TerraLeveler 的发布 JAR 中。
- Fabric API（Apache-2.0）、MaLiLib（LGPLv3）、Quick Shulker（MIT）是运行时前置，由玩家自行安装，不随本项目分发。

更新记录见 [CHANGELOG.md](CHANGELOG.md)。
