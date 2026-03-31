---
permalink: plugins/canvas
---
Canvas é um [[Plugins nativos|plugin nativo]] para tomada de notas visual. Oferece um espaço infinito para organizar notas e ligá-las a outras notas, anexos e páginas web.

A tomada de notas visual ajuda-o a dar sentido às suas notas, organizando-as num espaço a 2D. Ligue notas com linhas e agrupe notas relacionadas para compreender melhor a relação entre elas.

Os dados do Canvas que cria no Obsidian são guardados como ficheiros `.canvas` utilizando o formato de ficheiro aberto [JSON Canvas](https://jsoncanvas.org/).

## Criar um novo canvas

Para começar a usar o Canvas, primeiro precisa de criar um ficheiro para guardar o seu canvas. Pode criar um novo canvas usando os seguintes métodos.

**Paleta de comandos:**

1. Abra a [[Paleta de comandos]].
2. Selecione **Canvas: Criar novo canvas** para criar um canvas na mesma pasta do ficheiro ativo.

**Explorador de ficheiros:**

- No [[Explorador de ficheiros]], clique com o botão direito na pasta onde pretende criar o canvas.
- Selecione **Novo canvas**.

**Faixa de opções:**

- No menu vertical da faixa de opções, selecione **Criar novo canvas** ![[lucide-layout-dashboard.svg#icon]] para criar um canvas na mesma pasta do ficheiro ativo.

> [!note] A extensão de ficheiro .canvas
> O Obsidian guarda os dados do seu canvas como ficheiros `.canvas` usando um formato de ficheiro aberto chamado [JSON Canvas](https://jsoncanvas.org/).

## Adicionar cartões

Pode arrastar ficheiros para o seu canvas a partir do Obsidian ou de outras aplicações. Por exemplo, ficheiros Markdown, imagens, áudio, PDFs ou até tipos de ficheiro não reconhecidos.

### Adicionar cartões de texto

Pode adicionar cartões apenas de texto que não referenciam um ficheiro. Pode usar Markdown, ligações e blocos de código tal como numa nota.

Para adicionar um novo cartão de texto ao seu canvas:

- Selecione ou arraste o ícone de ficheiro em branco na parte inferior do canvas.

Também pode adicionar cartões de texto fazendo duplo clique no canvas.

Para converter um cartão de texto num ficheiro:

1. Clique com o botão direito no cartão de texto e selecione **Converter em ficheiro...**.
2. Introduza o nome da nota e selecione **Guardar**.

> [!note] Nota
> Os cartões apenas de texto não aparecem em [[Links inversos]]. Para que apareçam, precisa de os converter num ficheiro.

### Adicionar cartões a partir de notas

Para adicionar uma nota do seu cofre ao canvas:

1. Selecione ou arraste o ícone de documento na parte inferior do canvas.
2. Selecione a nota que pretende adicionar.

Também pode adicionar notas a partir do menu de contexto do canvas:

1. Clique com o botão direito no canvas e selecione **Adicionar nota do cofre**.
2. Selecione a nota que pretende adicionar.

Ou pode adicioná-las ao canvas arrastando o ficheiro do [[Explorador de ficheiros]].

### Adicionar cartões a partir de multimédia

Para adicionar multimédia do seu cofre ao canvas:

1. Selecione ou arraste o ícone de ficheiro de imagem na parte inferior do canvas.
2. Selecione o ficheiro multimédia que pretende adicionar.

Também pode adicionar multimédia a partir do menu de contexto do canvas:

1. Clique com o botão direito no canvas e selecione **Adicionar multimédia do cofre**.
2. Selecione o ficheiro multimédia que pretende adicionar.

Ou pode adicioná-los ao canvas arrastando o ficheiro do [[Explorador de ficheiros]].

### Adicionar cartões a partir de páginas web

Para incorporar uma página web no seu canvas:

1. Clique com o botão direito no canvas e selecione **Adicionar página web**.
2. Introduza o URL da página web e selecione **Guardar**.

Também pode selecionar um URL no seu navegador e arrastá-lo para o canvas para o incorporar num cartão.

Para abrir a página web no seu navegador, prima `Ctrl` (ou `Cmd` no macOS) e selecione a etiqueta do cartão. Ou clique com o botão direito no cartão e selecione **Abrir no navegador**.

### Adicionar cartões a partir de pastas

Arraste uma pasta do explorador de ficheiros para adicionar todos os ficheiros dessa pasta ao canvas.

### Editar um cartão

Faça duplo clique num cartão de texto ou de nota para começar a editá-lo. Clique fora do cartão para parar de o editar. Também pode premir `Escape` para parar de editar um cartão.

Também pode editar um cartão clicando com o botão direito nele e selecionando **Editar**.

### Eliminar um cartão

Remova os cartões selecionados clicando com o botão direito em qualquer um deles e selecionando **Eliminar**. Ou prima `Backspace` (ou `Delete` no macOS).

Também pode selecionar **Remover** ![[lucide-trash-2.svg#icon]] nos controlos de seleção acima da seleção.

### Trocar cartões

Pode trocar um cartão de nota ou multimédia por outro cartão do mesmo tipo.

Para trocar um cartão de nota:

1. Clique com o botão direito no cartão que pretende substituir.
2. Selecione **Trocar ficheiro**.
3. Selecione a nota pela qual pretende substituir.

## Selecionar cartões

Selecione cartões no canvas clicando neles. Pode selecionar vários cartões arrastando uma seleção em redor deles.

Também pode adicionar e remover cartões de uma seleção existente premindo `Shift` e selecionando-os.

Prima `Ctrl+a` (ou `Cmd+a` no macOS) para selecionar todos os cartões no canvas.

Para percorrer o conteúdo de um cartão, primeiro precisa de o selecionar.

### Organizar cartões

Arraste um cartão selecionado para o mover.

Prima `Alt` (ou `Option` no macOS) e arraste para duplicar a seleção.

Pode premir `Shift` enquanto arrasta para mover apenas numa direção.

Prima `Space` enquanto move uma seleção para desativar o encaixe.

Selecionar um cartão move-o para a frente.

### Redimensionar um cartão

Arraste qualquer uma das arestas de um cartão para o redimensionar.

Pode premir `Space` enquanto redimensiona para desativar o encaixe.

Para manter a proporção ao redimensionar, prima `Shift` enquanto redimensiona.

## Ligar cartões

Desenhe linhas entre cartões para criar relações entre eles. Use cores e etiquetas para descrever como se relacionam entre si.

### Ligar dois cartões

Para ligar dois cartões com uma linha direcional:

1. Passe o cursor sobre uma das arestas de um cartão até ver um círculo preenchido.
2. Arraste o círculo até à aresta de um cartão diferente para os ligar.

> [!tip] Dica
> Se arrastar a linha sem a ligar a outro cartão, pode então adicionar o cartão ao qual pretende ligá-la.

### Desligar dois cartões

Para remover a ligação entre dois cartões:

1. Passe o cursor sobre uma linha de ligação até aparecerem dois pequenos círculos na linha.
2. Arraste um dos círculos do cartão sem o ligar a outro.

Também pode desligar dois cartões clicando com o botão direito na linha entre eles e selecionando **Remover**. Ou selecionando a linha e premindo `Backspace` (ou `Delete` no macOS).

### Ligar um cartão a um cartão diferente

Para mover uma das extremidades de uma linha de ligação:

1. Passe o cursor sobre uma linha de ligação até aparecerem dois pequenos círculos na linha.
2. Arraste o círculo sobre a extremidade que pretende reconectar para outro cartão.

### Navegar numa ligação

Se dois cartões ligados estiverem distantes, pode navegar para a origem ou o destino da ligação clicando com o botão direito na linha e selecionando **Ir para o destino** ou **Ir para a origem**.

### Adicionar uma etiqueta a uma ligação

Pode adicionar uma etiqueta a uma linha para descrever a relação entre dois cartões.

Para etiquetar uma ligação:

1. Faça duplo clique na linha.
2. Introduza a etiqueta e prima `Escape` ou clique em qualquer lugar do canvas.

Também pode etiquetar uma ligação selecionando-a e depois selecionando **Editar etiqueta** nos controlos de seleção.

Para editar uma etiqueta de ligação, faça duplo clique na linha, ou clique com o botão direito na linha e selecione **Editar etiqueta**.

### Alterar a cor de um cartão ou ligação

1. Selecione os cartões ou ligações que pretende colorir.
2. Nos controlos de seleção, selecione **Definir cor** ![[lucide-palette.svg#icon]].
3. Selecione uma cor.

## Agrupar cartões

### Agrupar cartões selecionados

Para criar um grupo vazio:

- Clique com o botão direito no canvas e selecione **Criar grupo**.

Para agrupar cartões relacionados:

1. Selecione os cartões.
2. Clique com o botão direito em qualquer um dos cartões selecionados e selecione **Criar grupo**.

**Renomear grupo:** Faça duplo clique no nome do grupo para o editar e prima `Enter` para guardar.

## Navegar no canvas

À medida que adiciona mais cartões ao seu canvas, vai querer saber como navegar no canvas para ver uma parte dele. Aprenda a deslocar e ampliar para se mover pelo canvas com facilidade.

### Deslocar o canvas

Para mover o canvas verticalmente e horizontalmente, também conhecido como _deslocamento_, pode usar qualquer uma das seguintes abordagens:

- Prima `Space` e arraste o canvas.
- Arraste o canvas usando o botão central do rato.
- Use a roda do rato para deslocar verticalmente e prima `Shift` enquanto desloca para deslocar horizontalmente.

### Ampliar o canvas

Para ampliar o canvas, prima `Space` ou `Ctrl` (ou `Cmd` no macOS) e use a roda do rato. Ou selecione **Ampliar** ![[lucide-plus.svg#icon]] e **Reduzir** ![[lucide-minus.svg#icon]] nos controlos de zoom no canto superior direito.

#### Ampliar para caber

Para ampliar o canvas de modo a que todos os itens sejam visíveis, selecione **Ampliar para caber** ![[lucide-maximize.svg#icon]]. Ou use o atalho de teclado `Shift+1`.

#### Ampliar para a seleção

Para ampliar o canvas de modo a que todos os itens selecionados sejam visíveis, clique com o botão direito num cartão selecionado e selecione **Ampliar para a seleção**. Ou use o atalho de teclado premindo `Shift+2`.

#### Repor zoom

Para repor o nível de zoom para o valor predefinido, selecione **Repor zoom** nos controlos de zoom no canto superior direito.

## Dicas avançadas

Criámos alguns vídeos rápidos para demonstrar alguns casos de uso avançados do Canvas.

Pode [ver todas as 72 dicas aqui](https://obsidian.md/canvas#protips). Note que os vídeos de dicas só são visíveis no computador.
