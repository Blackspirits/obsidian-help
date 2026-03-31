---
permalink: sync/migrate
cssclasses:
  - soft-embed
publish: true
mobile: true
description: 'Move your Sync vault to a different region, perform and encryption upgrade.'
---
Por predefinição, o Obsidian Sync utiliza [[Obsidian Sync/Segurança e privacidade#Encryption|encriptação ponta a ponta]] para todos os seus dados. Isto garante que ninguém — nem mesmo a equipa do Obsidian — consegue aceder às suas notas.

O Obsidian actualiza ocasionalmente a encriptação do Sync para manter os mais elevados padrões de [[Obsidian Sync/Segurança e privacidade|segurança]]. Se houver uma actualização de encriptação disponível, verá uma opção com o título **Upgrade vault encryption** em **Configurações do Obsidian → Sync**. Este processo também lhe permite alterar a sua [[Regiões do Sync|região do Sync]].

## Versões de encriptação

Todos os cofres novos utilizam automaticamente a encriptação mais recente. Os cofres existentes podem ser actualizados com o assistente de migração. Note que todos os dispositivos devem estar a utilizar uma versão da aplicação Obsidian que suporte a versão de encriptação do Sync para a qual está a migrar.

| Data de lançamento                                                      | Versão do Sync | Versão mínima da aplicação |
| ----------------------------------------------------------------------- | -------------- | -------------------------- |
| [2025-08-22](https://obsidian.md/changelog/2025-08-22-sync/)            | 3              | 1.8.3                      |
| [2020-12-07](https://obsidian.md/changelog/2020-12-07-desktop-v0.9.21/) | 0              | 0.9.21                     |

## Actualizar a encriptação com o assistente de migração

Antes de continuar, crie uma [[Criar cópia de segurança dos seus ficheiros do Obsidian|cópia de segurança]] do seu cofre para evitar qualquer perda potencial de dados. Este processo irá eliminar permanentemente todos os dados do seu cofre remoto com a encriptação antiga, incluindo o histórico de versões.

> [!danger] As migrações são destrutivas
>
> **Faça sempre uma [[Criar cópia de segurança dos seus ficheiros do Obsidian|cópia de segurança]] do seu cofre antes de prosseguir com uma migração.**
>
> Quando migra um cofre remoto, os seus dados serão substituídos. Isto significa:
>
> 1. Os dados remotos serão removidos dos servidores do Obsidian, e os dados do cofre serão recarregados em substituição.
> 2. Todo o [[Histórico de versões|histórico de versões]] do cofre será perdido.

1. Abra as **[[Configurações]]**.
2. Na barra lateral, seleccione **Sync**.
3. Clique em **Upgrade vault**. Esta opção apenas será visível se houver uma actualização disponível para o seu cofre remoto.
4. Verifique as suas cópias de segurança e clique em **Continue**.
5. Em **Vault name**, introduza o nome do cofre remoto.
6. Em **Region**, escolha a [[Configurar o Obsidian Sync#Regional sync servers|região]] do servidor para o seu cofre remoto.
7. Em **Encryption password**, escolha uma palavra-passe para o seu cofre. Isto cria um cofre com encriptação ponta a ponta. A palavra-passe do cofre é separada da sua conta Obsidian e pode ser diferente para cada um dos seus cofres. Para mais informações, consulte [[Segurança e privacidade]].
8. Depois de recarregar os seus dados com a nova encriptação, volte a ligar-se ao novo cofre Sync nos seus outros dispositivos.
