---
permalink: sync/faq
publish: true
mobile: true
description: This page lists some of the common questions related to questions and limitations for Obsidian Sync.
---

Esta página lista algumas das perguntas mais comuns relacionadas com as questões e limitações do [[Introdução ao Obsidian Sync|Obsidian Sync]].

## Geral

### Que sistemas operativos são suportados pelo Obsidian Sync?

O Obsidian Sync suporta todas as plataformas em que o Obsidian pode ser executado. Atualmente, isso inclui Windows, macOS, Linux, Android e iOS.

### O Obsidian funciona com o modo de isolamento da Apple?

O Obsidian pode ser utilizado no [modo de isolamento](https://support.apple.com/en-us/105120) desde que seja adicionado como excepção.

### Que tipo de dados são sincronizados?

Por omissão, as suas notas do Obsidian, imagens e a sua [[Pasta de configuração]] são sincronizadas.

Pode adicionar opções de sincronização adicionais para PDF, ficheiros de áudio, ficheiros de vídeo e outros ficheiros ao configurar as [[Configurações do Sync e sincronização seletiva]].

### Qual é o meu espaço de armazenamento?

O limite de armazenamento depende do seu [[Planos e limites de armazenamento#Plans|plano do Sync]] do Obsidian. O máximo de armazenamento disponível é de 100 GB. Este limite inclui o [[Histórico de versões|histórico de versões]].

Pode ver a **Utilização do armazenamento** na aplicação Obsidian em **[[Configurações]] → Sync**.

### Quantos cofres remotos posso ter?

O número de cofres remotos que pode ter é determinado com base no seu [[Planos e limites de armazenamento#Plans|plano do Sync]]. O plano Standard inclui 1 cofre; o plano Plus inclui 10 cofres. Os cofres partilhados consigo não contam para o limite de cofres.

### Qual o tamanho máximo de cada cofre remoto?

Não existe limite por cofre. O limite de armazenamento está associado à sua conta e pode ser distribuído por todos os seus cofres.

### Com quantas pessoas posso partilhar um cofre remoto?

Pode [[Colaborar num cofre partilhado|partilhar um cofre remoto]] com até 20 pessoas.

### Qual o tamanho máximo de cada ficheiro?

O tamanho máximo de ficheiro depende do seu [[Planos e limites de armazenamento|plano do Obsidian Sync]]. Para o plano Standard, o limite é de 5 MB. Para o plano Plus, o limite é de 200 MB por ficheiro.

### Os meus dados são sincronizados em segundo plano?

Não, os ficheiros só são sincronizados quando o Obsidian está em execução.

### O Obsidian Sync recarrega as configurações em tempo real?

O Obsidian Sync pode recarregar automaticamente certas configurações, mas existem algumas limitações. Para mais detalhes, consulte [[Configurações do Sync e sincronização seletiva#Reloading of settings|Recarga de configurações]].

### Posso utilizar um serviço de sincronização de terceiros com o Obsidian Sync?

Não recomendamos a utilização de um serviço de sincronização de terceiros em conjunto com o Obsidian Sync. A utilização de um serviço de terceiros e do Obsidian Sync em vários dispositivos pode originar conflitos, resultando em ficheiros duplicados ou corrompidos.

Serviços de armazenamento em nuvem como o OneDrive e o Dropbox oferecem funcionalidades de "Ficheiros a pedido" ou "Ficheiros apenas online", que transferem os ficheiros apenas quando necessário e removem-nos localmente para poupar espaço. No entanto, como estes ficheiros nem sempre estão disponíveis localmente, o Obsidian Sync irá interpretá-los como eliminados, levando à sua remoção do cofre remoto.

Para evitar estes problemas, desactive as transferências a pedido ao utilizar o Obsidian Sync com serviços como o OneDrive ou o Dropbox. Terá de garantir que as configurações do serviço de terceiros estão configuradas para manter sempre os ficheiros no dispositivo.

## Retenção de dados

Estas são perguntas frequentes sobre a retenção de dados do Obsidian. Para respostas mais detalhadas, consulte [[Obsidian Sync/Segurança e privacidade|Segurança e privacidade]].

### Durante quanto tempo é conservado o histórico de versões?

O [[Histórico de versões]] depende do seu [[Planos e limites de armazenamento|plano do Obsidian Sync]]. No plano Standard, as suas notas são conservadas durante 1 mês. No plano Plus, as suas notas são conservadas durante 12 meses. Após este período, as versões mais antigas são eliminadas.

As versões mais antigas de [[Anexos|anexos]] são armazenadas durante duas semanas.

### Durante quanto tempo são conservados os meus dados após o fim da subscrição?

Conservamos os dados nos seus cofres remotos, incluindo o histórico de versões, durante um mês após o fim da sua subscrição. Os cofres locais nos seus dispositivos não são afectados.

Desde que renove dentro de um mês, não deverá haver qualquer impacto na sua utilização. Se renovar após um mês, quando os seus cofres remotos já tiverem sido removidos, pode [[Configurar o Obsidian Sync|criar um novo cofre remoto]] e ligar o seu cofre local.

### Os meus dados são conservados se solicitar o reembolso da subscrição?

Não. Os dados são eliminados imediatamente dos servidores do Obsidian Sync. Os dados no seu [[Cofres locais e remotos|cofre local]] não são afectados.
