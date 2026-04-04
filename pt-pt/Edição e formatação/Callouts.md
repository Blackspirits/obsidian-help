---
aliases:
  - How to/Use callouts
description: Esta página explica como usar callouts para incluir conteúdo adicional sem interromper o fluxo das suas notas.
mobile: true
permalink: callouts
publish: true
---

Use callouts para incluir conteúdo adicional sem interromper o fluxo das suas notas.

Para criar um callout, adicione `[!info]` à primeira linha de uma citação em bloco, onde `info` é o _identificador de tipo_. O identificador de tipo determina o aspeto e comportamento do callout. Para ver todos os tipos disponíveis, consulte [[#Tipos suportados]]. Os callouts também são suportados nativamente no [[Introdução ao Obsidian Publish|Obsidian Publish]].

```markdown
> [!info] Título do callout
> Aqui está um bloco callout.
> Suporta **Markdown**, [[Internal link|Wikilinks]], e [[Incorporar ficheiros|incorporações]]!
> ![[Engelbart.jpg]]
```

> [!info] Título do callout
> Aqui está um bloco callout.
> Suporta **Markdown**, [[Links internos|Wikilinks]] e [[Incorporar ficheiros|incorporações]]!
> ![[Engelbart.jpg]]

Pode inserir um callout `[!note]` predefinido usando o [[Paleta de comandos|comando]] `Inserir callout`. O cursor posiciona-se automaticamente no campo do nome do callout, permitindo-lhe eliminar o nome predefinido e escrever um novo antes de editar o conteúdo.

Para envolver conteúdo existente num callout, selecione o texto (incluindo listas, blocos de código, etc.) e execute o comando `Inserir callout`. O conteúdo selecionado será automaticamente encerrado no callout.

No [[Vistas e modo de edição#Live Preview|Live Preview]], também pode clicar com o botão direito no nome do callout para alterar o tipo de callout.


### Alterar o título

Por predefinição, o título do callout é o seu identificador de tipo com maiúsculas iniciais. Pode alterá-lo adicionando texto após o identificador de tipo:

```markdown
> [!tip] Os callouts podem ter títulos personalizados
> Como este.
```

> [!tip] Os callouts podem ter títulos personalizados
> Como este.

Pode inclusive omitir o corpo para criar callouts apenas com título:

```markdown
> [!tip] Callout só com título
```

> [!tip] Callout só com título

### Callouts recolhíveis

Pode tornar um callout recolhível adicionando um sinal de mais (`+`) ou de menos (`-`) imediatamente após o identificador de tipo.

Um sinal de mais expande o callout por predefinição, e um sinal de menos recolhe-o.

```markdown
> [!faq]- Os callouts são recolhíveis?
> Sim! Num callout recolhível, o conteúdo fica oculto quando o callout está recolhido.
```

> [!faq]- Os callouts são recolhíveis?
> Sim! Num callout recolhível, o conteúdo fica oculto quando recolhido.

### Callouts aninhados

Pode aninhar callouts em múltiplos níveis.

```markdown
> [!question] Os callouts podem ser aninhados?
> > [!todo] Sim!, podem.
> > > [!example]  Pode inclusive usar múltiplos níveis de aninhamento.
```

> [!question] Os callouts podem ser aninhados?
> > [!todo] Sim!, podem.
> > > [!example]  Pode inclusive usar múltiplos níveis de aninhamento.

### Personalizar callouts

Os [[Fragmentos CSS]] e os [[Plugins da comunidade]] podem definir callouts personalizados ou mesmo substituir a configuração predefinida.

Para definir um callout personalizado, crie o seguinte bloco CSS:

```css
.callout[data-callout="custom-question-type"] {
    --callout-color: 0, 0, 0;
    --callout-icon: lucide-alert-circle;
}
```

O valor do atributo `data-callout` é o identificador de tipo que pretende usar, por exemplo `[!custom-question-type]`.

- `--callout-color` define a cor de fundo usando números (0–255) para vermelho, verde e azul.
- `--callout-icon` pode ser um ID de ícone de [lucide.dev](https://lucide.dev), ou um elemento SVG.

> [!warning] Nota sobre versões de ícones Lucide
> O Obsidian atualiza os ícones Lucide periodicamente. A versão atual incluída é mostrada abaixo; use estes ou ícones anteriores em callouts personalizados.
> ![[Créditos#^lucide]]

> [!tip] Ícones SVG
> Em vez de usar um ícone Lucide, pode também usar um elemento SVG como ícone do callout.
>
> ```css
> --callout-icon: '<svg>...svg personalizado...</svg>';
> ```

### Tipos suportados

Pode usar vários tipos de callout e aliases. Cada tipo tem uma cor de fundo e ícone diferentes.

Para usar estes estilos predefinidos, substitua `info` nos exemplos por qualquer um destes tipos, como `[!tip]` ou `[!warning]`. Os tipos de callout também podem ser alterados clicando com o botão direito num callout no modo Live Preview.

A não ser que [[#Personalizar callouts]], qualquer tipo não suportado assume o tipo `note`. O identificador de tipo não distingue maiúsculas de minúsculas.

> [!note]
> ```md
> > [!note]
> > Lorem ipsum dolor sit amet
> ```

---

> [!abstract]-
> ```md
> > [!abstract]
> > Lorem ipsum dolor sit amet
> ```

Aliases: `summary`, `tldr`

---

> [!info]-
> ```md
> > [!info]
> > Lorem ipsum dolor sit amet
> ```

---

> [!todo]-
> ```md
> > [!todo]
> > Lorem ipsum dolor sit amet
> ```

---

> [!tip]-
> ```md
> > [!tip]
> > Lorem ipsum dolor sit amet
> ```

Aliases: `hint`, `important`

---

> [!success]-
> ```md
> > [!success]
> > Lorem ipsum dolor sit amet
> ```

Aliases: `check`, `done`

---

> [!question]-
> ```md
> > [!question]
> > Lorem ipsum dolor sit amet
> ```

Aliases: `help`, `faq`

---

> [!warning]-
>  ```md
> > [!warning]
> > Lorem ipsum dolor sit amet
> ```

Aliases: `caution`, `attention`

---

> [!failure]-
> ```md
> > [!failure]
> > Lorem ipsum dolor sit amet
> ```

Aliases: `fail`, `missing`

---

> [!danger]-
> ```md
> > [!danger]
> > Lorem ipsum dolor sit amet
> ```

Alias: `error`

---

> [!bug]-
> ```md
> > [!bug]
> > Lorem ipsum dolor sit amet
> ```

---

> [!example]-
> ```md
> > [!example]
> > Lorem ipsum dolor sit amet
> ```

---

> [!quote]-
> ```md
> > [!quote]
> > Lorem ipsum dolor sit amet
> ```

Alias: `cite`
