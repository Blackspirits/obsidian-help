---
permalink: bases/functions
publish: true
mobile: true
description: Esta página detalha as funções utilizadas no Obsidian Bases para manipular dados de propriedades em filtros e fórmulas.
---

As funções são utilizadas no [[Introdução ao Bases|Bases]] para manipular dados de [[Propriedades]] em [[Vistas#Filters|filtros]] e [[Fórmulas]]. Consulte a referência de [[Sintaxe de Bases|sintaxe de bases]] para saber mais sobre como pode utilizar as funções.

Para além das funções [[Funções#Global|Globais]], a maioria das funções depende do tipo de valor que pretende modificar:

- [[Funções#Any|Any]]
- [[Funções#Date|Date]]
- [[Funções#String|String]]
- [[Funções#Number|Number]]
- [[Funções#List|List]]
- [[Funções#Link|Link]]
- [[Funções#File|File]]
- [[Funções#Object|Object]]
- [[Funções#Regular expression|Regular expression]]

## Global

As funções globais são utilizadas sem um tipo.

### `escapeHTML()`

`escapeHTML(html: string): string`

- Escapa caracteres especiais numa string para torná-la segura para inclusão em HTML.

### `date()`

`date(date: string): date`

- `date(string): date` analisa a string fornecida e devolve um objeto de data.
- A string `date` deve estar no formato `YYYY-MM-DD HH:mm:ss`.

### `duration()`

`duration(value: string): duration`

- Analisa uma string como uma duração. Consulte a [[Sintaxe de Bases#Date arithmetic|secção de aritmética de datas]] para o formato da string `value`.
- As durações não precisam de ser explicitamente analisadas ao realizar aritmética de datas (por exemplo, `now() + '1d'`), mas precisam ao realizar aritmética em durações (por exemplo, `now() + (duration('1d') * 2)`).
- Ao realizar aritmética em durações com escalares, a duração deve estar à esquerda. Por exemplo `duration('5h') * 2`, em vez de `2 * duration('5h')`.

### `file()`

`file(path: string | file | url): file`

- Devolve um objeto de ficheiro para o ficheiro ou caminho indicado.
- Exemplo: `file(link("[[filename]]"))` ou `file("path to file")`.

### `html()`

`html(html: string): html`

- Converte uma string num fragmento de código que é renderizado como HTML.

### `if()`

`if(condition: any, trueResult: any, falseResult?: any): any`

- `condition` é a condição a ser avaliada.
- `trueResult` é o resultado se a condição for verdadeira.
- `falseResult` é o resultado opcional se a condição for falsa. Se não for fornecido, assume-se `null`.
- Devolve `trueResult` se `condition` for verdadeira ou um valor truthy, ou `falseResult` caso contrário.
- Exemplo: `if(isModified, "Modified", "Unmodified")`

### `image()`

`image(path: string | file | url): image`

- Devolve um objeto de imagem que renderiza a imagem na vista.
- Exemplo: `image(image-property)` ou `image("https://obsidian.md/images/obsidian-logo-gradient.svg")`

### `icon()`

`icon(name: string): icon`

- Devolve um valor que é renderizado como ícone numa vista. O nome do ícone deve corresponder a um ícone Lucide suportado.
- Exemplo: `icon("arrow-right")`.

### `link()`

`link(path: string | file, display?: value): Link`

- Analisa uma string `path` e devolve um objeto Link que é renderizado como uma ligação para o caminho indicado.
- Forneça opcionalmente o parâmetro `display` para alterar o texto apresentado na ligação.

### `list()`

`list(element: any): List`

- Se o elemento fornecido for uma lista, devolve-o sem modificações.
- Caso contrário, envolve o `element` fornecido numa lista, criando uma lista com um único elemento.
- Esta função pode ser útil quando uma propriedade contém uma mistura de strings ou listas em todo o cofre.
- Exemplo: `list("value")` devolve `["value"]`.

### `max()`

`max(value1: number, value2: number...): number`

- Devolve o maior de todos os números fornecidos.

### `min()`

`min(value1: number, value2: number...): number`

- Devolve o menor de todos os números fornecidos.

### `now()`

`now(): date`

- `now()` devolve um objeto de data representando o momento atual.

### `number()`

`number(input: any): number`

- Tenta devolver o valor fornecido como número.
- Os objetos de data serão devolvidos como milissegundos desde a época unix.
- Os booleanos devolverão 1 ou 0.
- As strings serão analisadas como número e devolverão um erro se o resultado for inválido.
- Exemplo: `number("3.4")` devolve `3.4`.

### `duration()`

`duration(value: string): duration`

- Analisa uma string como uma duração. Consulte a [[Sintaxe de Bases#Date arithmetic|secção de aritmética de datas]] para o formato da string `value`.
- As durações não precisam de ser explicitamente analisadas ao realizar aritmética de datas (por exemplo, `now() + '1d'`), mas precisam ao realizar aritmética em durações (por exemplo, `now() + (duration('1d') * 2)`).
- Ao realizar aritmética em durações com escalares, a duração deve estar à esquerda. Por exemplo `duration('5h') * 2`, em vez de `2 * duration('5h')`.

### `today()`

`today(): date`

- `today()` devolve um objeto de data representando a data atual. A parte de hora é definida como zero.

### `random()`

`random(): number`

- `random()` devolve um número aleatório entre 0 e 1.
- A geração do número é atualizada sempre que uma vista é carregada. Navegar entre vistas altera o número aleatório.

## Any

Funções que pode utilizar com qualquer valor. Inclui strings (por exemplo, `"hello"`), números (por exemplo, `42`), listas (por exemplo, `[1,2,3]`), objetos, e muito mais.

### `isTruthy()`

`any.isTruthy(): boolean`

- Devolve o valor convertido num booleano.
- Exemplo: `1.isTruthy()` devolve `true`.

### `isType()`

`any.isType(type: string): boolean`

- Devolve true se o valor for do tipo fornecido.
- Exemplo: `"example".isType("string")` e `true.isType("boolean")` ambos devolvem true.

### `toString()`

`any.toString(): string`

- Devolve a representação em string de qualquer valor.
- Exemplo: `123.toString()` devolve `"123"`.

## Date

Funções que pode utilizar com uma data e hora, como `date("2025-05-27")`. As comparações de datas podem ser feitas utilizando [[Sintaxe de Bases#Date arithmetic|aritmética de datas]].

### Fields

Os seguintes campos estão disponíveis para datas:

| Campo              | Tipo     | Descrição                       |
| ------------------ | -------- | ------------------------------- |
| `date.year`        | `number` | O ano da data                   |
| `date.month`       | `number` | O mês da data (1–12)            |
| `date.day`         | `number` | O dia do mês                    |
| `date.hour`        | `number` | A hora (0–23)                   |
| `date.minute`      | `number` | O minuto (0–59)                 |
| `date.second`      | `number` | O segundo (0–59)                |
| `date.millisecond` | `number` | O milissegundo (0–999)          |

### `date()`

`date.date(): date`

- Devolve um objeto de data com a hora removida.
- Exemplo: `now().date().format("YYYY-MM-DD HH:mm:ss")` devolve uma string como "2025-12-31 00:00:00"

### `format()`

`date.format(format: string): string`

- `format` é a string de formato (por exemplo, `"YYYY-MM-DD"`).
- Devolve a data formatada conforme especificado por uma string de formato Moment.js.
- Exemplo: `date.format("YYYY-MM-DD")` devolve `"2025-05-27"`.

### `time()`

`date.time(): string`

- Devolve a hora.
- Exemplo: `now().time()` devolve uma string como "23:59:59"

### `relative()`

`date.relative(): string`

- Devolve uma comparação legível da data com a data e hora atuais.
- Exemplo: `file.mtime.relative()` devolve um valor como `3 days ago`.

### `isEmpty()`

`date.isEmpty(): boolean`

- Devolve false.

## String

Funções que pode utilizar com uma sequência de caracteres, como `"hello"`.

### Fields

| Campo           | Tipo     | Descrição                               |
| --------------- | -------- | --------------------------------------- |
| `string.length` | `number` | O número de caracteres na string        |

### `contains()`

`string.contains(value: string): boolean`

- `value` é a substring a procurar.
- Devolve true se a string contiver `value`.
- Exemplo: `"hello".contains("ell")` devolve `true`.

### `containsAll()`

`string.containsAll(...values: string): boolean`

- `values` são uma ou mais substrings a procurar.
- Devolve true se a string contiver todos os `values`.
- Exemplo: `"hello".containsAll("h", "e")` devolve `true`.

### `containsAny()`

`string.containsAny(...values: string): boolean`

- `values` são uma ou mais substrings a procurar.
- Devolve true se a string contiver pelo menos um dos `values`.
- Exemplo: `"hello".containsAny("x", "y", "e")` devolve `true`.

### `endsWith()`

`string.endsWith(query: string): boolean`

- `query` é a string a verificar no final.
- Devolve true se esta string terminar com `query`.
- Exemplo: `"hello".endsWith("lo")` devolve `true`.

### `isEmpty()`

`string.isEmpty(): boolean`

- Devolve true se a string não tiver caracteres ou não estiver presente.
- Exemplo: `"Hello world".isEmpty()` devolve `false`.
- Exemplo: `"".isEmpty()` devolve `true`.

### `lower()`

`string.lower(): string`

- Devolve a string convertida para minúsculas.

### `replace()`

`string.replace(pattern: string | Regexp, replacement: string): string`

- `pattern` é o valor a procurar na string alvo.
- `replacement` é o valor com que substituir os padrões encontrados.
- Se `pattern` for uma string, todas as ocorrências do padrão serão substituídas.
- Se `pattern` for um Regexp, o indicador `g` determina se apenas a primeira ou todas as ocorrências são substituídas.
- Exemplo: `""a:b:c:d".replace(/:/, "-")` devolve `"a-b,c,d"`, enquanto `"a:b:c:d".replace(/:/g, "-")` devolve `"a-b-c-d"`.

### `repeat()`

`string.repeat(count: number): string`

- `count` é o número de vezes para repetir a string.
- Exemplo: `"123".repeat(2)` devolve `"123123"`

### `reverse()`

`string.reverse(): string`

- Inverte a string.
- Exemplo: `"hello".reverse()` devolve `"olleh"`.

### `slice()`

`string.slice(start: number, end?: number): string`

- `start` é o índice inicial inclusivo.
- `end` é o índice final exclusivo opcional.
- Devolve uma substring de `start` (inclusivo) a `end` (exclusivo).
- Exemplo: `"hello".slice(1, 4)` devolve `"ell"`.
- Se `end` for omitido, vai até ao final da string.

### `split()`

`string.split(separator: string | Regexp, n?: number): list`

- `separator` é o delimitador para dividir a string.
- `n` é um número opcional. Se fornecido, o resultado terá os primeiros `n` elementos.
- Devolve uma lista de substrings.
- Exemplo: `"a,b,c,d".split(",", 3)` ou `"a,b,c,d".split(/,/, 3)` devolve `["a", "b", "c"]`.

### `startsWith()`

`string.startsWith(query: string): boolean`

- `query` é a string a verificar no início.
- Devolve true se esta string começar com `query`.
- Exemplo: `"hello".startsWith("he")` devolve `true`.

### `title()`

`string.title(): string`

- Converte a string para capitalização de título (primeira letra de cada palavra em maiúscula).
- Exemplo: `"hello world".title()` devolve `"Hello World"`.

### `trim()`

`string.trim(): string`

- Remove espaços em branco de ambas as extremidades da string.
- Exemplo: `"  hi  ".trim()` devolve `"hi"`.

## Number

Funções que pode utilizar com valores numéricos como `42`, `3.14`.

### `abs()`

`number.abs(): number`

- Devolve o valor absoluto do número.
- Exemplo: `(-5).abs()` devolve `5`.

### `ceil()`

`number.ceil(): number`

- Arredonda o número para o inteiro superior.
- Exemplo: `(2.1).ceil()` devolve `3`.

### `floor()`

`number.floor(): number`

- Arredonda o número para o inteiro inferior.
- Exemplo: `(2.9).floor()` devolve `2`.

### `isEmpty()`

`number.isEmpty(): boolean`

- Devolve true se o número não estiver presente.
- Exemplo: `5.isEmpty()` devolve `false`.

### `round()`

`number.round(digits: number): number`

- Arredonda o número para o inteiro mais próximo.
- Opcionalmente, forneça um parâmetro `digits` para arredondar para esse número de casas decimais.
- Exemplo: `(2.5).round()` devolve `3`, e `(2.3333).round(2)` devolve `2.33`.

### `toFixed()`

`number.toFixed(precision: number): string`

- `precision` é o número de casas decimais.
- Devolve uma string com o número em notação de vírgula fixa.
- Exemplo: `(3.14159).toFixed(2)` devolve `"3.14"`.

## List

Funções que pode utilizar com uma lista ordenada de elementos como `[1, 2, 3]`.

### Fields

| Campo         | Tipo     | Descrição                           |
| ------------- | -------- | ----------------------------------- |
| `list.length` | `number` | O número de elementos na lista      |

### `contains()`

`list.contains(value: any): boolean`

- `value` é o elemento a procurar.
- Devolve true se a lista contiver `value`.
- Exemplo: `[1,2,3].contains(2)` devolve `true`.

### `containsAll()`

`list.containsAll(...values: any): boolean`

- `values` são um ou mais elementos a procurar.
- Devolve true se a lista contiver todos os `values`.
- Exemplo: `[1,2,3].containsAll(2,3)` devolve `true`.

### `containsAny()`

`list.containsAny(...values: any): boolean`

- `values` são um ou mais elementos a procurar.
- Devolve true se a lista contiver pelo menos um dos `values`.
- Exemplo: `[1,2,3].containsAny(3,4)` devolve `true`.

### `filter()`

`list.filter(value: Boolean): list`

- Filtra os elementos desta lista chamando uma função de filtro, que utiliza as variáveis `index` e `value`, e devolve um valor booleano indicando se o elemento deve ser mantido.
- `value` é o valor de um item na lista.
- `index` é o índice do valor atual.
- Exemplo: `[1,2,3,4].filter(value > 2)` devolve `[3,4]`.

### `flat()`

`list.flat(): list`

- Achata listas aninhadas numa única lista.
- Exemplo: `[1,[2,3]].flat()` devolve `[1,2,3]`.

### `isEmpty()`

`list.isEmpty(): boolean`

- Devolve true se a lista não tiver elementos.
- Exemplo: `[1,2,3].isEmpty()` devolve `false`.

### `join()`

`list.join(separator: string): string`

- `separator` é a string a inserir entre os elementos.
- Junta todos os elementos da lista numa única string.
- Exemplo: `[1,2,3].join(",")` devolve `"1,2,3"`.

### `map()`

`list.map(value: Any): list`

- Transforma cada elemento desta lista chamando uma função de conversão, que utiliza as variáveis `index` e `value`, e devolve o novo valor a colocar na lista.
- `value` é o valor de um item na lista.
- `index` é o índice do valor atual.
- Exemplo: `[1,2,3,4].map(value + 1)` devolve `[2,3,4,5]`.

### `reduce()`

`list.reduce(expression: Any, acc: Any): Any`

- Reduz os elementos desta lista a um único valor executando uma expressão para cada elemento. A expressão pode utilizar as variáveis `index`, `value` e `acc` (o acumulador), e deve devolver o próximo valor do acumulador.
- `expression` é avaliada para cada elemento da lista.
- `value` é o valor do item atual na lista.
- `index` é o índice do item atual.
- `acc` é o valor acumulado até ao momento.
- Exemplo (soma): `[1,2,3].reduce(acc + value, 0)` devolve `6`.
- Exemplo (máximo): `values.filter(value.isType("number")).reduce(if(acc == null || value > acc, value, acc), null)` devolve o maior número, ou `null` se não existir nenhum.

### `reverse()`

`list.reverse(): list`

- Inverte a lista no local.
- Exemplo: `[1,2,3].reverse()` devolve `[3,2,1]`.

### `slice()`

`list.slice(start: number, end?: number): list`

- `start` é o índice inicial inclusivo.
- `end` é o índice final exclusivo opcional.
- Devolve uma cópia superficial de uma porção da lista de `start` (inclusivo) a `end` (exclusivo).
- Exemplo: `[1,2,3,4].slice(1,3)` devolve `[2,3]`.
- Se `end` for omitido, vai até ao final da lista.

### `sort()`

`list.sort(): list`

- Ordena os elementos da lista do menor para o maior.
- Exemplo: `[3, 1, 2].sort()` devolve `[1, 2, 3]`.
- Exemplo: `["c", "a", "b"].sort()` devolve `["a", "b", "c"]`.

### `unique()`

`list.unique(): list`

- Remove elementos duplicados.
- Exemplo: `[1,2,2,3].unique()` devolve `[1,2,3]`.

## Link

Funções que pode utilizar numa ligação. As ligações podem ser criadas a partir de um ficheiro (`file.asLink()`) ou de um caminho (`link("path")`).

### `asFile()`

`link.asFile(): file`

- Devolve um objeto de ficheiro se a ligação se referir a um ficheiro local válido.
- Exemplo: `link("[[filename]]").asFile()`

### `linksTo()`

`link.linksTo(file): boolean`

- Devolve se o ficheiro representado pela `link` tem uma ligação para `file`.

## File

Funções que pode utilizar com ficheiros no cofre.

### Fields

Os seguintes campos estão disponíveis para ficheiros:

| Campo             | Tipo     | Descrição                                                       |
| ----------------- | -------- | --------------------------------------------------------------- |
| `file.name`       | `string` | O nome deste ficheiro.                                          |
| `file.basename`   | `string` | O nome deste ficheiro sem a extensão.                           |
| `file.path`       | `string` | O caminho completo para este ficheiro, relativo à raiz do cofre.|
| `file.folder`     | `string` | O caminho completo para a pasta pai.                            |
| `file.ext`        | `string` | A extensão do ficheiro.                                         |
| `file.size`       | `number` | O tamanho deste ficheiro, em bytes.                             |
| `file.properties` | `object` | As propriedades da nota para este ficheiro.                     |
| `file.tags`       | `list`   | As etiquetas deste ficheiro. Inclui etiquetas inline.           |
| `file.links`      | `list`   | As ligações internas neste ficheiro.                            |
| `file.ctime`      | `date`   | Timestamp de quando este ficheiro foi criado.                   |
| `file.mtime`      | `date`   | Timestamp de quando este ficheiro foi modificado pela última vez.|

### `asLink()`

`file.asLink(display?: string): Link`

- `display` texto de apresentação opcional para a ligação.
- Devolve um objeto Link que é renderizado como uma ligação funcional.
- Exemplo: `file.asLink()`

### `hasLink()`

`file.hasLink(otherFile: file | string): boolean`

- `otherFile` é outro objeto de ficheiro ou caminho de string a verificar.
- Devolve true se `file` ligar a `otherFile`.
- Exemplo: `file.hasLink(otherFile)` devolve `true` se existir uma ligação de `file` para `otherFile`.

### `hasProperty()`

`file.hasProperty(name: string): boolean`

- Devolve true se a nota tiver a propriedade de ficheiro indicada.

### `hasTag()`

`file.hasTag(...values: string): boolean`

- `values` são um ou mais nomes de etiqueta.
- Devolve true se o ficheiro tiver alguma das etiquetas em `values`.
- Exemplo: `file.hasTag("tag1", "tag2")` devolve `true` se o ficheiro tiver a etiqueta `#tag1` ou `#tag2`. Também inclui quaisquer [[Tags#Nested tags|etiquetas aninhadas]], como `#tag1/a` ou `#tag2/b`.

### `inFolder()`

`file.inFolder(folder: string): boolean`

- `folder` é o nome da pasta a verificar.
- Devolve true se o ficheiro estiver na pasta especificada ou numa das suas subpastas.
- Exemplo: `file.inFolder("notes")` devolve `true`.

## Object

Funções que pode utilizar com uma coleção de pares chave-valor como `{"a": 1, "b": 2}`.

### `isEmpty()`

`object.isEmpty(): boolean`

- Devolve true se o objeto não tiver propriedades próprias.
- Exemplo: `{}.isEmpty()` devolve `true`.

### `keys()`

`object.keys(): list`

- Devolve uma lista com as chaves do objeto.

### `values()`

`object.values(): list`

- Devolve uma lista com os valores do objeto.

## Regular expression

Funções que pode utilizar com um padrão de expressão regular. Exemplo: `/abc/`.

### `matches()`

`regexp.matches(value: string): boolean`

- `value` é a string a testar.
- Devolve true se a expressão regular corresponder a `value`.
- Exemplo: `/abc/.matches("abcde")` devolve `true`.
