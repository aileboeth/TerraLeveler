# TerraLeveler

[English](README.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | **Français** | [Deutsch](README.de.md) | [Русский](README.ru.md) | [Português (Brasil)](README.pt-BR.md)

TerraLeveler est un mod Fabric pour Minecraft qui fonctionne **uniquement côté client**. En mode survie, il prend le contrôle de votre propre joueur et nivelle une zone à une hauteur cible (un rectangle que vous sélectionnez, ou une île entière), ou éclaire une zone avec des torches. Il n'utilise que les actions normales de marche, de minage, de pose de blocs et d'ouverture de conteneurs, et vous pouvez le mettre en pause, le reprendre ou l'arrêter à tout moment.

> L'interface en jeu (écran des paramètres et messages du chat) n'existe pour l'instant qu'en chinois.

## Fonctionnalités

### Nivellement du terrain

- **Sélection :** tenez une pomme ordinaire, faites un clic gauche sur le premier coin et un clic droit sur le coin opposé. Ou activez la détection automatique d'île : à partir de la terre sur laquelle vous vous trouvez, TerraLeveler repère l'île entière grâce à l'eau continue qui l'entoure. Les grandes îles sont traitées section par section.
- Retire tous les blocs au-dessus de la hauteur cible et pose une seule couche de surface en terre / herbe à cette hauteur. Les grottes et les fluides sous la surface ne sont pas comblés.
- Trouve ses propres chemins. Quand il doit atteindre des endroits en hauteur, il construit des échafaudages ou des piliers temporaires et les retire une fois le travail terminé. Le nombre de blocs d'échafaudage est limité par un budget d'échafaudage et noté dans un registre local, si bien que les échafaudages restants peuvent encore être retirés après être revenu dans le monde.
- Gère les fluides : comble l'eau au-dessus de la hauteur cible et essaie d'abord de trouver et de boucher les sources qui arrivent de l'extérieur de la sélection.
- Si vous avez un seau d'eau, il l'utilise pour atterrir en redescendant d'une hauteur.
- Protège les conteneurs et les entités de bloc (activé par défaut) : il se met en pause et indique la position lorsqu'il atteint un coffre, une boîte de Shulker, un four ou un bloc similaire.

### Éclairage de zone

- Sélectionnez avec la pomme deux coins d'une zone 3D. TerraLeveler pose des torches sur tous les sols où l'on peut en poser et dont la lumière de bloc est inférieure ou égale à un seuil (la lumière du ciel n'est pas prise en compte). Les torches peuvent être prises dans des boîtes de Shulker de l'inventaire.

### Dans les deux modes

- Change d'outil quand la durabilité atteint une valeur de réserve et peut, en option, prendre des outils de rechange dans des boîtes de Shulker portant un nom choisi (« boîtes à outils »).
- Quand les matériaux récoltés, comme la terre, dépassent une limite, il range le surplus dans une boîte de Shulker de l'inventaire et le ressort quand la surface en a besoin (la boîte est ouverte via Quick Shulker, aucun écran ne s'affiche donc).
- Riposte aux mobs qui vous attaquent, mange automatiquement, sort de l'eau ou de la lave, et se met en pause quand la vie est basse avant de reprendre une fois rétabli.
- Élimine les animaux ordinaires qui bloquent le chemin. Les villageois, les golems, les animaux de compagnie et chevaux apprivoisés, ainsi que les animaux nommés ou tenus en laisse ne sont jamais attaqués ; il les contourne ou attend qu'ils s'écartent.
- Affiche à l'écran l'état actuel et un pourcentage de progression. Quand il se met en pause, il en donne la raison dans le chat et joue un son quand vous devez intervenir.
- Journal de diagnostic facultatif pour le dépannage.

## Téléchargements

Les versions compilées se trouvent sur la page [Releases](https://github.com/aileboeth/TerraLeveler/releases). Les deux versions ont les mêmes fonctionnalités.

| Minecraft | TerraLeveler | Branche des sources |
|---|---|---|
| 26.3 | 0.9.25+26.3 | `mc-26.3` |
| 26.1.2 | 0.9.24 | `main` |

## Prérequis

| | Minecraft 26.3 | Minecraft 26.1.2 |
|---|---|---|
| Fabric Loader | 0.19.5 ou plus récent | 0.19.3 ou plus récent |
| Java | 25 ou plus récent | 25 ou plus récent |
| [Fabric API](https://github.com/FabricMC/fabric) | Requis (compilé avec 0.163.0+26.3) | Requis (compilé avec 0.154.2+26.1.2) |
| [MaLiLib](https://github.com/maruohon/malilib) | Requis, 0.30.2 ou plus récent (écran des paramètres) | Requis, 0.28.6 ou plus récent |
| [Quick Shulker](https://github.com/MoRanpcy/quickshulker) | Requis, version pour 26.3 (testé avec 3.1.1-26.3) | Requis, version pour 26.1.2 |
| [Mod Menu](https://github.com/TerraformersMC/ModMenu) | Facultatif, ajoute un bouton « Config » à la liste des mods | Facultatif |

TerraLeveler lui-même n'a besoin d'être installé que sur le client. Sur un serveur multijoueur, les fonctions liées aux boîtes de Shulker nécessitent aussi Quick Shulker sur le serveur. Sans lui, les matériaux en trop sont jetés et, quand la terre manque, TerraLeveler creuse à la place la terre située au-dessus de la hauteur cible dans la sélection.

## Installation

1. Installez Fabric Loader pour votre version de Minecraft.
2. Placez le JAR de TerraLeveler correspondant à cette version et les mods requis du tableau ci-dessus dans le dossier `mods` du répertoire du jeu.
3. Lancez le jeu.

## Utilisation

### Ouvrir les paramètres

- Ouvrez le menu de configuration de MaLiLib (son raccourci par défaut est `A + C`) et choisissez TerraLeveler en haut, ou
- cliquez sur le bouton « Config » de TerraLeveler dans la liste des mods de Mod Menu.

Choisissez-y le mode de travail (nivellement du terrain ou éclairage de zone) et réglez les options. Les modifications sont enregistrées immédiatement.

### Attribuer les raccourcis

TerraLeveler **n'a aucun raccourci attribué par défaut**. Attribuez-les dans les paramètres avant la première utilisation :

| Raccourci | Action |
|---|---|
| Démarrer / arrêter | Lance un travail à l'arrêt ; l'arrête s'il est en cours ou en pause |
| Pause / reprise | Met en pause ou reprend le travail en cours |
| Enregistrer la hauteur cible | Enregistre la hauteur du bloc plein sous vos pieds comme niveau du sol cible (vous pouvez aussi saisir la valeur Y dans les paramètres) |
| Enregistrer un objet conservé | Ajoute l'objet de votre main principale à la liste personnalisée des objets conservés, ou l'en retire ; les objets de la liste ne sont jamais jetés |

Les messages du chat indiquent les touches que vous avez réellement attribuées.

### Niveler un rectangle

1. Choisissez le mode de nivellement du terrain dans les paramètres.
2. Placez-vous à la hauteur de sol voulue et appuyez sur « Enregistrer la hauteur cible », ou saisissez le Y cible dans les paramètres.
3. Tenez une pomme ordinaire dans la main principale, faites un clic gauche sur un coin et un clic droit sur le coin opposé.
4. Appuyez sur « Démarrer / arrêter ».

### Niveler une île entière

1. Activez la détection automatique d'île dans les paramètres et réglez au besoin les options associées (largeur de rivage conservée, nivellement ou non des mares intérieures, etc.).
2. Enregistrez la hauteur cible, placez-vous sur l'île et appuyez sur « Démarrer / arrêter ». Le premier appui affiche un aperçu de l'île détectée ; appuyez à nouveau pour confirmer et démarrer.

Quand le mode île est activé, les coins posés avec la pomme sont ignorés et l'île détectée est utilisée à la place.

### Éclairer une zone

1. Choisissez le mode d'éclairage de zone dans les paramètres.
2. Placez les deux coins de la zone 3D avec la pomme (clic gauche et clic droit), puis appuyez sur « Démarrer / arrêter ».

### Emplacement des fichiers

Tous les fichiers se trouvent dans le répertoire du jeu (`.minecraft/versions/<nom de la version>/` si votre lanceur utilise un dossier séparé par version) :

- `config/terraleveler.json` : paramètres
- `config/terraleveler-scaffold-ledgers.json` : registre des échafaudages temporaires (ne le videz pas à la main, sinon les échafaudages restants ne pourront plus être retirés automatiquement)
- `config/terraleveler-island-survey/` : données de terrain enregistrées pendant la détection d'île
- `logs/terraleveler-diagnostic.log` : journal de diagnostic (activé et désactivé par l'option de journal de diagnostic ; sa description dans les paramètres affiche le chemin complet sur votre ordinateur)

Lors d'une mise à jour depuis l'ancien nom WETA (WorldEater Trench Assistant), l'ancien `weta.json` et les fichiers associés sont copiés sous les nouveaux noms au premier lancement. Supprimez l'ancien `worldeater-trench-assistant-*.jar` du dossier `mods`, sinon les deux mods fonctionneront en même temps.

### À savoir

- Le travail automatique tourne la caméra, se déplace et casse des blocs très souvent. Les serveurs dotés d'un anti-triche peuvent le signaler ; vérifiez d'abord les règles du serveur.
- Pendant un travail, les pommes ordinaires sont gardées pour sélectionner des zones et ne sont jamais mangées.
- Se déplacer manuellement pendant un travail est considéré comme une reprise en main, et le travail se met en pause.

## Compiler depuis les sources

Il faut le JDK 25. Passez sur la branche de votre version de Minecraft (`main` pour 26.1.2, `mc-26.3` pour 26.3), puis exécutez à la racine du projet :

```bash
./gradlew directTest build -x test
```

Sous Windows, utilisez `gradlew.bat directTest build -x test`. Le JAR du mod est créé dans `build/libs/terraleveler-<version>.jar` (le `-sources.jar` à côté contient le code source).

`directTest` initialise d'abord les registres de blocs et d'objets de Minecraft, puis exécute tous les tests avec JUnit Platform Console Launcher. La tâche standard `test` de Gradle saute cette étape, si bien que certains tests échouent avec `Not bootstrapped` ; c'est pourquoi la compilation l'ignore avec `-x test`.

Structure du projet :

```text
src/client/java/      code source du client (cn.terraleveler)
src/client/resources/ configuration Mixin
src/main/resources/   fabric.mod.json et icône
src/test/java/        tests unitaires
libs/                 dépendance utilisée seulement à la compilation (Mod Menu ; non incluse dans le mod)
tools/Make-Icon.ps1   script PowerShell qui génère l'icône du mod
```

Le numéro de version est défini par `mod_version` dans `gradle.properties`.

## Licence

TerraLeveler est publié sous [licence MIT](LICENSE), Copyright (c) 2026 cys.

Composants tiers :

- Le JAR de Mod Menu dans `libs/` (`modmenu-21.0.0.jar` sur `mc-26.3`, `modmenu-18.0.0-beta.1.jar` sur `main`) est [Mod Menu](https://github.com/TerraformersMC/ModMenu) de TerraformersMC, sous licence MIT (le texte de la licence est inclus dans le JAR sous le nom `LICENSE_modmenu`). Il sert uniquement à compiler l'intégration facultative avec Mod Menu et n'est pas inclus dans le JAR publié de TerraLeveler.
- Fabric API (Apache-2.0), MaLiLib (LGPLv3) et Quick Shulker (MIT) sont des dépendances d'exécution que les joueurs installent eux-mêmes ; elles ne sont pas distribuées avec ce projet.

Voir [CHANGELOG.md](CHANGELOG.md) pour l'historique des versions (rédigé en chinois).
