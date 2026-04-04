---
permalink: plugins/templates
cssclasses:
  - soft-embed
publish: true
mobile: true
description: Templates is a Core plugins|core plugin that lets you insert pre-defined snippets of text into your ative note.
---

Modelos é um [[Plugins nativos|plugin nativo]] que lhe permite inserir fragmentos de texto predefinidos na sua nota ativa.

## Definir a pasta de modelos

1. No canto inferior esquerdo, clique em **[[Configurações]]** ![[lucide-cog.svg#icon]].
2. Em **Plugins nativos → Modelos → Localização da pasta de modelos**, introduza a pasta que contém os seus modelos.

## Variáveis de modelo

Pode adicionar informações dinâmicas aos seus modelos usando _variáveis de modelo_. Quando insere um modelo que contém uma variável de modelo, o plugin Modelos substitui-a pelo valor correspondente.

| Variável    | Descrição                                              |
|-------------|--------------------------------------------------------|
| `{{title}}` | Título da nota ativa.                                  |
| `{{date}}`  | Data de hoje. **Formato predefinido:** `YYYY-MM-DD`.   |
| `{{time}}`  | Hora atual. **Formato predefinido:** `HH:mm`.          |

Tanto `{{date}}` como `{{time}}` permitem alterar o formato predefinido usando uma _cadeia de formato_.

Para definir uma cadeia de formato, adicione dois pontos (`:`) seguidos de uma cadeia de [tokens de formato do Moment.js](https://momentjs.com/docs/#/displaying/format/), por exemplo `{{date:YYYY-MM-DD}}`.

Pode usar `{{date}}` e `{{time}}` de forma intercambiável com cadeias de formato, por exemplo `{{time:YYYY-MM-DD}}`.

Pode alterar os formatos de data e hora predefinidos em **[[Configurações]] → Modelos → Formato de data** e **[[Configurações]] → Modelos → Formato de hora**. ^template-settings-date-time-formatting

> [!tip] Dica
> Também pode usar as variáveis de modelo `{{date}}` e `{{time}}` nos plugins [[Notas diárias]] e [[Criador de nota única]].

## Criar um modelo

Na [[#Definir a pasta de modelos|pasta de modelos]], [[Gerir notas#Create a new note|crie uma nota]] com o texto que pretende que apareça quando usar o modelo. Pode usar [[#Variáveis de modelo|variáveis de modelo]] para texto dinâmico como a data atual.

Por exemplo, aqui está um modelo para notas de estudo:

```markdown
---
topic: 
date: "{{date}}"
course: 
tags:
  - studies
---

# {{title}}

## Conceitos-chave


## Detalhes importantes


## Exemplos


## Questões
- 

## Resumo


## Tópicos relacionados
- [[]]
```

## Inserir um modelo na nota ativa

**Importante:** Para inserir um modelo, precisa primeiro de [[#Definir a pasta de modelos]].

1. Na faixa de opções, clique em **Inserir modelo**.
2. Selecione o modelo para inserir na posição do cursor na nota ativa.

Para inserir um modelo usando a [[Paleta de comandos]] ou [[Teclas de atalho#Set a hotkey|um atalho de teclado personalizado]], use o comando `Modelos: Inserir modelo`.

O conteúdo do modelo é inserido na posição atual do cursor. Se o cursor não estiver no corpo da nota, o conteúdo é inserido na última posição do cursor.

### Propriedades do modelo

![[Propriedades#^templates-properties]]

## Inserir a data e hora atuais na nota ativa

Use os comandos `Modelos: Inserir data atual` e `Modelos: Inserir hora atual` para inserir a data e hora atuais na posição atual do cursor. Tal como o comando `Inserir modelo`, isto pode ser feito com a [[Paleta de comandos]] ou [[Teclas de atalho#Set a hotkey|um atalho de teclado personalizado]].

A data e hora inseridas usam a [[#^template-settings-date-time-formatting|formatação definida nas definições do plugin]].
