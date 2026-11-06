# TerraLeveler

[English](README.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Русский](README.ru.md) | **Português (Brasil)**

TerraLeveler é um mod Fabric para Minecraft que roda **só no cliente**. No modo sobrevivência, ele assume o controle do seu próprio jogador e nivela uma área até uma altura-alvo (um retângulo que você seleciona ou uma ilha inteira), ou ilumina uma área com tochas. Ele usa apenas as ações normais de andar, minerar, colocar blocos e abrir contêineres, e você pode pausar, retomar ou parar a qualquer momento.

> A interface dentro do jogo (tela de configurações e mensagens do chat) por enquanto está disponível apenas em chinês.

## Recursos

### Nivelamento de terreno

- **Seleção:** segure uma maçã comum, clique com o botão esquerdo no primeiro canto e com o direito no canto oposto. Ou ative a detecção automática de ilha: partindo da terra em que você está, o TerraLeveler encontra a ilha inteira pela água contínua ao redor dela. Ilhas grandes são trabalhadas por seções.
- Remove todos os blocos acima da altura-alvo e coloca uma única camada de superfície de terra / grama nessa altura. Cavernas e fluidos abaixo da superfície não são preenchidos.
- Encontra os próprios caminhos. Quando precisa alcançar lugares altos, constrói andaimes ou pilares temporários e os remove ao terminar o trabalho. A quantidade de blocos de andaime é limitada por um orçamento de andaimes e anotada em um registro local, então os andaimes que sobrarem ainda podem ser removidos depois que você voltar ao mundo.
- Lida com fluidos: preenche a água acima da altura-alvo e primeiro tenta encontrar e tampar as fontes que entram de fora da seleção.
- Se você tiver um balde de água, usa-o para aterrissar ao descer de lugares altos.
- Protege contêineres e entidades de bloco (ativado por padrão): pausa e informa a posição ao chegar a um baú, caixa de shulker, fornalha ou bloco parecido.

### Iluminação de área

- Selecione com a maçã dois cantos de uma área 3D. O TerraLeveler coloca tochas em todo piso onde é possível colocá-las e cuja luz de bloco esteja igual ou abaixo de um limite (a luz do céu não é considerada). As tochas podem ser tiradas de caixas de shulker no inventário.

### Nos dois modos

- Troca de ferramenta quando a durabilidade chega a um valor de reserva e, opcionalmente, pega ferramentas de reposição de caixas de shulker com um nome escolhido ("caixas de ferramentas").
- Quando materiais coletados, como terra, passam de um limite, guarda o excedente em uma caixa de shulker no inventário e o retira de volta quando a superfície precisa de mais (a caixa é aberta pelo Quick Shulker, então nenhuma tela aparece).
- Revida mobs que atacam você, come automaticamente, sai da água ou da lava e pausa quando a vida está baixa, continuando depois de se recuperar.
- Tira do caminho animais comuns que bloqueiam a passagem. Aldeões, golens, pets e cavalos domados e animais com nome ou presos por guia nunca são atacados; ele os contorna ou espera que saiam.
- Mostra na tela o estado atual e uma porcentagem de progresso. Ao pausar, explica o motivo no chat e toca um som quando você precisa intervir.
- Log de diagnóstico opcional para solucionar problemas.

## Downloads

As versões compiladas estão na página de [Releases](https://github.com/aileboeth-web/TerraLeveler/releases). As duas versões têm os mesmos recursos.

| Minecraft | TerraLeveler | Branch do código |
|---|---|---|
| 26.3 | 0.9.25+26.3 | `mc-26.3` |
| 26.1.2 | 0.9.24 | `main` |

## Requisitos

| | Minecraft 26.3 | Minecraft 26.1.2 |
|---|---|---|
| Fabric Loader | 0.19.5 ou mais recente | 0.19.3 ou mais recente |
| Java | 25 ou mais recente | 25 ou mais recente |
| [Fabric API](https://github.com/FabricMC/fabric) | Obrigatório (compilado com 0.163.0+26.3) | Obrigatório (compilado com 0.154.2+26.1.2) |
| [MaLiLib](https://github.com/maruohon/malilib) | Obrigatório, 0.30.2 ou mais recente (tela de configurações) | Obrigatório, 0.28.6 ou mais recente |
| [Quick Shulker](https://github.com/MoRanpcy/quickshulker) | Obrigatório, versão para 26.3 (testado com 3.1.1-26.3) | Obrigatório, versão para 26.1.2 |
| [Mod Menu](https://github.com/TerraformersMC/ModMenu) | Opcional, adiciona um botão "Config" à lista de mods | Opcional |

O próprio TerraLeveler só precisa estar instalado no cliente. Em um servidor multijogador, os recursos de caixas de shulker também precisam do Quick Shulker no servidor. Sem ele, o material excedente é descartado e, quando falta terra, o TerraLeveler cava a terra acima da altura-alvo dentro da seleção.

## Instalação

1. Instale o Fabric Loader da sua versão do Minecraft.
2. Coloque o JAR do TerraLeveler dessa versão e os mods obrigatórios da tabela acima na pasta `mods` do diretório do jogo.
3. Inicie o jogo.

## Uso

### Abrir as configurações

- Abra o menu de configuração do MaLiLib (o atalho padrão do MaLiLib é `A + C`) e escolha TerraLeveler no topo, ou
- clique no botão "Config" do TerraLeveler na lista de mods do Mod Menu.

Escolha ali o modo de trabalho (nivelamento de terreno ou iluminação de área) e ajuste as opções. As alterações são salvas na hora.

### Definir atalhos

O TerraLeveler **não tem nenhum atalho definido por padrão**. Defina-os nas configurações antes do primeiro uso:

| Atalho | O que faz |
|---|---|
| Iniciar / parar | Inicia um trabalho quando ocioso; para quando está em andamento ou pausado |
| Pausar / retomar | Pausa ou continua o trabalho atual |
| Registrar altura-alvo | Registra a altura do bloco inteiro sob seus pés como nível do chão alvo (você também pode digitar o valor Y nas configurações) |
| Registrar item mantido | Adiciona o item da mão principal à lista personalizada de itens mantidos, ou o remove; itens da lista nunca são descartados |

As mensagens do chat mostram as teclas que você realmente definiu.

### Nivelar um retângulo

1. Escolha o modo de nivelamento de terreno nas configurações.
2. Fique na altura de chão desejada e pressione "Registrar altura-alvo", ou digite o Y alvo nas configurações.
3. Segure uma maçã comum na mão principal, clique com o botão esquerdo em um canto e com o direito no canto oposto.
4. Pressione "Iniciar / parar".

### Nivelar uma ilha inteira

1. Ative a detecção automática de ilha nas configurações e ajuste as opções relacionadas se precisar (margem de costa preservada, se os lagos internos também são nivelados etc.).
2. Registre a altura-alvo, fique sobre a ilha e pressione "Iniciar / parar". O primeiro toque mostra uma prévia da ilha detectada; pressione de novo para confirmar e começar.

Com o modo ilha ativado, os cantos marcados com a maçã são ignorados e a ilha detectada é usada no lugar.

### Iluminar uma área

1. Escolha o modo de iluminação de área nas configurações.
2. Marque os dois cantos da área 3D com a maçã (clique esquerdo e direito) e pressione "Iniciar / parar".

### Localização dos arquivos

Todos os arquivos ficam dentro do diretório do jogo (`.minecraft/versions/<nome da versão>/` se o seu launcher usa uma pasta separada para cada versão):

- `config/terraleveler.json`: configurações
- `config/terraleveler-scaffold-ledgers.json`: registro dos andaimes temporários (não o limpe manualmente, ou os andaimes que sobraram não poderão mais ser removidos automaticamente)
- `config/terraleveler-island-survey/`: dados de terreno gravados durante a detecção de ilha
- `logs/terraleveler-diagnostic.log`: log de diagnóstico (ligado e desligado pela opção de log de diagnóstico; a descrição dela nas configurações mostra o caminho completo no seu computador)

Ao atualizar a partir do nome antigo WETA (WorldEater Trench Assistant), o antigo `weta.json` e os arquivos relacionados são copiados para os novos nomes na primeira inicialização. Remova o antigo `worldeater-trench-assistant-*.jar` da pasta `mods`, senão os dois mods vão rodar ao mesmo tempo.

### Bom saber

- O trabalho automático gira a câmera, se move e quebra blocos com muita frequência. Servidores com anticheat podem considerar isso uma infração; confira antes as regras do servidor.
- Enquanto um trabalho está em andamento, as maçãs comuns ficam reservadas para selecionar áreas e nunca são comidas.
- Mover-se manualmente durante um trabalho conta como assumir o controle, e o trabalho é pausado.

## Compilar a partir do código-fonte

Você precisa do JDK 25. Mude para o branch da sua versão do Minecraft (`main` para 26.1.2, `mc-26.3` para 26.3) e execute na raiz do projeto:

```bash
./gradlew directTest build -x test
```

No Windows, use `gradlew.bat directTest build -x test`. O JAR do mod é gerado em `build/libs/terraleveler-<versão>.jar` (o `-sources.jar` ao lado contém o código-fonte).

`directTest` primeiro inicializa os registros de blocos e itens do Minecraft e depois executa todos os testes com o JUnit Platform Console Launcher. A tarefa padrão `test` do Gradle pula essa etapa, então alguns testes falham com `Not bootstrapped`; por isso a compilação a ignora com `-x test`.

Estrutura do projeto:

```text
src/client/java/      código-fonte do cliente (cn.terraleveler)
src/client/resources/ configuração do Mixin
src/main/resources/   fabric.mod.json e ícone
src/test/java/        testes unitários
libs/                 dependência usada só na compilação (Mod Menu; não vai dentro do mod)
tools/Make-Icon.ps1   script PowerShell que gera o ícone do mod
```

O número da versão é definido por `mod_version` em `gradle.properties`.

## Licença

O TerraLeveler é publicado sob a [Licença MIT](LICENSE), Copyright (c) 2026 cys.

Componentes de terceiros:

- O JAR do Mod Menu em `libs/` (`modmenu-21.0.0.jar` no `mc-26.3`, `modmenu-18.0.0-beta.1.jar` no `main`) é o [Mod Menu](https://github.com/TerraformersMC/ModMenu) da TerraformersMC, sob a Licença MIT (o texto da licença está dentro do JAR como `LICENSE_modmenu`). Ele só é usado para compilar a integração opcional com o Mod Menu e não está incluído no JAR publicado do TerraLeveler.
- Fabric API (Apache-2.0), MaLiLib (LGPLv3) e Quick Shulker (MIT) são dependências de execução que os próprios jogadores instalam; elas não são distribuídas com este projeto.

Veja o histórico de versões em [CHANGELOG.md](CHANGELOG.md) (escrito em chinês).
