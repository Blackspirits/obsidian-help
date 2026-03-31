---
aliases:
  - Advanced topics/How Obsidian stores data
description: Esta página explica como o Obsidian armazena os seus dados no seu dispositivo.
mobile: true
permalink: data-storage
publish: true
---

O Obsidian armazena as suas notas como ficheiros de texto simples [[Sintaxe de formatação básica|formatados em Markdown]] num _cofre_. Um cofre é uma pasta no seu sistema de ficheiros local, incluindo quaisquer subpastas.

Como as notas são ficheiros de texto simples, pode usar outros editores de texto e gestores de ficheiros para editar e gerir as notas. O Obsidian atualiza automaticamente o seu cofre para acompanhar quaisquer alterações externas.

Pode criar um cofre em qualquer local que o seu sistema operativo permita. O Obsidian sincroniza com o [[Introdução ao Obsidian Sync|Obsidian Sync]], Dropbox, iCloud, OneDrive, Git e muitos outros serviços de terceiros.

Pode abrir várias pastas como cofres individuais, por exemplo para separar notas de trabalho e de escola.

> [!warning] Cofres dentro de cofres
> Como os [[Links internos]] são locais a um cofre, recomendamos que não crie cofres dentro de cofres. Os links podem não ser atualizados corretamente.

## Definições do cofre

O Obsidian cria uma [[Pasta de configuração]] `.obsidian` na pasta raiz do cofre, que contém preferências específicas desse cofre, como [[Teclas de atalho]], [[Temas]] e [[Plugins da comunidade]].

Por predefinição, a maioria dos sistemas operativos oculta pastas que começam com um ponto (`.`), pelo que poderá ter de atualizar as definições do seu gestor de ficheiros para as ver.

- **macOS**: No Finder, prima `Cmd+Shift+.` (ponto) para mostrar ficheiros ocultos.
- **Windows**: [Mostrar ficheiros ocultos](https://support.microsoft.com/en-us/windows/show-hidden-files-0320fe58-0117-fd59-6851-9b7f9840fdb2)
+ **GNU/Linux:** Na maioria dos gestores de ficheiros, prima `Ctrl + h` para mostrar ficheiros ocultos.

> [!tip] Adicionar `.obsidian` ao Git
> Os ficheiros `.obsidian/workspace.json` e `.obsidian/workspaces.json` armazenam o esquema atual da área de trabalho e são atualizados sempre que abre um novo ficheiro. Se usar o [Git](https://git-scm.com) para gerir o seu cofre, poderá querer adicionar estes ficheiros ao `.gitignore`.

## Definições globais

O Obsidian armazena as definições globais numa pasta de sistema. A localização da pasta de sistema depende do sistema operativo que está a utilizar.

- **macOS**: `/Users/yourusername/Library/Application Support/obsidian`
- **Windows**: `%APPDATA%\Obsidian\`
- **Linux**: `$XDG_CONFIG_HOME/obsidian/` ou `~/.config/obsidian/`

> [!warning] Não crie um cofre na pasta de sistema. Isto pode levar a dados corrompidos ou perda de dados.

## IndexedDB

O IndexedDB é uma base de dados de baixo nível do lado do cliente que o Obsidian usa para armazenamento em segundo plano. Ajuda a manter o estado das ligações do [[Introdução ao Obsidian Sync|Obsidian Sync]] e preserva a [[#Cache de metadados]] quando a aplicação é fechada. 

> [!warning] Se o [Modo de Isolamento](<https://support.apple.com/en-us/105120>) da Apple estiver ativado e o Obsidian não estiver excluído, estes ficheiros de base de dados não serão guardados, exigindo reindexação cada vez que a aplicação inicia.

### Cache de metadados

Para proporcionar uma experiência rápida ao usar a aplicação, o Obsidian mantém um registo local de metadados sobre os ficheiros do seu cofre denominado **cache de metadados**. Estes metadados alimentam muitas funcionalidades da aplicação, desde a vista de grafo até à vista de sumário.

O Obsidian mantém esta cache em sincronização com os ficheiros do seu cofre, mas é possível que os dados fiquem dessincronizados com os ficheiros subjacentes. Caso isso aconteça no seu cofre, pode reconstruir a cache de metadados a partir das definições da aplicação na secção *Ficheiros e links*.

