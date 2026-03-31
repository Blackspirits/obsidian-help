---
permalink: web-clipper/capture
---
Depois de instalar a extensão de navegador [[Introdução ao Obsidian Web Clipper|Web Clipper]], pode aceder-lhe de várias formas, consoante o seu navegador:

1. O ícone do Obsidian na barra de ferramentas do navegador.
2. Atalhos de teclado, para ativar a extensão a partir do teclado.
3. Menu de contexto, clicando com o botão direito na página web que está a visitar.

Para guardar uma página no Obsidian, clique no botão **Adicionar ao Obsidian**.

## Capturar uma página

Quando abre a extensão, o Web Clipper extrai dados da página web atual seguindo as definições do seu [[Obsidian Web Clipper/Modelos|modelo]]. Pode criar os seus próprios modelos e personalizar o resultado utilizando [[Variáveis]] e [[Filtros]].

Por predefinição, o Web Clipper tenta extrair de forma inteligente apenas o conteúdo principal do artigo, excluindo outros elementos da página. No entanto, pode substituir este comportamento das seguintes formas:

- Se estiver presente um modelo personalizado, é utilizado esse modelo.
- Se houver uma seleção, é utilizada a seleção. Pode utilizar `Ctrl/Cmd+A` para selecionar a página inteira.
- Se houver [[Destacar páginas web|destaques]] presentes, são utilizados os destaques.

## Transferir imagens

As imagens não são transferidas automaticamente quando utiliza o Web Clipper. Em vez disso, as imagens ficam ligadas ao respetivo URL na web. Isto poupa espaço no seu cofre, mas significa que as imagens não estarão acessíveis offline ou se o URL deixar de funcionar.

Pode transferir imagens para qualquer ficheiro no Obsidian utilizando o [[Paleta de comandos|comando]] com o nome **Transferir anexos do ficheiro atual**. Este comando também pode ser associado a um atalho de teclado no Obsidian.

## Atalhos de teclado

O Web Clipper inclui atalhos de teclado que pode utilizar para agilizar o seu fluxo de trabalho. Para alterar os mapeamentos de teclas, aceda a **Definições do Web Clipper** → **Geral** e siga as instruções para o seu navegador. Os mapeamentos podem ser alterados em todos os navegadores, exceto no Safari, que não suporta a edição de atalhos de teclado.

| Ação                          | macOS         | Windows/Linux  |
| ----------------------------- | ------------- | -------------- |
| Abrir o clipper               | `Cmd+Shift+O` | `Ctrl+Shift+O` |
| Captura rápida                | `Opt+Shift+O` | `Alt+Shift+O`  |
| Ativar/desativar o marcador   | `Opt+Shift+H` | `Alt+Shift+H`  |

## Funcionalidade da interface

A interface do Web Clipper está dividida em quatro secções:

1. **Cabeçalho** onde pode mudar de modelos, ativar o [[Destacar páginas web|marcador]], o [[Leitor|modo de leitura]] e aceder às definições.
2. **Propriedades** mostra os [[Propriedades|metadados]] extraídos da página que serão guardados como [[Propriedades]] no Obsidian.
3. **Conteúdo da nota** que será guardado no Obsidian.
4. **Rodapé** permite selecionar o cofre e a pasta, e adicionar ao Obsidian.

A funcionalidade do cabeçalho inclui:

- Menu pendente **Modelo** para alternar entre os [[Obsidian Web Clipper/Modelos|modelos]] guardados adicionados nas definições do Web Clipper.
- Botão **Mais (...)** para apresentar as variáveis de página que pode utilizar nos modelos.
- Botão **Marcador** para ativar o [[Destacar páginas web|marcador]].
- Botão **Engrenagem** para abrir as definições do Web Clipper.

A funcionalidade do rodapé inclui:

- Botão **Adicionar ao Obsidian** para guardar dados no Obsidian.
- Menu pendente **Cofre** para alternar entre os cofres guardados adicionados nas definições do Web Clipper.
- Campo **Pasta** para definir em que pasta guardar.
- **Intérprete** para executar [[Interpretar páginas web|instruções em linguagem natural]] na página.
