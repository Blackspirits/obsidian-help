---
permalink: cli
description: Tudo o que consegue fazer no Obsidian pode ser feito a partir da linha de comandos.
---
O Obsidian CLI é uma interface de linha de comandos que permite controlar o Obsidian a partir do terminal — ideal para scripting, automação e integração com ferramentas externas.

Tudo o que consegue fazer no Obsidian pode ser feito pela linha de comandos. O Obsidian CLI inclui ainda [[#Developer commands|comandos de programador]] para aceder às ferramentas de desenvolvimento, inspecionar elementos, tirar capturas de ecrã, recarregar plugins e muito mais.

![[obsidian-cli.mp4#interface]]

> [!warning] Requer o instalador do Obsidian 1.12
> A utilização do CLI requer o instalador do Obsidian 1.12. Consulte o [[Atualizar o Obsidian#Installer updates|guia de atualização da versão do instalador]].

## Instalar o Obsidian CLI

Atualize para a [[Atualizar o Obsidian|versão mais recente do instalador do Obsidian]] (1.11.7) e para a [[Versões de acesso antecipado|versão de acesso antecipado]] mais recente (1.12.x).

Para ativar o Obsidian CLI:

1. Aceda a **[[Configurações]]** → **Geral**.
2. Ative a **Interface de linha de comandos**.
3. Siga as instruções para registar o Obsidian CLI.

Se tiver dificuldades a instalar o Obsidian CLI, consulte [[#Troubleshooting|Resolução de problemas]].

## Get started

O Obsidian CLI suporta comandos individuais e uma interface de utilizador em modo terminal (TUI) com ajuda interativa e preenchimento automático.

> [!info] A aplicação Obsidian tem de estar em execução
> O Obsidian CLI requer que a aplicação Obsidian esteja em execução. Se o Obsidian não estiver aberto, o primeiro comando que executar irá lançá-lo automaticamente.
>
> Pretende sincronizar sem a aplicação de secretária? Consulte [[Obsidian Headless|Obsidian Headless]].

### Executar um comando

Execute um comando individual sem abrir a TUI:

```shell
# Executar o comando de ajuda
obsidian help
```

### Usar a interface de terminal

Abra a TUI digitando `obsidian`. Os comandos seguintes podem ser introduzidos sem `obsidian`.

```shell
# Abrir a TUI e executar a ajuda
obsidian
help
```

A TUI suporta preenchimento automático, histórico de comandos e pesquisa inversa. Use `Ctrl+R` para pesquisar no histórico de comandos. Consulte [[#Keyboard shortcuts|Atalhos de teclado]] para ver todos os atalhos disponíveis.

## Exemplos

Alguns exemplos do que o Obsidian CLI consegue fazer.

### Uso do dia a dia

```shell
# Abrir a nota diária de hoje
obsidian daily

# Adicionar uma tarefa à nota diária
obsidian daily:append content="- [ ] Comprar mantimentos"

# Pesquisar no cofre
obsidian search query="notas de reunião"

# Ler o ficheiro ativo
obsidian read

# Listar todas as tarefas da nota diária
obsidian tasks daily

# Criar uma nova nota a partir de um modelo
obsidian create name="Viagem a Lisboa" template=Viagem

# Listar todas as etiquetas do cofre com contagens
obsidian tags counts

# Comparar duas versões de um ficheiro
obsidian diff file=README from=1 to=3
```

### Para programadores

Existem muitos [[#Developer commands|comandos de programador]] disponíveis para o desenvolvimento de plugins e temas. Estes comandos permitem que ferramentas de programação automática testem e depurem código automaticamente.

```shell
# Abrir as ferramentas de programador
obsidian devtools

# Recarregar um plugin da comunidade em desenvolvimento
obsidian plugin:reload id=o-meu-plugin

# Tirar uma captura de ecrã da aplicação
obsidian dev:screenshot path=captura.png

# Executar JavaScript na consola da aplicação
obsidian eval code="app.vault.getFiles().length"
```

## Como fazer

### Usar parâmetros e sinalizadores

Os comandos podem usar **parâmetros** e **sinalizadores**. A maioria dos comandos não requer qualquer parâmetro ou sinalizador. Os parâmetros obrigatórios estão marcados como `required`. Por exemplo:

```shell
# Criar uma nova nota com o nome predefinido "Sem título"
obsidian create
```

Um **parâmetro** recebe um valor, escrito como `parâmetro=valor`. Se o valor tiver espaços, coloque-o entre aspas:

```shell
# Criar uma nova nota chamada "Nota" com o conteúdo "Olá mundo"
obsidian create name=Nota content="Olá mundo"
```

Um **sinalizador** é um interruptor booleano sem valor. Inclua-o para o ativar; por exemplo, `open` e `overwrite` são sinalizadores:

```shell
# Criar uma nota e abri-la
obsidian create name=Nota content="Olá" open overwrite
```

Para conteúdo em várias linhas, use `\n` para nova linha e `\t` para tabulação.

```bash
obsidian create name=Nota content="# Título\n\nTexto do corpo"
```

### Escolher um cofre

Se o diretório de trabalho atual do terminal for uma pasta de cofre, esse cofre é usado por predefinição. Caso contrário, é utilizado o cofre atualmente ativo.

Use `vault=<nome>` ou `vault=<id>` para indicar um cofre específico. Este deve ser o primeiro parâmetro antes do comando:

```shell
obsidian vault=Notas daily
obsidian vault="O Meu Cofre" search query="teste"
```

Na TUI, use `vault:open <nome>` ou `<id>` para mudar para um cofre diferente.

### Escolher um ficheiro

Muitos comandos aceitam os parâmetros `file` e `path` para indicar um ficheiro específico. Se nenhum for fornecido, o comando utiliza o ficheiro ativo por predefinição.

- `file=<nome>` resolve o ficheiro usando a mesma lógica de resolução de ligações dos [[Links internos|wikilinks]], encontrando-o pelo nome sem precisar do caminho completo nem da extensão.
- `path=<caminho>` requer o caminho exato a partir da raiz do cofre, por exemplo `pasta/nota.md`.

```shell
# Equivalentes se "Recipe.md" for o único ficheiro com esse nome
obsidian read file=Recipe
obsidian read path="Templates/Recipe.md"
```

### Copiar resultado

Adicione `--copy` a qualquer comando para copiar o resultado para a área de transferência:

```shell
read --copy
search query="TODO" --copy
```


## Comandos gerais

### `help`

Mostra a lista de todos os comandos disponíveis.

| Parâmetro   | Descrição                              |
| ----------- | -------------------------------------- |
| `<command>` | Mostra a ajuda de um comando específico. |

### `version`

Mostra a versão do Obsidian.

### `reload`

Recarrega a janela da aplicação.

### `restart`

Reinicia a aplicação.


## Bases

Comandos para [[Introdução ao Bases|Bases]].

### `bases`

Lista todos os ficheiros `.base` no cofre.

### `base:views`

Lista as vistas do ficheiro de base atual.

### `base:create`

Cria um novo item numa base. Usa a vista de base ativa por predefinição, se não for indicado nenhum ficheiro.

```bash
file=<name>        # nome do ficheiro de base
path=<path>        # caminho do ficheiro de base
view=<name>        # nome da vista
name=<name>        # nome do novo ficheiro
content=<text>     # conteúdo inicial

open               # abrir o ficheiro após criação
newtab             # abrir em novo separador
```

### `base:query`

Consulta uma base e devolve os resultados.

```bash
file=<name>                    # nome do ficheiro de base
path=<path>                    # caminho do ficheiro de base
view=<name>                    # nome da vista a consultar
format=json|csv|tsv|md|paths   # formato de saída (predefinição: json)
```

## Favoritos

Comandos para [[Favoritos]].

### `bookmarks`

Lista os favoritos.

```bash
total              # devolver o número de favoritos
verbose            # incluir tipos de favoritos
format=json|tsv|csv  # formato de saída (predefinição: tsv)
```

### `bookmark`

Adiciona um favorito.

```bash
file=<path>        # ficheiro a adicionar aos favoritos
subpath=<subpath>  # subcaminho (cabeçalho ou bloco) dentro do ficheiro
folder=<path>      # pasta a adicionar aos favoritos
search=<query>     # consulta de pesquisa a adicionar aos favoritos
url=<url>          # URL a adicionar aos favoritos
title=<title>      # título do favorito
```

## Paleta de comandos

Comandos para a [[Paleta de comandos]] e [[Teclas de atalho]]. Inclui todos os comandos registados por plugins.

### `commands`

Lista os IDs de comandos disponíveis.

```bash
filter=<prefix>    # filtrar por prefixo de ID
```

### `command`

Executa um comando do Obsidian.

```bash
id=<command-id>    # (obrigatório) ID do comando a executar
```

### `hotkeys`

Lista as teclas de atalho de todos os comandos.

```bash
total              # devolver o número de teclas de atalho
verbose            # mostrar se a tecla de atalho é personalizada
format=json|tsv|csv  # formato de saída (predefinição: tsv)
```

### `hotkey`

Obtém a tecla de atalho de um comando.

```bash
id=<command-id>    # (obrigatório) ID do comando

verbose            # mostrar se é personalizada ou predefinida
```

## Notas diárias

Comandos para [[Notas diárias]].

### `daily`

Abre a nota diária.

```bash
paneType=tab|split|window    # tipo de painel para abrir
```

### `daily:path`

Obtém o caminho da nota diária. Devolve o caminho esperado mesmo que o ficheiro ainda não tenha sido criado.

### `daily:read`

Lê o conteúdo da nota diária.

### `daily:append`

Acrescenta conteúdo à nota diária.

```bash
content=<text>     # (obrigatório) conteúdo a acrescentar
paneType=tab|split|window    # tipo de painel para abrir

inline             # acrescentar sem nova linha
open               # abrir o ficheiro após adicionar
```

### `daily:prepend`

Adiciona conteúdo ao início da nota diária.

```bash
content=<text>     # (obrigatório) conteúdo a adicionar
paneType=tab|split|window    # tipo de painel para abrir

inline             # adicionar sem nova linha
open               # abrir o ficheiro após adicionar
```

## Histórico de ficheiros

### `diff`

Lista ou compara versões da [[Recuperação de ficheiros]] local e do [[Introdução ao Obsidian Sync|Sync]]. As versões são numeradas da mais recente para a mais antiga.

```bash
file=<name>          # nome do ficheiro
path=<path>          # caminho do ficheiro
from=<n>             # número da versão de partida
to=<n>               # número da versão de destino
filter=local|sync    # filtrar por origem da versão
```

**Exemplos:**

```shell
# Listar todas as versões do ficheiro ativo
diff

# Listar todas as versões de um ficheiro específico
diff file=Recipe

# Comparar a versão mais recente com o ficheiro atual
diff file=Recipe from=1

# Comparar duas versões
diff file=Recipe from=2 to=1

# Mostrar apenas versões do Sync
diff filter=sync
```

### `history`

Lista versões apenas da [[Recuperação de ficheiros]]. Consulte [[#Sync|sync:history]] para o comando equivalente do Sync.

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
```

### `history:list`

Lista todos os ficheiros com histórico local.

### `history:read`

Lê uma versão do histórico local.

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
version=<n>        # número da versão (predefinição: 1)
```

### `history:restore`

Restaura uma versão do histórico local.

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
version=<n>        # (obrigatório) número da versão
```

### `history:open`

Abre a recuperação de ficheiros.

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
```

## Ficheiros e pastas

### `file`

Mostra informações do ficheiro (predefinição: ficheiro ativo).

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
```

Exemplo:

```
path       Notes/Recipe.md
name       Recipe
extension  md
size       1024
created    1700000000000
modified   1700001000000
```

### `files`

Lista os ficheiros no cofre.

```bash
folder=<path>      # filtrar por pasta
ext=<extension>    # filtrar por extensão

total              # devolver o número de ficheiros
```

### `folder`

Mostra informações da pasta.

```bash
path=<path>              # (obrigatório) caminho da pasta
info=files|folders|size  # devolver apenas informação específica
```

### `folders`

Lista as pastas no cofre.

```bash
folder=<path>      # filtrar por pasta-mãe

total              # devolver o número de pastas
```

### `open`

Abre um ficheiro.

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro

newtab             # abrir em novo separador
```

### `create`

Cria ou substitui um ficheiro.

```bash
name=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
content=<text>     # conteúdo inicial
template=<name>    # modelo a usar

overwrite          # substituir se o ficheiro existir
open               # abrir o ficheiro após criação
newtab             # abrir em novo separador
```

### `read`

Lê o conteúdo de um ficheiro (predefinição: ficheiro ativo).

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
```

### `append`

Acrescenta conteúdo a um ficheiro (predefinição: ficheiro ativo).

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
content=<text>     # (obrigatório) conteúdo a acrescentar

inline             # acrescentar sem nova linha
```

### `prepend`

Adiciona conteúdo antes do corpo do ficheiro, após o frontmatter (predefinição: ficheiro ativo).

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
content=<text>     # (obrigatório) conteúdo a adicionar

inline             # adicionar sem nova linha
```

### `move`

Move ou renomeia um ficheiro (predefinição: ficheiro ativo). Atualiza automaticamente os [[Links internos]] se essa opção estiver ativa nas [[Configurações#Automatically update internal links|definições do cofre]].

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
to=<path>          # (obrigatório) pasta ou caminho de destino
```

### `rename`

Renomeia um ficheiro (predefinição: ficheiro ativo). A extensão é preservada automaticamente se for omitida do novo nome. Use [[#`move`|move]] para renomear e mover um ficheiro ao mesmo tempo. Atualiza automaticamente os [[Links internos]] se essa opção estiver ativa nas [[Configurações#Automatically update internal links|definições do cofre]].

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
name=<name>        # (obrigatório) novo nome do ficheiro
```

### `delete`

Elimina um ficheiro (predefinição: ficheiro ativo, para o lixo por predefinição).

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro

permanent          # ignorar o lixo, eliminar permanentemente
```

## Ligações

Comandos para [[Links inversos]] e [[Links de saída]].

### `backlinks`

Lista os links inversos de um ficheiro (predefinição: ficheiro ativo).

```bash
file=<name>        # nome do ficheiro de destino
path=<path>        # caminho do ficheiro de destino

counts             # incluir contagens de ligações
total              # devolver o número de links inversos
format=json|tsv|csv  # formato de saída (predefinição: tsv)
```

### `links`

Lista as ligações de saída de um ficheiro (predefinição: ficheiro ativo).

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro

total              # devolver o número de ligações
```

### `unresolved`

Lista as ligações não resolvidas no cofre.

```bash
total              # devolver o número de ligações não resolvidas
counts             # incluir contagens de ligações
verbose            # incluir ficheiros de origem
format=json|tsv|csv  # formato de saída (predefinição: tsv)
```

### `orphans`

Lista os ficheiros sem ligações de entrada.

```bash
total              # devolver o número de ficheiros órfãos
```

### `deadends`

Lista os ficheiros sem ligações de saída.

```bash
total              # devolver o número de becos sem saída
```

## Estrutura

Comandos para [[Sumário]].

### `outline`

Mostra os cabeçalhos do ficheiro atual.

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
format=tree|md|json  # formato de saída (predefinição: tree)

total              # devolver o número de cabeçalhos
```

## Plugins

Comandos para [[Plugins nativos]] e [[Plugins da comunidade]].

### `plugins`

Lista os plugins instalados.

```bash
filter=core|community  # filtrar por tipo de plugin

versions               # incluir números de versão
format=json|tsv|csv    # formato de saída (predefinição: tsv)
```

### `plugins:enabled`

Lista os plugins ativos.

```bash
filter=core|community  # filtrar por tipo de plugin

versions               # incluir números de versão
format=json|tsv|csv    # formato de saída (predefinição: tsv)
```

### `plugins:restrict`

Ativa/desativa ou verifica o modo restrito.

```bash
on                 # ativar o modo restrito
off                # desativar o modo restrito
```

### `plugin`

Obtém informações de um plugin.

```bash
id=<plugin-id>     # (obrigatório) ID do plugin
```

### `plugin:enable`

Ativa um plugin.

```bash
id=<id>                # (obrigatório) ID do plugin
filter=core|community  # tipo de plugin
```

### `plugin:disable`

Desativa um plugin.

```bash
id=<id>                # (obrigatório) ID do plugin
filter=core|community  # tipo de plugin
```

### `plugin:install`

Instala um plugin da comunidade.

```bash
id=<id>            # (obrigatório) ID do plugin

enable             # ativar após instalação
```

### `plugin:uninstall`

Desinstala um plugin da comunidade.

```bash
id=<id>            # (obrigatório) ID do plugin
```

### `plugin:reload`

Recarrega um plugin (para programadores).

```bash
id=<id>            # (obrigatório) ID do plugin
```

## Propriedades

Comandos para [[Propriedades]].

### `aliases`

Lista os apelidos no cofre. Use `ative` ou `file`/`path` para mostrar os apelidos de um ficheiro específico.

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro

total              # devolver o número de apelidos
verbose            # incluir caminhos de ficheiros
ative             # mostrar apelidos do ficheiro ativo
```

### `properties`

Lista as propriedades no cofre. Use `ative` ou `file`/`path` para mostrar as propriedades de um ficheiro específico.

```bash
file=<name>        # mostrar propriedades do ficheiro
path=<path>        # mostrar propriedades do caminho
name=<name>        # obter contagem de uma propriedade específica
sort=count         # ordenar por contagem (predefinição: nome)
format=yaml|json|tsv  # formato de saída (predefinição: yaml)

total              # devolver o número de propriedades
counts             # incluir contagens de ocorrências
ative             # mostrar propriedades do ficheiro ativo
```

### `property:set`

Define uma propriedade num ficheiro (predefinição: ficheiro ativo).

```bash
name=<name>                                    # (obrigatório) nome da propriedade
value=<value>                                  # (obrigatório) valor da propriedade
type=text|list|number|checkbox|date|datetime   # tipo de propriedade
file=<name>                                    # nome do ficheiro
path=<path>                                    # caminho do ficheiro
```

### `property:remove`

Remove uma propriedade de um ficheiro (predefinição: ficheiro ativo).

```bash
name=<name>        # (obrigatório) nome da propriedade
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
```

### `property:read`

Lê o valor de uma propriedade de um ficheiro (predefinição: ficheiro ativo).

```bash
name=<name>        # (obrigatório) nome da propriedade
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
```

## Publicar

Comandos para o [[Introdução ao Obsidian Publish|Obsidian Publish]].

### `publish:site`

Mostra informações do site publicado (slug, URL).

### `publish:list`

Lista os ficheiros publicados.

```bash
total              # devolver o número de ficheiros publicados
```

### `publish:status`

Lista as alterações pendentes para publicação.

```bash
total              # devolver o número de alterações
new                # mostrar apenas ficheiros novos
changed            # mostrar apenas ficheiros alterados
deleted            # mostrar apenas ficheiros eliminados
```

### `publish:add`

Publica um ficheiro ou todos os ficheiros alterados (predefinição: ficheiro ativo).

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro

changed            # publicar todos os ficheiros alterados
```

### `publish:remove`

Remove um ficheiro da publicação (predefinição: ficheiro ativo).

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
```

### `publish:open`

Abre o ficheiro no site publicado (predefinição: ficheiro ativo).

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
```

## Notas aleatórias

Comandos para [[Nota aleatória]].

### `random`

Abre uma nota aleatória.

```bash
folder=<path>      # limitar a uma pasta

newtab             # abrir em novo separador
```

### `random:read`

Lê uma nota aleatória (inclui o caminho).

```bash
folder=<path>      # limitar a uma pasta
```

## Pesquisa

Comandos para [[Pesquisa]].

### `search`

Pesquisa texto no cofre. Devolve os caminhos dos ficheiros correspondentes.

```bash
query=<text>       # (obrigatório) consulta de pesquisa
path=<folder>      # limitar a uma pasta
limit=<n>          # número máximo de ficheiros
format=text|json   # formato de saída (predefinição: text)

total              # devolver o número de correspondências
case               # distinguir maiúsculas de minúsculas
```

### `search:context`

Pesquisa com contexto de linha. Devolve resultado no formato grep: `caminho:linha: texto`.

```bash
query=<text>       # (obrigatório) consulta de pesquisa
path=<folder>      # limitar a uma pasta
limit=<n>          # número máximo de ficheiros
format=text|json   # formato de saída (predefinição: text)

case               # distinguir maiúsculas de minúsculas
```

### `search:open`

Abre a vista de pesquisa.

```bash
query=<text>       # consulta de pesquisa inicial
```

## Sync

Comandos para o [[Introdução ao Obsidian Sync|Obsidian Sync]].

> [!tip] Sincronizar sem a aplicação de secretária
> Estes comandos controlam o Sync dentro da aplicação Obsidian em execução. Para sincronizar cofres a partir da linha de comandos sem a aplicação de secretária, consulte [[Sync sem interface]].

### `sync`

Pausa ou retoma a sincronização.

```bash
on                 # retomar a sincronização
off                # pausar a sincronização
```

### `sync:status`

Mostra o estado e utilização do Sync.

### `sync:history`

Lista o histórico de versões do Sync para um ficheiro (predefinição: ficheiro ativo).

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro

total              # devolver o número de versões
```

### `sync:read`

Lê uma versão do Sync (predefinição: ficheiro ativo).

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
version=<n>        # (obrigatório) número da versão
```

### `sync:restore`

Restaura uma versão do Sync (predefinição: ficheiro ativo).

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
version=<n>        # (obrigatório) número da versão
```

### `sync:open`

Abre o histórico do Sync (predefinição: ficheiro ativo).

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
```

### `sync:deleted`

Lista os ficheiros eliminados no Sync.

```bash
total              # devolver o número de ficheiros eliminados
```

## Etiquetas

Comandos para [[Tags]].

### `tags`

Lista as etiquetas no cofre. Use `ative` ou `file`/`path` para mostrar as etiquetas de um ficheiro específico.

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
sort=count         # ordenar por contagem (predefinição: nome)

total              # devolver o número de etiquetas
counts             # incluir contagens de etiquetas
format=json|tsv|csv  # formato de saída (predefinição: tsv)
ative             # mostrar etiquetas do ficheiro ativo
```

### `tag`

Obtém informações de uma etiqueta.

```bash
name=<tag>         # (obrigatório) nome da etiqueta

total              # devolver o número de ocorrências
verbose            # incluir lista de ficheiros e contagem
```

## Tarefas

Comandos para gestão de tarefas.

### `tasks`

Lista as tarefas no cofre. Use `ative` ou `file`/`path` para mostrar as tarefas de um ficheiro específico.

```bash
file=<name>        # filtrar por nome de ficheiro
path=<path>        # filtrar por caminho de ficheiro
status="<char>"    # filtrar por caráter de estado

total              # devolver o número de tarefas
done               # mostrar tarefas concluídas
todo               # mostrar tarefas por fazer
verbose            # agrupar por ficheiro com números de linha
format=json|tsv|csv  # formato de saída (predefinição: text)
ative             # mostrar tarefas do ficheiro ativo
daily              # mostrar tarefas da nota diária
```

**Exemplos:**

```bash
# Listar todas as tarefas no cofre
tasks

# Listar tarefas por fazer no cofre
tasks todo

# Listar tarefas concluídas de um ficheiro específico
tasks file=Recipe done

# Listar tarefas da nota diária de hoje
tasks daily

# Contar tarefas na nota diária
tasks daily total

# Listar tarefas com caminhos e números de linha
tasks verbose

# Filtrar por estado personalizado (colocar chars especiais entre aspas)
tasks 'status=?'
```

### `task`

Mostra ou atualiza uma tarefa.

```bash
ref=<path:line>    # referência da tarefa (caminho:linha)
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro
line=<n>           # número de linha
status="<char>"    # definir caráter de estado

toggle             # alternar o estado da tarefa
daily              # nota diária
done               # marcar como concluída
todo               # marcar como por fazer
```

**Exemplos:**

```bash
# Mostrar informações da tarefa
task file=Recipe line=8
task ref="Recipe.md:8"

# Alternar conclusão da tarefa
task ref="Recipe.md:8" toggle

# Alternar tarefa na nota diária
task daily line=3 toggle

# Definir estado da tarefa
task file=Recipe line=8 done      # → [x]
task file=Recipe line=8 todo      # → [ ]
task file=Recipe line=8 status=-  # → [-]
task daily line=3 done            # Marcar tarefa da nota diária como concluída
```


## Modelos

Comandos para [[Plugins/Modelos|Modelos]].

### `templates`

Lista os modelos.

```bash
total              # devolver o número de modelos
```

### `template:read`

Lê o conteúdo de um modelo.

```bash
name=<template>    # (obrigatório) nome do modelo
title=<title>      # título para resolução de variáveis

resolve            # resolver as variáveis do modelo
```

### `template:insert`

Insere um modelo no ficheiro ativo.

```bash
name=<template>    # (obrigatório) nome do modelo
```

**Notas:**
- A opção `resolve` processa as variáveis `{{date}}`, `{{time}}`, `{{title}}`
- Use `create path=<caminho> template=<nome>` para criar um ficheiro com um modelo

## Temas e fragmentos

Comandos para [[Temas]] e [[Fragmentos CSS]].

### `themes`

Lista os temas instalados.

```bash
versions           # incluir números de versão
```

### `theme`

Mostra o tema ativo ou obtém informações.

```bash
name=<name>        # nome do tema para detalhes
```

### `theme:set`

Define o tema ativo.

```bash
name=<name>        # (obrigatório) nome do tema (vazio para predefinição)
```

### `theme:install`

Instala um tema da comunidade.

```bash
name=<name>        # (obrigatório) nome do tema

enable             # ativar após instalação
```

### `theme:uninstall`

Desinstala um tema.

```bash
name=<name>        # (obrigatório) nome do tema
```

### `snippets`

Lista os fragmentos CSS instalados.

### `snippets:enabled`

Lista os fragmentos CSS ativos.

### `snippet:enable`

Ativa um fragmento CSS.

```bash
name=<name>        # (obrigatório) nome do fragmento
```

### `snippet:disable`

Desativa um fragmento CSS.

```bash
name=<name>        # (obrigatório) nome do fragmento
```

## Notas únicas

Comandos para [[Criador de nota única]].

### `unique`

Cria uma nota única.

```bash
name=<text>        # nome da nota
content=<text>     # conteúdo inicial
paneType=tab|split|window    # tipo de painel para abrir

open               # abrir o ficheiro após criação
```

## Cofre

### `vault`

Mostra informações do cofre.

```bash
info=name|path|files|folders|size  # devolver apenas informação específica
```

### `vaults`

Lista os cofres conhecidos.

```bash
total              # devolver o número de cofres
verbose            # incluir caminhos dos cofres
```

### `vault:open`

Muda para um cofre diferente (apenas na TUI).

```bash
name=<name>        # (obrigatório) nome do cofre
```

## Visualizador web

Comandos para [[Visualizador web]].

### `web`

Abre um URL no visualizador web.

```bash
url=<url>          # (obrigatório) URL a abrir

newtab             # abrir em novo separador
```

## Contagem de palavras

Comandos para [[Contagem de palavras]].

### `wordcount`

Conta palavras e caracteres (predefinição: ficheiro ativo).

```bash
file=<name>        # nome do ficheiro
path=<path>        # caminho do ficheiro

words              # devolver apenas a contagem de palavras
characters         # devolver apenas a contagem de caracteres
```

## Área de trabalho

Comandos para [[Área de trabalho]] e o plugin [[Áreas de trabalho]].

### `workspace`

Mostra a árvore da área de trabalho.

```bash
ids                # incluir IDs dos itens da área de trabalho
```

### `workspaces`

Lista as áreas de trabalho guardadas.

```bash
total              # devolver o número de áreas de trabalho
```

### `workspace:save`

Guarda o esquema atual como área de trabalho.

```bash
name=<name>        # nome da área de trabalho
```

### `workspace:load`

Carrega uma área de trabalho guardada.

```bash
name=<name>        # (obrigatório) nome da área de trabalho
```

### `workspace:delete`

Elimina uma área de trabalho guardada.

```bash
name=<name>        # (obrigatório) nome da área de trabalho
```

### `tabs`

Lista os separadores abertos.

```bash
ids                # incluir IDs dos separadores
```

### `tab:open`

Abre um novo separador.

```bash
group=<id>         # ID do grupo de separadores
file=<path>        # ficheiro a abrir
view=<type>        # tipo de vista a abrir
```

### `recents`

Lista os ficheiros abertos recentemente.

```bash
total              # devolver o número de ficheiros recentes
```

## Comandos de programador

Comandos para ajudar no desenvolvimento de [[Plugins da comunidade]] e [[Temas]]. Saiba mais consultando a [Documentação para Programadores do Obsidian](https://docs.obsidian.md).

### `devtools`

Ativa/desativa as ferramentas de desenvolvimento do Electron.

### `dev:debug`

Liga/desliga o debugger do protocolo Chrome DevTools.

```bash
on                 # ligar o debugger
off                # desligar o debugger
```

### `dev:cdp`

Executa um comando do protocolo Chrome DevTools.

```bash
method=<CDP.method>  # (obrigatório) método CDP a invocar
params=<json>        # parâmetros do método em JSON
```

### `dev:errors`

Mostra os erros JavaScript capturados.

```bash
clear              # limpar o buffer de erros
```

### `dev:screenshot`

Tira uma captura de ecrã (devolve PNG em base64).

```bash
path=<filename>    # caminho do ficheiro de saída
```

### `dev:console`

Mostra as mensagens da consola capturadas.

```bash
limit=<n>                        # número máximo de mensagens (predefinição: 50)
level=log|warn|error|info|debug  # filtrar por nível de log

clear                            # limpar o buffer da consola
```

### `dev:css`

Inspeciona CSS com localizações de origem.

```bash
selector=<css>     # (obrigatório) seletor CSS
prop=<name>        # filtrar por nome de propriedade
```

### `dev:dom`

Consulta elementos do DOM.

```bash
selector=<css>     # (obrigatório) seletor CSS
attr=<name>        # obter valor de atributo
css=<prop>         # obter valor de propriedade CSS

total              # devolver o número de elementos
text               # devolver conteúdo de texto
inner              # devolver innerHTML em vez de outerHTML
all                # devolver todas as correspondências em vez da primeira
```

### `dev:mobile`

Ativa/desativa a emulação de dispositivo móvel.

```bash
on                 # ativar emulação de móvel
off                # desativar emulação de móvel
```

### `eval`

Executa JavaScript e devolve o resultado.

```bash
code=<javascript>  # (obrigatório) código JavaScript a executar
```

## Atalhos de teclado

Estes atalhos estão disponíveis na [[#Usar a interface de terminal|TUI]].

### Navegação

| Ação                                                        | Atalho         |
| ----------------------------------------------------------- | -------------- |
| Mover cursor para a esquerda                                | `←` / `Ctrl+B` |
| Mover cursor para a direita (aceita sugestão no fim da linha) | `→` / `Ctrl+F` |
| Saltar para o início da linha                               | `Ctrl+A`       |
| Saltar para o fim da linha                                  | `Ctrl+E`       |
| Recuar uma palavra                                          | `Alt+B`        |
| Avançar uma palavra                                         | `Alt+F`        |

### Edição

| Ação                    | Atalho                     |
| ----------------------- | -------------------------- |
| Apagar até ao início da linha | `Ctrl+U`                   |
| Apagar até ao fim da linha    | `Ctrl+K`                   |
| Apagar palavra anterior       | `Ctrl+W` / `Alt+Backspace` |

### Preenchimento automático

| Ação                                                          | Atalho      |
| ------------------------------------------------------------- | ----------- |
| Entrar no modo de sugestão / aceitar sugestão selecionada     | `Tab`       |
| Sair do modo de sugestão                                      | `Shift+Tab` |
| Entrar no modo de sugestão (a partir de entrada em branco)    | `↓`         |
| Aceitar a primeira/sugestão selecionada (no fim da linha)     | `→`         |

### Histórico

| Ação                                                                 | Atalho         |
| -------------------------------------------------------------------- | -------------- |
| Entrada anterior no histórico / navegar sugestões para cima          | `↑` / `Ctrl+P` |
| Entrada seguinte no histórico / navegar sugestões para baixo         | `↓` / `Ctrl+N` |
| Pesquisa inversa no histórico (escreva para filtrar, `Ctrl+R` para ciclar) | `Ctrl+R`  |

### Outros

| Ação                                                          | Atalho              |
| ------------------------------------------------------------- | ------------------- |
| Executar comando ou aceitar sugestão                          | `Enter`             |
| Desfazer preenchimento / sair do modo de sugestão / limpar entrada | `Escape`       |
| Limpar ecrã                                                   | `Ctrl+L`            |
| Sair                                                          | `Ctrl+C` / `Ctrl+D` |

## Resolução de problemas

Se tiver dificuldades a executar o Obsidian CLI:

- Certifique-se de que está a usar a [[Atualizar o Obsidian|versão mais recente do instalador do Obsidian]] (1.12.4 ou superior).
- Reinicie o terminal após registar o CLI para que as alterações ao PATH entrem em vigor.
- O Obsidian tem de estar em execução. O CLI liga-se à instância do Obsidian em execução. Se o Obsidian não estiver aberto, o primeiro comando CLI deverá lançar a aplicação.

### Windows

O Obsidian CLI no Windows requer o instalador do Obsidian 1.12.4+. Consulte [[Atualizar o Obsidian|Atualização da versão do instalador]].

O Windows usa um redirecionador de terminal que liga o Obsidian corretamente ao stdin/stdout. Isto é necessário porque o Obsidian funciona normalmente como uma aplicação GUI, o que é incompatível com as saídas de terminal no Windows. Ao instalar o Obsidian 1.12.4+, o redirecionador de terminal `Obsidian.com` será adicionado na pasta onde instalou o ficheiro `Obsidian.exe`.

### macOS

O registo do CLI adiciona o diretório de binários do Obsidian ao seu PATH através de `~/.zprofile`. Se tiver problemas, verifique o seguinte:

O seu ficheiro `~/.zprofile` deve conter a seguinte linha. Se estiver em falta, pode adicioná-la manualmente:

```
export PATH="$PATH:/Applications/Obsidian.app/Contents/MacOS"
```

#### Shells alternativos

O registo do CLI apenas modifica `~/.zprofile`, que é usado pelo zsh (o shell predefinido do macOS). Se usar um shell diferente, adicione o diretório de binários do Obsidian ao ficheiro de configuração do seu shell manualmente:

- Bash: adicione `export PATH="$PATH:/Applications/Obsidian.app/Contents/MacOS"` a `~/.bash_profile`
- Fish: execute `fish_add_path /Applications/Obsidian.app/Contents/MacOS`


### Linux

O registo do CLI cria uma hiperligação simbólica em `/usr/local/bin/obsidian` apontando para o binário do Obsidian (requer sudo).

#### AppImage

Para instalações AppImage, a hiperligação simbólica aponta para o ficheiro `.AppImage` em vez do binário interno, pois o caminho de montagem muda a cada arranque. Se o sudo falhar, a hiperligação simbólica é criada em `~/.local/bin/obsidian` como alternativa. Se tiver problemas, verifique o seguinte.

Confirme que a hiperligação simbólica existe e aponta para o binário correto:

```
ls -l /usr/local/bin/obsidian
```

Se a hiperligação simbólica estiver em falta, crie-a manualmente:

```
sudo ln -s /caminho/para/obsidian /usr/local/bin/obsidian
```

Se a hiperligação simbólica tiver sido criada em `~/.local/bin/`, certifique-se de que esse diretório está no seu PATH. Adicione o seguinte ao seu `~/.bashrc` ou `~/.zshrc`:

```
export PATH="$PATH:$HOME/.local/bin"
```

Se a hiperligação simbólica quebrar após mover ou renomear o ficheiro `.AppImage`, volte a registar o CLI ou atualize a hiperligação simbólica manualmente.

#### Snap

O pacote Snap guarda os dados da compilação insider no seu próprio diretório de dados de utilizador. Se o CLI não detetar o `.asar` insider, defina `XDG_CONFIG_HOME` para apontar para o caminho de configuração do Snap:

```
export XDG_CONFIG_HOME="$HOME/snap/obsidian/current/.config"
```

Adicione isto ao seu `~/.bashrc` ou `~/.zshrc` para tornar a configuração persistente.


#### Flatpak

O Obsidian tenta fazer isto automaticamente, mas abaixo estão as instruções manuais. Se for uma instalação de sistema:

```
ln -s /var/lib/flatpak/exports/bin/md.obsidian.Obsidian ~/.local/bin/obsidian
```

Se for uma instalação de utilizador:

```
ln -s ~/.local/share/flatpak/exports/bin/md.obsidian.Obsidian ~/.local/bin/obsidian
```
