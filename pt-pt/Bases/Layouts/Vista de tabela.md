---
permalink: bases/views/table
---
Tabela é um tipo de [[Vistas|vista]] que pode usar em [[Introdução ao Bases|Bases]].

Selecione ![[lucide-table.svg#icon]] **Table** no menu de vistas para apresentar ficheiros numa tabela com uma linha por ficheiro e colunas para as [[Propriedades]] desse ficheiro.

![Exemplo de uma base com uma vista de tabela com uma lista de livros](bases-noshadow.png#interface)

## Definições

As definições da vista de tabela podem ser configuradas nas [[Vistas#View settings|definições de vista]].

### Altura da linha

A altura da linha permite apresentar mais informação. Escolha entre **short**, **medium**, **tall** e **extra tall**.

## Resumos

Pode adicionar resumos a uma coluna da tabela para calcular rapidamente valores como totais, médias ou contagens para as linhas atualmente visíveis na vista.

Os resumos estão associados à vista, não à base. Cada vista pode mostrar resumos diferentes para a mesma coluna.

### Adicionar um resumo

1. Clique com o botão direito no cabeçalho da coluna numa vista de tabela.
2. Selecione ![[lucide-calculator.svg#icon]] **Summarize…**.
3. Escolha uma das funções de resumo incorporadas, ou selecione ![[lucide-square-function.svg#icon]] **Add summary** para definir a sua própria.

O resumo aparece na parte inferior da coluna. Quando os resultados estão [[Vistas#Sort and group results|agrupados]], o resumo de cada grupo é apresentado no topo do grupo.

Após adicionar a barra de resumo, pode adicionar mais resumos para outras colunas clicando na célula de resumo. A barra de resumo fica oculta se todos os resumos forem removidos.

### Resumos incorporados

Os seguintes resumos estão disponíveis por predefinição. As opções podem variar consoante o tipo de propriedade.

#### Todos os tipos de propriedade

- **Empty**: contagem de linhas sem valor.
- **Filled**: contagem de linhas com valor.
- **Unique**: número de valores distintos.

#### Números

- **Average**: média de todos os valores numéricos.
- **Max**: maior valor.
- **Median**: valor mediano.
- **Min**: menor valor.
- **Range**: diferença entre o máximo e o mínimo.
- **Stddev**: desvio padrão.
- **Sum**: total de todos os valores.

#### Datas

- **Earliest**: a data mais antiga.
- **Latest**: a data mais recente.
- **Range**: diferença entre a mais antiga e a mais recente.

#### Caixa de verificação

- **Checked**: número de linhas com a caixa marcada.
- **Unchecked**: número de linhas com a caixa desmarcada.

### Resumos personalizados

Pode definir o seu próprio resumo usando uma fórmula:

1. No menu ![[lucide-calculator.svg#icon]] **Summarize…**, escolha ![[lucide-square-function.svg#icon]] **Add summary**.
2. Dê um nome ao resumo.
3. Introduza uma fórmula. A fórmula é executada sobre a lista de valores dessa coluna (por exemplo, usando uma [[Funções|função]] como `values.reduce(...)`).
4. Guarde o resumo.

Os resumos personalizados são úteis quando precisa de um cálculo que não está disponível nas opções incorporadas.

## Atalhos

Pode navegar rapidamente numa vista de tabela usando o rato e os [[Atalhos de edição|atalhos de teclado]] seguintes.

- Shift+clique cria uma seleção de células.
- Clique com o botão direito numa seleção de células para aceder a ações adicionais para esses ficheiros.

| Ação                                                                                                                             | Atalho              | macOS              |
| -------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ------------------ |
| Copiar as células selecionadas                                                                                                   | `Ctrl+C`            | `Cmd+C`            |
| Colar as células selecionadas                                                                                                    | `Ctrl+V`            | `Cmd+V`            |
| Desfazer alterações a propriedades                                                                                               | `Ctrl+Z`            | `Cmd+Z`            |
| Refazer alterações a propriedades                                                                                                | `Ctrl+Shift+Z`      | `Cmd+Shift+Z`      |
| Selecionar todas as células do grupo atual                                                                                       | `Ctrl+A`            | `Cmd+A`            |
| Selecionar todas as células numa direção                                                                                         | `Ctrl+Shift+Seta`   | `Ctrl+Shift+Seta`  |
| Selecionar a coluna                                                                                                              | `Ctrl+Space`        |                    |
| Selecionar a linha                                                                                                               | `Shift+Space`       |                    |
| Focar a célula atual — para caixas de verificação, alterna o estado; para fórmulas, abre o editor de fórmulas                  | `Enter`             |                    |
| Ir para a primeira coluna                                                                                                        | `Home`              |                    |
| Ir para a última coluna                                                                                                          | `End`               |                    |
| Navegar para cima e para baixo pela altura da página                                                                             | `PageUp`,`PageDown` |                    |
| Limpar a seleção de células atual                                                                                                | `Esc`               |                    |
| Limpar as células atuais                                                                                                         | `Backspace`         |                    |
| Ir para a célula seguinte                                                                                                        | `Tab`               |                    |
| Ir para a célula anterior                                                                                                        | `Shift-Tab`         |                    |
