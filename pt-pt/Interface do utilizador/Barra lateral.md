---
aliases:
  - Sidebar
  - left Sidebar
  - right Sidebar
description: Saiba mais sobre as barras laterais esquerda e direita do Obsidian e como gerir separadores e grupos de separadores.
mobile: true
permalink: sidebar
publish: true
---

O Obsidian tem duas barras laterais: uma barra lateral esquerda e uma barra lateral direita. As barras laterais contêm separadores criados por plugins, como [[Links inversos]], [[Links de saída]] e o [[Explorador de ficheiros]]. No computador, também pode arrastar notas para a barra lateral para as manter visíveis junto ao editor principal.

No computador e em tablets maiores, a barra lateral esquerda inclui a [[Faixa de opções]]. Em dispositivos móveis e tablets mais pequenos, as barras laterais estão [[#Open hidden sidebars|recolhidas por predefinição]].

## Abrir barras laterais ocultas

### Computador e tablets maiores

No computador e em tablets maiores, abra uma barra lateral recolhida selecionando o ícone de expandir esquerdo ![[obsidian-icon-side-bar-left.svg#icon]] ou direito ![[obsidian-icon-side-bar-right.svg#icon]].

### Dispositivos móveis e tablets mais pequenos

Em dispositivos móveis e tablets mais pequenos, pode abrir barras laterais ocultas das seguintes formas:

- Deslize para a esquerda ou para a direita
- Selecione o ícone de expandir esquerdo ![[obsidian-icon-side-bar-left.svg#icon]] (apenas barra lateral esquerda)
- Use as opções *Alternar esquerda* ou *Alternar direita* da [[Paleta de comandos]].

## Separadores

Por predefinição, os plugins criam novos separadores em vez de novos [[#Tab groups|grupos de separadores]].

Pode alternar entre separadores selecionando o ícone. Aparece uma dica de ferramenta para o ajudar a identificar os separadores.

Em cada painel, só pode ver um separador de cada vez. Algumas ações trazem automaticamente um separador para a vista. Por exemplo, quando seleciona uma etiqueta, o seu separador abre.

### Abrir ou reabrir separadores

Existem várias formas de adicionar separadores às suas barras laterais:

- **Ativar um plugin**: Muitos plugins criam automaticamente separadores na barra lateral quando ativados. Vá a **Configurações → Plugins da comunidade** (ou **Plugins nativos**) e ative o plugin para o separador que pretende.
- **Executar um comando**: Use a [[Paleta de comandos]] para pesquisar comandos que abrem separadores específicos. Por exemplo, pesquise "Links inversos" ou "Links de saída" para abrir esses separadores.
- **Arrastar uma nota** (apenas computador): No computador, pode arrastar uma nota do [[Explorador de ficheiros]] ou de um separador do editor para a barra lateral para a abrir aí.

Se fechou um separador e pretende recuperá-lo, estes mesmos métodos irão reabri-lo.

### Fechar separadores

Alguns separadores podem ser fechados através do menu de clique com o botão direito, enquanto outros não. Se não pretender ver um separador que não pode ser fechado, considere desativar o plugin relevante ou recolher a barra lateral selecionando o ícone de seta.

### Reorganizar separadores

Pode arrastar e largar ícones de separadores para os reorganizar dentro de um grupo de separadores.

No computador, também pode arrastar separadores da barra lateral para a área do editor principal para os abrir aí.

### Afixar separadores

Pode afixar um separador na barra lateral para controlar como é atualizado quando interage com outras partes da aplicação.

Para afixar ou desafixar um separador na barra lateral, arraste o separador para a barra lateral ou a partir dela.

O comportamento de um separador afixado na barra lateral depende do seu tipo de conteúdo:

- **Notas e Bases**: Um separador de nota ou base afixado permanece no lugar. Novas notas abrem como separadores separados no editor principal em vez de substituírem o separador afixado.
- **Painéis** (como [[Links inversos]] ou [[Links de saída]]): Um painel afixado permanece focado na última nota selecionada. Selecionar uma nota diferente não atualiza o painel afixado.

Para informações sobre afixar separadores no editor principal, consulte [[Separadores#Pin a tab|Afixar um separador]].

## Grupos de separadores

Pode ter múltiplos grupos de separadores na barra lateral.

### Criar grupos de separadores

Para criar um novo grupo de separadores, arraste o ícone de um separador acima ou abaixo de um grupo de separadores atual. A área realçada indica onde o novo grupo de separadores será criado.

### Fechar grupos de separadores

Para fechar um grupo de separadores, pode [[#Close tabs|fechar todos os separadores nele]], ou arrastar todos os separadores do grupo pelos seus ícones e largá-los em grupos de separadores existentes.

Quando apenas a área do separador de um grupo está realçada, o separador que está a ser arrastado irá fundir-se com outros separadores nesse grupo.
