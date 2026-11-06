# TerraLeveler

[English](README.md) | [简体中文](README.zh-CN.md) | **繁體中文** | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Русский](README.ru.md) | [Português (Brasil)](README.pt-BR.md)

TerraLeveler 是一個 Minecraft Fabric **用戶端**模組。它在生存模式下控制你自己的玩家，把一片區域整平到指定高度（自己框選的矩形，或者整座島），或者為一個區域補上火把照明。它只使用正常的走路、挖掘、放置和開箱操作，可以隨時暫停、繼續和停止。

> 遊戲內介面（設定畫面和聊天提示）目前只有簡體中文。

## 功能

### 整地

- **選區：**手持普通蘋果，左鍵設定角點一、右鍵設定角點二；或者開啟島嶼自動辨識，以玩家所在的陸地為起點，依照周圍連續的水面辨識整座島。大島會分區施工。
- 挖掉目標高度以上的所有方塊，在目標高度鋪一層泥土／草地表。地表以下的空洞和流體不會被填滿。
- 自動尋路。需要到達高處時會搭臨時鷹架或臨時柱子，施工結束後回收。鷹架數量受「鷹架預算」限制，並記錄在本機帳本裡，重新進入世界後仍能回收遺留的鷹架。
- 處理流體：填掉目標高度以上的水，並盡量先找到、堵住從選區外流進來的水源。
- 背包裡有水桶時，從高處下來會用水桶落地。
- 保護容器和方塊實體（預設開啟）：遇到箱子、界伏盒、熔爐等方塊時暫停並回報座標。

### 區域照明

- 用蘋果選兩個角點框出一個立體區域，在方塊光不高於門檻的所有可放置地面上放火把（不計天空光）。火把可以從背包裡的界伏盒取出。

### 兩種模式通用

- 工具耐久降到保護值時更換工具；可選擇從指定名稱的界伏盒（「工具盒」）取出替換工具。
- 挖到的泥土等材料超過上限時，把多出來的存進背包裡的界伏盒，鋪地表缺料時再取出（透過 Quick Shulker 開盒，不會跳出介面）。
- 反擊攻擊你的怪物、自動進食、掉進水或岩漿後自救；血量過低時暫停，回血後繼續。
- 清除擋路的普通動物。村民、傀儡、已馴服的寵物和馬、改過名或拴著的動物不會被攻擊，會繞開或等牠走開。
- 畫面上顯示目前狀態和進度百分比；暫停時在聊天欄說明原因，需要你處理時會有提示音。
- 可選的診斷日誌，方便排查問題。

## 下載

請到 [Releases](https://github.com/aileboeth/TerraLeveler/releases) 頁面下載。兩個版本功能相同。

| Minecraft | TerraLeveler | 原始碼分支 |
|---|---|---|
| 26.3 | 0.9.25+26.3 | `mc-26.3` |
| 26.1.2 | 0.9.24 | `main` |

## 執行需求

| | Minecraft 26.3 | Minecraft 26.1.2 |
|---|---|---|
| Fabric Loader | 0.19.5 或更新 | 0.19.3 或更新 |
| Java | 25 或更新 | 25 或更新 |
| [Fabric API](https://github.com/FabricMC/fabric) | 必需（以 0.163.0+26.3 建置） | 必需（以 0.154.2+26.1.2 建置） |
| [MaLiLib](https://github.com/maruohon/malilib) | 必需，0.30.2 或更新（設定畫面） | 必需，0.28.6 或更新 |
| [Quick Shulker](https://github.com/MoRanpcy/quickshulker) | 必需，26.3 版（以 3.1.1-26.3 測試） | 必需，26.1.2 版 |
| [Mod Menu](https://github.com/TerraformersMC/ModMenu) | 可選，在模組清單中提供「設定」按鈕 | 可選 |

TerraLeveler 本身只需要安裝在用戶端。多人連線時若要使用界伏盒相關功能，伺服器也需要安裝 Quick Shulker；伺服器沒有安裝時，多餘的材料會直接丟棄，缺土時改為挖選區內高於目標高度的土來補充。

## 安裝

1. 安裝對應 Minecraft 版本的 Fabric Loader。
2. 把該版本的 TerraLeveler JAR 和上表中的必需前置模組放進遊戲目錄的 `mods` 資料夾。
3. 啟動遊戲。

## 使用方式

### 開啟設定

- 開啟 MaLiLib 的設定選單（MaLiLib 預設快捷鍵為 `A + C`），在上方選擇 TerraLeveler；
- 或者在 Mod Menu 的模組清單中點 TerraLeveler 的「設定」按鈕。

在設定中選擇工作模式（整地／區域照明）並調整各項參數，變更會立即儲存。

### 綁定快捷鍵

TerraLeveler 的快捷鍵**預設全部未綁定**，第一次使用前請在設定中綁定：

| 快捷鍵 | 作用 |
|---|---|
| 開始／停止施工 | 閒置時開始；施工中或暫停中則停止 |
| 暫停／繼續 | 暫停或繼續目前的施工 |
| 記錄目標高度 | 把腳下完整方塊的高度記為目標地面高度（也可以在設定中直接填寫 Y） |
| 記錄保留物品 | 把主手物品加入或移出自訂保留清單，清單中的物品不會被丟棄 |

聊天提示中會顯示你實際綁定的按鍵。

### 整地（矩形選區）

1. 在設定中選擇整地模式。
2. 站到想要的地面高度上，按「記錄目標高度」，或在設定中填寫目標 Y。
3. 主手持普通蘋果，左鍵點一個角，右鍵點對角。
4. 按「開始／停止施工」。

### 整地（整座島）

1. 在設定中開啟島嶼自動辨識，視需要調整岸線保留、是否一併鋪平島內水塘等選項。
2. 記錄目標高度後站在島上，按「開始／停止施工」：第一次按會顯示辨識結果預覽，再按一次確認開工。

開啟島嶼模式時，蘋果選點不會生效，以辨識出的島嶼範圍為準。

### 區域照明

1. 在設定中選擇區域照明模式。
2. 用蘋果左右鍵設定立體區域的兩個角點，按「開始／停止施工」。

### 檔案位置

以下檔案都在遊戲目錄下（啟動器開啟版本隔離時為 `.minecraft/versions/<版本名稱>/`）：

- `config/terraleveler.json`：設定
- `config/terraleveler-scaffold-ledgers.json`：臨時鷹架帳本（請勿手動清空，否則遺留的鷹架將無法自動回收）
- `config/terraleveler-island-survey/`：島嶼辨識時記錄的地形資料
- `logs/terraleveler-diagnostic.log`：診斷日誌（以設定中的診斷日誌開關控制；該項說明會顯示本機的完整路徑）

從舊名稱 WETA（WorldEater Trench Assistant）升級時，舊的 `weta.json` 等檔案會在首次啟動時自動複製為新名稱。請刪除 `mods` 中舊的 `worldeater-trench-assistant-*.jar`，否則新舊兩個模組會同時執行。

### 注意事項

- 自動施工會頻繁轉動視角、移動和破壞方塊，在開啟反作弊的伺服器上可能被判定違規，請先確認伺服器規則。
- 施工時普通蘋果保留給選區使用，不會被自動吃掉。
- 施工過程中手動移動會被視為手動接管，施工隨即暫停。

## 從原始碼建置

需要 JDK 25。先切換到對應 Minecraft 版本的分支（26.1.2 用 `main`，26.3 用 `mc-26.3`），然後在專案根目錄執行：

```bash
./gradlew directTest build -x test
```

Windows 下使用 `gradlew.bat directTest build -x test`。產生的模組 JAR 位於 `build/libs/terraleveler-<版本>.jar`（同目錄下的 `-sources.jar` 是原始碼包）。

`directTest` 會先初始化 Minecraft 的方塊和物品註冊表，再用 JUnit Platform Console Launcher 執行全部測試。Gradle 標準的 `test` 工作不做這一步，部分測試會因 `Not bootstrapped` 而失敗，所以建置時用 `-x test` 略過它。

專案結構：

```text
src/client/java/      用戶端原始碼（cn.terraleveler）
src/client/resources/ Mixin 設定
src/main/resources/   fabric.mod.json 與圖示
src/test/java/        單元測試
libs/                 僅編譯期使用的相依套件（Mod Menu，不打包進模組）
tools/Make-Icon.ps1   產生模組圖示的 PowerShell 指令碼
```

版本號在 `gradle.properties` 的 `mod_version` 中設定。

## 授權條款

TerraLeveler 以 [MIT 授權條款](LICENSE) 發布，Copyright (c) 2026 cys。

第三方元件：

- `libs/` 中的 Mod Menu JAR（`mc-26.3` 分支為 `modmenu-21.0.0.jar`，`main` 分支為 `modmenu-18.0.0-beta.1.jar`）是 TerraformersMC 的 [Mod Menu](https://github.com/TerraformersMC/ModMenu)，MIT 授權（授權文字包含在該 JAR 內的 `LICENSE_modmenu`）。它僅用於編譯可選的 Mod Menu 整合，不包含在 TerraLeveler 的發布 JAR 中。
- Fabric API（Apache-2.0）、MaLiLib（LGPLv3）、Quick Shulker（MIT）是執行時前置模組，由玩家自行安裝，不隨本專案散布。

更新記錄見 [CHANGELOG.md](CHANGELOG.md)（簡體中文）。
