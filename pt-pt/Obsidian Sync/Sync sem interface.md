---
permalink: sync/headless
cssclasses:
  - reference
description: 'Obsidian Sync offers a headless client to sync vaults without using the desktop app. Useful for CI pipelines, agents, and automated workflows. Sync the latest changes or keep files continuously up to date.'
---
O [[Introdução ao Obsidian Sync|Obsidian Sync]] disponibiliza um cliente sem interface para sincronizar cofres sem utilizar a aplicação de desktop. Útil para pipelines de CI, agentes e fluxos de trabalho automatizados. Sincronize as últimas alterações ou mantenha os ficheiros continuamente atualizados.

Instale o [[Obsidian Headless]] **(beta aberto)** para interagir com o [[Introdução ao Obsidian Sync|Obsidian Sync]] a partir da linha de comandos sem a aplicação de desktop do Obsidian. O Sync sem interface utiliza as mesmas [[Segurança e privacidade|protecções de encriptação e privacidade]] que a aplicação de desktop, incluindo encriptação ponta a ponta.

## Início rápido

> [!error] Faça uma cópia de segurança dos dados antes de começar
> 1. Faça sempre uma cópia de segurança dos dados antes de começar, em caso de algo inesperado.
> 2. Não utilize *em simultâneo* o Sync da aplicação de desktop e o Sync sem interface no mesmo dispositivo, pois pode causar conflitos de dados. Utilize apenas um método de sincronização por dispositivo.

Instale o [[Obsidian Headless|Obsidian Headless]] **(beta aberto)**:

```shell
npm install -g obsidian-headless
```

Tem de ter uma [[Planos e limites de armazenamento|subscrição ativa do Obsidian Sync]].

```shell
# Login
ob login

# List your remote vaults
ob sync-list-remote

# Set up a vault for syncing
cd ~/vaults/my-vault
ob sync-setup --vault "My Vault"

# Run a one-time sync
ob sync

# Run continuous sync (watches for changes)
ob sync --continuous
```

## Comandos

### `ob sync-list-remote`

Lista todos os cofres remotos disponíveis na sua conta, incluindo cofres partilhados.

### `ob sync-list-local`

Lista os cofres configurados localmente e os respectivos caminhos.

### `ob sync-create-remote`

Cria um novo cofre remoto.

```
ob sync-create-remote --name "Vault Name" [--encryption <standard|e2ee>] [--password <password>] [--region <region>]
```

| Opção | Descrição |
| --- | --- |
| `--name` | Nome do cofre (obrigatório) |
| `--encryption` | `standard` para encriptação gerida, `e2ee` para encriptação ponta a ponta |
| `--password` | Palavra-passe de encriptação ponta a ponta (solicitada se omitida) |
| `--region` | [[Sync regions\|Região]] do servidor (automático se omitido) |

### `ob sync-setup`

Configura a sincronização entre um cofre local e um cofre remoto.

```
ob sync-setup --vault <id-or-name> [--path <local-path>] [--password <password>] [--device-name <name>] [--config-dir <name>]
```

| Opção | Descrição |
| --- | --- |
| `--vault` | ID ou nome do cofre remoto (obrigatório) |
| `--path` | Directório local (predefinição: directório atual) |
| `--password` | Palavra-passe de encriptação ponta a ponta (solicitada se omitida) |
| `--device-name` | Nome do dispositivo apresentado no [[Version history\|histórico de versões do sync]] |
| `--config-dir` | Nome do [[Configuration folder\|directório de configuração]] (predefinição: `.obsidian`) |

### `ob sync`

Executa a sincronização para um cofre configurado.

```
ob sync [--path <local-path>] [--continuous]
```

| Opção | Descrição |
| --- | --- |
| `--path` | Caminho do cofre local (predefinição: directório atual) |
| `--continuous` | Executa continuamente, monitorizando as alterações |

### `ob sync-config`

Vê ou altera as [[Configurações do Sync e sincronização seletiva|configurações do sync]] para um cofre. Execute sem opções para apresentar a configuração atual.

```
ob sync-config [--path <local-path>] [options]
```

| Opção                | Descrição                                                                                                                                                                                                    |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `--path`              | Caminho do cofre local (predefinição: directório atual)                                                                                                                                                       |
| `--mode`              | Modo de sincronização: `bidirectional` (predefinição), `pull-only` (apenas transferir, ignorar alterações locais) ou `mirror-remote` (apenas transferir, reverter alterações locais)                           |
| `--conflict-strategy` | `merge` ou `conflict`                                                                                                                                                                                          |
| `--file-types`        | Tipos de anexos a sincronizar: `image`, `audio`, `video`, `pdf`, `unsupported` (separados por vírgula, vazio para limpar)                                                                                      |
| `--configs`           | Categorias de configuração a sincronizar: `app`, `appearance`, `appearance-data`, `hotkey`, `core-plugin`, `core-plugin-data`, `community-plugin`, `community-plugin-data` (separados por vírgula, vazio para desativar a sincronização de configurações) |
| `--excluded-folders`  | Pastas a excluir (separadas por vírgula, vazio para limpar)                                                                                                                                                    |
| `--device-name`       | Nome do dispositivo para identificar este cliente no histórico de versões do sync                                                                                                                              |
| `--config-dir`        | Nome do directório de configuração (predefinição: `.obsidian`)                                                                                                                                                 |

### `ob sync-status`

Apresenta o estado da sincronização e a configuração de um cofre.

```
ob sync-status [--path <local-path>]
```

### `ob sync-unlink`

Desliga um cofre da sincronização e remove as credenciais armazenadas.

```
ob sync-unlink [--path <local-path>]
```

## Módulos nativos

O Obsidian Headless inclui um addon nativo pré-compilado para definir a hora de criação de ficheiros (birthtime) no Windows e macOS. Isto preserva os carimbos temporais de criação originais ao transferir ficheiros do servidor.

O addon tem como alvo a versão 3 do N-API, pelo que os binários compilados são estáveis ao nível da ABI e funcionam em diferentes versões do Node.js sem necessidade de recompilação.

No Linux, o birthtime não é suportado — o addon não está incluído e a sincronização funciona normalmente sem ele.

Os binários pré-compilados estão incluídos para:

- `win32-x64`
- `win32-arm64`
- `win32-ia32`
- `darwin-x64`
- `darwin-arm64`
