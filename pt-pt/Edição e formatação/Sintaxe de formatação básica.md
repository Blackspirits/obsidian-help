---
aliases:
  - How to/Format your notes
  - Markdown
description: Aprenda a aplicar formatação básica às suas notas no Obsidian, usando Markdown.
mobile: true
permalink: syntax
publish: true
---

Aprenda a aplicar formatação básica às suas notas, usando [Markdown](https://daringfireball.net/projects/markdown/). Para uma sintaxe de formatação mais avançada, consulte [[Sintaxe de formatação avançada]].

## Parágrafos

Para criar parágrafos em Markdown, use uma **linha em branco** para separar blocos de texto. Cada bloco de texto separado por uma linha em branco é tratado como um parágrafo distinto.

```md
Este é um parágrafo.

Este é outro parágrafo.
```

Este é um parágrafo.

Este é outro parágrafo.

Uma linha em branco entre linhas de texto cria parágrafos separados. Este é o comportamento predefinido em Markdown.

> [!tip]- Múltiplos espaços em branco
> Múltiplos espaços adjacentes dentro e entre parágrafos colapsam num único espaço quando apresentados na [[Vistas e modo de edição#Reading view|Vista de leitura]] ou em sites do [[Introdução ao Obsidian Publish|Obsidian Publish]].
>
> ```md
> Múltiplos          espaços          adjacentes
>
>
>
> e múltiplas linhas novas entre parágrafos.
> ```
>
> > Múltiplos          espaços          adjacentes
> >
> >
> >
> > e múltiplas linhas novas entre parágrafos.
>
> Se pretender evitar que os espaços colapsem ou adicionar múltiplos espaços em branco, pode usar as tags HTML `&nbsp;` (espaço não separável) ou `<br>` (quebra de linha).

### Quebras de linha

Por predefinição no Obsidian, premir `Enter` uma vez criará uma nova linha na sua nota, mas esta é tratada como uma *continuação* do mesmo parágrafo no resultado renderizado, seguindo o comportamento típico do Markdown. Para inserir uma quebra de linha *dentro* de um parágrafo sem começar um novo parágrafo, pode:

- Adicionar **dois espaços** no final de uma linha antes de premir `Enter`, ou
- Usar o atalho `Shift+Enter` para inserir diretamente uma quebra de linha.

> [!question]- Por que múltiplas pressões de `Enter` não criam mais quebras de linha na vista de leitura?
> Em Markdown, um único `Enter` é ignorado e múltiplas pressões consecutivas de `Enter` resultam em apenas um novo parágrafo. Este comportamento está alinhado com a regra de ajuste suave do Markdown, onde linhas em branco extra não geram quebras de linha ou parágrafos adicionais — são colapsadas numa única quebra de parágrafo. É assim que o Markdown trata o texto por predefinição, garantindo que os parágrafos fluem naturalmente sem quebras inesperadas.

O Obsidian inclui uma definição de **[[Configurações#Strict line breaks|Quebras de linha estritas]]**, que faz o Obsidian seguir a especificação Markdown padrão para quebras de linha.

Para ativar esta funcionalidade:

1. Abra as **[[Configurações]]**.
2. Vá ao separador **Editor**.
3. Ative **Quebras de linha estritas**.

Quando as **Quebras de linha estritas** estão ativas no Obsidian, as quebras de linha têm três comportamentos distintos dependendo de como as linhas são separadas:

**Return único sem espaços**: Um único `Enter` sem espaços no final combinará as duas linhas separadas numa única linha quando renderizadas.

```md
linha um
linha dois
```

Renderiza como:

linha um linha dois

**Return único com dois ou mais espaços no final**: Se adicionar dois ou mais espaços no final da primeira linha antes de premir `Enter`, as duas linhas permanecem parte do mesmo parágrafo, mas são separadas por uma quebra de linha (elemento HTML `<br>`). Usaremos dois sublinhados para representar espaços neste exemplo.

```md
linha três__
linha quatro
```

Renderiza como:

linha três<br>
linha quatro

**Return duplo (com ou sem espaços no final)**: Premir `Enter` duas vezes (ou mais) separa as linhas em dois parágrafos distintos (elementos HTML `<p>`), independentemente de adicionar espaços no final da primeira linha.

```md
linha cinco

linha seis
```

Renderiza como:

<p>linha cinco</p>
<p>linha seis</p>

## Cabeçalhos

Para criar um cabeçalho, adicione até seis símbolos `#` antes do texto do cabeçalho. O número de símbolos `#` define o nível do cabeçalho (como mostrado no [[Sumário]]).

```md
# Este é um cabeçalho 1
## Este é um cabeçalho 2
### Este é um cabeçalho 3
#### Este é um cabeçalho 4
##### Este é um cabeçalho 5
###### Este é um cabeçalho 6
```

%% These headings use HTML to avoid cluttering the Outline/Table of contents %%
<h1>Este é um cabeçalho 1</h1>
<h2>Este é um cabeçalho 2</h2>
<h3>Este é um cabeçalho 3</h3>
<h4>Este é um cabeçalho 4</h4>
<h5>Este é um cabeçalho 5</h5>
<h6>Este é um cabeçalho 6</h6>

## Negrito, itálico, realces

A formatação de texto também pode ser aplicada usando [[Atalhos de edição]].

| Estilo | Sintaxe | Exemplo | Resultado |
|-|-|-|-|
| Negrito | `** **` ou `__ __` | `**Texto a negrito**` | **Texto a negrito** |
| Itálico | `* *` ou `_ _` | `*Texto em itálico*` | *Texto em itálico* |
| Tachado | `~~ ~~` | `~~Texto tachado~~` | ~~Texto tachado~~ |
| Realce | `== ==` | `==Texto realçado==` | ==Texto realçado== |
| Negrito e itálico aninhado | `** **` e `_ _` | `**Texto a negrito e _itálico aninhado_**` | **Texto a negrito e _itálico aninhado_** |
| Negrito e itálico | `*** ***` ou `___ ___` | `***Texto a negrito e itálico***` | ***Texto a negrito e itálico*** |

A formatação pode ser forçada a aparecer como texto simples adicionando uma barra invertida `\` antes dela.

\*\*Esta linha não ficará a negrito\*\*

```markdown
\*\*Esta linha não ficará a negrito\*\*
```

\**Esta linha ficará em itálico e mostrará os asteriscos*\*

```markdown
\**Esta linha ficará em itálico e mostrará os asteriscos*\*
```

## Ligações internas

O Obsidian suporta dois formatos para [[Links internos]] entre notas:

- Wikilink: `[[Três leis do movimento]]`
- Markdown: `[Três leis do movimento](Tres%20leis%20do%20movimento.md)`

## Ligações externas

Se pretender criar uma ligação para um URL externo, pode criar uma ligação inline rodeando o texto da ligação entre parênteses retos (`[ ]`), e depois o URL entre parênteses curvos (`( )`).

```md
[Ajuda do Obsidian](https://help.obsidian.md)
```

[Ajuda do Obsidian](https://help.obsidian.md)

Também pode criar ligações externas para ficheiros noutros cofres, ligando a um [[Obsidian URI|URI do Obsidian]].

```md
[Nota](obsidian://open?vault=CoffrePrincipal&file=Nota.md)
```

### Escapar espaços em ligações

Se o seu URL contiver espaços, deve escapá-los substituindo-os por `%20`.

```md
[A minha nota](obsidian://open?vault=CoffrePrincipal&file=A%20minha%20nota.md)
```

Também pode escapar o URL envolvendo-o com parênteses angulares (`< >`).

```md
[A minha nota](<obsidian://open?vault=CoffrePrincipal&file=A minha nota.md>)
```

## Imagens externas

Pode adicionar imagens com URLs externos, adicionando um símbolo `!` antes de uma [[#Ligações externas|ligação externa]].

```md
![Engelbart](https://history-computer.com/ModernComputer/Basis/images/Engelbart.jpg)
```

![Engelbart](https://history-computer.com/ModernComputer/Basis/images/Engelbart.jpg)

Pode alterar as dimensões da imagem adicionando `|640x480` ao destino da ligação, onde 640 é a largura e 480 é a altura.

```md
![Engelbart|100x145](https://history-computer.com/ModernComputer/Basis/images/Engelbart.jpg)
```

Se especificar apenas a largura, a imagem é dimensionada de acordo com a sua proporção original. Por exemplo:

```md
![Engelbart|100](https://history-computer.com/ModernComputer/Basis/images/Engelbart.jpg)
```

> [!tip]- Dica
> Se pretender adicionar uma imagem de dentro do seu cofre, também pode [[Incorporar ficheiros#Embed an image in a note|incorporar uma imagem numa nota]].

## Citações

Pode citar texto adicionando um símbolo `>` antes do texto.

```md
> Os seres humanos enfrentam problemas cada vez mais complexos e urgentes, e a sua eficácia em lidar com estes problemas é uma questão crítica para a estabilidade e o progresso contínuo da sociedade.

\- Doug Engelbart, 1961
```

> Os seres humanos enfrentam problemas cada vez mais complexos e urgentes, e a sua eficácia em lidar com estes problemas é uma questão crítica para a estabilidade e o progresso contínuo da sociedade.

\- Doug Engelbart, 1961

> [!tip]- Dica
> Pode transformar a sua citação num [[Callouts|callout]] adicionando `[!info]` como primeira linha numa citação.

## Listas

Pode criar uma lista não ordenada adicionando `-`, `*` ou `+` antes do texto.

```md
- Primeiro item da lista
- Segundo item da lista
- Terceiro item da lista
```

- Primeiro item da lista
- Segundo item da lista
- Terceiro item da lista

Para criar uma lista ordenada, comece cada linha com um número seguido de `.` ou `)`.

```md
1. Primeiro item da lista
2. Segundo item da lista
3. Terceiro item da lista
```

1. Primeiro item da lista
2. Segundo item da lista
3. Terceiro item da lista

```md
1) Primeiro item da lista
2) Segundo item da lista
3) Terceiro item da lista
```

1) Primeiro item da lista
2) Segundo item da lista
3) Terceiro item da lista

Pode usar `Shift+Enter` para inserir uma [[#Quebras de linha|quebra de linha]] numa lista ordenada sem alterar a numeração.

### Listas de tarefas

Para criar uma lista de tarefas, comece cada item da lista com um hífen e um espaço seguido de `[ ]`.

```md
- [x] Esta é uma tarefa concluída.
- [ ] Esta é uma tarefa incompleta.
```

- [x] Esta é uma tarefa concluída.
- [ ] Esta é uma tarefa incompleta.

Pode marcar uma tarefa na Vista de leitura selecionando a caixa de verificação.

> [!tip]- Dica
> Pode usar qualquer carácter dentro dos parênteses retos para a marcar como concluída.
>
> ```md
> - [x] Leite
> - [?] Ovos
> - [-] Ovos
> ```
>
> - [x] Leite
> - [?] Ovos
> - [-] Ovos

### Aninhar listas

Pode aninhar qualquer tipo de lista — ordenada, não ordenada ou de tarefas — sob qualquer outro tipo de lista.

Para criar uma lista aninhada, indente um ou mais itens da lista. Pode misturar tipos de listas numa estrutura aninhada:

```md
1. Primeiro item da lista
   1. Item de lista ordenada aninhada
2. Segundo item da lista
   - Item de lista não ordenada aninhada
```

1. Primeiro item da lista
   1. Item de lista ordenada aninhada
2. Segundo item da lista
   - Item de lista não ordenada aninhada

Da mesma forma, pode criar uma lista de tarefas aninhada indentando um ou mais itens:

```md
- [ ] Item de tarefa 1
	- [ ] Subtarefa 1
- [ ] Item de tarefa 2
	- [ ] Subtarefa 1
```

- [ ] Item de tarefa 1
	- [ ] Subtarefa 1
- [ ] Item de tarefa 2
	- [ ] Subtarefa 1

Use `Tab` ou `Shift+Tab` para indentar ou desidentar itens de lista selecionados para os organizar facilmente.

## Linha horizontal

Pode usar três ou mais asteriscos `***`, hífens `---` ou sublinhados `___` numa linha própria para adicionar uma barra horizontal. Também pode separar símbolos usando espaços.

```md
***
****
* * *
---
----
- - -
___
____
_ _ _
```

***

## Código

Pode formatar código tanto inline dentro de uma frase como num bloco próprio.

### Código inline

Pode formatar código dentro de uma frase usando crases simples.

```md
O texto dentro de `crases` numa linha será formatado como código.
```

O texto dentro de `crases` numa linha será formatado como código.

Se pretender colocar crases num bloco de código inline, rodeie-o com crases duplas: código inline ``com uma crase ` dentro``.

### Blocos de código

Para formatar código como um bloco, encerre-o com três ou mais crases ou três ou mais tils.

~~~
`````
cd ~/Desktop
`````
~~~
`````
~~~
cd ~/Desktop
~~~
`````
`````md
cd ~/Desktop
`````

Também pode criar um bloco de código indentando o texto com `Tab` ou 4 espaços em branco.
`````md
    cd ~/Desktop
`````

Pode adicionar realce de sintaxe a um bloco de código adicionando um código de linguagem após o primeiro conjunto de crases.

~~~md
`````js
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
`````
~~~
`````js
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
`````

O Obsidian usa o Prism para realce de sintaxe. Para mais informações, consulte [Linguagens suportadas](https://prismjs.com/#supported-languages).

> [!info]+ PrismJS e vistas de edição
> O [[Vistas e modo de edição#Source mode|Modo de código-fonte]] e o [[Vistas e modo de edição#Live Preview|Live Preview]] não suportam PrismJS e podem renderizar o realce de sintaxe de forma diferente.

#### Aninhar blocos de código

Quando precisa de incluir um bloco de código dentro de outro bloco de código (por exemplo, ao documentar como usar blocos de código), pode usar mais de três crases ou tils para o bloco de código exterior.

Para aninhar blocos de código, use quatro ou mais crases (ou tils) para o bloco exterior, enquanto o bloco interior usa três:
`````md
````md
Aqui está como criar um bloco de código:
```js
console.log("Olá mundo")
```
````
`````

Também pode misturar crases e tils. Isto é particularmente útil ao trabalhar com código que gera outros blocos de código:
`````md
````md
```dataviewjs
dv.paragraph(`
~~~mermaid
graph TD
    A --> B
~~~
`)
```
````
`````

O princípio fundamental é que o bloco de código exterior deve usar **mais** carateres de cerca (crases ou tils) do que qualquer bloco interior, ou usar um tipo diferente de carácter de cerca.

## Notas de rodapé

Pode adicionar notas de rodapé[^nota] às suas notas usando a seguinte sintaxe:

[^nota]: Esta é uma nota de rodapé.

```md
Esta é uma nota de rodapé simples[^1].

[^1]: Este é o texto referenciado.
[^2]: Adicione 2 espaços no início de cada nova linha.
  Isto permite escrever notas de rodapé que abrangem múltiplas linhas.
[^nota]: As notas de rodapé com nome ainda aparecem como números, mas podem facilitar a identificação e ligação de referências.
```

Também pode incluir notas de rodapé inline numa frase. Note que o acento circunflexo vai fora dos parênteses retos.

```md
Também pode usar notas de rodapé inline. ^[Esta é uma nota de rodapé inline.]
```

> [!note] Nota
> As notas de rodapé inline só funcionam na vista de leitura, não no Live Preview.

## Comentários

Pode adicionar comentários envolvendo texto com `%%`. Os comentários só são visíveis na Vista de edição.

```md
Este é um comentário %%inline%%.

%%
Este é um comentário em bloco.

Os comentários em bloco podem abranger múltiplas linhas.
%%
```

## Escapar sintaxe Markdown

Em alguns casos, poderá precisar de apresentar carateres especiais em Markdown, como `*`, `_` ou `#`, sem acionar a sua formatação. Para apresentar estes carateres literalmente, coloque uma barra invertida (`\`) antes deles.

> [!example] Carateres comuns a escapar
>
> - Asterisco: `\*`
> - Sublinhado: `\_`
> - Cardinal: `\#`
> - Crase: `` \` ``
> - Barra vertical (usada em tabelas): `\|`
> - Til: `\~`

```md
\*Este texto não ficará em itálico\*.
```

\*Este texto não ficará em itálico\*.

Ao trabalhar com listas numeradas, poderá precisar de escapar o ponto após o número para evitar a formatação automática de lista. Coloque a barra invertida (`\`) antes do ponto, **não** antes do número.

```md
1\. Isto não será um item de lista.
```

1\. Isto não será um item de lista.

## Saber mais

Para aprender sintaxe de formatação mais avançada, como tabelas, diagramas e expressões matemáticas, consulte [[Sintaxe de formatação avançada]].

Para aprender mais sobre como o Obsidian processa o Markdown, consulte [[Obsidian Flavored Markdown]].
