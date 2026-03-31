---
localized: false
permalink: obsidian-flavored-markdown
publish: true
mobile: true
description: 'Learn about Obsidian Flavored Markdown, including supported extensions and how Markdown interacts with HTML elements.'
---

Obsidian strives for maximum capability without breaking any existing formats. As a result, we use a combination of flavors of [[Sintaxe de formatação básica|Markdown]].

Obsidian supports [CommonMark](https://commonmark.org/), [GitHub Flavored Markdown](https://github.github.com/gfm/), and [LaTeX](https://www.latex-project.org/). 

> [!tip]- Markdown inside HTML
> Obsidian does not render Markdown syntax inside HTML elements. This is an intentional design choice for performance optimization and to keep parser complexity low when managing large documents.
>
> For example, Markdown formatting like `**bold**` or `` `code` `` will not be processed inside `<div>`, `<span>`, `<table>`, or any other HTML tags.
>
> ```md
> <div>
> This **will not** be bold.
> </div>
> ```

### Supported Markdown extensions

| Syntax          | Description                                                           |
| --------------- | --------------------------------------------------------------------- |
| `[[Link]]`      | [[Links internos]]                                                    |
| `![[Link]]`     | [[Incorporar ficheiros]]                                                       |
| `![[Link#^id]]` | [[Links internos#Link to a block in a note\|Block references]]        |
| `^id`           | [[Links internos#Link to a block in a note\|Defining a block]]        |
| `[^id]`         | [[Sintaxe de formatação básica#Footnotes\|Footnotes]]                      |
| `%%Text%%`      | [[Sintaxe de formatação básica#Comments\|Comments]]                        |
| `~~Text~~`      | [[Sintaxe de formatação básica#Bold, italics, highlights\|Strikethroughs]] |
| `==Text==`      | [[Sintaxe de formatação básica#Bold, italics, highlights\|Highlights]]     |
| `` ``` ``       | [[Sintaxe de formatação básica#Code blocks\|Code blocks]]                  |
| `- [ ]`         | [[Sintaxe de formatação básica#Task lists\|Incomplete task]]               |
| `- [x]`         | [[Sintaxe de formatação básica#Task lists\|Completed task]]                |
| `> [!note]`     | [[Callouts]]                                                          |
| (see link)      | [[Sintaxe de formatação avançada#Tables\|Tables]]                         |
