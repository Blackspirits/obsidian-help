---
permalink: web-clipper/filters
---
Os filtros permitem modificar [[Variáveis]] nos [[Obsidian Web Clipper/Modelos|modelos do Web Clipper]]. Os filtros são aplicados a variáveis usando a sintaxe `{{variável|filtro}}`.

- Os filtros funcionam para qualquer tipo de [[Variáveis|variável]], incluindo variáveis `prompt`, `meta`, `selector` e `schema`.
- Os filtros podem ser encadeados, por exemplo `{{variável|filtro1|filtro2}}`, e são aplicados na ordem em que são adicionados.

## Datas

Converter e modificar datas.

### `date`

Converte uma data para o formato especificado, [consulte a referência](https://day.js.org/docs/en/display/format).

- `{{date|date:"YYYY-MM-DD"}}` converte a data atual para "YYYY-MM-DD".
- Use `date:("formatoSaída", "formatoEntrada")` para especificar o formato de entrada, por exemplo `"12/01/2024"|date:("YYYY-MM-DD", "MM/DD/YYYY")` analisa "12/01/2024" e devolve `"2024-12-01"`.

### `date_modify`

Modifica uma data adicionando ou subtraindo uma quantidade de tempo especificada, [consulte a referência](https://day.js.org/docs/en/manipulate/add).

- `"2024-12-01"|date_modify:"+1 year"` devolve `"2025-12-01"`
- `"2024-12-01"|date_modify:"- 2 months"` devolve `"2024-10-01"`

### `duration`

Converte cadeias de duração ISO 8601 ou segundos em cadeias de tempo formatadas. Usa tokens: `HH` (horas com preenchimento), `H` (horas), `mm` (minutos com preenchimento), `m` (minutos), `ss` (segundos com preenchimento), `s` (segundos).

- `"PT1H30M"|duration:"HH:mm:ss"` devolve `"01:30:00"`.
- `"3665"|duration:"H:mm:ss"` devolve `"1:01:05"`.
- Definir `duration` sem parâmetros usa `HH:mm:ss` para mais de 1 hora, `mm:ss` para menos de 1 hora.
- Suporta cadeias de duração ISO 8601 (por exemplo, `PT6702S`, `PT1H30M`) e segundos simples.

## Conversão e capitalização de texto

Converter cadeias de texto de um formato para outro.

### `camel`

Converte texto para `camelCase`.

### `capitalize`

Capitaliza o primeiro caractere do valor e converte o resto para minúsculas, por exemplo `"oLÁ mUNDO"|capitalize` devolve `"Olá mundo"`.

### `decode_uri`

Descodifica uma cadeia codificada por URI, por exemplo `"%E4%BD%A0%E5%A5%BD"|decode_uri` devolve `"你好"`.

- `"hello%20world"|decode_uri` devolve `"hello world"`.
- Devolve a cadeia original se a descodificação falhar (por exemplo, sequências URI malformadas).

### `kebab`

Converte texto para `kebab-case`.

### `lower`

Converte texto para `minúsculas`.

### `pascal`

Converte texto para `PascalCase`.

### `replace`

Substitui ocorrências de texto especificado:

- Substituição simples: `"olá!"|replace:",":""` remove todas as vírgulas.
- Múltiplas substituições: `"hello world"|replace:("e":"a","o":"0")` devolve `"hall0 w0rld"`.
- As substituições são aplicadas na ordem em que são especificadas.
- Para remover texto especificado, use `""` como valor de substituição.
- Os caracteres especiais incluindo `: | { } ( ) ' "` devem ser escapados com uma barra invertida quando usados no termo de pesquisa, por exemplo `\:` para pesquisar um dois-pontos literal.

O Regex é suportado usando a sintaxe de regex JavaScript:

- Substituir todas as vogais: `"hello world"|replace:"/[aeiou]/g":"*"` → `"h*ll* w*rld".`
- Sem distinção entre maiúsculas e minúsculas: `"HELLO world"|replace:"/hello/i":"hi"` → `"hi world".`
- Múltiplos regex: `"hello world"|replace:("/[aeiou]/g":"*","/\s+/":"-")` → `"h*ll*-w*rld"`.
- Sinalizadores disponíveis: `g` (global), `i` (sem distinção entre maiúsculas/minúsculas), `m` (multilinha), `s` (dotAll), `u` (unicode), `y` (sticky).

### `safe_name`

Converte texto para um nome de ficheiro seguro.

- Por defeito, `safe_name` aplica as regras de sanitização mais conservadoras.
- Regras específicas do SO podem ser aplicadas com `safe_name:os` onde `os` pode ser `windows`, `mac` ou `linux` para aplicar apenas as regras desse sistema operativo.

### `snake`

Converte texto para `snake_case`.

### `title`

Converte texto para `Título com Maiúsculas`, por exemplo `"hello world"|title` devolve `"Hello World"`.

### `trim`

Remove os espaços em branco de ambas as extremidades de uma cadeia.

- `"  hello world  "|trim` devolve `"hello world"`.

### `uncamel`

Converte camelCase ou PascalCase para palavras separadas por espaços, que pode formatar com outros filtros como `title` ou `capitalize`.

- `"camelCase"|uncamel` devolve `"camel case"`.
- `"PascalCase"|uncamel` devolve `"pascal case"`.

### `upper`

Converte um valor para maiúsculas, por exemplo `"hello world"|upper` devolve `"HELLO WORLD"`.

## Formatação de texto

Aplicar [[Sintaxe de formatação básica]] e [[Sintaxe de formatação avançada]] ao texto.

### `blockquote`

Adiciona um prefixo de citação Markdown (`> `) a cada linha da entrada.

### `callout`

Cria um [[Callouts|callout]] com parâmetros opcionais: `{{variável|callout:("tipo", "título", estadoDobrável)}}`

- `tipo` é o tipo de callout e por defeito é "info"
- `título` é o título do callout e por defeito está vazio
- `estadoDobrável` é um booleano para definir o estado dobrável (true para dobrado, false para desdobrado, null para não dobrável)

### `footnote`

Converte uma matriz ou objeto numa lista de notas de rodapé Markdown.

- Para matrizes: `["primeiro item","segundo item"]|footnote` devolve: `[^1]: primeiro item` etc.
- Para objetos: `{"Primeira Nota": "Conteúdo 1", "Segunda Nota": "Conteúdo 2"}|footnote` devolve: `[^primeira-nota]: Conteúdo 1` etc.

### `fragment_link`

Converte cadeias e matrizes em ligações de [fragmento de texto](https://developer.mozilla.org/en-US/docs/Web/URI/Fragment/Text_fragments). Por defeito usa "link" para o texto da ligação.

- `highlights|fragment_link` devolve `Conteúdo destacado [link](url-fragmento-texto)`
- `highlights|fragment_link:"título personalizado"` devolve `Conteúdo destacado [título personalizado](url-fragmento-texto)`

### `image`

Converte cadeias, matrizes ou objetos em sintaxe de imagem Markdown.

- Para cadeias: `"imagem.jpg"|image:"texto alternativo"` devolve `![texto alternativo](imagem.jpg)`.
- Para matrizes: `["imagem1.jpg","imagem2.jpg"]|image:"texto alternativo"` devolve uma matriz de cadeias de imagem Markdown com o mesmo texto alternativo para todas as imagens.
- Para objetos: `{"imagem1.jpg": "Alt 1", "imagem2.jpg": "Alt 2"}|image` devolve cadeias de imagem Markdown com texto alternativo proveniente das chaves do objeto.

### `link`

Converte cadeias, matrizes ou objetos em sintaxe de ligação Markdown (a não confundir com [[Filtros#`wikilink`|wikilink]]).

- Para cadeias: `"url"|link:"autor"` devolve `[autor](url)`.
- Para matrizes: `["url1","url2"]|link:"autor"` devolve uma matriz de ligações Markdown com o mesmo texto para todas as ligações.
- Para objetos: `{"url1": "Autor 1", "url2": "Autor 2"}|link` devolve ligações Markdown com o texto correspondente às chaves do objeto.

### `list`

Converte uma matriz numa lista Markdown.

- `list` para converter numa lista com marcadores.
- `list:task` para converter numa lista de tarefas.
- `list:numbered` para converter numa lista numerada.
- `list:numbered-task` para converter numa lista de tarefas com números.

### `table`

Converte uma matriz ou matriz de objetos numa [[Sintaxe de formatação avançada#Tables|tabela Markdown]]:

- Para uma matriz de objetos, usa as chaves do objeto como cabeçalhos.
- Para uma matriz de matrizes, cria uma tabela com cada matriz aninhada como uma linha.
- Para uma matriz simples, cria uma tabela de coluna única com "Value" como cabeçalho.
- Cabeçalhos de coluna personalizados podem ser especificados usando: `table:("Coluna 1", "Coluna 2", "Coluna 3")`. Quando usado com uma matriz simples, divide automaticamente os dados em linhas com base no número de colunas especificado.

### `wikilink`

Converte cadeias, matrizes ou objetos em sintaxe de [[Ligar notas|wikilink]] do Obsidian.

- Para cadeias: `"página"|wikilink` devolve `[[página]]`.
- Para cadeias com apelido: `"página"|wikilink:"apelido"` devolve `[[página|apelido]]`.
- Para matrizes: `["página1","página2"]|wikilink` devolve uma matriz de wikilinks sem apelidos.
- Para matrizes com apelido: `["página1","página2"]|wikilink:"apelido"` devolve uma matriz de wikilinks com o mesmo apelido para todas as ligações.
- Para objetos: `{"página1": "apelido1", "página2": "apelido2"}|wikilink` devolve wikilinks com as chaves como nomes de página e os valores como apelidos.

## Números

### `calc`

Realiza operações aritméticas básicas em números.

- Suporta operadores: `+`, `-`, `*`, `/`, `**` (ou `^`) para exponenciação.
- Exemplo: `5|calc:"+10"` devolve `15`.
- Exemplo: `2|calc:"**3"` devolve `8` (2 ao cubo).
- Devolve a cadeia original se a entrada não for um número.

### `length`

Devolve o comprimento de cadeias, matrizes ou o número de chaves em objetos.

- Para cadeias: `"hello"|length` devolve `5`.
- Para matrizes: `["a","b","c"]|length` devolve `3`.
- Para objetos: `{"a":1,"b":2}|length` devolve `2`.

### `round`

Arredonda um número para o inteiro mais próximo ou para um número especificado de casas decimais.

- Sem parâmetros: `3.7|round` devolve `4`.
- Com casas decimais especificadas: `3.14159|round:2` devolve `3.14`.

## Processamento de HTML

Processar conteúdo HTML e converter HTML para Markdown. Note que a sua [[Variáveis|variável]] de entrada deve conter conteúdo HTML, por exemplo usando `{{fullHtml}}`, `{{contentHtml}}` ou uma variável `{{selectorHtml:}}`.

### `markdown`

Converte uma cadeia para uma cadeia formatada em [[Obsidian Flavored Markdown]].

- Útil quando combinado com variáveis que devolvem HTML como `{{contentHtml}}`, `{{fullHtml}}` e variáveis selector como `{{selectorHtml:seletorCSS}}`.

### `remove_attr`

Remove apenas os atributos HTML especificados das tags.

- Exemplo: `"<div class="test" id="example">Conteúdo</div>"|remove_attr:"class"` devolve `<div id="example">Conteúdo</div>`.
- Múltiplos atributos: `{{fullHtml|remove_attr:("class,style,id")}}`

### `remove_html`

Remove os elementos HTML especificados e o seu conteúdo de uma cadeia.

- Suporta nome de tag, classe ou id, por exemplo `{{fullHtml|remove_html:("img,.nome-classe,#id-elemento")}}`
- Para remover apenas tags ou atributos HTML sem remover o conteúdo, use os filtros `strip_tags` ou `strip_attr`.

### `remove_tags`

Remove apenas as tags HTML especificadas. Mantém o conteúdo das tags.

- Exemplo: `"<p>Olá <b>mundo</b>!</p>"|remove_tags:"b"` devolve `"<p>Olá mundo!</p>"`.
- Múltiplas tags: `{{fullHtml|remove_tags:("a,em,strong")}}`

### `replace_tags`

Substitui tags HTML, mantendo o conteúdo e os atributos da tag.

- `{{fullHtml|replace_tags:"strong":"h2"}}` substitui todas as tags `<strong>` por `<h2>`.

### `strip_attr`

Remove **todos** os atributos HTML de uma cadeia.

- Use `strip_attr:("class, id")` para manter atributos específicos.
- Exemplo: `"<div class="test" id="example">Conteúdo</div>"|strip_attr:("class")` devolve `<div id="example">Conteúdo</div>`.

### `strip_md`

Remove **toda** a formatação Markdown e devolve uma cadeia de texto simples, por exemplo convertendo `**texto**` em `texto`.

- Converte texto formatado em texto simples não formatado, incluindo negrito, itálico, realces, cabeçalhos, código, citações, tabelas, listas de tarefas e wikilinks.
- Remove completamente tabelas, notas de rodapé, imagens e elementos HTML.

### `strip_tags`

Remove **todas** as tags HTML de uma cadeia. O conteúdo dentro da tag é preservado.

- Use `strip_tags:("p,strong,em")` para manter tags específicas.
- Exemplo: `"<p>Olá <b>mundo</b>!</p>"|strip_tags:("b")` devolve `Olá <b>mundo</b>!`.

## Matrizes e objetos

Processar matrizes e objetos.

### `first`

Devolve o primeiro elemento de uma matriz como cadeia.

- `["a","b","c"]|first` devolve `"a"`.
- Se a entrada não for uma matriz, devolve a entrada inalterada.

### `join`

Combina elementos de uma matriz numa cadeia.

- `["a","b","c"]|join` devolve `"a,b,c"`.
- Um separador personalizado pode ser especificado: `["a","b","c"]|join:" "` devolve `"a b c"`. Use `join:"\n"` para separar elementos com uma quebra de linha.
- Pode ser útil após `split` ou `slice`: `"a,b,c,d"|split:","|slice:1,3|join:" "` devolve `"b c"`.

### `last`

Devolve o último elemento de uma matriz como cadeia.

- `["a","b","c"]|last` devolve `"c"`.
- Se a entrada não for uma matriz, devolve a entrada inalterada.

### `map`

Aplica uma transformação a cada elemento de uma matriz usando a sintaxe `map:item => item.propriedade` ou `map:item => item.propriedade.aninhada` para propriedades aninhadas.

- `[{gem: "obsidian", color: "black"}, {gem: "amethyst", color: "purple"}]|map:item => item.gem` devolve `["obsidian", "amethyst"]`.
- Use parênteses para literais de objeto e expressões complexas: `map:item => ({chave: valor})`, por exemplo: `[{gem: "obsidian", color: "black"}, {gem: "amethyst", color: "purple"}]|map:item => ({name: item.gem, color: item.color})` devolve `[{name: "obsidian", color: "black"}, {name: "amethyst", color: "purple"}]`.

Os literais de cadeia também são suportados, por exemplo `["rock", "pop"]|map:item => "genres/${item}"` devolve `["genres/rock", "genres/pop"]`.

Combine `map` com o filtro `template`, por exemplo `map:item => ({name: ${item.gem}, color: item.color})|template:"- ${name} is ${color}\n"`. Para mapas de literais de cadeia, use `${str}` no template, por exemplo `["rock", "pop"]|map:item => "genres/${item}"|template:"- ${str}"`.

Nota: Os filtros incorporados não podem ser usados dentro de `map`. Isto significa que, por exemplo, aparar cada valor de uma matriz não pode ser feito com `map`.

### `merge`

Adiciona novos valores a uma matriz.

- Para matrizes: `["a","b"]|merge:("c","d")` devolve `["a","b","c","d"]`.
- Valor único: `["a","b"]|merge:"c"` devolve `["a","b","c"]`.
- Se a entrada não for uma matriz, cria uma nova matriz: `"a"|merge:("b","c")` devolve `["a","b","c"]`.
- Os valores podem ser citados: `["a"]|merge:('b,"c,d",e')` devolve `["a","b","c,d","e"]`.

### `nth`

Mantém os enésimos itens de uma matriz usando a sintaxe nth-child estilo CSS e padrões de grupo. Todas as posições são baseadas em 1 (o primeiro item está na posição 1).

- `matriz|nth:3` mantém apenas o 3.º elemento.
- `matriz|nth:3n` mantém cada 3.º elemento (3, 6, 9, etc.).
- `matriz|nth:n+3` mantém o 3.º e todos os elementos seguintes.

Sintaxe de padrão de grupo para estruturas repetidas:

- `matriz|nth:1,2,3:5` mantém as posições 1, 2, 3 de cada grupo de 5 itens. Exemplo: `[1,2,3,4,5,6,7,8,9,10]|nth:1,2,3:5` devolve `[1,2,3,6,7,8]`.

### `object`

Manipula dados de objetos:

- `object:array` converte um objeto numa matriz de pares chave-valor.
- `object:keys` devolve uma matriz das chaves do objeto.
- `object:values` devolve uma matriz dos valores do objeto.
- Exemplo: `{"a":1,"b":2}|object:array` devolve `[["a",1],["b",2]]`.

### `slice`

Extrai uma parte de uma cadeia ou matriz.

- Para cadeias: `"hello"|slice:1,4` devolve `"ell"`.
- Para matrizes: `["a","b","c","d"]|slice:1,3` devolve `["b","c"]`.
- Se apenas um parâmetro for fornecido, corta desde esse índice até ao fim: `"hello"|slice:2` devolve `"llo"`.
- Os índices negativos contam a partir do fim: `"hello"|slice:-3` devolve `"llo"`.
- O segundo parâmetro é exclusivo: `"hello"|slice:1,4` inclui os caracteres nos índices 1, 2 e 3.
- Usar um segundo parâmetro negativo exclui elementos do fim: `"hello"|slice:0,-2` devolve `"hel"`.

### `split`

Divide uma cadeia numa matriz de subcadeias.

- `"a,b,c"|split:","` devolve `["a","b","c"]`.
- `"hello world"|split:" "` devolve `["hello","world"]`.
- Se nenhum separador for fornecido, divide em cada caractere: `"hello"|split` devolve `["h","e","l","l","o"]`.
- Expressões regulares podem ser usadas como separadores: `"a1b2c3"|split:[0-9]` devolve `["a","b","c"]`.

### `template`

Aplica uma cadeia de template a um objeto ou matriz de objetos, usando a sintaxe `objeto|template:"Template com ${variável}"`.

- Aceder a propriedades aninhadas: `{"gem":{"name":"Obsidian"}}|template:"${gem.name}"` devolve `"Obsidian"`.
- Para objetos: `{"gem":"obsidian","hardness":5}|template:"${gem} has a hardness of ${hardness}"` devolve `"obsidian has a hardness of 5"`.
- Para matrizes: `[{"gem":"obsidian","hardness":5},{"gem":"amethyst","hardness":7}]|template:"- ${gem} has a hardness of ${hardness}\n"` devolve uma lista formatada.

Funciona com literais de cadeia de `map` usando `${str}`:

- Exemplo: `["rock", "pop"]|map:item => "genres/${item}"|template:"- ${str}"` devolve uma lista formatada.

### `unique`

Remove valores duplicados de matrizes e objetos.

- Para matrizes de primitivos: `[1,2,2,3,3]|unique` devolve `[1,2,3]`.
- Para matrizes de objetos: `[{"a":1},{"b":2},{"a":1}]|unique` devolve `[{"a":1},{"b":2}]`.
- Para objetos remove propriedades com valores duplicados, mantendo a chave da última ocorrência.
- Para cadeias devolve a entrada inalterada.
