---
permalink: plugins/graph
publish: true
mobile: true
description: Graph view is a core plugin that lets you visualize the relationships between the notes in your vault.
---
A Vista de grafo é um [[Plugins nativos|plugin nativo]] que lhe permite visualizar as relações entre as notas no seu cofre.

Para abrir a Vista de grafo, clique em **Abrir vista de grafo** na [[Faixa de opções]].

- Os círculos representam notas, ou _nós_.
- As linhas representam [[Links internos]] entre dois nós.

Quanto mais nós referenciam um dado nó, maior ele fica.

Para interagir com as notas no grafo:

- Passe o cursor sobre cada círculo para realçar as ligações dessa nota.
- Clique numa nota no grafo para a abrir.
- Clique com o botão direito numa nota para abrir um menu de contexto com as ações disponíveis para essa nota.

Para navegar no grafo:

- Amplie e reduza usando a roda do rato, ou usando as teclas `+` e `-`.
- Mova o grafo arrastando-o com o cursor do rato, ou usando as teclas de seta.

Pode manter Shift premido enquanto usa o teclado para acelerar os movimentos.

## Definições

Para abrir as definições do grafo, clique no ícone de engrenagem no canto superior direito da vista de grafo.

Clique em **Restaurar definições predefinidas** no canto superior direito da caixa de definições para repor quaisquer alterações que faça.

### Filtros

Esta secção controla que nós mostrar no grafo.

- **Pesquisar ficheiros** permite-lhe filtrar notas com base num termo de pesquisa. Para saber como pode escrever termos de pesquisa mais avançados, consulte [[Pesquisa]].
- **Tags** alterna se deve mostrar tags no grafo.
- **Anexos** alterna se deve mostrar anexos no grafo.
- **Apenas ficheiros existentes** alterna se deve mostrar notas que existem no seu cofre. Como uma nota não precisa de existir para criar uma ligação para ela, isto pode ajudar a limitar o seu grafo às notas que realmente tem no cofre.
- **Órfãos** alterna se deve mostrar notas sem quaisquer ligações.

> [!info] Ficheiros excluídos
> Os ficheiros que correspondam aos seus padrões de [[Configurações#Excluded files|Ficheiros excluídos]] não aparecerão na Vista de grafo.

### Grupos

Crie grupos de notas para as distinguir entre si usando cores.

Para criar um novo grupo:

1. Clique em **Novo grupo**.
2. Na caixa de pesquisa, escreva um termo de pesquisa para as notas que pretende adicionar ao grupo.
3. Clique no círculo colorido para dar uma cor ao grupo.

Para saber como pode escrever termos de pesquisa mais avançados, consulte [[Pesquisa]].

### Apresentação

Esta secção controla como visualizar nós e ligações no grafo.

- **Setas** alterna se deve mostrar a direção de cada ligação.
- **Limiar de desbotamento do texto** controla a transparência do texto para o nome de cada nota.
- **Tamanho do nó** controla o tamanho do círculo que representa cada nota.
- **Espessura da ligação** controla a largura da linha para cada ligação.
- **Animar** inicia uma [[#Start a time-lapse animation|animação em time-lapse]].

### Forças

Esta secção controla as forças que atuam em cada nó do grafo.

- **Força central** controla o quão compacto é o grafo. Um valor mais alto cria um grafo mais circular.
- **Força de repulsão** controla o quanto um nó empurra outros nós para longe dele.
- **Força de ligação** controla a atração em cada ligação. Se a ligação fosse um elástico, a força de ligação controla o quão tenso ou frouxo é o elástico.
- **Distância de ligação** controla o comprimento das linhas entre cada nota.

## Iniciar uma animação em time-lapse

As notas e os anexos aparecem por ordem cronológica com base na sua data de criação.

![[obsidian-graph-view.png#interface]]

## Grafo local

Para abrir uma Vista de grafo local, use o comando **Abrir grafo local**. Enquanto a Vista de grafo mostra todas as notas no seu cofre, uma Vista de grafo local mostra as notas ligadas à nota ativa.

A Vista de grafo local pode usar todas as [[#Definições]] disponíveis para a Vista de grafo global. Adicionalmente, pode alterar a profundidade do grafo local. Cada nível de profundidade mostrará notas ligadas às notas reveladas na profundidade anterior. Para controlar a profundidade do grafo local, use o controlo deslizante no topo do painel de definições do filtro do grafo local.
