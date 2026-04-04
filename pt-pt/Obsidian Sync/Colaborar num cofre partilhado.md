---
permalink: sync/collaborate
publish: true
mobile: true
description: This page details how you can collaborate with other Obsidian Sync users.
---
Com o [[Introdução ao Obsidian Sync|Obsidian Sync]] pode colaborar num cofre partilhado com a sua equipa.

Todos os colaboradores devem ter uma subscrição ativa do Sync para aceder a um cofre partilhado. Aderir a um cofre partilhado não conta para o seu [[Perguntas frequentes#How many remote vaults can I have?|limite de cofres]].

Se o cofre remoto tiver [[Obsidian Sync/Segurança e privacidade|encriptação ponta a ponta]], os colaboradores devem introduzir a palavra-passe de encriptação quando configuram o cofre.

## Gerir utilizadores

### Adicionar utilizadores

Para convidar um utilizador a partilhar um cofre remoto:

1. Abra as **[[Configurações]]**.
2. No menu lateral, seleccione **Sync**.
3. Junto a **Remote vault**, seleccione **Manage**.
4. Junto ao cofre remoto que pretende partilhar, seleccione **Manage sharing** ![[lucide-users.svg#icon]].
5. Em **Invite user**, introduza o e-mail do utilizador que pretende convidar.
6. Seleccione **Add**.

### Remover utilizadores

1. Abra as **[[Configurações]]**.
2. No menu lateral, seleccione **Sync**.
3. Junto a **Remote vault**, seleccione **Manage**.
4. Junto ao utilizador cujo acesso pretende remover, seleccione **Remove user** ![[lucide-x.svg#icon]].

## Colaborar com a sua equipa

### Permissões

As permissões granulares ainda não são suportadas. Todos os colaboradores recebem as mesmas permissões que o proprietário do cofre, com uma excepção: apenas o proprietário do cofre pode convidar colaboradores.

### Edição em tempo real

Os cofres partilhados permitem que as equipas trabalhem em conjunto num conjunto de ficheiros, no entanto o Obsidian ainda não suporta edição colaborativa em tempo real no mesmo ficheiro. Não verá o cursor do outro utilizador, e as suas edições só aparecerão depois de as alterações serem sincronizadas.

Se vários utilizadores estiverem a editar o mesmo ficheiro ao mesmo tempo, as [[Resolução de problemas do Obsidian Sync#Conflict resolution|alterações serão fundidas]] durante o processo de sincronização. As alterações podem ser visualizadas e restauradas utilizando o [[Histórico de versões]].

![[version-history-collaboration.png]]^version-history-image

## Limitações

Tenha em atenção que o Obsidian Sync tem [[Perguntas frequentes|limitações]] que podem afectar a sua equipa:

- O número máximo de colaboradores num cofre partilhado é de 20 utilizadores.
- O tamanho máximo de ficheiro para anexos depende do [[Planos e limites de armazenamento|plano]] do anfitrião do seu cofre remoto, com 5 MB para o Plano Standard e 200 MB para o Plano Plus.

Saiba mais sobre [[Sync para equipas]].
