---
permalink: plugins/search
publish: true
mobile: true
description: Search is a core plugin that helps you find data in your Obsidian vault by using search terms and operators to narrow down results.
---

A Pesquisa é um [[Plugins nativos|plugin nativo]] que o ajuda a encontrar dados no seu cofre do Obsidian usando termos de pesquisa e operadores para restringir os resultados.

Por predefinição, pode encontrar a Pesquisa na barra lateral esquerda ![[lucide-search.svg#icon]]. Também pode abrir a Pesquisa premindo `Ctrl+Shift+F` (Windows/Linux) ou `Command+Shift+F` (macOS).

- **Pesquisar texto selecionado**: Se selecionar texto no editor e abrir a Pesquisa com o atalho de teclado, a Pesquisa mostra os resultados para o texto selecionado.
- **Pesquisar termos recentes**: Abra a Pesquisa com um termo de pesquisa vazio para listar os termos de pesquisa recentes. Clique em qualquer um deles para usar o termo de pesquisa novamente.

> [!info] Ficheiros excluídos
> Os ficheiros que correspondam aos seus padrões de [[Configurações#Excluded files|Ficheiros excluídos]] não aparecerão nos resultados da Pesquisa.

## Termos de pesquisa

Um termo de pesquisa é a palavra ou frase que introduz no campo de pesquisa. Aprender a escrever termos de pesquisa eficazmente pode ajudá-lo a encontrar rapidamente o que procura, mesmo em cofres grandes. O Obsidian pesquisa apenas o conteúdo de notas e canvas.

> [!tip]- Pesquisar caminhos e nomes de ficheiros
> Por predefinição, só pode pesquisar os caminhos e nomes de ficheiros de notas e canvas. Para pesquisar o caminho ou nome de ficheiro de qualquer ficheiro no cofre, use o operador `path` ou `file`.

Cada palavra no termo de pesquisa é correspondida independentemente em cada ficheiro. Para pesquisar uma frase exata, coloque-a entre aspas, por exemplo `"star wars"`. Para pesquisar texto entre aspas dentro de uma frase exata, pode _escapar_ as aspas adicionando uma barra invertida (`\`) antes das aspas, por exemplo `"eles disseram \"olá\" um ao outro"`.

Pode controlar se devem ser devolvidos ficheiros que contêm _todas_ as palavras do seu termo de pesquisa ou _qualquer uma_ das palavras:

- `reunião trabalho` devolve ficheiros que contêm `reunião` e `trabalho`.
- `reunião OR trabalho` devolve ficheiros que contêm `reunião` ou `trabalho`.

Pode até combinar os dois no mesmo termo de pesquisa.

- `reunião trabalho OR encontro pessoal` devolve ficheiros para reuniões de trabalho e encontros pessoais.

Pode usar parênteses para controlar a prioridade de cada expressão.

- `reunião (trabalho OR encontro) pessoal` devolve ficheiros que contêm `reunião`, `pessoal` e `trabalho` ou `encontro`.

Para excluir, ou negar, uma palavra dos resultados da pesquisa, adicione um hífen (`-`) antes dela:

- `reunião -trabalho` devolve ficheiros que contêm `reunião` mas não `trabalho`.

Pode excluir várias expressões:

- `reunião -trabalho -encontro` devolve ficheiros que contêm `reunião` mas não `trabalho` nem `encontro`.

Pode excluir uma combinação de expressões usando parênteses:

- `reunião -(trabalho encontro)` devolve ficheiros que contêm `reunião` mas não _ambos_ `trabalho` e `encontro`.

Para filtrar resultados usando os operadores menor que (`<`) e maior que (`>`), coloque-os entre parênteses retos (`[]`) ou aspas (`""`):

- `reunião [duração:<5]` devolve ficheiros onde reunião está presente e a duração é menor que 5.
- `reunião [duração:>5]` devolve ficheiros onde reunião está presente e a duração é maior que 5.

> [!tip]- Explicar termo de pesquisa
> Se precisar de resolver um termo de pesquisa complexo, pode clicar em **Explicar termo de pesquisa** na Pesquisa para obter uma explicação do seu termo de pesquisa.

## Operadores de pesquisa

Os operadores de pesquisa permitem termos de pesquisa mais detalhados para filtrar os resultados ainda mais.

Alguns operadores permitem até adicionar um termo de pesquisa aninhado entre parênteses, por exemplo: `task:(ligar OR email)`.

| Operador de pesquisa | Descrição                                                                                                                                                                                                                                                                                                                              |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `file:`              | Encontrar texto no nome do ficheiro. Corresponde a qualquer ficheiro no cofre.<p/>Exemplo: `file:.jpg` ou `file:202209`.                                                                                                                                                                                                               |
| `path:`              | Encontrar texto no caminho do ficheiro. Corresponde a qualquer ficheiro no cofre.<p/>Exemplo: `path:"Notas diárias/2022-07"`.                                                                                                                                                                                                          |
| `content:`           | Encontrar texto no conteúdo do ficheiro.<p/>Exemplo: `content:"gato feliz"`.                                                                                                                                                                                                                                                           |
| `match-case:`        | Correspondência sensível a maiúsculas/minúsculas.<p/>Exemplo: `match-case:GatoFeliz`.                                                                                                                                                                                                                                                  |
| `ignore-case:`       | Correspondência insensível a maiúsculas/minúsculas.<p/>Exemplo: `ignore-case:ikea`.                                                                                                                                                                                                                                                    |
| `tag:`               | Encontrar tag no ficheiro.<p/>Exemplo: `tag:#trabalho`.<p/>Tenha em mente que pesquisar `tag:#trabalho` não devolverá resultados para `#meuprojeto/trabalho`.<br /><br />**Nota**: Como `tag:` ignora correspondências em blocos de código e em conteúdo não Markdown, é frequentemente mais rápido e preciso do que uma pesquisa de texto completo por `#trabalho`. |
| `line:`              | Encontrar ficheiros que contenham pelo menos uma linha correspondente a `x`.<p/>Exemplo: `line:(misturar farinha)`.<p/><br>**Nota:** Usar `-line` nega a pesquisa, o que significa que encontrará ficheiros onde nenhuma linha corresponde a `x`.                                                                                       |
| `block:`             | Encontrar correspondências no mesmo bloco.<p/>Exemplo: `block:(cão gato)`.<p/>**Nota**: Como `block:` exige que a Pesquisa analise o conteúdo Markdown em cada ficheiro, pode fazer com que o seu termo de pesquisa demore mais tempo a concluir.                                                                                      |
| `section:`           | Encontrar correspondências na mesma secção (texto entre dois cabeçalhos).<p/>Exemplo: `section:(cão gato)`.                                                                                                                                                                                                                            |
| `task:`              | Encontrar correspondências numa [[Sintaxe de formatação básica#Task lists\|tarefa]] bloco a bloco.<p/>Exemplo: `task:ligar`.                                                                                                                                                                                                           |
| `task-todo:`         | Encontrar correspondências numa [[Sintaxe de formatação básica#Task lists\|tarefa]] *incompleta* bloco a bloco.<p/>Exemplo: `task-todo:ligar`.                                                                                                                                                                                         |
| `task-done:`         | Encontrar correspondências numa [[Sintaxe de formatação básica#Task lists\|tarefa]] *concluída* bloco a bloco.<p/>Exemplo: `task-done:ligar`.                                                                                                                                                                                          |

## Pesquisar propriedades

Pode usar dados armazenados em [[Propriedades]] nos seus termos de pesquisa.

Use parênteses retos em torno do nome de uma propriedade `[propriedade]` para devolver ficheiros com essa propriedade:

- `[aliases]` devolve ficheiros que contêm a propriedade `aliases`

Use parênteses retos e dois pontos `[propriedade:valor]` para devolver ficheiros com essa propriedade e valor:

- `[aliases:Nome]` devolve ficheiros onde o valor da propriedade `aliases` é `Nome`

Use `null` como valor para encontrar propriedades sem valor:

- `[aliases:null]` devolve ficheiros onde a propriedade `aliases` existe mas não tem valor

> [!info]+ Valores vazios
> O operador `null` funciona quando uma propriedade está vazia (por exemplo, `aliases: `), mas não quando a propriedade contém aspas vazias (`""`) ou parênteses retos vazios (`[]`).

Tanto a propriedade como o valor permitem subconsultas, tais como parênteses para agrupamento, o operador `OR`, aspas duplas para correspondência exata e expressões regulares.

- `[status:Rascunho OR Publicado]` devolve ficheiros onde o valor da propriedade `status` é `Rascunho` ou `Publicado`

## Alterar sensibilidade a maiúsculas/minúsculas

Por predefinição, os termos de pesquisa não são sensíveis a maiúsculas/minúsculas. Se pretender pesquisar com a capitalização exata do seu termo de pesquisa, selecione **Corresponder capitalização** ![[obsidian-icon-upper-lowercase.svg#icon]] dentro da barra de pesquisa.

Esta definição pode ser alternada. Se o ícone **Corresponder capitalização** estiver realçado, significa que está atualmente a fazer uma pesquisa sensível a maiúsculas/minúsculas.

## Alterar a ordem de ordenação dos resultados

1. Introduza um [[#Termos de pesquisa|termo de pesquisa]].
2. Abaixo do campo de pesquisa, selecione a lista pendente à direita.
3. Selecione a ordem de ordenação que pretende. A predefinição é "Nome do ficheiro (A a Z)".

Estão disponíveis as seguintes opções:

- Nome do ficheiro (A a Z)
- Nome do ficheiro (Z a A)
- Data de modificação (mais recente primeiro)
- Data de modificação (mais antiga primeiro)
- Data de criação (mais recente primeiro)
- Data de criação (mais antiga primeiro)

## Copiar resultados da pesquisa

1. Introduza um [[#Termos de pesquisa|termo de pesquisa]].
2. Abaixo do campo de pesquisa, selecione o ícone dos três pontos junto ao número de resultados.
3. Selecione **Copiar resultados da pesquisa**.

## Usar expressões regulares

Uma expressão regular é um conjunto de caracteres que descreve um padrão de texto. Para usar expressões regulares no seu termo de pesquisa, coloque a expressão entre barras oblíquas (`/`).

- `/\d{4}-\d{2}-\d{2}/` corresponde a uma data ISO 8601, como 2022-01-01.

Pode até combinar expressões regulares com operadores de pesquisa:

- `path:/\d{4}-\d{2}-\d{2}/` devolve ficheiros com uma data no caminho do ficheiro.

Para mais informações sobre como escrever expressões regulares, consulte o [Guia Prático de Regex](https://www.freecodecamp.org/news/practical-regex-guide-with-real-life-examples/) do FreeCodeCamp ou as [Expressões regulares](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) da Mozilla.

> [!info]+ Expressões regulares com sabor JavaScript
> As expressões regulares existem em diferentes variantes que podem parecer diferentes entre si. O Obsidian usa expressões regulares com sabor JavaScript.

## Configurar definições da pesquisa

Para configurar a Pesquisa, selecione **Definições da pesquisa** ![[lucide-sliders-horizontal.svg#icon]] no lado direito da barra de pesquisa para ver os botões de alternância.

| Definição                   | Descrição                                                                         |
|-----------------------------|-----------------------------------------------------------------------------------|
| **Explicar termo de pesquisa** | Decompõe os termos de pesquisa e explica-os em texto simples.                  |
| **Recolher resultados**     | Alterna entre mostrar ou ocultar o contexto da pesquisa.                          |
| **Mostrar mais contexto**   | Expande o resultado da pesquisa para mostrar mais texto em torno da correspondência. |

## Incorporar resultados de pesquisa numa nota

Para incorporar resultados de pesquisa numa nota, adicione um bloco de código `query`:

````
```query
embed OR search
```
````

O [[Introdução ao Obsidian Publish|Obsidian Publish]] não suporta [[Limitações do Publish#Search|resultados de pesquisa]] incorporados. Para ver um exemplo renderizado ao vivo, use o bloco de código acima no seu cofre.

![[search-query-rendered.png]]
