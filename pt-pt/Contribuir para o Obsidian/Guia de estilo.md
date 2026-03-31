---
permalink: style-guide
publish: true
mobile: true
description: Esta página explica o guia de estilo para escrever a nossa documentação de suporte.
---

A documentação do Obsidian segue as diretrizes de estilo listadas nesta página. Estas diretrizes baseiam-se nas melhores práticas do setor, em particular no [Google developer documentation style guide](<https://developers.google.com/style>) e no [Microsoft Style Guide](https://learn.microsoft.com/en-us/style-guide/). Para casos não abrangidos abaixo, consulte esses guias externos como referências secundárias.

> [!tip]- Contribuir
> A maior parte da documentação existia antes deste guia de estilo.
>
> Se encontrar violações deste guia de estilo, por favor [crie uma issue](https://github.com/obsidianmd/obsidian-docs/issues/new) e submeta um pull request em [obsidianmd/obsidian-docs](https://github.com/obsidianmd/obsidian-docs).

## Terminologia e gramática

### Estilo de linguagem

Para a nossa documentação em inglês, recomenda-se o uso de [Global English](https://docs.openedx.org/en/latest/documentors/references/doc_english_writing.html) para melhor servir o nosso público mundial e para auxiliar nas [[#Translations|Traduções]]. Isto significa:

- Evitar expressões idiomáticas e culturalmente específicas
- Usar voz ativa e construção frásica direta
- Preferir palavras simples e comuns a terminologia complexa
- Ser explícito em vez de implícito
- Para convenções ortográficas, usar inglês americano (por exemplo, 'organize' e não 'organise').

### Termos

- Preferir "keyboard shortcut" a "hotkey". Usar Hotkey quando se referir à funcionalidade específica.
- Preferir "the Obsidian app" em dispositivos móveis, e "the Obsidian application" em computadores.
- Preferir "sync" ou "syncing" a "synchronise" ou "synchronising".
- Preferir "search term" a "search query".
- Preferir "heading" a "header" quando se referir a um texto que introduz uma secção.
- Preferir "maximum" a "max" e "minimum" a "min".

### Nomes de produtos

Os nomes dos produtos Obsidian começam com "Obsidian", por exemplo "Obsidian Publish" e "Obsidian Sync".

Se um parágrafo se tornar excessivamente repetitivo, pode usar a forma abreviada nas referências subsequentes.

Por exemplo:

_Para permitir a configuração específica por dispositivo, o Obsidian Sync não sincroniza as suas próprias definições. É necessário configurar o Sync para cada um dos seus dispositivos._

### UI e interações

- Use **negrito** para indicar o texto dos botões
- Preferir "select" a "tap" ou "click".
	- Para instruções específicas de dispositivos móveis, "tap" é aceitável quando se descrevem interações táteis, pois "click" não está disponível.
- Preferir "sidebar" a "side bar".
- Preferir "perform" a "invoke" e "execute" quando se referir a comandos ou ações.

Quando se referir a múltiplas interações de UI em sequência, use o símbolo → (U+2192). Por exemplo, "**[[Configurações]] → Community plugins**".

### Notas, ficheiros e pastas

- Use "note" quando se referir a um ficheiro Markdown no cofre.
- Use "file" quando se referir a outras extensões de ficheiro que não Markdown.
- Preferir "note name" a "note title".
- Preferir "active note" a "current note".
- Preferir "folder" a "directory".
- Preferir "file type" a "file format", exceto quando se referir especificamente ao formato de dados do conteúdo do ficheiro.

Quando se mover entre notas, use "open" se o destino estiver oculto, e "switch" se tanto a nota de origem como a de destino estiverem abertas em divisões separadas.

### Documentação de referência para definições

Sempre que possível, quaisquer definições devem ser documentadas dentro do Obsidian usando um texto descritivo. Evite documentar uma definição específica na Ajuda do Obsidian, exceto se:

- Requer conhecimento mais aprofundado sobre como e quando utilizá-la.
- É comummente mal utilizada ou questionada.
- _Altera drasticamente_ a experiência do utilizador.

Considere usar um callout de dica se quiser chamar a atenção para uma definição específica.

### Termos direcionais

Use hífen nos termos direcionais quando os utilizar como adjetivos. Evite o hífen quando a direção é usada como substantivo.

**Recomendado:**

- Selecione **[[Configurações]]** no canto inferior esquerdo.
- Selecione **[[Configurações]]** no canto inferior esquerdo.

**Não recomendado:**

- Selecione **[[Configurações]]** no canto inferior esquerdo.
- Selecione **[[Configurações]]** no inferior-esquerdo.

Preferir "upper-left" e "upper-right" a "top-left" e "top-right".

Não indique uma direção quando se referir a definições. A localização do controlo de definições depende do dispositivo.

**Recomendado:**

- Ao lado de **Pick remote vault**, selecione **Choose**.

**Não recomendado:**

- À direita de **Pick remote vault**, selecione **Choose**.

Quando descrever direção vertical em elementos de UI, use "above" e "below" para relações espaciais. Evite "up" e "down" pois são ambíguos em diferentes contextos.

**Recomendado:**

- The search box appears above the file list.
- Additional options are available below.

**Não recomendado:**

- The search box is up from the file list.
- More options are down below.

### Instruções

Use imperativos para os nomes de guias, títulos de secções e instruções passo a passo. O modo imperativo é conciso e orientado para a ação, o que é mais direto para utilizadores que seguem instruções.

- Preferir "Set up" a "Setting up"
- Preferir "Move a file" a "Moving a file"
- Preferir "Import your notes" a "Importing your notes"

### Capitalização de frases

Preferir *sentence case* a *title case* para títulos, botões e títulos. Ao referenciar elementos de UI, corresponda sempre à capitalização do texto na UI.

**Recomendado:**

- How Obsidian stores data

**Não recomendado:**

- How Obsidian Stores Data

### Exemplos

Preferir exemplos realistas a termos sem sentido.

**Recomendado:**

- `task:(call OR schedule)`

**Não recomendado:**

- `task:(foo OR bar)`

### Nomes de teclas e atalhos de teclado

Ao referir-se a teclas e atalhos de teclado, use notação consistente.

**Nomes de teclas individuais:**

Ao referir-se a um caractere do teclado pelo nome, adicione o caractere entre parênteses logo após o nome.

**Recomendado:**

- Press the hyphen (-) key to add a dash.
- Use the question mark (?) to search.

**Não recomendado:**

- Press the hyphen key to add a dash.
- Use the ? to search.
- Add a `-` in front of the word.

**Atalhos de teclado:**

Formate os atalhos de teclado sem espaços em torno do sinal de adição. Quando um atalho difere entre sistemas operativos, especifique ambos.

**Recomendado:**

- Press `Ctrl+Z` (Windows) or `Command+Z` (macOS) to undo.
- Press `Escape` to close this window.
- Use `Tab` to move between fields.

**Não recomendado:**

- Press `Cmd+Z` to undo.
- Press `Ctrl + Z` (with spaces) to undo.
- Press `Ctrl/Cmd+Z` to undo.

Para atalhos que são idênticos em todas as plataformas, não é necessário especificar o SO. Se não tiver a certeza se um atalho difere por plataforma, especifique o SO para maior segurança. Windows e Linux tipicamente usam os mesmos atalhos.

### Markdown

Use linhas em branco entre blocos Markdown:

**Recomendado:**

```md
# Heading 1

This is a section.

1. First item
2. Second item
3. Third item
```

**Não recomendado:**

```md
# Heading 1
This is a section.
1. First item
2. Second item
3. Third item
```

**Travessões em listas:**

Use travessões (—) para separar termos em negrito das suas descrições em listas com marcadores. Não use travessões em listas com marcadores simples aninhadas com ligações.

**Recomendado:**

- **View menu** — create, edit, and switch views.
- **Calculate values** — add prices, compute totals, or perform math operations.

**Não recomendado:**

- [[Criar uma base]] — Learn how to create and embed a base.

### Imagens

Use "**largura** x **altura** pixels" para descrever as dimensões de imagens ou ecrãs.

**Exemplo:**

Dimensões de imagem recomendadas: 1920 x 1080 pixels.

## Estrutura de informação

### Tipos de callout

Use callouts estrategicamente para destacar tipos específicos de informação:

**Tip** (`[!tip]-`) - Conselhos práticos ou melhores práticas que melhoram o fluxo de trabalho do utilizador. Use para atalhos, soluções alternativas ou informação útil mas não essencial. Estes callouts começam recolhidos.

**Info** (`[!info]+`) - Contexto adicional, informação de fundo ou esclarecimentos. Use quando a informação acrescenta compreensão mas não é necessária para completar uma tarefa. Estes callouts começam abertos.

**Warning** (`[!warning]+`) - Avisos importantes que evitam perda de dados, erros ou consequências não intencionais. Use com moderação para situações genuinamente arriscadas. Estes callouts nunca devem ser recolhidos.

**Example** (`[!example]-`) - Notas laterais gerais ou detalhes suplementares. Use para informação tangencial que alguns utilizadores possam achar relevante. Estes callouts começam recolhidos.

**Exemplos:**
```md
> [!tip]- Use keyboard shortcuts
> You can speed up your workflow by memorizing the most-used shortcuts.

> [!info]+ This is a paid addon
> This feature requires a paid subscription to use.

> [!warning]+ This action cannot be undone
> Deleting a vault is permanent. Consider exporting your notes first.

> [!example]- Advanced usage
> You can also configure this setting via the Graph menu.
```

### Listas vs. prosa

Use listas quando apresentar itens discretos que não têm relações sequenciais ou causais fortes. Use prosa e parágrafos quando os itens se constroem uns sobre os outros, requerem explicação ou beneficiam de um fluxo narrativo.

**Use uma lista para:**
- Um conjunto de funcionalidades não relacionadas
- Requisitos de instalação
- Opções de configuração
- Passos de resolução de problemas

**Use prosa para:**
- Explicações de como algo funciona
- Fluxos de trabalho com dependências
- Visões gerais conceptuais
- Orientação que requer contexto

### Tabelas

Use tabelas para comparar funcionalidades, versões ou pontos de dados relacionados onde o alinhamento auxilia a compreensão. Evite tabelas para listas simples ou dados de coluna única.

**Bom caso de uso:**

| Feature | Mobile | Desktop |
|---------|--------|---------|
| Sync | Yes | Yes |
| Plugins | No | Yes |
| Themes | Limited | Full |

### Referências cruzadas

Use ligações wiki internas (`[[Note name]]`) liberalmente para ajudar os utilizadores a navegar em tópicos relacionados. No entanto, evite ligações excessivas:

- Não ligue o mesmo termo várias vezes numa única página
- Ligue apenas quando a página referenciada fornece contexto adicional significativo
- Use texto de ligação descritivo quando útil: `[[Note name#Section|descriptive text]]`

**Exemplo:**

Primeira menção: "Learn about [[Introdução ao Obsidian Sync|Obsidian Sync]] to keep your vault updated across devices."
Menção posterior: "You can configure Sync for each device separately."

### Conteúdo específico por plataforma

Ao documentar funcionalidades que diferem entre plataformas, use títulos de secção para organizar o conteúdo.

Use `Desktop` e `Mobile` como títulos de subsecção para separar instruções ou funcionalidades específicas por plataforma.

**Recomendado:**
```md
## Customizing the ribbon

### Desktop

On the desktop version, you can customize the ribbon as follows:

- Rearrange the order of ribbon actions by dragging and dropping the icons.
- To hide specific actions, right-click on an empty space and uncheck the actions you want to hide.

### Mobile

In the mobile version, you can customize the ribbon through settings:

1. Open **[[Configurações]]**.
2. Navigate to **Appearance**.
3. Click **Manage** under **Ribbon menu**.
```

> [!info]+ Quando criar secções?
> Crie secções separadas apenas se o conteúdo diferir significativamente. Se as instruções forem em grande parte as mesmas com pequenas variações, use notas em linha.

## Ícones e imagens

Inclua ícones e imagens quando facilitarem a explicação de coisas difíceis de descrever com palavras, ou quando precisar de mostrar partes importantes da aplicação Obsidian. Pode guardar imagens na pasta `Attachments`.

- A imagem deve facilitar a compreensão do texto que acompanha.

 **Exemplo**: Uma vez ativado, o plugin [[Contagem de palavras]] criará uma nova entrada na sua barra de estado inferior.

![[Style-guide-zoomed-example.png#interface|300]]

- As imagens devem estar no formato `.png` ou `.svg`.
- Se uma imagem parecer demasiado grande na nota, reduza-a fora do Obsidian, ou ajuste as suas dimensões conforme explicado em [[Incorporar ficheiros#Embed an image in a note|incorporar uma imagem numa nota]].
- Em casos raros, pode querer colocar imagens especialmente grandes ou complexas num [[Callouts#Foldable callouts|callout recolhível]].
- Para janelas pop-up ou modais, a imagem deve mostrar toda a janela da aplicação Obsidian.
 ![[Style-guide-modal-example.png#interface]]

### Ícones

Os ícones [Lucide](https://lucide.dev/icons/) e os ícones personalizados do Obsidian podem ser usados junto a elementos detalhados para fornecer uma representação visual de uma funcionalidade.

**Exemplo:** Na barra lateral à esquerda, selecione **Create new canvas** ![[lucide-layout-dashboard.svg#icon]] para criar um canvas na mesma pasta que o ficheiro ativo.

**Diretrizes para ícones**

- Guarde os ícones na pasta `Attachments/icons`.
- Adicione o prefixo `lucide-` antes do nome do ícone Lucide.
- Adicione o prefixo `obsidian-icon-` antes do nome do ícone Obsidian.

**Exemplo:** O ícone para criar um novo canvas deve ser nomeado `lucide-layout-dashboard`.

- Use a versão SVG dos ícones disponíveis.
- Os ícones devem ter `18` pixels de largura, `18` pixels de altura e uma espessura de traço de `1.5`. Pode ajustar estas definições nos dados SVG.

> [!info]- Ajustar tamanho e traço num SVG
> ```html
> <svg xmlns="http://www.w3.org/2000/svg" width="WIDTH" height="HEIGHT" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="STROKE-WIDTH" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-layout-dashboard"><rect width="7" height="9" x="3" y="3" rx="1"/><rect width="7" height="5" x="14" y="3" rx="1"/><rect width="7" height="9" x="14" y="12" rx="1"/><rect width="7" height="5" x="3" y="16" rx="1"/></svg>
>```

- Utilize a âncora `icon` em imagens incorporadas, para ajustar o espaçamento à volta do ícone de modo a que fique alinhado com o texto nas proximidades.
- Os ícones devem ser rodeados por parênteses. ![[lucide-cog.svg#icon]]

**Exemplo**: `![[lucide-cog.svg#icon]]`

### Etiquetas de âncora de imagem

As etiquetas de âncora de imagem estão disponíveis para adicionar alterações decorativas às imagens incorporadas.

> [!warning] Aviso de Live Preview
> As etiquetas de âncora de ícone não serão exibidas corretamente no **Live Preview.** Use a **Vista de leitura** para confirmar que a etiqueta de âncora foi aplicada.

**Ícone**

`![[lucide-menu.svg#icon]]`

A etiqueta de âncora de ícone garante o alinhamento vertical correto para ícones usados para indicar elementos de interface.

O primeiro ícone de menu usa a etiqueta de âncora ![[lucide-menu.svg#icon]], enquanto o segundo ícone de menu ( ![[lucide-menu.svg]] ) não usa.

**Interface**

`![[Vault picker.png#interface]]`

A etiqueta de âncora de interface adiciona uma sombra decorativa à volta da imagem. Na primeira imagem, a etiqueta de âncora de interface é aplicada.
![[Vault picker.png#interface]]
Em contraste, a segunda imagem não tem a âncora de interface aplicada.

![[Vault picker.png]]

**Contorno**

`![[Backlinks.png#outline]]`

A etiqueta de âncora de contorno adiciona uma borda subtil à volta da imagem. Na primeira imagem, a etiqueta de âncora de contorno é aplicada.

> [!tip] Observe o canto inferior esquerdo da imagem para ver a diferença.

![[Backlinks.png#outline]]

A segunda imagem não tem a etiqueta de âncora de contorno.

![[Backlinks.png]]

### Otimização

As imagens atrasam o tempo de carregamento da página e ocupam valioso espaço de armazenamento do [[Introdução ao Obsidian Publish|Publish]]. Otimizar imagens permite reduzir o tamanho do ficheiro, mantendo a integridade visual da imagem.

Tanto as imagens como os ícones devem ser otimizados.

> [!info] Ferramentas para otimizar imagens
> Aqui estão alguns programas recomendados para reduzir o tamanho das suas imagens.
> - **Windows:** [FileOptimizer](https://sourceforge.net/projects/nikkhokkho/)
> - **macOS:** [ImageOptim](https://imageoptim.com/)
> - **Linux/Unix** [Trimage](https://trimage.org)
>
> Recomendamos uma taxa de otimização de 65-75%.

## Disposição

### Ligações quebradas

Antes de submeter o seu Pull Request, verifique se existem ligações quebradas na documentação da tradução em que está a trabalhar, e corrija-as. As ligações quebradas podem ocorrer naturalmente ao longo do tempo, pelo que verificar a sua precisão ajuda a manter a qualidade da documentação.

Pode verificar ligações quebradas usando [[Plugins da comunidade]] ou ferramentas disponíveis no seu IDE.

### Descrições

Esta documentação é editada no GitHub e alojada online através do [[Introdução ao Obsidian Publish|Obsidian Publish]], que inclui [[Pré-visualizações de links em redes sociais#Description|descrições]] para cartões sociais e outros elementos [[SEO]].

Se a página em que está a trabalhar não tiver uma [[Propriedades|propriedade]] `description`, por favor adicione uma. A descrição deve ter 150 caracteres ou menos e fornecer um resumo objetivo do conteúdo da página.

**Bom**: Learn to create templates that capture and organize web page metadata automatically with Web Clipper.
**Pode ser ajustado**: Learn how to create templates that automatically capture and organize metadata from web pages with Web Clipper.

### Direções

Ao escrever ou reescrever [[#Instruções]] sobre como realizar uma ação dentro da aplicação, certifique-se de incluir passos tanto para as versões móvel como de computador.

Se não tiver acesso a um dispositivo móvel ou de computador, por favor mencione isso ao submeter o seu Pull Request.

## Translations

  Translate the entirety of the content when completing a translation. This includes and is not limited to:

- Note names
- Folder names
- Aliases
- Attachment names
- Alt link text
