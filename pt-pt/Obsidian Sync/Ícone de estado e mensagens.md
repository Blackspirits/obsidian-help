---
permalink: sync/messages
publish: true
mobile: true
description: This page explains the Obsidian Sync status icons and provides details about the sync activity log.
---

O Obsidian Sync disponibiliza vários elementos para indicar o estado da sincronização, principalmente o [[#Ícone de estado do Sync]] e o [[#Registo de atividade do Sync]]. Os detalhes sobre o controlo de versões no Obsidian Sync estão disponíveis na página [[Histórico de versões]].

## Ícone de estado do Sync

O ícone de estado do Sync encontra-se na [[Barra de estado]] na versão de desktop e na [[Barra lateral#Open hidden sidebars|barra lateral direita]] em dispositivos móveis e tablets. O ícone reflecte os vários estados de sincronização:

- ![[obsidian-icon-sync-synced.svg#icon]] **Sincronizado**: O Obsidian Sync sincronizou completamente os seus ficheiros. Este ícone é normalmente verde.
- ![[obsidian-icon-sync-syncing.svg#icon]] **A sincronizar**: O Obsidian está a atualizar o cofre remoto. Este ícone é normalmente roxo.
- ![[obsidian-icon-sync-paused.svg#icon]] **Em pausa**: A sincronização foi pausada, mas o Obsidian ainda está ligado ao cofre remoto. O ícone é normalmente roxo.
- ![[obsidian-icon-sync-disconnected.svg#icon]] **Desligado**: O plugin de base do Sync está ativo, mas o [[Cofres locais e remotos|cofre local]] não está ligado a um cofre remoto. Este ícone é normalmente vermelho.

Ao clicar ou tocar no ícone, abre-se um menu de contexto com as seguintes opções:
- ![[obsidian-icon-sync-paused.svg#icon]] Pausar (ou ![[lucide-circle-play.svg#icon]] Retomar se estiver em pausa)
- ![[lucide-history.svg#icon]] [[Histórico de versões]] (A cinzento se não estiver a ver uma nota)
- ![[lucide-align-left.svg#icon]] Abrir [[#Registo de atividade do Sync|registo do Sync]]
- ![[lucide-trash-2.svg#icon]] [[Histórico de versões#Restore a deleted file|Ficheiros eliminados]]
- ![[lucide-cog.svg#icon]] [[Configurações do Sync e sincronização seletiva|Configurações do Sync]]

## Registo de atividade do Sync

O Obsidian Sync inclui um registo detalhado que acompanha todas as interacções entre os seus ficheiros locais e o cofre remoto. O registo mostra carregamentos, transferências, eliminações e quaisquer problemas como conflitos de combinação ou problemas de conectividade.

**Aceder ao registo de atividade:**
- Clique no ícone de estado do Sync na barra de estado
- Aceda a **[[Configurações]] → Sync → Registo de atividade**
- Use **Paleta de comandos → Sync: Open activity log**

O registo fornece carimbos temporais e detalhes para cada operação de sincronização, sendo útil para resolver problemas de sincronização.

> [!warning] O registo do Sync não persiste após o encerramento do Obsidian. Se encontrar um problema, certifique-se de que copia o registo _antes_ de fechar a aplicação.

O registo categoriza as mensagens nos seguintes tipos:

- [[#Mensagens gerais]]
- [[#Mensagens de erro]]
- [[#Mensagens de itens ignorados]]
- [[#Mensagens de conta]]

Pode filtrar o registo do Sync por **Todos**, **Erros**, **Ignorados** e **Conflitos de combinação**. Adicionalmente, pode pesquisar no registo do Sync utilizando a caixa de pesquisa na janela do Sync.

> [!summary] Incluímos abaixo algumas das mensagens mais prováveis com que se pode deparar. A lista não é exaustiva. Se estiver a ter um problema e não tiver a certeza sobre uma mensagem do registo do Sync, [[Ajuda e suporte#Contact Obsidian support|contacte o suporte da Obsidian]].

### Mensagens gerais

Estas são mensagens comuns do dia-a-dia com que pode deparar-se.

**A ligar ao servidor**  
O Obsidian está a tentar ligar-se ao [[Obsidian Sync/Segurança e privacidade#Where can I find my current Sync server and where is it hosted?|servidor do Sync]] do seu cofre remoto.

**Ligado ao servidor. A detectar alterações...**  
O Obsidian estabeleceu uma ligação e está a comparar o cofre local com o cofre remoto para determinar se são necessárias alterações.

> [!info] Esta mensagem também pode indicar outros potenciais problemas do Sync. Se a vir repetidamente e acreditar que ainda existem itens a sincronizar, [[Ajuda e suporte#Contact Obsidian support|contacte o suporte da Obsidian]].

**Totalmente sincronizado**  
- Os cofres local e remoto estão completamente sincronizados.

**A combinar ficheiro em conflito**  
Foi detectado um conflito durante a sincronização e o ficheiro foi combinado em vez de substituído. Consulte [[Resolução de problemas do Obsidian Sync#Conflict resolution|resolução de conflitos]] para mais informações. Se a combinação não for desejada, pode restaurar versões anteriores através do [[Histórico de versões]] ou da [[Recuperação de ficheiros]].

**Alteração do servidor rejeitada**  
As alterações no cofre remoto são mais antigas do que a versão no seu dispositivo local, por isso a versão local é mantida e a alteração remota é ignorada.

### Mensagens de erro

Estas são mensagens que detalham um erro na sincronização de um ficheiro.

**Memória insuficiente**  
Este problema ocorre normalmente em dispositivos móveis quando não há espaço de armazenamento ou memória suficiente para transferir um ficheiro. É mais comum com ficheiros grandes, como vídeos.

### Mensagens de itens ignorados

Estas são mensagens que detalham o que foi ignorado e, potencialmente, porquê.

**Impossível transferir ficheiro com nome inválido**

O ficheiro contém um [carácter especial ou convenção de nomenclatura](https://stackoverflow.com/questions/1976007/what-characters-are-forbidden-in-windows-and-linux-directory-names) que não é permitido no sistema operativo de destino. Para facilitar, pode renomear o ficheiro no dispositivo de origem para remover todos os caracteres especiais excepto `-` e `_`.

Note que isto também inclui ficheiros com múltiplos pontos `.` no nome em dispositivos Android.

### Mensagens de conta

Estas são mensagens relacionadas com uma alteração na sua subscrição ou conta.

**Limite do cofre excedido**  
A sua conta excedeu o [[Perguntas frequentes#How large can each remote vault be|tamanho máximo de armazenamento]]. Os anexos e o histórico de versões contribuem para este tamanho. Mesmo que o seu cofre pareça menor do que o limite, versões e ficheiros mais antigos podem ultrapassá-lo.

Para reduzir o tamanho do cofre:
1. Abra **[[Configurações]] → Sync**.
2. Utilize as opções em **Tamanho do cofre acima do limite** para remover ficheiros grandes.

**Cofre não encontrado**  
`{"res":"err","msg":"Vault not found."}`

Este erro pode ocorrer nestes casos:

1. O cofre foi eliminado de outro dispositivo.
2. A subscrição do sync esteve inactiva durante mais de 30 dias, fazendo com que o cofre remoto fosse removido.
3. A subscrição foi cancelada ou reembolsada, resultando na eliminação do cofre remoto.

Nestes casos, terá de [[Configurar o Obsidian Sync#Disconnect from a remote vault|desligar do cofre remoto]] e [[Configurar o Obsidian Sync#Create a new remote vault|criar um novo cofre remoto]], garantindo que os dados locais são preservados.

**Falha na autenticação: A sua subscrição do Obsidian Sync expirou**  
A sua conta está agora em estado completamente expirado, pois não foi possível processar o pagamento registado.

Para continuar a utilizar o Obsidian Sync, terá de subscrever novamente em [a sua conta](https://obsidian.md/account/sync).

**Falha na autenticação: Não iniciou sessão**

O Obsidian Sync detectou que não tem sessão iniciada. Terá de iniciar sessão novamente na aplicação, na secção [[Configurações#General#Account|Conta]] das **[[Configurações]]**.

Em alguns casos, um plugin da comunidade também pode impedir que o Obsidian Sync confirme o estado de início de sessão da sua conta. Entre no **[[Segurança de plugins#Restricted mode|Modo restrito]]** e tente novamente.

### Mensagens de rede

**Desligado do servidor**
`Unable to connect to server`

O Obsidian Sync desligou-se do servidor do Sync por razão desconhecida. O Sync tentará restabelecer a ligação ao servidor periodicamente.

No iOS, esta mensagem é apresentada como o seguinte erro:
`Null is not an object (evaluating 'this.socket.send')`

Significa exactamente o mesmo que a mensagem `Unable to connect to server`, e não indica de forma alguma que algo mais esteja errado.
