---
permalink: headless
description: Obsidian Headless is a command line client for Obsidian services. Sync your vaults without the desktop app.
---
O Obsidian Headless **(beta aberto)** é um cliente headless para os serviços do Obsidian. Permite-lhe [[Sync sem interface|sincronizar cofres]] a partir da linha de comandos sem a aplicação de computador, com todos os benefícios de velocidade, privacidade e encriptação de ponta a ponta do [[Introdução ao Obsidian Sync|Obsidian Sync]].

Razões pelas quais pode querer utilizar o Obsidian Headless:

- Automatizar cópias de segurança remotas.
- Automatizar a publicação de um website.
- Dar a ferramentas agênticas acesso a um cofre sem acesso ao seu computador completo.
- Sincronizar um cofre de equipa partilhado para um servidor que alimenta outras ferramentas.
- Executar automatizações agendadas, por exemplo agregar notas diárias em resumos semanais, marcação automática de tags, etc.

> [!info] Obsidian Headless vs Obsidian CLI
> O [[Obsidian CLI]] controla a aplicação de computador do Obsidian a partir do seu terminal. O Obsidian Headless é um cliente autónomo que funciona de forma independente, sem necessidade de aplicação de computador.

## Instalar

O Obsidian Headless **(beta aberto)** requer o Node.js 22 ou superior. Instale-o a partir do [npm](https://www.npmjs.com/package/obsidian-headless):

```shell
npm install -g obsidian-headless
```

## Autenticação

### Iniciar sessão

```shell
ob login
```

Se já tiver sessão iniciada, `ob login` apresenta as informações da sua conta. Para mudar de conta, passe `--email` e/ou `--password` para iniciar sessão novamente.

```
ob login [--email <email>] [--password <password>] [--mfa <code>]
```

Todas as opções são interativas quando omitidas — o email e a palavra-passe são solicitados, e o 2FA é pedido automaticamente se estiver ativado na conta.

Para terminar sessão e limpar as credenciais armazenadas:

```shell
ob logout
```

## Serviços

- [[Sync sem interface]]: utilize o [[Introdução ao Obsidian Sync|Obsidian Sync]] a partir da linha de comandos sem a aplicação de computador.
- [[Headless Publish]]: utilize o [[Introdução ao Obsidian Publish|Obsidian Publish]] a partir da linha de comandos sem a aplicação de computador.
