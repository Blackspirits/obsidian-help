---
permalink: bases/views
---
As vistas permitem-lhe organizar a informação de uma [[Introdução ao Bases|Base]] de múltiplas formas. Uma base pode conter várias vistas, e cada vista pode ter uma configuração única para apresentar, ordenar e filtrar ficheiros.

Por exemplo, pode criar uma base chamada "Livros" com vistas separadas para "Lista de leitura" e "Lidos recentemente".

## Barra de ferramentas

No topo de uma base existe uma barra de ferramentas que lhe permite interagir com as vistas e os seus resultados.

- ![[lucide-table.svg#icon]] **Menu de vistas** — criar, editar e alternar vistas.
- **Resultados** — limitar, copiar e exportar ficheiros.
- ![[lucide-arrow-up-down.svg#icon]] **Ordenar** — ordenar e agrupar ficheiros.
- ![[lucide-list-filter.svg#icon]] **Filtrar** — filtrar ficheiros.
- ![[lucide-list.svg#icon]] **Propriedades** — escolher propriedades a apresentar e criar [[Fórmulas]].
- ![[lucide-search.svg#icon]] **Pesquisar** — pesquisar itens pelas suas propriedades apresentadas.
- ![[lucide-plus.svg#icon]] **Novo** — criar um novo ficheiro na vista atual.

## Adicionar e alternar vistas

Existem duas formas de adicionar uma vista a uma base:

- Clique no nome da vista no canto superior esquerdo e selecione ![[lucide-plus.svg#icon]] **Adicionar vista**.
- Use a [[Paleta de comandos]] e selecione **Bases: Adicionar vista**.

A primeira vista da lista carrega por predefinição. Arraste as vistas pelo ícone para alterar a sua ordem.

## Definições de vista

Cada vista tem as suas próprias opções de configuração. Para editar as definições de uma vista:

1. Clique no nome da vista no canto superior esquerdo.
2. Clique na seta para a direita ao lado da vista que pretende configurar.

Em alternativa, clique com o botão direito no nome da vista na barra de ferramentas da base para aceder rapidamente às definições da vista.

## Esquema

As vistas podem ser apresentadas com diferentes esquemas, incluindo ![[lucide-table.svg#icon]] **tabela**, ![[lucide-list.svg#icon]] **lista**, ![[lucide-layout-grid.svg#icon]] **cartões** e ![[lucide-map.svg#icon]] **mapa**. Esquemas adicionais podem ser adicionados por [[Plugins da comunidade]]. Alguns esquemas ainda estão em desenvolvimento e requerem [[Versões de acesso antecipado]] do Obsidian.

| Esquema                    | Descrição                                                                                          | Versão&nbsp;app |
| -------------------------- | -------------------------------------------------------------------------------------------------- | --------------- |
| [[Table view\|Tabela]]     | Apresenta ficheiros como linhas numa tabela. As colunas são preenchidas com [[Propriedades]] das suas notas. | 1.9             |
| [[Cards view\|Cartões]]    | Apresenta ficheiros como uma grelha de cartões. Permite criar vistas de galeria com imagens.       | 1.9             |
| [[List view\|Lista]]       | Apresenta ficheiros como uma [[Sintaxe de formatação básica#Lists\|lista]] com marcadores ou numeração. | 1.10            |
| [[Map view\|Mapa]]         | Apresenta ficheiros como marcadores num mapa interativo. Requer o plugin Mapas.                    | 1.10            |

## Filtros

Abra o menu ![[lucide-list-filter.svg#icon]] **Filtrar** no topo de uma base para adicionar filtros.

Uma base sem filtros mostra todos os ficheiros do seu cofre. Os filtros restringem os resultados para mostrar apenas ficheiros que cumprem critérios específicos. Por exemplo, pode usar filtros para apresentar apenas ficheiros com uma determinada [[Tags|etiqueta]] ou dentro de uma pasta específica. Existem muitos tipos de filtros disponíveis.

Os filtros podem ser aplicados a todas as vistas de uma base, ou apenas a uma única vista, escolhendo nas duas secções do menu ![[lucide-list-filter.svg#icon]] **Filtrar**.

- **Todas as vistas** aplica filtros a todas as vistas da base.
- **Esta vista** aplica filtros à vista ativa.

#### Componentes de um filtro

Os filtros têm três componentes:

1. **Propriedade** — permite escolher uma [[Propriedades|propriedade]] do seu cofre, incluindo [[Sintaxe de Bases#File properties|propriedades de ficheiro]].
2. **Operador** — permite escolher como comparar as condições. A lista de operadores disponíveis depende do tipo de propriedade (texto, data, número, etc.)
3. **Valor** — permite escolher o valor com que está a comparar. Os valores podem incluir expressões matemáticas e [[Funções|funções]].

#### Conjunções

- **Todas as seguintes são verdadeiras** é uma instrução `and` — os resultados só são mostrados se *todas* as condições do grupo de filtros forem cumpridas.
- **Qualquer das seguintes é verdadeira** é uma instrução `or` — os resultados são mostrados se *alguma* das condições do grupo de filtros for cumprida.
- **Nenhuma das seguintes é verdadeira** é uma instrução `not` — os resultados não são mostrados se *alguma* das condições do grupo de filtros for cumprida.

#### Grupos de filtros

Os grupos de filtros permitem criar lógica mais complexa através de combinações de conjunções.

#### Editor de filtros avançado

Clique no botão de código ![[lucide-code-xml.svg#icon]] para utilizar o editor de **filtros avançado**. Este apresenta a [[Sintaxe de Bases|sintaxe]] em bruto do filtro e pode ser usado com [[Funções|funções]] mais complexas que não podem ser apresentadas na interface de ponto e clique.

## Ordenar e agrupar resultados

Abra o menu ![[lucide-arrow-up-down.svg#icon]] **Ordenar** para ordenar e agrupar os resultados de uma vista.

Pode organizar os resultados por uma ou mais propriedades em ordem ascendente ou descendente. Isto facilita a listagem de notas por nome, hora da última edição ou qualquer outra propriedade — incluindo fórmulas.

Também pode agrupar resultados por uma propriedade para organizar itens semelhantes em secções visualmente distintas. Atualmente, o Obsidian suporta agrupamento por apenas uma propriedade.

### Adicionar uma ordenação

1. Abra o menu ![[lucide-arrow-up-down.svg#icon]] **Ordenar** no topo da vista.
2. Escolha a propriedade pela qual pretende ordenar (ou agrupar).
3. Se tiver múltiplas ordenações, arraste-as para cima ou para baixo usando a pega ![[lucide-grip-vertical.svg#icon]] para alterar a sua prioridade.

As opções de ordenação dos resultados dependem do tipo de propriedade:

- **Texto**: ordenar *alfabeticamente* (A→Z) ou em *ordem alfabética inversa* (Z→A).
- **Número**: ordenar do *menor para o maior* (0→1) ou do *maior para o menor* (1→0).
- **Data e hora**: ordenar do *mais antigo para o mais recente* ou do *mais recente para o mais antigo*.

### Remover uma ordenação

1. Abra o menu ![[lucide-arrow-up-down.svg#icon]] **Ordenar** no topo da vista.
2. Clique no botão do caixote do lixo ![[lucide-trash-2.svg#icon]] ao lado da ordenação ou agrupamento que pretende remover.

## Limitar, copiar e exportar resultados

### Limitar resultados

O menu *resultados* mostra o número de resultados na vista. Clique no botão de resultados para limitar o número de resultados e aceder a ações adicionais.

### Copiar para a área de transferência

Esta ação copia a vista para a sua área de transferência. Uma vez na área de transferência, pode colá-la num ficheiro Markdown ou noutras aplicações de documentos, incluindo folhas de cálculo como Google Sheets, Excel e Numbers.

### Exportar CSV

Esta ação guarda um CSV da sua vista atual.

## Incorporar uma vista

Pode incorporar ficheiros de base em [[Incorporar ficheiros|qualquer outro ficheiro]] usando a sintaxe `![[Ficheiro.base]]`. A primeira vista da lista será utilizada. Pode alterar a ordem arrastando as vistas no menu de vistas.

Para especificar a vista predefinida para uma incorporação, use `![[Ficheiro.base#Vista]]`.
