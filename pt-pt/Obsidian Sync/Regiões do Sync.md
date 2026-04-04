---
permalink: sync/region
cssclasses:
  - soft-embed
publish: true
mobile: true
description: Move your Sync vault to a different region.
---
Quando cria um [[Cofres locais e remotos|cofre remoto]] através do [[Introdução ao Obsidian Sync|Obsidian Sync]], os seus dados são encriptados e armazenados num dos servidores regionais do Sync da Obsidian. Este guia explica como mover o seu cofre do Sync para um servidor regional diferente.

## Regiões disponíveis

As seguintes regiões estão disponíveis com o Obsidian Sync. Recomendamos a utilização de **Automático** ou a escolha de uma localização próxima de si para reduzir a latência e tornar o processo de sincronização mais rápido.

![[Obsidian Sync/Segurança e privacidade#^sync-geo-regions]]

## Alterar a região do Sync

Para alterar a região do seu cofre remoto, terá de recriar o cofre num servidor do Sync diferente. Note que também pode alterar a região utilizando o assistente de migração [[Atualizar encriptação do Sync]], se o seu cofre remoto estiver numa versão mais antiga.

> [!danger] As migrações são destrutivas
> 
> **Faça sempre [[Criar cópia de segurança dos seus ficheiros do Obsidian|uma cópia de segurança]] do seu cofre antes de prosseguir com uma migração.**
> 
> Quando migra um cofre remoto, os seus dados serão substituídos. Isto significa que:
> 
> 1. Os dados remotos serão removidos dos servidores da Obsidian e os dados do cofre serão carregados novamente no seu lugar.
> 2. Todo o [[Histórico de versões|histórico de versões]] do cofre será perdido.

![[Configurar o Obsidian Sync#Disconnect from a remote vault]]

Se estiver no [[Planos e limites de armazenamento|Plano Standard]], também terá de [[Configurar o Obsidian Sync#Delete a remote vault|eliminar o seu cofre remoto]] antes de prosseguir.

![[Configurar o Obsidian Sync#Create a new remote vault]]

Adicionalmente, pode [[Configurar o Obsidian Sync#Delete a remote vault|eliminar o cofre remoto antigo]] depois de ter confirmado a transição para o novo cofre remoto e a sua região.
