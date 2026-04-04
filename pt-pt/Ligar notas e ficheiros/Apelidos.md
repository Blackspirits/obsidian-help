---
aliases:
  - alias
  - aliases
  - How to/Add aliases to note
permalink: aliases
cssclasses:
  - soft-embed
---

Se pretender referenciar um ficheiro usando nomes diferentes, considere adicionar _apelidos_ à nota. Um apelido é um nome alternativo para uma nota.

Use apelidos para coisas como siglas, alcunhas, ou para referenciar uma nota noutro idioma.

Se apenas pretender alterar a aparência de uma ligação num único local, veja como [[Links internos#Change the link display text|Alterar o texto de apresentação da ligação]].

![[Links internos#^callout-internal-links-link-text]]

## Adicionar um apelido a uma nota

Para adicionar um apelido a uma nota, adicione a propriedade `aliases` nas [[Propriedades]] da nota. Os apelidos devem ser sempre formatados como uma lista em YAML.

```md
---
aliases:
  - Doggo
  - Woofer
  - Yapper
---

# Dog
```

## Ligar a uma nota usando um apelido

Para ligar a uma nota usando um apelido:

1. Comece a escrever o apelido numa [[Links internos|ligação interna]]. Qualquer apelido aparece na lista de sugestões, com um ícone de seta curva ao lado.
2. Prima `Enter` para selecionar o apelido.

O Obsidian cria a ligação com o apelido como texto de apresentação personalizado, por exemplo `[[Inteligência Artificial|IA]]`.

> [!note] Nota
> Em vez de usar apenas o apelido como destino da ligação (`[[IA]]`), o Obsidian usa o formato de ligação `[[Inteligência Artificial|IA]]` para garantir a interoperabilidade com outras aplicações que usam o formato Wikilink.

## Encontrar menções não ligadas para um apelido

Usando [[Links inversos]], pode encontrar menções não ligadas de apelidos.

Por exemplo, após definir "IA" como apelido de "Inteligência artificial", pode ver menções de "IA" noutras notas.

Se ligar uma menção não ligada a um apelido, o Obsidian transforma a menção numa [[Links internos|ligação interna]] com o apelido como texto de apresentação.
