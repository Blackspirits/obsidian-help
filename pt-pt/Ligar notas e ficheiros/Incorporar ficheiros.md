---
aliases:
  - How to/Embed files
  - Linking notes and files/Embedding files
cssclasses:
  - soft-embed
permalink: embeds
---

Aprenda como pode incorporar outras notas e multimédia nas suas notas. Ao incorporar ficheiros nas suas notas, pode reutilizar conteúdo em todo o seu cofre.

Para incorporar um ficheiro no seu cofre, adicione um ponto de exclamação (`!`) antes de uma [[Links internos|Ligação interna]]. Pode incorporar ficheiros em qualquer um dos [[Formatos de ficheiro aceites]].

> [!tip] Incorporar com arrastar e largar
> No computador, também pode arrastar e largar ficheiros suportados diretamente na sua nota para os incorporar automaticamente.

## Incorporar uma nota noutra nota

Para incorporar uma nota:

```md
![[Links internos]]
```

Também pode incorporar ligações para [[Links internos#Link to a heading in a note|cabeçalhos]] e [[Links internos#Link to a block in a note|blocos]].

```md
![[Links internos#^b15695]]
```

O texto abaixo é um exemplo de um bloco incorporado:

![[Links internos#^b15695]]

## Incorporar uma imagem numa nota

Para incorporar uma imagem:

```md
![[Engelbart.jpg]]
```

![[Engelbart.jpg#outline]]

Pode alterar as dimensões da imagem adicionando `|640x480` ao destino da ligação, onde 640 é a largura e 480 é a altura.

```md
![[Engelbart.jpg|100x145]]
```

Se especificar apenas a largura, a imagem é dimensionada de acordo com a sua proporção original. Por exemplo, `![[Engelbart.jpg|100]]`.

![[Engelbart.jpg#outline|100]]

Também pode incorporar uma imagem alojada externamente usando uma ligação markdown. Pode controlar a largura e a altura da mesma forma que com uma wikilink.

```md
![250](https://publish-01.obsidian.md/access/f786db9fac45774fa4f0d8112e232d67/Attachments/Engelbart.jpg)
```

![250](https://publish-01.obsidian.md/access/f786db9fac45774fa4f0d8112e232d67/Attachments/Engelbart.jpg)

## Incorporar um ficheiro de áudio numa nota

Para incorporar um ficheiro de áudio:

```md
![[Excerpt from Mother of All Demos (1968).ogg]]
```

![[Excerpt from Mother of All Demos (1968).ogg]]

## Incorporar um PDF numa nota

Para incorporar um PDF:

```md
![[Document.pdf]]
```

Também pode abrir uma página específica do PDF adicionando `#page=N` ao destino da ligação, onde `N` é o número da página:

```md
![[Document.pdf#page=3]]
```

Também pode especificar a altura em píxeis para o visualizador de PDF incorporado, adicionando `#height=[número]` à ligação. Por exemplo:

```md
![[Document.pdf#height=400]]
```

## Incorporar uma lista numa nota

Para incorporar uma lista de uma nota diferente, primeiro adicione um [[Links internos#Link to a block in a note|identificador de bloco]] à sua lista:

```md

- item de lista 1
- item de lista 2

^my-list-id
```

Depois ligue à lista usando o identificador de bloco:

```md
![[A minha nota#^my-list-id]]
```

## Incorporar resultados de pesquisa

![[Pesquisa#Embed search results in a note]]
