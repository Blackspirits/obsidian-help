---
permalink: tabs
publish: true
mobile: true
description: 'Learn how to open, organize, and manage tabs in Obsidian, including pinning, stacking, and linked views.'
---

Os separadores no Obsidian funcionam de forma semelhante aos separadores noutras aplicações, como os navegadores web.

Pode abrir quantos separadores quiser no Obsidian. Também pode organizar os separadores para criar esquemas personalizados que persistem até à próxima vez que abrir a aplicação.

> [!note] Separadores em dispositivos móveis
> Em dispositivos móveis, pode gerir os separadores abertos a partir do contador de separadores na [[Aplicação móvel#Navigation bar|barra de navegação]].

## Abrir um novo separador

Na parte superior da janela da aplicação, junto ao último separador à direita, selecione **Novo separador** ![[lucide-plus.svg#icon]]. Em alternativa, utilize um atalho de teclado:

- **Windows e Linux:** `Ctrl+t`
- **macOS:** `Cmd+t`

## Abrir uma ligação

Selecione uma ligação no Obsidian para a abrir no separador ativo.

Para abrir uma ligação num novo separador, prima `Ctrl` (ou `Cmd` no macOS) e selecione a ligação.

As seguintes são todas as teclas modificadoras que pode utilizar para abrir ligações de várias formas:

|Ação|MacOS|Windows/Linux|
|---|---|---|
|**Navegar**|_Nenhuma_|_Nenhuma_|
|**Novo separador**|`⌘` (+ `Shift` no modo de fonte)|`Ctrl` (+ `Shift` no modo de fonte)|
|**Novo grupo de separadores**|`⌘` `⌥`| `Ctrl` `Alt`|
|**Nova janela**|`⌘` `⌥` `Shift`|`Ctrl` `Alt` `Shift`|

## Organizar os separadores e janelas

Cada separador pertence a um _grupo de separadores_. Pode arrastar e largar separadores para os reorganizar dentro de um grupo, movê-los para um grupo diferente ou criar um novo grupo. No ambiente de trabalho, pode arrastar separadores para fora da janela para os abrir numa [[Janelas destacáveis|janela destacável]] separada.

Os separadores nas barras laterais mostram apenas o ícone. Passe o cursor sobre o ícone para ver uma dica de ferramenta com o título do separador.

### Reorganizar separadores

Para alterar a ordem dos separadores, arraste o separador ao longo dos outros separadores no grupo.

Ao arrastar um separador, _zonas de largagem_ — áreas onde pode largar o separador — ficam realçadas. A zona de largagem determina onde inserir o separador. Alguns separadores só podem estar numa das barras laterais.

### Dividir um grupo de separadores

Clique com o botão direito num separador e selecione **Dividir à direita** ou **Dividir para baixo** para criar um novo grupo de separadores com esse separador.

Também pode dividir um grupo de separadores arrastando um separador para a parte inferior de outro separador.

### Redimensionar um grupo de separadores

Para redimensionar um grupo de separadores, passe o cursor sobre uma extremidade do grupo. A extremidade fica realçada quando pode ser arrastada para redimensionar.

Pode redimensionar as barras laterais de forma semelhante para criar mais espaço para os grupos de separadores no centro.

### Mover um separador para uma nova janela

**Arrastar e largar:**

- Selecione e arraste o separador para fora da janela da aplicação para o abrir numa nova janela.

**Paleta de comandos:**

- Abra a Paleta de comandos e selecione **Mover o separador atual para uma nova janela**.

### Mover um separador para uma janela diferente

Para mover um separador para outra janela existente, arraste o separador para a janela para a qual pretende movê-lo.

### Fixar um separador

Para fixar um separador no editor principal, clique com o botão direito no separador e selecione **Fixar**. As ligações num separador fixo abrem sempre num separador separado.

Para desafixar um separador fixo no editor principal, clique com o botão direito no separador e selecione **Desafixar**.

Para fixar ou desafixar um separador na barra lateral, consulte [[Barra lateral#Pin tabs|fixar separadores na barra lateral]].

## Mudar para um separador diferente

Selecione um separador para mudar para ele. Em alternativa, utilize um atalho de teclado:

| Mudar para                        | MacOS            | Windows/Linux        |
|-----------------------------------|------------------|----------------------|
| **Separador seguinte**            | `⌃`+`⇥`         | `Ctrl`+`Tab`         |
| **Separador anterior**            | `⌃`+`⇧`+`⇥`    | `Ctrl`+`Shift`+`Tab` |
| **Primeiro separador à esquerda** | `⌘`+`1`          | `Ctrl`+`1`           |
| **2.º ao 8.º separador**          | `⌘`+`2`..`8`     | `Ctrl`+`2`..`8`      |
| **Último separador à direita**    | `⌘`+`9`          | `Ctrl`+`9`           |
| **Separador fechado recentemente**| `⌘`+`⇧`+`t`     | `Ctrl`+`Shift`+`t`   |

## Empilhar grupos de separadores

Pode empilhar separadores para os deslizar sobre outros separadores no mesmo grupo.

Para empilhar notas, selecione a seta para baixo no canto superior direito do grupo de separadores e, em seguida, selecione **Empilhar notas**.

![tab-stacks](https://user-images.githubusercontent.com/693981/188205363-0f24b2a5-3706-4a8c-b38b-7a66baa68ce6.gif)

Os empilhamentos de separadores foram inspirados nas [notas deslizantes de Andy Matuschak](https://notes.andymatuschak.org/).

## Vistas ligadas

As _vistas ligadas_ são separadores que fazem referência a um separador diferente. Quando o conteúdo do separador referenciado muda, a vista ligada também muda.

Para separadores de notas, pode utilizar os seguintes plugins como vistas ligadas:

- [[Vista de grafo]] (local)
- [[Links inversos]]
- [[Sumário]]

Para abrir uma vista ligada para um separador de nota:

1. Selecione **Mais opções** ![[lucide-more-horizontal.svg#icon]] no canto superior direito da nota.
2. Em **Abrir vista ligada**, selecione a vista ligada que pretende abrir.

## Guardar esquemas

Pode guardar e restaurar esquemas de janela utilizando o plugin [[Áreas de trabalho]].
