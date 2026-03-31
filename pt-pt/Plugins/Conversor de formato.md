---
permalink: plugins/format-converter
publish: true
mobile: true
description: Format converter is a core plugin that lets you convert Markdown from other applications to Obsidian format.
---

O Conversor de formato é um [[Plugins nativos|plugin nativo]] que lhe permite converter Markdown de outras aplicações para o formato do Obsidian. Também lhe permite converter determinadas [[Propriedades]] para os novos formatos requeridos.

> [!warning] Aviso
> O Conversor de formato converte o seu cofre inteiro com base nas suas definições. [[Criar cópia de segurança dos seus ficheiros do Obsidian|Crie uma cópia de segurança]] antes de realizar a conversão.

Para converter todas as notas do seu cofre:

1. Na [[Paleta de comandos]], selecione **Abrir conversor de formato**. Também pode encontrá-lo na [[Faixa de opções]] com o ícone **Abrir conversor de formato** ![[lucide-binary.svg#icon]].
2. Ative os formatos que pretende converter.
3. Clique em **Iniciar conversão**.

Para mais informações, consulte [[Sintaxe de formatação básica]].

## Formatos suportados

### Roam Research

O Conversor de formato pode converter a seguinte sintaxe do Roam Research:

- **Tags**: Converte `#tag` e `#[[tag]]` para `[[tag]]`
- **Destaques**: Converte `^^destaque^^` para `==destaque==`
- **Itens de tarefas**: Converte `{{[[TODO]]}}` para `[ ]`

### Bear

O Conversor de formato pode converter a seguinte sintaxe do Bear:

- **Destaques**: Converte `::destaque::` para `==destaque==`

### Zettelkasten

O Conversor de formato pode converter a seguinte sintaxe do Zettelkasten:

- **Ligações completas**: Converte `[[UID]]` para `[[UID Nome do ficheiro]]`
- **Ligações formatadas**: Converte `[[UID]]` para `[[UID Nome do ficheiro|Nome do ficheiro]]`

### [[Propriedades]]

A partir do Obsidian `1.9.3`, o Conversor de formato pode converter formatos de [[Propriedades#Deprecated properties|propriedades obsoletas]] para o formato atual:

**Apelidos**

```yaml
# Antes

alias: O Título da Minha Nota

# Depois

aliases:
  - O Título da Minha Nota
```

**Tags**

```yaml
# Antes

tag: projeto, importante

# Depois

tags:
  - projeto
  - importante
```

**Classes CSS**

```yaml
# Antes

cssclass: estilo-personalizado

# Depois

cssclasses:
  - estilo-personalizado
```
