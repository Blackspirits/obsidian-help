---
permalink: publish/headless
cssclasses:
  - reference
description: O Obsidian Publish oferece um cliente headless para publicar cofres sem usar a aplicação de ambiente de trabalho. Útil para pipelines de CI e fluxos de trabalho automatizados.
---
O [[Introdução ao Obsidian Publish|Obsidian Publish]] oferece um cliente headless para publicar cofres sem usar a aplicação de ambiente de trabalho. Útil para pipelines de CI e fluxos de trabalho automatizados. Publique as suas alterações mais recentes de forma agendada ou como parte de um pipeline de compilação.

Instale o [[Obsidian Headless]] **(beta aberto)** para interagir com o [[Introdução ao Obsidian Publish|Obsidian Publish]] a partir da linha de comandos sem a aplicação de ambiente de trabalho do Obsidian.

## Início rápido

Instale o [[Obsidian Headless|Obsidian Headless]] **(beta aberto)**:

```shell
npm install -g obsidian-headless
```

Deve ter uma [[Introdução ao Obsidian Publish|subscrição ativa do Obsidian Publish]].

```shell
# Iniciar sessão
ob login

# Listar os seus sites Publish
ob publish-list-sites

# Ligar um cofre local a um site Publish
cd ~/vaults/my-vault
ob publish-setup --site "my-site"

# Pré-visualizar alterações sem publicar
ob publish --dry-run

# Publicar alterações
ob publish
```

## Comandos

### `ob publish-list-sites`

Lista todos os sites Publish disponíveis na sua conta.

### `ob publish-create-site`

Cria um novo site Publish.

```
ob publish-create-site --slug <slug>
```

| Opção | Descrição |
| --- | --- |
| `--slug` | Identificador de URL para o seu site (ex.: `my-notes` cria `publish.obsidian.md/my-notes`) |

### `ob publish-setup`

Liga um cofre local a um site Publish.

```
ob publish-setup [--site <id-or-slug>] [--path <local-path>]
```

| Opção | Descrição |
| --- | --- |
| `--site` | ID ou slug do site |
| `--path` | Caminho local do cofre (predefinição: diretório atual) |

### `ob publish`

Publica as alterações do cofre no seu site. Por predefinição, apenas os ficheiros com `publish: true` no frontmatter são incluídos.

```
ob publish [--path <local-path>] [--all] [--dry-run] [--yes]
```

| Opção | Descrição |
| --- | --- |
| `--path` | Caminho local do cofre (predefinição: diretório atual) |
| `--all` | Inclui todos os ficheiros, não apenas os que têm a indicação de publicação |
| `--dry-run` | Mostra as alterações sem publicar |
| `--yes` | Publica sem pedir confirmação |

### `ob publish-config`

Visualiza ou altera as definições de inclusão/exclusão de pastas para um cofre. Execute sem opções para mostrar a configuração atual.

```
ob publish-config [--path <local-path>] [options]
```

| Opção | Descrição |
| --- | --- |
| `--path` | Caminho local do cofre (predefinição: diretório atual) |
| `--includes` | Pastas a incluir, separadas por vírgula (cadeia vazia para limpar) |
| `--excludes` | Pastas a excluir, separadas por vírgula (cadeia vazia para limpar) |

### `ob publish-site-options`

Visualiza ou atualiza as definições globais de apresentação e navegação do site. Execute sem opções para mostrar as definições atuais.

```
ob publish-site-options [--path <local-path>] [options]
```

| Opção | Descrição |
| --- | --- |
| `--path` | Caminho local do cofre (predefinição: diretório atual) |
| `--site-name` | Nome do site |
| `--index-file` | Caminho do ficheiro da página inicial |
| `--logo` | Caminho do ficheiro do logótipo (cadeia vazia para limpar) |
| `--show-navigation` | Mostrar barra lateral de navegação |
| `--show-graph` | Mostrar vista de grafo |
| `--show-outline` | Mostrar índice |
| `--show-search` | Mostrar pesquisa |
| `--show-backlinks` | Mostrar links inversos |
| `--show-hover-preview` | Mostrar pré-visualização ao passar o cursor |
| `--show-theme-toggle` | Mostrar botão de alternância de tema |
| `--default-theme` | Tema predefinido: `light` ou `dark` |
| `--readable-line-length` | Comprimento de linha legível |
| `--strict-line-breaks` | Quebras de linha estritas |
| `--hide-title` | Ocultar título em linha |
| `--sliding-window` | Modo de janela deslizante |
| `--nav-order` | Ordem de navegação, caminhos separados por vírgula (cadeia vazia para limpar) |
| `--nav-hidden` | Itens de navegação ocultos, caminhos separados por vírgula (cadeia vazia para limpar) |

### `ob publish-unlink`

Desliga um cofre de um site Publish.

```
ob publish-unlink [--path <local-path>]
```
