---
aliases:
  - Obsidian Markdown
description: Saiba mais sobre o Obsidian Flavored Markdown, incluindo extensões suportadas e como o Markdown interage com elementos HTML.
mobile: true
permalink: obsidian-flavored-markdown
publish: true
---

O Obsidian visa a máxima capacidade sem quebrar formatos existentes. Como resultado, usamos uma combinação de variantes do [[Sintaxe de formatação básica|Markdown]].

O Obsidian suporta [CommonMark](https://commonmark.org/), [GitHub Flavored Markdown](https://github.github.com/gfm/) e [LaTeX](https://www.latex-project.org/).

> [!tip]- Markdown dentro de HTML
> O Obsidian não renderiza sintaxe Markdown dentro de elementos HTML. Esta é uma escolha de design intencional para otimização de desempenho e para manter a complexidade do parser baixa ao gerir documentos grandes.
>
> Por exemplo, a formatação Markdown como `**negrito**` ou `` `código` `` não será processada dentro de `<div>`, `<span>`, `<table>` ou quaisquer outras tags HTML.
>
> ```md
> <div>
> Este **não ficará** a negrito.
> </div>
> ```

### Extensões Markdown suportadas

| Sintaxe         | Descrição                                                                         |
| --------------- | --------------------------------------------------------------------------------- |
| `[[Link]]`      | [[Links internos]]                                                                |
| `![[Link]]`     | [[Incorporar ficheiros]]                                                          |
| `![[Link#^id]]` | [[Links internos#Link to a block in a note\|Referências de bloco]]                |
| `^id`           | [[Links internos#Link to a block in a note\|Definir um bloco]]                    |
| `[^id]`         | [[Sintaxe de formatação básica#Footnotes\|Notas de rodapé]]                       |
| `%%Texto%%`     | [[Sintaxe de formatação básica#Comments\|Comentários]]                            |
| `~~Texto~~`     | [[Sintaxe de formatação básica#Bold, italics, highlights\|Tachado]]               |
| `==Texto==`     | [[Sintaxe de formatação básica#Bold, italics, highlights\|Realce]]                |
| `` ``` ``       | [[Sintaxe de formatação básica#Code blocks\|Blocos de código]]                    |
| `- [ ]`         | [[Sintaxe de formatação básica#Task lists\|Tarefa incompleta]]                    |
| `- [x]`         | [[Sintaxe de formatação básica#Task lists\|Tarefa concluída]]                     |
| `> [!note]`     | [[Callouts]]                                                                      |
| (ver ligação)   | [[Sintaxe de formatação avançada#Tables\|Tabelas]]                                |
