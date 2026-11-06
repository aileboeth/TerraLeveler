# TerraLeveler

[English](README.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | **Deutsch** | [Русский](README.ru.md) | [Português (Brasil)](README.pt-BR.md)

TerraLeveler ist eine **rein clientseitige** Fabric-Mod für Minecraft. Im Überlebensmodus steuert sie deinen eigenen Spieler und ebnet ein Gebiet auf eine Zielhöhe ein (ein selbst gewähltes Rechteck oder eine ganze Insel) oder beleuchtet ein Gebiet mit Fackeln. Sie nutzt nur normales Laufen, Abbauen, Platzieren und Öffnen von Behältern, und du kannst sie jederzeit pausieren, fortsetzen oder stoppen.

> Die Oberfläche im Spiel (Einstellungsbildschirm und Chatnachrichten) gibt es derzeit nur auf Chinesisch.

## Funktionen

### Gelände einebnen

- **Auswahl:** Halte einen normalen Apfel, klicke mit links auf die erste Ecke und mit rechts auf die gegenüberliegende Ecke. Oder schalte die automatische Inselerkennung ein: Ausgehend vom Land, auf dem du stehst, findet TerraLeveler die ganze Insel anhand des zusammenhängenden Wassers um sie herum. Große Inseln werden abschnittsweise bearbeitet.
- Entfernt alle Blöcke oberhalb der Zielhöhe und legt auf der Zielhöhe eine einzelne Oberfläche aus Erde / Grasblöcken. Höhlen und Flüssigkeiten unter der Oberfläche werden nicht aufgefüllt.
- Findet selbst Wege. Wenn sie hohe Stellen erreichen muss, baut sie temporäre Gerüste oder Säulen und entfernt sie nach getaner Arbeit wieder. Die Anzahl der Gerüstblöcke ist durch ein Gerüstbudget begrenzt und wird in einem lokalen Verzeichnis festgehalten, sodass übrig gebliebene Gerüste auch nach dem erneuten Betreten der Welt noch abgebaut werden können.
- Kümmert sich um Flüssigkeiten: füllt Wasser oberhalb der Zielhöhe auf und versucht zuerst, Quellen zu finden und zu verschließen, die von außerhalb der Auswahl hereinfließen.
- Landet beim Abstieg aus der Höhe mit einem Wassereimer, falls du einen dabeihast.
- Schützt Behälter und Blockobjekte (standardmäßig an): pausiert und meldet die Position, wenn sie auf eine Truhe, eine Shulkerkiste, einen Ofen oder einen ähnlichen Block trifft.

### Gebiet beleuchten

- Wähle mit dem Apfel zwei Ecken eines 3D-Bereichs. TerraLeveler stellt Fackeln auf jeden Boden, auf dem das möglich ist und dessen Blocklicht höchstens einem Schwellenwert entspricht (Himmelslicht wird nicht berücksichtigt). Fackeln können aus Shulkerkisten im Inventar genommen werden.

### In beiden Modi

- Wechselt das Werkzeug, wenn die Haltbarkeit einen Reservewert erreicht, und kann optional Ersatzwerkzeuge aus Shulkerkisten mit einem gewählten Namen nehmen („Werkzeugkisten“).
- Wenn gesammelte Materialien wie Erde ein Limit überschreiten, lagert sie den Überschuss in einer Shulkerkiste im Inventar ein und holt ihn wieder heraus, wenn die Oberfläche mehr braucht (die Kiste wird über Quick Shulker geöffnet, daher erscheint kein Bildschirm).
- Wehrt sich gegen Mobs, die dich angreifen, isst automatisch, rettet sich aus Wasser oder Lava und pausiert bei niedriger Gesundheit; nach der Erholung geht es weiter.
- Räumt gewöhnliche Tiere aus dem Weg. Dorfbewohner, Golems, gezähmte Haustiere und Pferde sowie benannte oder angeleinte Tiere werden nie angegriffen; sie geht um sie herum oder wartet, bis sie Platz machen.
- Zeigt den aktuellen Zustand und einen Fortschritt in Prozent auf dem Bildschirm an. Beim Pausieren nennt sie den Grund im Chat und spielt einen Ton ab, wenn du eingreifen musst.
- Optionales Diagnoseprotokoll zur Fehlersuche.

## Downloads

Fertige Versionen gibt es auf der Seite [Releases](https://github.com/aileboeth/TerraLeveler/releases). Beide Versionen haben dieselben Funktionen.

| Minecraft | TerraLeveler | Quellcode-Branch |
|---|---|---|
| 26.3 | 0.9.25+26.3 | `mc-26.3` |
| 26.1.2 | 0.9.24 | `main` |

## Voraussetzungen

| | Minecraft 26.3 | Minecraft 26.1.2 |
|---|---|---|
| Fabric Loader | 0.19.5 oder neuer | 0.19.3 oder neuer |
| Java | 25 oder neuer | 25 oder neuer |
| [Fabric API](https://github.com/FabricMC/fabric) | Erforderlich (gebaut mit 0.163.0+26.3) | Erforderlich (gebaut mit 0.154.2+26.1.2) |
| [MaLiLib](https://github.com/maruohon/malilib) | Erforderlich, 0.30.2 oder neuer (Einstellungsbildschirm) | Erforderlich, 0.28.6 oder neuer |
| [Quick Shulker](https://github.com/MoRanpcy/quickshulker) | Erforderlich, Version für 26.3 (getestet mit 3.1.1-26.3) | Erforderlich, Version für 26.1.2 |
| [Mod Menu](https://github.com/TerraformersMC/ModMenu) | Optional, fügt der Mod-Liste eine „Config“-Schaltfläche hinzu | Optional |

TerraLeveler selbst muss nur auf dem Client installiert sein. Auf einem Mehrspielerserver brauchen die Shulkerkisten-Funktionen auch Quick Shulker auf dem Server. Ohne es wird überschüssiges Material weggeworfen, und wenn Erde fehlt, gräbt TerraLeveler stattdessen Erde oberhalb der Zielhöhe innerhalb der Auswahl ab.

## Installation

1. Installiere Fabric Loader für deine Minecraft-Version.
2. Lege die TerraLeveler-JAR für diese Version und die erforderlichen Mods aus der Tabelle oben in den Ordner `mods` deines Spielverzeichnisses.
3. Starte das Spiel.

## Verwendung

### Einstellungen öffnen

- Öffne das Konfigurationsmenü von MaLiLib (MaLiLibs Standard-Tastenkürzel ist `A + C`) und wähle oben TerraLeveler, oder
- klicke in der Mod-Liste von Mod Menu bei TerraLeveler auf „Config“.

Wähle dort den Arbeitsmodus (Gelände einebnen oder Gebiet beleuchten) und passe die Optionen an. Änderungen werden sofort gespeichert.

### Tastenkürzel belegen

TerraLeveler hat **standardmäßig keine Tastenkürzel belegt**. Belege sie vor der ersten Verwendung in den Einstellungen:

| Tastenkürzel | Funktion |
|---|---|
| Start / Stopp | Startet einen Auftrag im Leerlauf; stoppt ihn, wenn er läuft oder pausiert ist |
| Pause / Fortsetzen | Pausiert den aktuellen Auftrag oder setzt ihn fort |
| Zielhöhe speichern | Speichert die Höhe des vollen Blocks unter deinen Füßen als Ziel-Bodenhöhe (den Y-Wert kannst du auch in den Einstellungen eintippen) |
| Behaltenen Gegenstand speichern | Fügt den Gegenstand in deiner Haupthand zur eigenen Behalten-Liste hinzu oder entfernt ihn; Gegenstände auf der Liste werden nie weggeworfen |

Die Chatnachrichten zeigen die Tasten an, die du tatsächlich belegt hast.

### Ein Rechteck einebnen

1. Wähle in den Einstellungen den Modus „Gelände einebnen“.
2. Stell dich auf die gewünschte Bodenhöhe und drücke „Zielhöhe speichern“ oder trage den Ziel-Y-Wert in den Einstellungen ein.
3. Halte einen normalen Apfel in der Haupthand, klicke mit links auf eine Ecke und mit rechts auf die gegenüberliegende Ecke.
4. Drücke „Start / Stopp“.

### Eine ganze Insel einebnen

1. Schalte in den Einstellungen die automatische Inselerkennung ein und passe bei Bedarf die zugehörigen Optionen an (Breite des erhaltenen Ufers, ob Teiche im Inselinneren mit eingeebnet werden usw.).
2. Speichere die Zielhöhe, stell dich auf die Insel und drücke „Start / Stopp“. Beim ersten Drücken erscheint eine Vorschau der erkannten Insel; drücke erneut, um zu bestätigen und zu starten.

Solange der Inselmodus aktiv ist, werden mit dem Apfel gesetzte Ecken ignoriert und stattdessen die erkannte Insel verwendet.

### Ein Gebiet beleuchten

1. Wähle in den Einstellungen den Modus „Gebiet beleuchten“.
2. Setze mit dem Apfel (Links- und Rechtsklick) die beiden Ecken des 3D-Bereichs und drücke dann „Start / Stopp“.

### Speicherorte der Dateien

Alle Dateien liegen im Spielverzeichnis (`.minecraft/versions/<Versionsname>/`, wenn dein Launcher für jede Version einen eigenen Ordner verwendet):

- `config/terraleveler.json`: Einstellungen
- `config/terraleveler-scaffold-ledgers.json`: Verzeichnis der temporären Gerüste (nicht von Hand leeren, sonst können übrig gebliebene Gerüste nicht mehr automatisch abgebaut werden)
- `config/terraleveler-island-survey/`: Geländedaten, die bei der Inselerkennung aufgezeichnet wurden
- `logs/terraleveler-diagnostic.log`: Diagnoseprotokoll (wird mit der Option für das Diagnoseprotokoll ein- und ausgeschaltet; ihre Beschreibung in den Einstellungen zeigt den vollständigen Pfad auf deinem Computer)

Beim Upgrade vom alten Namen WETA (WorldEater Trench Assistant) werden die alte `weta.json` und zugehörige Dateien beim ersten Start unter die neuen Namen kopiert. Entferne die alte `worldeater-trench-assistant-*.jar` aus `mods`, sonst laufen beide Mods gleichzeitig.

### Gut zu wissen

- Die automatische Arbeit dreht sehr häufig die Kamera, bewegt sich und baut Blöcke ab. Server mit Anti-Cheat können das als Verstoß werten; prüfe zuerst die Serverregeln.
- Während ein Auftrag läuft, werden normale Äpfel für die Gebietsauswahl aufgehoben und nie gegessen.
- Wenn du dich während eines Auftrags selbst bewegst, gilt das als Übernahme, und der Auftrag pausiert.

## Aus dem Quellcode bauen

Du brauchst JDK 25. Wechsle auf den Branch für deine Minecraft-Version (`main` für 26.1.2, `mc-26.3` für 26.3) und führe im Projektstamm aus:

```bash
./gradlew directTest build -x test
```

Unter Windows verwende `gradlew.bat directTest build -x test`. Die Mod-JAR wird unter `build/libs/terraleveler-<Version>.jar` erzeugt (die `-sources.jar` daneben enthält den Quellcode).

`directTest` initialisiert zuerst die Block- und Item-Registries von Minecraft und führt dann alle Tests mit dem JUnit Platform Console Launcher aus. Gradles Standardaufgabe `test` überspringt diesen Schritt, sodass einige Tests mit `Not bootstrapped` fehlschlagen; deshalb lässt der Build sie mit `-x test` aus.

Projektstruktur:

```text
src/client/java/      Client-Quellcode (cn.terraleveler)
src/client/resources/ Mixin-Konfiguration
src/main/resources/   fabric.mod.json und Symbol
src/test/java/        Unit-Tests
libs/                 Abhängigkeit nur zum Kompilieren (Mod Menu; nicht in der Mod enthalten)
tools/Make-Icon.ps1   PowerShell-Skript, das das Mod-Symbol erzeugt
```

Die Versionsnummer wird über `mod_version` in `gradle.properties` festgelegt.

## Lizenz

TerraLeveler wird unter der [MIT-Lizenz](LICENSE) veröffentlicht, Copyright (c) 2026 cys.

Komponenten von Drittanbietern:

- Die Mod-Menu-JAR in `libs/` (`modmenu-21.0.0.jar` auf `mc-26.3`, `modmenu-18.0.0-beta.1.jar` auf `main`) ist [Mod Menu](https://github.com/TerraformersMC/ModMenu) von TerraformersMC unter der MIT-Lizenz (der Lizenztext liegt in der JAR als `LICENSE_modmenu`). Sie wird nur zum Kompilieren der optionalen Mod-Menu-Anbindung verwendet und ist nicht in der veröffentlichten TerraLeveler-JAR enthalten.
- Fabric API (Apache-2.0), MaLiLib (LGPLv3) und Quick Shulker (MIT) sind Laufzeitabhängigkeiten, die Spieler selbst installieren; sie werden nicht mit diesem Projekt verteilt.

Die Versionsgeschichte steht in [CHANGELOG.md](CHANGELOG.md) (auf Chinesisch).
