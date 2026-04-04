---
permalink: sync/setup
cssclasses:
  - soft-embed
publish: true
mobile: true
description: You've purchased Obsidian Sync and are ready to get started. This guide will help you set up and adjust your Obsidian Sync settings for daily use.
---
Adquiriu o Obsidian Sync e está pronto para começar. Este guia irá ajudá-lo a configurar e ajustar as definições do Obsidian Sync para utilização diária.

- **Novo no Obsidian Sync?** Consulte: [[#Set up Obsidian Sync for the first time|Configurar o Obsidian Sync pela primeira vez]]
- **A ligar um segundo dispositivo?** Consulte: [[#Sync a remote vault on another device|Sincronizar um cofre remoto noutro dispositivo]]
- **Precisa de efectuar alterações?** Consulte: [[#Manage your remote vaults|Gerir os seus cofres remotos]]

## Configurar o Obsidian Sync pela primeira vez

Nesta secção, irá criar um novo [[Cofres locais e remotos|cofre remoto]] e ligá-lo a um cofre local existente. Não precisa de criar um cofre local novo e vazio para utilizar o Obsidian Sync para este fim.

> [!info] O seu cofre atual está numa pasta do iCloud, OneDrive, Dropbox ou noutro serviço de sincronização? Se a resposta for **sim**, ou se **não tiver a certeza**, leia [[Perguntas frequentes#Can I use a third-party sync with Obsidian Sync?|isto]] e [[Migrar para o Obsidian Sync]] antes de continuar.

**Pré-requisitos**

- Uma conta Obsidian. Se não tiver uma, [registe-se agora](https://obsidian.md/auth?returnto=%2Faccount%2Fsync#signup).
- Uma [[Planos e limites de armazenamento|subscrição]] ativa do Obsidian Sync. Se não tiver uma, subscreva a partir do [painel da sua conta](https://obsidian.md/account/sync).
- **Recomendado**: Um [[Criar cópia de segurança dos seus ficheiros do Obsidian|sistema de cópias de segurança]] configurado para os seus ficheiros Obsidian. Um serviço de sincronização não é uma cópia de segurança.

### Iniciar sessão com a sua conta Obsidian

1. Abra as **[[Configurações]]**.
2. Na barra lateral, seleccione **General**.
3. Em **Account → Your Account**, seleccione **Log in**.
4. Em **Email**, introduza o seu e-mail.
5. Em **Password**, introduza a sua palavra-passe.
6. Seleccione **Login**.

### Ativar o Obsidian Sync

1. Abra as **[[Configurações]]**.
2. Na barra lateral, em **Options**, seleccione **Core Plugins**.
3. Ative o **Sync**.

### Criar um novo cofre remoto

1. Abra as **[[Configurações]]**.
2. Na barra lateral, seleccione **Sync**.
3. Junto a **Remote vault**, seleccione **Choose**.
4. Seleccione **Create new vault**.
5. Em **Vault name**, introduza o nome do cofre remoto.
6. Em **Region**, escolha a [[Configurar o Obsidian Sync#Regional sync servers|região]] do servidor para o seu cofre remoto.
7. Em **Encryption password**, escolha uma palavra-passe para o seu cofre. Isto cria um cofre com encriptação ponta a ponta. A palavra-passe do cofre é separada da sua conta Obsidian e pode ser diferente para cada um dos seus cofres. Para mais informações, consulte [[Segurança e privacidade]].
8. Seleccione **Create**.

### Ligar a um cofre remoto

1. Seleccione **Connect** junto ao cofre recém-criado.
2. Introduza a palavra-passe que configurou para o cofre no campo **Encryption password**, caso tenha optado pela [[Obsidian Sync/Segurança e privacidade#What does end-to-end encryption mean?|encriptação ponta a ponta]].
3. Seleccione **Unlock vault**.
4. **Não inicie ainda a sincronização.** Verifique as suas definições de sincronização em [[#Adjust Obsidian Sync settings|ajustar as definições do Obsidian Sync]].
    - Se pretender iniciar a sincronização imediatamente, avance para [[#Begin syncing with Obsidian Sync|iniciar a sincronização com o Obsidian Sync]].
5. Se ainda não o fez, feche ou dispense a janela pop-up que lhe pede para **Exclude Folders** e **Start Syncing**. Avance para o próximo passo.

#### Ajustar as definições do Obsidian Sync

1. Navegue para **[[Configurações]]** → **Sync**, se necessário.
2. Se ainda não foi adicionado um nome ao dispositivo, adicione um para facilitar a leitura dos registos do Sync!
3. Ative as definições em **Seletive Sync** e **Vault configuration sync** para indicar quais os itens que devem ser sincronizados de e para o cofre remoto.
    - **Nota**: Se se desligou recentemente de um cofre remoto e está a reconectar-se sem reiniciar a aplicação, algumas definições podem já estar ativadas.
4. Se efectuar alterações a quaisquer definições, reinicie completamente o Obsidian.
5. Depois de o Obsidian ser reiniciado, regresse a **[[Configurações]]** → **Sync**.

#### Iniciar a sincronização com o Obsidian Sync

Se está a iniciar a sincronização após ligar a um cofre remoto, verá um botão **Start Syncing**. Seleccione este botão para iniciar a sincronização.

Se está a iniciar a sincronização após ajustar as definições do Obsidian Sync e reiniciar a aplicação, verá um botão **Resume** nas definições do Sync. Seleccione este botão para iniciar a sincronização.

> [!done] Estado da sincronização
> Quando o Obsidian Sync terminar, um círculo verde com uma marca de verificação ![[obsidian-icon-sync-synced.svg#icon]] aparece no canto inferior direito (computador) ou na barra lateral direita (dispositivos móveis). O registo do Sync também irá apresentar "Fully Synced" como uma das mensagens mais recentes.
>
> Para mais detalhes sobre os estados de sincronização, consulte [[Ícone de estado e mensagens]].
^obsidian-sync-status

Para ligar outros dispositivos ao cofre remoto recém-criado e sincronizado, avance para [[Configurar o Obsidian Sync#Sync a remote vault on another device|Sincronizar um cofre remoto noutro dispositivo]].

Para saber mais sobre definições e ficheiros, avance para [[Configurações do Sync e sincronização seletiva]].

## Sincronizar um cofre remoto noutro dispositivo

Nesta secção, já criou um cofre remoto e carregou dados para o mesmo. Agora, pretende ligar os seus outros dispositivos ao mesmo.

**Pré-requisitos**
- Uma conta Obsidian. Se não tiver uma, [registe-se agora](https://obsidian.md/account#mode=signup).
- Uma subscrição ativa do Obsidian Sync. Se não tiver uma, subscreva a partir do [painel da sua conta](https://obsidian.md/account).
- O Sync ativado nas definições dos [[Plugins nativos]].
- Um cofre remoto ativo. Se ainda não criou um, crie primeiro um [[Configurar o Obsidian Sync#Create a new remote vault|cofre remoto]].
- **Recomendado**: Um [[Criar cópia de segurança dos seus ficheiros do Obsidian|sistema de cópias de segurança]] configurado para os seus ficheiros Obsidian no dispositivo que mais utiliza. Um serviço de sincronização não é uma cópia de segurança.

### Sincronizar o seu cofre a partir do selector de cofres

Se instalou o Obsidian pela primeira vez, ao abrir o programa ser-lhe-á apresentado o [[Gerir cofres|selector de cofres]]. Para criar um novo cofre local a partir do conteúdo de um cofre remoto, siga os passos abaixo.

1. Abra o Obsidian (assumindo que é a primeira vez que o abre)
2. Seleccione uma das opções consoante a sua instalação:
	1. **Computador**: Na secção que diz Open vault from Obsidian Sync, escolha **Setup**
	2. **Dispositivo móvel/Tablet**: **Setup Obsidian Sync**
3. Inicie sessão com a sua conta de utilizador Obsidian
	1. Se a [[Autenticação de 2 fatores|autenticação de 2 factores]] estiver configurada, introduza o seu código 2FA.
4. Ser-lhe-á pedido que escolha qual o cofre remoto que pretende sincronizar com este dispositivo. Seleccione **Connect**.
5. Ser-lhe-á pedido que escolha um nome para o cofre local que será criado no dispositivo para guardar estes dados. Introduza o nome da sua escolha.
	1. Se utilizar [[Obsidian URI]]s, deverá usar o mesmo nome que o cofre local no seu outro dispositivo.
6. Seleccione **Create**.
7. A janela de cofres remotos abrirá momentaneamente enquanto o Obsidian Sync se liga ao servidor e valida a subscrição. De seguida, apresentar-lhe-á uma janela de *Setup Connection*.
	1. É altamente recomendado que feche ou deslize para baixo a partir desta janela e que [[#Adjust Obsidian Sync settings|ajuste as definições do Obsidian Sync]] primeiro.
	2. Se alterar quaisquer definições do Sync, recarregue ou reinicie o Obsidian.

### Sincronizar o seu cofre a partir das Configurações do Obsidian

Se já criou um cofre local neste dispositivo e pretende ligar este cofre local a um cofre remoto, as instruções são muito semelhantes a [[#Set up Obsidian Sync for the first time|Configurar o Obsidian Sync pela primeira vez]].

![[Configurar o Obsidian Sync#Log in with your Obsidian account]]

![[Configurar o Obsidian Sync#Enable Obsidian Sync]]

#### Ligar a um cofre remoto

1. Abra as **[[Configurações]]**.
2. Na barra lateral, seleccione **Sync**.
3. Junto a **Pick remote vault**, clique em **Choose**.
4. Clique em **Connect** junto ao cofre remoto ao qual pretende ligar.
5. Em **Encryption password**, introduza a palavra-passe do seu cofre, se tiver uma.
6. Ser-lhe-á pedido que inicie a sincronização. Recomenda-se aguardar e ajustar primeiro as definições de sincronização. Se pretender sincronizar todo o cofre com o dispositivo tal como está, pode clicar em **Start Syncing**.

> [!warning] Se o cofre no seu dispositivo já contiver algumas notas (não recomendado), será avisado de que essas notas serão fundidas antes de continuar. Os conflitos serão resolvidos através da [[Resolução de problemas do Obsidian Sync#Conflict resolution|resolução de conflitos do Sync]].

![[Configurar o Obsidian Sync#Adjust Obsidian Sync settings]]

![[Configurar o Obsidian Sync#Begin syncing with Obsidian Sync]]

## Gerir os seus cofres remotos

Criou e ligou-se a um cofre remoto. Poderá também ter sincronizado este cofre remoto com vários dispositivos. Esta secção aborda algumas das outras instruções comuns de que poderá necessitar para gerir este cofre remoto.

### Desligar de um cofre remoto

1. Abra as **[[Configurações]]** do Obsidian.
2. Seleccione **Sync** na barra lateral.
3. Clique no botão **Disconnect** junto a Remote vaults.

Está agora desligado do cofre remoto e já não está a sincronizar neste dispositivo.

### Eliminar um cofre remoto

> [!tip] Eliminar um cofre remoto não eliminará os seus dados locais no dispositivo.

1. Abra as **[[Configurações]]**.
2. Na barra lateral, seleccione **Sync**.
3. Seleccione **Manage** junto a Remote vaults. Abrirá uma janela com a sua lista de cofres remotos.
4. Seleccione o ícone do caixote do lixo ![[lucide-trash-2.svg#icon]] junto ao cofre remoto que pretende eliminar.
5. Confirme a eliminação seleccionando o botão vermelho **Delete**.
6. O seu cofre remoto foi eliminado.

> [!info] Se não houver nenhum ícone de caixote do lixo visível, poderá ter de se desligar primeiro do cofre remoto. Após a desligação, seleccione o botão **Choose** para abrir a lista de cofres remotos.

### Servidores de sincronização regionais

O Obsidian Sync permite-lhe escolher a localização de alojamento do seu cofre remoto. Se estiver a utilizar a versão `1.4.16` ou anterior do Obsidian, a localização será escolhida automaticamente.

Se não tiver a certeza de qual é a região do seu cofre atual, consulte [[Obsidian Sync/Segurança e privacidade#Where can I find my current Sync server and where is it hosted?|Onde posso encontrar o meu servidor Sync atual e onde está alojado?]] para obter orientação.

![[sync-regional-sync-servers.png#interface|300]]

Após seleccionar uma localização, o seu centro de dados **não pode** ser movido para um servidor diferente sem recarregar os seus dados. Para alterar regiões, siga o [[Regiões do Sync|guia de regiões do Sync do cofre]].

![[Obsidian Sync/Segurança e privacidade#^sync-geo-regions]]

## Próximos passos

Seguem-se alguns documentos sugeridos para ler a seguir.

- Explore mais sobre [[Configurações do Sync e sincronização seletiva|a selecção de ficheiros e definições a sincronizar]].
- Saiba o que acontece se o seu cofre remoto [[Histórico de versões|ficar cheio]].
- [[Colaborar num cofre partilhado]] com outro utilizador do Obsidian Sync.
- Consulte as [[Perguntas frequentes|Perguntas frequentes do Sync]] para obter respostas a questões comuns.
