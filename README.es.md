# TerraLeveler

[English](README.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | **Español** | [Français](README.fr.md) | [Deutsch](README.de.md) | [Русский](README.ru.md) | [Português (Brasil)](README.pt-BR.md)

TerraLeveler es un mod de Fabric para Minecraft que funciona **solo en el cliente**. En modo supervivencia toma el control de tu propio jugador y nivela una zona a una altura objetivo (un rectángulo que eliges o una isla entera), o ilumina una zona con antorchas. Solo usa las acciones normales de caminar, picar, colocar bloques y abrir contenedores, y puedes pausarlo, reanudarlo o detenerlo en cualquier momento.

> La interfaz del juego (pantalla de ajustes y mensajes del chat) por ahora solo está en chino.

## Funciones

### Nivelado del terreno

- **Selección:** sostén una manzana normal, haz clic izquierdo en la primera esquina y clic derecho en la esquina opuesta. O activa la detección automática de islas: partiendo de la tierra en la que estás, TerraLeveler encuentra la isla entera a partir del agua continua que la rodea. Las islas grandes se trabajan por secciones.
- Quita todos los bloques por encima de la altura objetivo y coloca una sola capa de superficie de tierra / césped a esa altura. Las cuevas y los fluidos por debajo de la superficie no se rellenan.
- Busca sus propios caminos. Cuando necesita llegar a sitios altos, construye andamios o pilares temporales y los retira al terminar el trabajo. La cantidad de bloques de andamio está limitada por un presupuesto de andamios y se anota en un registro local, así que los andamios que queden se pueden retirar aunque vuelvas a entrar al mundo.
- Gestiona fluidos: rellena el agua por encima de la altura objetivo y primero intenta encontrar y tapar las fuentes que entran desde fuera de la selección.
- Si llevas un cubo de agua, aterriza con él al bajar desde lo alto.
- Protege contenedores y entidades de bloque (activado por defecto): se pausa e indica la posición cuando llega a un cofre, una caja de shulker, un horno o un bloque similar.

### Iluminación de zonas

- Selecciona con la manzana dos esquinas de una zona 3D. TerraLeveler coloca antorchas en todos los suelos donde se puedan poner y cuya luz de bloque sea igual o menor que un umbral (la luz del cielo no se tiene en cuenta). Las antorchas se pueden sacar de cajas de shulker del inventario.

### En ambos modos

- Cambia de herramienta cuando la durabilidad llega a un valor de reserva y, opcionalmente, saca herramientas de repuesto de cajas de shulker con un nombre elegido («cajas de herramientas»).
- Cuando los materiales recogidos, como la tierra, superan un límite, guarda el sobrante en una caja de shulker del inventario y lo vuelve a sacar cuando la superficie necesita más (la caja se abre mediante Quick Shulker, así que no aparece ninguna pantalla).
- Contraataca a los mobs que te atacan, come automáticamente, sale del agua o la lava y se pausa con poca vida; continúa cuando te recuperas.
- Elimina animales comunes que bloquean el camino. Nunca ataca a aldeanos, gólems, mascotas y caballos domesticados ni a animales con nombre o atados con una correa; los rodea o espera a que se aparten.
- Muestra en pantalla el estado actual y un porcentaje de progreso. Cuando se pausa, te dice el motivo en el chat y emite un sonido cuando necesitas intervenir.
- Registro de diagnóstico opcional para resolver problemas.

## Descargas

Las versiones compiladas están en la página de [Releases](https://github.com/aileboeth-web/TerraLeveler/releases). Ambas versiones tienen las mismas funciones.

| Minecraft | TerraLeveler | Rama del código |
|---|---|---|
| 26.3 | 0.9.25+26.3 | `mc-26.3` |
| 26.1.2 | 0.9.24 | `main` |

## Requisitos

| | Minecraft 26.3 | Minecraft 26.1.2 |
|---|---|---|
| Fabric Loader | 0.19.5 o posterior | 0.19.3 o posterior |
| Java | 25 o posterior | 25 o posterior |
| [Fabric API](https://github.com/FabricMC/fabric) | Obligatorio (compilado con 0.163.0+26.3) | Obligatorio (compilado con 0.154.2+26.1.2) |
| [MaLiLib](https://github.com/maruohon/malilib) | Obligatorio, 0.30.2 o posterior (pantalla de ajustes) | Obligatorio, 0.28.6 o posterior |
| [Quick Shulker](https://github.com/MoRanpcy/quickshulker) | Obligatorio, versión para 26.3 (probado con 3.1.1-26.3) | Obligatorio, versión para 26.1.2 |
| [Mod Menu](https://github.com/TerraformersMC/ModMenu) | Opcional, añade un botón «Config» a la lista de mods | Opcional |

TerraLeveler solo hay que instalarlo en el cliente. En un servidor multijugador, las funciones de cajas de shulker también necesitan Quick Shulker en el servidor. Sin él, el material sobrante se tira y, cuando falta tierra, TerraLeveler la saca de la que hay por encima de la altura objetivo dentro de la selección.

## Instalación

1. Instala Fabric Loader para tu versión de Minecraft.
2. Copia el JAR de TerraLeveler de esa versión y los mods obligatorios de la tabla anterior en la carpeta `mods` del directorio del juego.
3. Inicia el juego.

## Uso

### Abrir los ajustes

- Abre el menú de configuración de MaLiLib (su atajo por defecto es `A + C`) y elige TerraLeveler arriba, o
- pulsa el botón «Config» de TerraLeveler en la lista de mods de Mod Menu.

Elige allí el modo de trabajo (nivelado del terreno o iluminación de zonas) y ajusta las opciones. Los cambios se guardan al momento.

### Asignar atajos de teclado

TerraLeveler **no trae ningún atajo asignado por defecto**. Asígnalos en los ajustes antes de usarlo por primera vez:

| Atajo | Qué hace |
|---|---|
| Iniciar / detener | Inicia un trabajo si está inactivo; lo detiene si está en marcha o en pausa |
| Pausar / reanudar | Pausa o continúa el trabajo actual |
| Guardar altura objetivo | Guarda la altura del bloque completo bajo tus pies como nivel del suelo objetivo (también puedes escribir el valor Y en los ajustes) |
| Guardar objeto conservado | Añade el objeto de tu mano principal a la lista personalizada de objetos conservados, o lo quita; los objetos de la lista nunca se tiran |

Los mensajes del chat muestran las teclas que realmente has asignado.

### Nivelar un rectángulo

1. Elige el modo de nivelado del terreno en los ajustes.
2. Colócate a la altura de suelo que quieras y pulsa «Guardar altura objetivo», o escribe la Y objetivo en los ajustes.
3. Sostén una manzana normal en la mano principal, haz clic izquierdo en una esquina y clic derecho en la opuesta.
4. Pulsa «Iniciar / detener».

### Nivelar una isla entera

1. Activa la detección automática de islas en los ajustes y ajusta las opciones relacionadas si hace falta (margen de costa que se conserva, si se nivelan también los estanques interiores, etc.).
2. Guarda la altura objetivo, ponte sobre la isla y pulsa «Iniciar / detener». La primera pulsación muestra una vista previa de la isla detectada; pulsa otra vez para confirmar y empezar.

Con el modo isla activado, las esquinas marcadas con la manzana se ignoran y se usa la isla detectada.

### Iluminar una zona

1. Elige el modo de iluminación de zonas en los ajustes.
2. Marca las dos esquinas de la zona 3D con la manzana (clic izquierdo y derecho) y pulsa «Iniciar / detener».

### Ubicación de los archivos

Todos los archivos están dentro del directorio del juego (`.minecraft/versions/<nombre de la versión>/` si tu launcher usa una carpeta separada para cada versión):

- `config/terraleveler.json`: ajustes
- `config/terraleveler-scaffold-ledgers.json`: registro de andamios temporales (no lo vacíes a mano o los andamios que queden ya no se podrán retirar automáticamente)
- `config/terraleveler-island-survey/`: datos del terreno guardados durante la detección de islas
- `logs/terraleveler-diagnostic.log`: registro de diagnóstico (se activa y desactiva con la opción de registro de diagnóstico; su descripción en los ajustes muestra la ruta completa en tu equipo)

Al actualizar desde el nombre antiguo WETA (WorldEater Trench Assistant), el antiguo `weta.json` y los archivos relacionados se copian con los nombres nuevos en el primer arranque. Borra el antiguo `worldeater-trench-assistant-*.jar` de `mods`, o los dos mods funcionarán a la vez.

### A tener en cuenta

- El trabajo automático gira la cámara, se mueve y rompe bloques con mucha frecuencia. Los servidores con anti-trampas pueden marcarlo como infracción; revisa antes las normas del servidor.
- Mientras hay un trabajo en marcha, las manzanas normales se reservan para seleccionar zonas y nunca se comen.
- Si te mueves manualmente durante un trabajo, se considera que tomas el control y el trabajo se pausa.

## Compilar desde el código fuente

Necesitas JDK 25. Cambia a la rama de tu versión de Minecraft (`main` para 26.1.2, `mc-26.3` para 26.3) y ejecuta en la raíz del proyecto:

```bash
./gradlew directTest build -x test
```

En Windows usa `gradlew.bat directTest build -x test`. El JAR del mod se genera en `build/libs/terraleveler-<versión>.jar` (el `-sources.jar` que hay al lado contiene el código fuente).

`directTest` inicializa primero los registros de bloques y objetos de Minecraft y luego ejecuta todas las pruebas con JUnit Platform Console Launcher. La tarea estándar `test` de Gradle se salta ese paso, así que algunas pruebas fallan con `Not bootstrapped`; por eso la compilación la omite con `-x test`.

Estructura del proyecto:

```text
src/client/java/      código fuente del cliente (cn.terraleveler)
src/client/resources/ configuración de Mixin
src/main/resources/   fabric.mod.json e icono
src/test/java/        pruebas unitarias
libs/                 dependencia solo de compilación (Mod Menu; no se incluye en el mod)
tools/Make-Icon.ps1   script de PowerShell que genera el icono del mod
```

El número de versión se define con `mod_version` en `gradle.properties`.

## Licencia

TerraLeveler se publica bajo la [licencia MIT](LICENSE), Copyright (c) 2026 cys.

Componentes de terceros:

- El JAR de Mod Menu en `libs/` (`modmenu-21.0.0.jar` en `mc-26.3`, `modmenu-18.0.0-beta.1.jar` en `main`) es [Mod Menu](https://github.com/TerraformersMC/ModMenu) de TerraformersMC, con licencia MIT (el texto de la licencia está dentro del JAR como `LICENSE_modmenu`). Solo se usa para compilar la integración opcional con Mod Menu y no se incluye en el JAR publicado de TerraLeveler.
- Fabric API (Apache-2.0), MaLiLib (LGPLv3) y Quick Shulker (MIT) son dependencias de ejecución que instalan los propios jugadores; no se distribuyen con este proyecto.

Consulta [CHANGELOG.md](CHANGELOG.md) para ver el historial de versiones (escrito en chino).
