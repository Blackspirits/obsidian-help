---
aliases:
  - front matter
  - Advanced topics/YAML front matter
  - metadata
  - property
  - frontmatter
cssclasses:
  - soft-embed
description: As propriedades permitem-lhe organizar informações sobre uma nota. As propriedades contêm dados estruturados como texto, ligações, datas, caixas de verificação e números.
mobile: false
permalink: properties
publish: true
---

As propriedades permitem-lhe organizar informações sobre uma nota. As propriedades contêm dados estruturados como texto, ligações, datas, caixas de verificação e números. As propriedades também podem ser usadas em combinação com [[Plugins da comunidade]] que podem fazer coisas úteis com os seus dados estruturados.

## Adicionar propriedades a uma nota

Existem várias formas de adicionar uma propriedade a uma nota:

- Use o [[Paleta de comandos|comando]] **Adicionar propriedade de ficheiro**.
- Use a [[Teclas de atalho|tecla de atalho]] **`Cmd/Ctrl+;`**.
- Escolha **Adicionar propriedade de ficheiro** no menu **Mais ações** (ativado pelo ícone de três pontos ou clicando com o botão direito no separador).
- Digite `---` no início de um ficheiro.

Depois de adicionar uma propriedade, aparecerá uma linha no topo do ficheiro com duas entradas: o _nome_ da propriedade e o _valor_ da propriedade.

Para o nome, pode escolher o que quiser. O Obsidian fornece várias propriedades predefinidas: `tags`, `cssclasses` e `aliases`.

Depois de escolher o nome da propriedade, pode dar-lhe um valor.

### Tipos de propriedade

Para além de um nome e valor, as propriedades também têm um _tipo_. O tipo de uma propriedade determina que tipo de valores pode armazenar e como o Obsidian as trata. Para alterar o tipo de uma propriedade, clique no ícone de tipo ao lado do nome da propriedade e selecione uma opção diferente. Também pode gerir tipos de propriedades usando o plugin principal [[Vista de propriedades]].

O Obsidian suporta os seguintes tipos de propriedade:

- **[[#Text|Texto]]**
- **[[#List|Lista]]**
- **[[#Number|Número]]**
- **[[#Checkbox|Caixa de verificação]]**
- **[[#Date|Data]]**
- **[[#Date & time|Data e hora]]**
- **[[#Tags|Etiquetas]]**

Depois de um tipo de propriedade ser atribuído a um nome de propriedade, todas as propriedades com esse nome em todo o seu cofre usarão o mesmo tipo.

## Usos avançados

### Pesquisar propriedades

As propriedades têm a sua própria [[Pesquisa|sintaxe de pesquisa]] que pode usar juntamente com outros termos e operadores de pesquisa. [[Pesquisa#Search properties|Consulte a sintaxe de pesquisa para propriedades]].

### Modelos

Pode adicionar propriedades a [[Plugins/Modelos|Modelos]].

Quando insere um modelo na nota ativa, todas as propriedades do modelo serão adicionadas à nota. O Obsidian também fundirá quaisquer propriedades que existam na sua nota com as propriedades do modelo. ^templates-properties

### Renomear propriedades

Pode renomear uma propriedade clicando com o botão direito nela na [[Vista de propriedades|Vista de todas as propriedades]].

### Modos de apresentação

Pode alterar como as propriedades são apresentadas na sua nota indo a **[[Configurações]] → Editor → Propriedades no documento**. As opções são:

- **Visível** (predefinição) — apresenta as propriedades no topo da nota, se existirem.
- **Oculto** — oculta as propriedades; ainda podem ser apresentadas na barra lateral via [[Vista de propriedades]].
- **Código-fonte** — apresenta as propriedades em formato YAML de texto simples.

### Fragmentos CSS

Pode usar [[Fragmentos CSS]] para alterar a aparência de notas específicas.

### Não suportado

Algumas funcionalidades não são atualmente suportadas no Obsidian:

- **Propriedades aninhadas**: Para ver propriedades aninhadas, recomendamos usar o [[Vistas e modo de edição#Source mode|modo de código-fonte]].
- **Edição em massa de propriedades**: Para edição em massa detalhada fora da [[Vista de propriedades]], recomendamos usar ferramentas de edição em massa como VSCode, scripts e plugins da comunidade.
- **Markdown em propriedades**: Esta é uma limitação intencional, pois as propriedades destinam-se a pequenas unidades atómicas de informação que são legíveis tanto por humanos como por máquinas.

## Teclas de atalho

### Adicionar uma propriedade

| Ação | Atalho |
|---|---|
| Adicionar nova propriedade | `Cmd + ;` |

### Navegar entre propriedades

Quando uma propriedade está focada

| Ação | Atalho |
|---|---|
| Focar a próxima propriedade | `Seta para baixo` ou `Tab` |
| Focar a propriedade anterior | `Seta para cima` ou `Shift+Tab` |
| Saltar para o editor | `Alt+Seta para baixo` |

### Selecionar propriedades

| Ação | Atalho |
|---|---|
| Expandir seleção para cima | `Shift+Seta para cima` |
| Expandir seleção para baixo | `Shift+Seta para baixo` |
| Selecionar tudo | `Cmd+A` |

### Editar propriedades

| Ação | Atalho |
|---|---|
| Editar nome da propriedade | `Seta para a esquerda` |
| Editar valor da propriedade | `Seta para a direita` |
| Focar propriedade | `Escape` |
| Eliminar propriedade | `Cmd+Backspace`<br><br>se alguma propriedade estiver selecionada, eliminará a seleção em vez disso. |
| Desfazer | `Cmd+Z` |
| Refazer | `Cmd+Shift+Z` |

### Vim (avançado)

| Ação | Atalho |
|---|---|
| Mover para baixo | `j` |
| Mover para cima | `k` |
| Focar chave | `h` |
| Focar valor | `l` |
| Focar valor (cursor no fim) | `A` |
| Focar valor (cursor no início) | `i` |
| Criar nova propriedade | `o` |

## Formato de propriedade

As propriedades são armazenadas no formato [YAML](https://yaml.org/) no topo do ficheiro. YAML é um formato popular que é fácil de ler tanto por humanos como por computadores.

Os nomes de propriedades são separados dos seus valores por dois pontos seguidos de um espaço:

```yaml
---
name: value
---
```

Embora a ordem de cada par nome-valor não importe, cada nome deve ser único numa nota. Por exemplo, não pode ter mais do que uma propriedade `tags`.

Os valores podem ser [[#Text|texto]], [[#Number|números]], [[#Checkbox|caixas de verificação]], [[#Date|datas]], [[#Date & time|datas e horas]] ou [[#List|listas]].

### Texto

As propriedades de texto contêm uma única linha de texto. A formatação Markdown não é renderizada em propriedades de texto. Os hashtags não criam etiquetas quando usados em propriedades de texto.

As propriedades de texto podem conter URLs e [[Links internos]] usando a sintaxe `[[Link]]`. Os [[Links internos]] em propriedades de texto devem ser rodeados por aspas. O Obsidian adiciona-as automaticamente se introduzir manualmente ligações internas nas propriedades, mas tenha cuidado ao adicioná-las quando usar plugins de modelos.

```yaml
---
title: A New Hope
link: "[[Episode IV]]"
url: https://www.example.com
---
```

### Lista

As propriedades de lista contêm múltiplos valores. Cada valor numa lista aparece na sua própria linha, precedido por um hífen (-) e um espaço.

Os valores de lista podem conter texto, números e [[Links internos]]. Ao usar [[Links internos]] em propriedades de lista, rodeie-os com aspas.

```yaml
---
cast:
  - Mark Hamill
  - Harrison Ford
  - Carrie Fisher
links:
  - "[[Link]]"
  - "[[Link2]]"
---
```

### Número

As propriedades do tipo número devem ser sempre um número literal, não uma expressão com operadores. São permitidos inteiros e decimais.

```yaml
---
year: 1977
pie: 3.14
---
```

### Caixa de verificação

As propriedades de caixa de verificação são `true` ou `false`. No Live Preview, são apresentadas como uma caixa de verificação.

```yaml
---
favorite: true
reply: false
last: # Valor indeterminado; frequentemente tratado como false
```

### Data

As propriedades de data são armazenadas no seguinte formato:

```yaml
---
date: 2020-08-21
---
```

O seletor de data segue o formato de data e hora predefinido do seu sistema operativo. Pode alterá-lo nas preferências do sistema:

> [!info]- Windows
> **[[Configurações]] → Hora e idioma → Idioma e região → Formato regional → Alterar formatos**
>
> ![[Windows-OS-DateTime.png#interface]]

> [!info]- Mac OS
> **Preferências do sistema → Idioma e região → Formato de data**
>
> ![[Mac-OS-DateTime.png|450]]

Com o plugin [[Notas diárias]] ativado, a propriedade de data funcionará adicionalmente como uma ligação interna para a nota diária correspondente dessa data.

![[Notas diárias#^daily-notes-date]]

### Data e hora

As propriedades de data e hora incluem tanto uma data como uma hora específica, armazenadas no seguinte formato:

```yaml
---
time: 2020-08-21T10:30:00
---
```

Tal como as [[#Date|propriedades de data]], o seletor de data e hora segue o formato predefinido do seu sistema operativo. Pode alterá-lo nas preferências do sistema.

### Etiquetas

As propriedades de etiquetas são um tipo especial de propriedade usado exclusivamente pela propriedade `tags`. Este tipo de propriedade não pode ser atribuído a outras propriedades.

As propriedades de etiquetas são formatadas como uma lista, com cada etiqueta na sua própria linha precedida por um hífen (-) e um espaço.

```yaml
---
tags:
  - diário
  - pessoal
  - rascunho
---
```

A propriedade `tags` é uma das [[#Default properties|propriedades predefinidas]] do Obsidian. Consulte [[Tags]] para mais informações sobre o uso de etiquetas no Obsidian.

### Propriedades JSON

Embora recomendemos usar YAML para definir propriedades, também pode definir propriedades usando [JSON](https://www.json.org/):

```json
---
{
  "tags": ["journal"],
  "publish": false
}
---
```

Note que o bloco JSON será lido, interpretado e guardado como YAML.

## Propriedades predefinidas

O Obsidian vem com um conjunto de propriedades predefinidas:

| Propriedade  | Tipo  | Descrição                                                          |
| ------------ | ----- | ------------------------------------------------------------------ |
| `tags`       | Lista | Consulte [[Editing and formatting/Tags\|Etiquetas]].              |
| `aliases`    | Lista | Consulte [[Apelidos]].                                             |
| `cssclasses` | Lista | Permite estilizar notas individuais usando [[Fragmentos CSS]].     |

### Propriedades para o Obsidian Publish

As seguintes propriedades predefinidas podem ser usadas com o [[Introdução ao Obsidian Publish|Obsidian Publish]]:

| Propriedade   | Descrição                                                                                                           |
| ------------- | ------------------------------------------------------------------------------------------------------------------- |
| `publish`     | Consulte [[Publicar o seu conteúdo#Automatically select data to publish\|Selecionar automaticamente dados a publicar]]. |
| `permalink`   | Consulte [[Permalinks\|Permalinks]].                                                                                |
| `description` | Consulte [[Pré-visualizações de links em redes sociais#Description\|Descrição]].                                    |
| `image`       | Consulte [[Pré-visualizações de links em redes sociais#Image\|Imagem]].                                             |
| `cover`       | Consulte [[Pré-visualizações de links em redes sociais#Image\|Imagem]].                                             |

### Propriedades descontinuadas

Estas propriedades foram descontinuadas no Obsidian 1.4 e devem ser substituídas pelos seus equivalentes modernos. O suporte como [[#Default properties|propriedades predefinidas]] foi removido no Obsidian 1.9.

| Propriedade | Descrição |
|-|-|
| `tag` | Alias descontinuado de `tags`. |
| `alias` | Alias descontinuado de `aliases`. |
| `cssclass` | Alias descontinuado de `cssclasses`. |

> [!tip] Se precisar de converter os ficheiros do seu cofre para o formato de [[#Default properties|propriedades predefinidas]], pode usar o [[Conversor de formato]] para alterar o seu cofre em massa.
