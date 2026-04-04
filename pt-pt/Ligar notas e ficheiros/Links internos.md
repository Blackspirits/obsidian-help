---
aliases:
  - How to/Internal link
  - How to/Link to blocks
cssclasses:
  - soft-embed
description: Aprenda a ligar a notas, anexos e outros ficheiros a partir das suas notas, usando ligações internas.
mobile: true
permalink: links
publish: true
---

Aprenda a ligar a notas, anexos e outros ficheiros a partir das suas notas, usando _ligações internas_. Ao ligar notas, pode criar uma rede de conhecimento. ^b15695

O Obsidian pode atualizar automaticamente as ligações internas no seu cofre quando renomeia um ficheiro. Se preferir ser questionado, pode desativar esta opção em:

**[[Configurações]]** → **[[Configurações#Files and links|Ficheiros e ligações]]** → **[[Configurações#Automatically update internal links|Atualizar automaticamente ligações internas]]**.

## Formatos suportados para ligações internas

O Obsidian suporta os seguintes formatos de ligação:

- Wikilink: `[[Três leis do movimento]]` ou `[[Três leis do movimento.md]]`
- Markdown: `[Três leis do movimento](Tres%20leis%20do%20movimento)` ou `[Três leis do movimento](Tres%20leis%20do%20movimento.md)`

Os exemplos acima são equivalentes e aparecem da mesma forma no editor e ligam à mesma nota.

> [!note] Nota
> Ao usar o formato Markdown, certifique-se de [codificar o URL](https://en.wikipedia.org/wiki/Percent-encoding) do destino da ligação. Por exemplo, os espaços em branco tornam-se `%20`.

Por predefinição, devido ao seu formato mais compacto, o Obsidian gera ligações usando o formato Wikilink. Se a interoperabilidade for importante para si, pode desativar os Wikilinks e usar ligações Markdown em vez disso.

Para usar o formato Markdown:

1. Abra as **[[Configurações]]**.
2. Em **Ficheiros e Ligações**, desative **Usar \[\[Wikilinks\]\]**.

Mesmo que desative o formato Wikilink, ainda pode autocompletar ligações digitando dois parênteses retos `[[`. Quando seleciona um dos ficheiros sugeridos, o Obsidian gera uma ligação Markdown em vez disso.

> [!note] Carateres inválidos
> Uma cadeia que contenha os seguintes carateres pode não funcionar como ligação: `# | ^ : %% [[ ]]`.
>
> Recomendamos evitar o uso desses carateres e praticar [boas práticas de nomes de ficheiros](https://stackoverflow.com/questions/1976007/what-characters-are-forbidden-in-windows-and-linux-directory-names).

## Ligar a um ficheiro

Para criar uma ligação na Vista de edição, use qualquer uma das seguintes formas:

- Digite `[[` no editor e selecione o ficheiro para o qual pretende criar uma ligação.
- Selecione texto no editor e depois digite `[[`.
- Abra a [[Command palette]] e selecione Adicionar ligação interna.

![[Alternador rápido#^search-autocomplete-large]]

Embora possa ligar a qualquer um dos [[Formatos de ficheiro aceites]], as ligações para formatos de ficheiro diferentes de Markdown precisam de incluir a extensão do ficheiro, como `[[Figura 1.png]]`.

> [!tip] Prefixar uma ligação interna com um ponto de exclamação (!) permite-lhe incorporar o conteúdo ligado. Para mais detalhes, consulte [[Incorporar ficheiros]].

> [!info] Ficheiros excluídos
> Os ficheiros que correspondem aos seus padrões de [[Configurações#Excluded files|Ficheiros excluídos]] têm menor prioridade nas sugestões de ligações ao criar ligações internas.

## Ligar a um cabeçalho numa nota

Pode ligar a cabeçalhos específicos em notas, também conhecidos como _ligações de âncora_.

**Ligar a um cabeçalho na mesma nota**

Para ligar a um cabeçalho na mesma nota, digite `[[#` para obter uma lista de cabeçalhos dentro da nota para ligar.

Por exemplo, `[[#Pré-visualizar um ficheiro ligado]]` criará uma ligação para [[#Pré-visualizar um ficheiro ligado]].

**Ligar a um cabeçalho noutra nota**

Para ligar a um cabeçalho noutra nota, adicione um cardinal (`#`) no final do destino da ligação, seguido do texto do cabeçalho.

Por exemplo, `[[Sobre o Obsidian#Links are first-class citizens]]` criará uma ligação para [[Sobre o Obsidian#Links are first-class citizens]].

**Ligar a subcabeçalhos**

Pode adicionar múltiplos símbolos de cardinal para cada subcabeçalho.

Por exemplo, `[[Ajuda e suporte#Questions and advice#Report bugs and request features]]` criará uma ligação para [[Ajuda e suporte#Questions and advice#Report bugs and request features]].

**Pesquisar cabeçalhos em todo o cofre**

Para pesquisar cabeçalhos em todo o cofre, use a sintaxe `[[## cabeçalho]]`.

Por exemplo, `[[##` pesquisará genericamente em todo o cofre, enquanto `[[## equipa]]` pesquisará todos os cabeçalhos que contêm a palavra _equipa_.

> [!info]- Captura de ecrã da pesquisa de uma ligação de cabeçalho
>
> ![[internal-links-header.png#interface]]

## Ligar a um bloco numa nota

Um bloco é uma unidade de texto na sua nota, como um parágrafo, citação em bloco ou item de lista.

Pode ligar a um bloco adicionando `#^` no final do destino da ligação, seguido de um identificador de bloco único. Por exemplo: `[[2023-01-01#^37066d]]`. Felizmente, não precisa de encontrar manualmente o identificador — quando digita o acento circunflexo (`^`), aparece uma lista de sugestões, permitindo-lhe selecionar o bloco correto.

Para *parágrafos simples*, coloque um espaço em branco seguido de um acento circunflexo `^` e o identificador de bloco no final da linha:

```md
The quick purple gem dashes through the paragraph with blazing speed. Pen in hand and a paperclip in the other, Gemmy works toward her goal of making the world of note-taking a happier place. ^37066d
```

Para *blocos estruturados* (listas, citações, callouts, tabelas), o identificador de bloco deve estar numa linha separada, com uma linha em branco antes e depois:

```md
> The quick purple gem dashes through the paragraph with blazing speed. Pen in hand and a paperclip in the other, Gemmy works toward her goal of making the world of note-taking a happier place.

^37066f

This is the tale of Gemmy, the Unhelpful assistant.
```

Para *linhas específicas dentro de uma lista*, o identificador de bloco pode ser colocado diretamente num item de marcador:

```mathjax
- Gemmy
    $$Paperclip / Pen$$
    ^37006f
- Unhelpful assistant
```

> [!warning] Não suportamos ligações para partes específicas de citações, callouts e tabelas.

**Pesquisar blocos em todo o cofre**

Também pode pesquisar blocos para ligar em todo o cofre usando a sintaxe `[[^^bloco]]`. No entanto, mais itens se qualificam como blocos em comparação com [[#Link to a heading in a note|ligações de cabeçalho]], por isso esta lista será muito maior.

> [!info]- Captura de ecrã da pesquisa de uma ligação de bloco
> ![[link-block-heading.png#interface]]

Também pode criar identificadores de bloco legíveis por humanos adicionando um espaço em branco seguido de um acento circunflexo (`^`) e o identificador. Os identificadores de bloco só podem consistir em letras latinas, números e hífens.

Por exemplo, adicione `^citacao-do-dia` no final de um bloco:

```md
"You do not rise to the level of your goals. You fall to the level of your systems." by James Clear ^citacao-do-dia
```

Agora pode ligar ao bloco digitando `[[2023-01-01#^citacao-do-dia]]`.

> [!warning] Interoperabilidade
> As referências de bloco são específicas do Obsidian e não fazem parte do formato Markdown padrão. As ligações que contêm referências de bloco não funcionarão fora do Obsidian.

## Alterar o texto de apresentação da ligação

Por predefinição, o Obsidian mostrará o texto da ligação tal como aparece. Por exemplo:
- `[[Exemplo]]` aparece como [[Exemplo]]
- `[[Exemplo#Detalhes]]` aparece como [[Exemplo#Detalhes]]

Pode alterar a forma como uma ligação é apresentada personalizando o seu texto de ligação:

**Formato Wikilink**:
Use uma barra vertical (`|`) para alterar o texto de apresentação.

- `[[Exemplo|Nome personalizado]]` aparece como [[Exemplo|Nome personalizado]]
- `[[Exemplo#Detalhes|Nome da secção]]` aparece como [[Exemplo#Detalhes|Nome da secção]]

**Formato Markdown**:
Use `[Texto de apresentação](URL da ligação)` para personalizar a aparência da ligação.

- `[Nome personalizado](Exemplo.md)` aparece como [Nome personalizado](Exemplo.md)
- `[Nome da secção](Exemplo.md#Detalhes)` aparece como [Nome da secção](Exemplo.md#Detalhes)

Este método é útil para situações pontuais em que pretende alterar a aparência de uma ligação num contexto específico. Se pretender configurar um nome de ligação alternativo que possa reutilizar em todo o cofre, considere usar um [[Apelidos|apelido]].

Por exemplo, se referenciar regularmente `[[Três leis do movimento]]` como `[[As 3 leis]]`, adicionar "3 leis" como apelido permite-lhe digitar apenas isso — sem necessidade de adicionar texto de apresentação personalizado de cada vez.

> [!tip] Dica
> Use o [[#Change the link display text|texto de apresentação da ligação]] quando pretender personalizar a aparência de uma ligação *num local específico*.
>
> Use [[Apelidos|apelidos]] quando pretender referenciar a mesma nota usando *nomes diferentes* em todo o cofre.
^callout-internal-links-link-text

## Pré-visualizar um ficheiro ligado

> [!note] Nota
> Para pré-visualizar ficheiros ligados, primeiro precisa de ativar a [[Pré-visualização de página]].

Para pré-visualizar um ficheiro ligado, passe o cursor sobre uma ligação interna. No modo de edição, prima `Ctrl` (ou `Cmd` no macOS) enquanto passa o cursor sobre a ligação. Aparece uma pré-visualização do conteúdo do ficheiro junto ao cursor.
