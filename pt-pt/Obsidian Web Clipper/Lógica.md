---
permalink: web-clipper/logic
description: 'Use condicionais, ciclos e atribuição de variáveis em modelos do Web Clipper.'
---
O [[Introdução ao Obsidian Web Clipper|Web Clipper]] suporta lógica de template para condicionais, ciclos e atribuição de variáveis. Esta sintaxe é inspirada nas linguagens de template [Twig](https://twig.symfony.com/) e [Liquid](https://shopify.github.io/liquid/).


> [!warning] Requer a versão mais recente
> As funcionalidades de lógica requerem o Obsidian Web Clipper 1.0.0, que ainda não foi aprovado em todas as lojas de extensões.

## Condicionais

Use `{% if %}` para incluir conteúdo condicionalmente com base em variáveis ou expressões.

```twig
{% if author %}
Autor: {{author}}
{% endif %}
```

Use `{% else %}` para fornecer conteúdo de fallback e `{% elseif %}` para encadear múltiplas condições:

```twig
{% if status == "published" %}
Artigo publicado
{% elseif status == "draft" %}
Artigo em rascunho
{% else %}
Estado desconhecido
{% endif %}
```

### Operadores de comparação

Os seguintes operadores de comparação são suportados:

| Operador | Descrição |
|----------|-----------|
| `==` | Igual a |
| `!=` | Diferente de |
| `>` | Maior que |
| `<` | Menor que |
| `>=` | Maior ou igual a |
| `<=` | Menor ou igual a |
| `contains` | Verificar se uma cadeia contém uma subcadeia, ou se uma matriz contém um valor |

Exemplos:
- `{% if title == "Home" %}` — igualdade de cadeia
- `{% if price >= 100 %}` — comparação numérica
- `{% if title contains "Review" %}` — verificação de subcadeia
- `{% if tags contains "important" %}` — pertença a uma matriz

### Operadores lógicos

Combine condições usando operadores lógicos:

| Operador | Alternativa | Descrição                              |
| -------- | ----------- | -------------------------------------- |
| `and`    | `&&`        | Ambas as condições devem ser verdade   |
| `or`     | \|\|        | Pelo menos uma condição deve ser verdade |
| `not`    | `!`         | Nega uma condição                      |

Exemplos:
- `{% if author and published %}` — ambos devem existir
- `{% if draft or archived %}` — qualquer condição
- `{% if not hidden %}` — negação
- `{% if (premium or featured) and published %}` — condições agrupadas

### Veracidade

Quando uma variável é usada sem um operador de comparação, é avaliada quanto à sua "veracidade":

- `false`, `null`, `undefined`, cadeia vazia `""` e `0` são considerados **falso**.
- Matrizes vazias `[]` são consideradas **falso**.
- Tudo o resto é **verdadeiro**.

```twig
{% if content %}
Tem conteúdo
{% endif %}
```

## Atribuir uma variável

Use `{% set %}` para criar ou modificar variáveis dentro do seu template:

```twig
{% set slug = title|lower|replace:" ":"-" %}
Ficheiro: {{slug}}.md
```

As variáveis podem ser definidas como:
- Outras variáveis: `{% set name = author %}`
- Literais: `{% set count = 5 %}` ou `{% set label = "Rascunho" %}`
- Expressões com filtros: `{% set excerpt = content|truncate:100 %}`
- Resultados de selector: `{% set comments = selector:.comment %}`

As variáveis definidas com `{% set %}` podem ser usadas na lógica de template subsequente e na saída `{{variável}}`.

## Fallbacks

Use o operador `??` para fornecer valores de fallback quando uma variável está vazia ou indefinida:

```twig
{{title ?? "Sem título"}}
```

Se `title` estiver vazio, indefinido ou falso, o valor de fallback `"Sem título"` será usado.

Este é um atalho para a instrução `if` equivalente:

```twig
{% if title %}{{title}}{% else %}Sem título{% endif %}
```

### Encadear fallbacks

Pode encadear múltiplos fallbacks:

```twig
{{title ?? headline ?? "Sem título"}}
```

Isto usará `title` se disponível, caso contrário `headline`, caso contrário a cadeia `"Sem título"`.

### Com filtros

Os filtros ligam-se mais fortemente do que `??`, portanto os filtros são aplicados antes da verificação de fallback:

```twig
{{title|upper ?? "SEM TÍTULO"}}
```

Isto aplica `upper` a `title` primeiro, depois recorre a `"SEM TÍTULO"` se o resultado estiver vazio. Para aplicar filtros ao valor de fallback, use parênteses ou expressões separadas:

```twig
{{title ?? "Sem título"|lower}}
```

Isto usará `title` se disponível, caso contrário aplica `lower` ao fallback, resultando em `"sem título"`.

## Ciclos

Use `{% for %}` para iterar sobre matrizes:

```twig
{% for item in schema:author %}
- {{item.name}}
{% endfor %}
```

### Fontes de ciclos

Pode iterar sobre:
- Matrizes de schema: `{% for item in schema:author %}`
- Resultados de selector: `{% for comment in selector:.comment %}`
- Variáveis definidas anteriormente: `{% set items = selector:.item %}{% for item in items %}`

### Variáveis de ciclo

Dentro de um ciclo, tem acesso a um objeto `loop` com as seguintes propriedades:

| Variável | Descrição |
|----------|-----------|
| `loop.index` | Iteração atual (indexada a partir de 1) |
| `loop.index0` | Iteração atual (indexada a partir de 0) |
| `loop.first` | `true` se for a primeira iteração |
| `loop.last` | `true` se for a última iteração |
| `loop.length` | Número total de itens |

```twig
{% for tag in tags %}
{{loop.index}}. {{tag}}
{% if loop.last %} (fim da lista){% endif %}
{% endfor %}
```

Para compatibilidade retroativa, também pode usar `item_index` (onde `item` é o nome da variável iteradora) para obter a posição com índice 0:

```twig
{% for tag in tags %}
{{tag_index}}. {{tag}}
{% endfor %}
```

### Aceder a elementos de matriz por índice

Use a notação de colchetes para aceder a elementos de matriz por índice:

```twig
{{items[0]}}
{{items[loop.index0]}}
```

Isto é útil quando precisa de aceder a itens de múltiplas matrizes em paralelo:

```twig
{% set transcripts = selector:.transcript-text %}
{% set timestamps = selector:.timestamp %}

{% for line in transcripts %}
{{timestamps[loop.index0]}} - {{line}}
{% endfor %}
```

A notação de colchetes também funciona com propriedades de objetos:

```twig
{{user["name"]}}
{{data["my-key"]}}
```

### Ciclos aninhados

Os ciclos podem ser aninhados para estruturas de dados complexas:

```twig
{% for section in sections %}
## {{section.title}}
{% for item in section.items %}
- {{item}}
{% endfor %}
{% endfor %}
```

## Combinar lógica

Os condicionais e ciclos podem ser combinados:

```twig
{% for item in items %}
{% if item.ative %}
- {{item.name}}
{% endif %}
{% endfor %}
```

## Ordem de avaliação

A lógica de template é processada na seguinte ordem:

1. **Lógica de template** — `{% if %}`, `{% for %}`, `{% set %}` e `{{variáveis}}` são avaliados primeiro
2. **Variáveis de prompt** — As [[Variáveis#Prompt variables|variáveis de prompt]] como `{{"resumir isto"|prompt}}` são enviadas ao Interpretador após a lógica de template estar completa

Isto significa que pode usar lógica de template para construir prompts dinamicamente, mas os resultados do prompt não estão disponíveis para uso em condicionais ou ciclos.
