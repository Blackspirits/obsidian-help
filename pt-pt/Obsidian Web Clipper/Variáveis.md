---
permalink: web-clipper/variables
---
Os [[Obsidian Web Clipper/Modelos|modelos do Web Clipper]] podem usar variáveis para pré-preencher automaticamente dados da página num modelo. As variáveis podem ser usadas no **nome da nota**, **localização da nota**, **propriedades** e **conteúdo da nota**. As variáveis também podem ser modificadas usando [[Filtros]].

Use o ícone `...` na extensão do [[Introdução ao Obsidian Web Clipper|Web Clipper]] para aceder às variáveis da página atual para uso em modelos. Existem cinco tipos de variáveis que pode usar:

- [[Variáveis#Preset variables|Variáveis predefinidas]]
- [[Variáveis#Prompt variables|Variáveis de prompt]]
- [[Variáveis#Meta variables|Variáveis meta]]
- [[Variáveis#Selector variables|Variáveis selector]]
- [[Variáveis#Schema.org variables|Variáveis Schema.org]]

## Variáveis predefinidas

As variáveis predefinidas são geradas automaticamente com base no conteúdo da página. Normalmente funcionam para a maioria dos sites.

A variável de conteúdo principal é `{{content}}`, que contém o conteúdo do artigo, os [[Destacar páginas web|destaques]] ou a seleção se houver texto selecionado na página. Note que `{{content}}` tenta extrair o conteúdo principal da página, o que pode nem sempre ser o que pretende. Nesse caso, pode usar outras variáveis predefinidas ou variáveis selector para extrair o conteúdo de que precisa.

| Variável            | Descrição                                                                              |
| ------------------- | -------------------------------------------------------------------------------------- |
| `{{author}}`        | Autor da página                                                                        |
| `{{content}}`       | Conteúdo do artigo, [[Highlight web pages\|destaques]] ou seleção, em formato Markdown |
| `{{contentHtml}}`   | Conteúdo do artigo, [[Highlight web pages\|destaques]] ou seleção, em formato HTML     |
| `{{date}}`          | Data atual, pode ser formatada usando o filtro `date`                                  |
| `{{description}}`   | Descrição ou excerto                                                                   |
| `{{domain}}`        | Domínio                                                                                |
| `{{favicon}}`       | URL do favicon                                                                         |
| `{{fullHtml}}`      | HTML não processado para o conteúdo completo da página                                 |
| `{{highlights}}`    | [[Highlight web pages\|Destaques]] com texto e marcas temporais                        |
| `{{image}}`         | URL da imagem de partilha social                                                       |
| `{{published}}`     | Data de publicação, pode ser formatada usando o filtro `date`                          |
| `{{selection}}`     | Seleção em formato Markdown                                                            |
| `{{selectionHtml}}` | Seleção em formato HTML                                                                |
| `{{site}}`          | Nome do site ou publicador                                                             |
| `{{title}}`         | Título da página                                                                       |
| `{{time}}`          | Data e hora atuais                                                                     |
| `{{url}}`           | URL atual                                                                              |
| `{{words}}`         | Contagem de palavras                                                                   |

## Variáveis de prompt

As variáveis de prompt utilizam modelos de linguagem para extrair e modificar dados usando linguagem natural. As variáveis de prompt requerem que o [[Interpretar páginas web|Interpretador]] esteja ativado e configurado.

As variáveis de prompt usam a sintaxe `{{"um resumo da página"}}`. As aspas duplas em torno do prompt são importantes e distinguem os prompts das variáveis predefinidas. As respostas dos prompts podem ser pós-processadas com [[Filtros]], por exemplo `{{"um resumo da página"|blockquote}}`.

### Quando usar variáveis de prompt

As variáveis de prompt têm a vantagem de serem extremamente flexíveis e fáceis de escrever, no entanto têm várias desvantagens: são mais lentas a executar e podem ter considerações de custo e privacidade dependendo do [[Interpretar páginas web#Models|fornecedor]] que escolher.

Ao contrário de outros tipos de variáveis, as variáveis de prompt precisam de ser processadas por um modelo de linguagem externo, pelo que são substituídas apenas depois de o [[Interpretar páginas web|Interpretador]] ter sido executado.

É melhor *não* usar variáveis de prompt se os dados que pretende extrair estão num formato consistente que pode ser extraído com outros tipos de variáveis.

Por outro lado, as variáveis de prompt podem ser úteis se os dados que pretende extrair estão num formato *inconsistente* entre sites. Por exemplo, pode criar um [[Obsidian Web Clipper/Modelos|modelo]] para guardar livros que seja agnóstico do site de livros. Variáveis de prompt como `{{"autor do livro"}}` funcionarão em qualquer site de livros, enquanto as variáveis selector normalmente funcionam apenas para um site.

### Exemplos

Os prompts podem usar quase qualquer consulta em linguagem natural. Dependendo do modelo que usar, os prompts podem consultar ou traduzir dados em vários idiomas.

- `{{"um resumo em três pontos, traduzido para francês"}}` para extrair pontos sobre a página e traduzi-los para francês.
- `{{"un resumé de la page en trois points"}}` para extrair três pontos usando um prompt em francês.

Os prompts podem transformar o conteúdo da página em JSON que pode ser manipulado com [[Filtros|filtros]]. Por exemplo:

```
{{"devolver um objeto JSON para cada tweet, que inclua o autor, tweet_text, data no formato YYYY-MM-DD e matriz de imagens (se existirem)"|map:tweet => ({text: tweet.tweet_text, author: tweet.author, date: tweet.date})|template:"${text}\n— [[@${author}]], [[${date}]]\n"}}
```


## Variáveis meta

As variáveis meta permitem extrair dados de [elementos meta](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) na página, incluindo dados do [Open Graph](https://ogp.me/) usados para preencher pré-visualizações de partilha social.

- `{{meta:name}}` devolve o conteúdo da tag meta name com o nome fornecido, por exemplo `{{meta:name:description}}` para a tag meta `description`.
- `{{meta:property}}` devolve o conteúdo da tag meta property com a propriedade fornecida, por exemplo `{{meta:property:og:title}}` para a tag meta `og:title`.

## Variáveis selector

As variáveis selector permitem extrair conteúdo de texto de elementos na página usando [seletores CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors/Selectors_and_combinators).

A sintaxe é `{{selector:seletorCSS?atributo}}`, onde `?atributo` é opcional. Se não for especificado nenhum atributo, é devolvido o conteúdo de texto do elemento. Também pode usar `{{selectorHtml:seletorCSS}}` para obter o conteúdo HTML do elemento. As variáveis selector tendem a funcionar melhor num site específico ou conjunto de sites que têm uma estrutura HTML consistente.

- `{{selector:h1}}` devolve o conteúdo de texto de quaisquer elementos `h1` na página.
- `{{selector:.author}}` devolve o conteúdo de texto de quaisquer elementos `.author` na página.
- `{{selector:img.hero?src}}` devolve o atributo `src` da imagem com a classe `hero`.
- `{{selector:a.main-link?href}}` devolve o atributo `href` da tag âncora com a classe `main-link`.
- `{{selectorHtml:body|markdown}}` devolve o HTML completo do elemento `body`, convertido para Markdown usando o [[Filtros#HTML processing|filtro]] `markdown`.
- Os seletores CSS aninhados e combinadores são suportados se precisar de maior especificidade.
- Se múltiplos elementos corresponderem ao seletor, é devolvida uma matriz, que pode processar com [[Filtros#Arrays and objects|filtros de matriz e objeto]] como `join` ou `map`.

As variáveis selector também podem ser usadas diretamente na [[Lógica|lógica de template]]:

- Em ciclos: `{% for comment in selector:.comment %}...{% endfor %}`
- Em condicionais: `{% if selector:.premium-badge %}...{% endif %}`
- Em atribuição de variáveis: `{% set items = selector:.list-item %}`

## Variáveis Schema.org

As variáveis schema permitem extrair dados do [schema.org](https://schema.org/) JSON-LD na página. Os dados do Schema.org também podem ser usados para [[Obsidian Web Clipper/Modelos#Schema.org matching|acionar automaticamente um modelo]].

- `{{schema:@Tipo:chave}}` devolve o valor da chave do schema.
- `{{schema:@Tipo:pai.filho}}` devolve o valor de uma propriedade aninhada.
- `{{schema:@Tipo:chaveMatriz}}` devolve o primeiro item de uma matriz.
- `{{schema:@Tipo:chaveMatriz[índice].propriedade}}` devolve o item no índice especificado de uma matriz.
- `{{schema:@Tipo:chaveMatriz[*].propriedade}}` devolve uma propriedade específica de todos os itens de uma matriz.

Também pode usar uma notação abreviada sem especificar o tipo de schema:

- `{{schema:author}}` corresponderá à primeira propriedade `author` encontrada em qualquer tipo de schema.
- `{{schema:name}}` corresponderá à primeira propriedade `name` encontrada em qualquer tipo de schema.

Esta abreviatura é particularmente útil quando não sabe ou não se preocupa com o tipo de schema específico, mas sabe o nome da propriedade que procura.

As propriedades aninhadas e o acesso a matrizes também funcionam, com e sem o `@Tipo` de schema especificado:

- `{{schema:author.name}}` encontrará a primeira propriedade `author` e depois acederá à sua subpropriedade `name`.
- `{{schema:author[0].name}}` acederá ao `name` do primeiro autor numa matriz de autores.
- `{{schema:author[*].name}}` devolverá uma matriz com todos os nomes de autores.
