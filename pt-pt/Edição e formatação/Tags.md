---
aliases:
  - How to/Working with tags
permalink: tags
---
As etiquetas são palavras-chave ou tópicos que o ajudam a encontrar rapidamente as notas que pretende.

## Adicionar uma etiqueta a uma nota

Para criar uma etiqueta, introduza um símbolo de cardinal (`#`) no editor, seguido de uma palavra-chave. Por exemplo, `#reunião`.

Também pode adicionar etiquetas usando a [[Propriedades|propriedade]] `tags`. As etiquetas em YAML devem ser sempre formatadas como uma lista:

```yaml
---
tags:
  - receita
  - culinária
---
```

## Encontrar notas usando etiquetas

Para encontrar notas usando o plugin [[Pesquisa]], use o [[Pesquisa#Search operators|operador de pesquisa]] `tag` no seu termo de pesquisa, por exemplo `tag:#reunião`.

Também pode pesquisar etiquetas clicando nelas nas suas notas.

Para encontrar notas usando o plugin [[Vista de tags]], selecione **Etiquetas: Mostrar etiquetas** na [[Paleta de comandos]] e, em seguida, selecione a etiqueta que pretende pesquisar.

## Etiquetas aninhadas

As etiquetas aninhadas definem hierarquias de etiquetas que facilitam a localização e filtragem de etiquetas relacionadas.

Crie etiquetas aninhadas usando barras oblíquas (`/`) no nome da etiqueta, por exemplo `#entrada/para-ler` e `#entrada/em-processamento`.

- Na [[Pesquisa]], `tag:entrada` corresponderá a `#entrada` bem como a todas as etiquetas aninhadas como `#entrada/para-ler`.
- Na [[Vista de tags]], as etiquetas aninhadas são mostradas como pertencentes à etiqueta principal.
- Em [[Introdução ao Bases|Bases]], as etiquetas aninhadas são reconhecidas pela função [[Funções#hasTag|`hasTag`]], pelo que `file.hasTag("a")` corresponderá a `#a` e `#a/b`.

## Formato das etiquetas

Pode usar qualquer um dos seguintes carateres nas suas etiquetas:

- Letras do alfabeto
- Números
- Sublinhado (`_`)
- Hífen (`-`)
- Barra oblíqua (`/`) para [[#Etiquetas aninhadas]]
- Carateres Unicode amplamente aceites, incluindo emojis e outros símbolos

As etiquetas devem conter pelo menos um carácter não numérico. Por exemplo, #1984 não é uma etiqueta válida, mas #a1984 é.

As etiquetas não distinguem maiúsculas de minúsculas. Por exemplo, #etiqueta e #ETIQUETA serão tratadas como idênticas.

> [!note]
> As etiquetas serão apresentadas com as maiúsculas com que foram criadas pela primeira vez na [[Vista de tags]].
> Por exemplo, criar #Etiqueta e depois #ETIQUETA mostrará #Etiqueta para ambas.

As etiquetas não podem conter espaços em branco. Para separar duas ou mais palavras, pode usar os seguintes formatos:

- #camelCase
- #PascalCase
- #snake_case
- #kebab-case
