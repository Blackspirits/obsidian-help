---
aliases:
  - Advanced Markdown
permalink: advanced-syntax
---
Aprenda a adicionar sintaxe de formatação avançada às suas notas.

## Tabelas

Pode criar tabelas usando barras verticais (`|`) para separar colunas e hífens (`-`) para definir cabeçalhos. Aqui está um exemplo:

```md
| Primeiro nome | Último nome |
| ------------- | ----------- |
| Max           | Planck      |
| Marie         | Curie       |
```

| Primeiro nome | Último nome |
| ------------- | ----------- |
| Max           | Planck      |
| Marie         | Curie       |

Embora as barras verticais em cada lado da tabela sejam opcionais, incluí-las é recomendado para melhor legibilidade.

> [!tip] No _Live Preview_, pode clicar com o botão direito numa tabela para adicionar ou eliminar colunas e linhas. Também pode ordená-las e movê-las usando o menu de contexto.

Pode inserir uma tabela usando o comando **Inserir tabela** da [[Paleta de comandos|Paleta de comandos]] ou clicando com o botão direito e selecionando _Inserir → Tabela_. Isto fornece uma tabela básica e editável:

```md
|     |     |
| --- | --- |
|     |     |
```

Note que as células não precisam de alinhamento perfeito, mas a linha de cabeçalho deve conter pelo menos dois hífens:

```md
Primeiro nome | Último nome
-- | --
Max | Planck
Marie | Curie
```

### Formatar conteúdo dentro de uma tabela

Pode usar a [[Sintaxe de formatação básica]] para estilizar conteúdo dentro de uma tabela.

| Primeira coluna    | Segunda coluna                                    |
| ------------------ | ------------------------------------------------- |
| [[Links internos]] | Ligação para um ficheiro _dentro_ do seu **cofre**. |
| [[Incorporar ficheiros]] | ![[Engelbart.jpg\|100]]                     |

> [!note] Barras verticais em tabelas
> Se pretender usar [[Apelidos]], ou [[Sintaxe de formatação básica#External images|redimensionar uma imagem]] na sua tabela, precisa de adicionar `\` antes da barra vertical.
>
> ```md
> Primeira coluna | Segunda coluna
> -- | --
> [[Basic formatting syntax\|Sintaxe Markdown]] | ![[Engelbart.jpg\|200]]
> ```
>
> Primeira coluna | Segunda coluna
> -- | --
> [[Basic formatting syntax\|Sintaxe Markdown]] | ![[Engelbart.jpg\|200]]

Alinhe o texto nas colunas adicionando dois pontos (`:`) à linha de cabeçalho. Também pode alinhar conteúdo no _Live Preview_ através do menu de contexto.

```md
Texto alinhado à esquerda | Texto centrado | Texto alinhado à direita
:-- | :--: | --:
Conteúdo | Conteúdo | Conteúdo
```

Texto alinhado à esquerda | Texto centrado | Texto alinhado à direita
:-- | :--: | --:
Conteúdo | Conteúdo | Conteúdo

## Diagramas

Pode adicionar diagramas e gráficos às suas notas usando [Mermaid](https://mermaid-js.github.io/). O Mermaid suporta uma variedade de diagramas, como [fluxogramas](https://mermaid.js.org/syntax/flowchart.html), [diagramas de sequência](https://mermaid.js.org/syntax/sequenceDiagram.html) e [linhas do tempo](https://mermaid.js.org/syntax/timeline.html).

> [!tip] Dica
> Também pode experimentar o [Editor ao vivo](https://mermaid-js.github.io/mermaid-live-editor) do Mermaid para ajudar a criar diagramas antes de os incluir nas suas notas.

Para adicionar um diagrama Mermaid, crie um [[Sintaxe de formatação básica#Code blocks|bloco de código]] `mermaid`.

````md
```mermaid
sequenceDiagram
    Alice->>+João: Olá João, como estás?
    Alice->>+João: João, consegues ouvir-me?
    João-->>-Alice: Olá Alice, consigo ouvir-te!
    João-->>-Alice: Estou muito bem!
```
````

```mermaid
sequenceDiagram
    Alice->>+João: Olá João, como estás?
    Alice->>+João: João, consegues ouvir-me?
    João-->>-Alice: Olá Alice, consigo ouvir-te!
    João-->>-Alice: Estou muito bem!
```

````md
```mermaid
graph TD

Biologia --> Química
```
````

```mermaid
graph TD

Biologia --> Química
```

### Ligar ficheiros num diagrama

Pode criar [[Links internos]] nos seus diagramas anexando a [classe](https://mermaid.js.org/syntax/flowchart.html#classes) `internal-link` aos seus nós.

````md
```mermaid
graph TD

Biologia --> Química

class Biologia,Química internal-link;
```
````

```mermaid
graph TD

Biologia --> Química

class Biologia,Química internal-link;
```

> [!note] Nota
> As ligações internas de diagramas não aparecem na [[Vista de grafo]].

Se tiver muitos nós nos seus diagramas, pode usar o seguinte fragmento.

````md
```mermaid
graph TD

A[Biologia]
B[Química]

A --> B

class A,B,C,D,E,F,G,H,I,J,K,L,M,N,O,P,Q,R,S,T,U,V,W,X,Y,Z internal-link;
```
````

Desta forma, cada nó de letra torna-se uma ligação interna, com o [texto do nó](https://mermaid.js.org/syntax/flowchart.html#a-node-with-text) como texto da ligação.

> [!note] Nota
> Se usar carateres especiais nos nomes das suas notas, precisa de colocar o nome da nota entre aspas duplas.
>
> ```
> class "⨳ carácter especial" internal-link
> ```
>
> Ou, `A["⨳ carácter especial"]`.

Para mais informações sobre a criação de diagramas, consulte a [documentação oficial do Mermaid](https://mermaid.js.org/intro/).

## Matemática

Pode adicionar expressões matemáticas às suas notas usando [MathJax](http://docs.mathjax.org/en/latest/basic/mathjax.html) e a notação LaTeX.

Para adicionar uma expressão MathJax à sua nota, rodeie-a com cifrões duplos (`$$`).

```md
$$
\begin{vmatrix}a & b\\
c & d
\end{vmatrix}=ad-bc
$$
```

$$
\begin{vmatrix}a & b\\
c & d
\end{vmatrix}=ad-bc
$$

Também pode incluir expressões matemáticas inline envolvendo-as com símbolos `$`.

```md
Esta é uma expressão matemática inline $e^{2i\pi} = 1$.
```

Esta é uma expressão matemática inline $e^{2i\pi} = 1$.

Para mais informações sobre a sintaxe, consulte o [Tutorial básico e referência rápida do MathJax](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference).

Para uma lista de pacotes MathJax suportados, consulte [A lista de extensões TeX/LaTeX](http://docs.mathjax.org/en/latest/input/tex/extensions/index.html).
