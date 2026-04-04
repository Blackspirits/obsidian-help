---
aliases:
  - Advanced topics/HTML sanitization
  - Editing and formatting/Using HTML
  - Editing and formatting/HTML content
description: Aprenda a usar HTML no Obsidian, incluindo limitações na renderização de Markdown e requisitos de blocos HTML.
mobile: true
permalink: html
publish: true
---

O Obsidian suporta HTML para lhe permitir apresentar as suas notas da forma que desejar, ou mesmo [[Incorporar páginas web|incorporar páginas web]]. Permitir HTML nas suas notas acarreta riscos. Para evitar que código malicioso cause danos, o Obsidian _sanitiza_ qualquer HTML nas suas notas.

> [!example]
> O elemento `<script>` normalmente permite executar JavaScript sempre que carrega. Se o Obsidian não sanitizasse o HTML, um atacante poderia convencê-lo a colar um texto contendo JavaScript que extrai informações sensíveis do seu computador e as envia de volta para eles.

Dito isto, uma vez que a sintaxe Markdown não suporta todas as formas de estilização, o uso de HTML sanitizado pode ser mais uma forma de melhorar a qualidade das suas notas. Incluímos alguns dos usos mais comuns de HTML.

## Limitações do HTML

O Obsidian tem limitações específicas ao usar HTML nas suas notas:

### Sem Markdown dentro de HTML

O Obsidian não renderiza sintaxe Markdown dentro de elementos HTML. Esta é uma escolha de design intencional para otimização de desempenho e para manter a complexidade do parser baixa ao gerir documentos grandes.

Por exemplo, isto não funcionará como esperado:

```md
<div>
Este **não ficará** a negrito e este `não será` código.
</div>
```

### Os blocos HTML devem ser autossuficientes

Os blocos HTML devem ser completos e não podem conter linhas em branco entre eles. As linhas em branco quebrarão o bloco HTML.

Isto funcionará:

```md
<table>
<tr>
<td>Conteúdo aqui</td>
</tr>
</table>
```

Isto não funcionará corretamente:

```md
<table>

<tr>

<td>Conteúdo aqui</td>

</tr>

</table>
```

### Quando o Markdown parece funcionar em HTML

Algumas tags HTML inline como `<span>` ou `<a>` têm funcionalidade limitada e podem parecer renderizar Markdown, mas não é isso que está a acontecer. O Markdown está a ser processado fora do contexto HTML.

Para mais detalhes sobre como o Obsidian trata o Markdown, consulte [[Obsidian Flavored Markdown]].

## Uso comum de HTML

> [!info] Mais detalhes sobre o uso de `<iframe>` podem ser encontrados em [[Incorporar páginas web]].

### Comentários

Os [[Sintaxe de formatação básica#Comments|comentários Markdown]] são a forma preferida de adicionar comentários ocultos nas suas notas. No entanto, alguns métodos de conversão de notas Markdown, como o [Pandoc](https://pandoc.org), têm suporte limitado a comentários Markdown. Nesses casos, pode usar `<!-- Comentário HTML -->` em vez disso!

### Sublinhado

Se precisar de sublinhar rapidamente um item nas suas notas, pode usar `<u>Exemplo</u>` para criar <u>o seu texto sublinhado</u>.

### Span/Div

As tags span e div podem ser usadas para aplicar classes personalizadas de um [[Fragmentos CSS|fragmento CSS]], ou estilização definida de forma personalizada, a uma área selecionada de texto. Por exemplo, usar `<span style="font-family: cursive">o seu texto</span>` pode permitir-lhe <span style="font-family: cursive">alterar rapidamente o tipo de letra</span>.

## Tachado

Precisa de tachar <s>algum texto</s>? Use `<s>isto</s>` para o tachar.
