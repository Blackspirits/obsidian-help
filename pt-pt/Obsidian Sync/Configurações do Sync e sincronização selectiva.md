---
permalink: sync/settings
publish: true
mobile: true
description: This page explains the Sync settings and guides you in selecting which files to sync.
---

Quando [[Planos e limites de armazenamento#Create a new remote vault|cria um cofre remoto]] e [[Configurar o Obsidian Sync#Connect to a remote vault|se liga a ele]], o plugin nativo Sync torna-se o local para gerir o seu cofre remoto.

## Definições do Sync

**Cofre remoto**
Esta secção mostra o seu cofre remoto actualmente ligado. Inclui um botão **Disconnect** para se desligar do cofre remoto e um botão **Manage** para ver todos os cofres remotos aos quais a sua conta tem acesso (incluindo cofres partilhados através de [[Colaborar num cofre partilhado|colaboração]]).

> [!warning]+ Cofre remoto num serviço de sincronização de terceiros
> Se o seu cofre remoto estiver localizado num serviço de sincronização de terceiros, verá uma mensagem de erro a vermelho. Siga os passos em [[Migrar para o Obsidian Sync]] para resolver este problema.

**Estado da sincronização**
Apresenta o estado de sincronização actual do cofre remoto. Esta secção inclui um botão **Pause** ou **Resume**, dependendo do estado.

**Nome do dispositivo**
Atribua um nome único ao dispositivo que está actualmente a sincronizar. Isto ajuda a acompanhar a actividade no [[Ícone de estado e mensagens#Sync activity log|registo do Sync]]. Esta definição é específica do dispositivo, tal como a [[#Selective syncing|sincronização selectiva]].

**[[#Conflict resolution|Resolução de conflitos]]**
Escolha como resolver conflitos quando modifica um ficheiro em vários dispositivos. Esta definição é específica do dispositivo, tal como a [[#Selective syncing|sincronização selectiva]].

**Ficheiros eliminados**
Contém um botão para **View** ou **Restore** ficheiros eliminados. Para mais detalhes, consulte [[Histórico de versões]].

**Utilização de armazenamento**
Apresenta uma barra de progresso que mostra quanto do seu armazenamento de sincronização está a ser utilizado.

> [!tip]- Tempo de processamento do servidor
> Pode demorar até 30 minutos para a utilização actual ser actualizada devido ao processamento do lado do servidor.

**Contactar suporte**
Fornece instruções sobre como [[Ajuda e suporte#Contact Obsidian support|contactar o suporte do Obsidian]], incluindo opções para **Copy debug info** e **Email support**.

### Resolução de conflitos

Escolha como resolver conflitos quando modifica um ficheiro em vários dispositivos antes de sincronizar. Pode fundir automaticamente as alterações ou criar ficheiros de conflito separados para revisão manual. Consulte [[Resolução de problemas do Obsidian Sync#Conflict resolution|Resolução de conflitos]] para obter detalhes sobre como os conflitos funcionam e como configurar esta definição.

> [!warning]+ Configurar em cada dispositivo
> Esta definição deve ser configurada separadamente em cada dispositivo.

---

Também pode escolher o que sincronizar nas definições do plugin nativo Sync. Esta secção aborda a **sincronização selectiva** e a **sincronização da configuração do cofre**, juntamente com as respectivas ressalvas.

## Sincronização selectiva

Os ficheiros sincronizados para o seu [[Cofres locais e remotos|cofre remoto]] contribuem para o seu [[Perguntas frequentes#How large can each remote vault be|limite de armazenamento]]. Por predefinição, o Obsidian Sync activa a **sincronização selectiva** para os seguintes tipos de ficheiros:
- Imagens
- Áudio
- Vídeos
- PDFs

Para sincronizar tipos de ficheiros adicionais, active a opção `Sync all other types`.

As definições predefinidas de **sincronização da configuração do cofre** incluem:
- Outros tipos de ficheiros
- Definições principais
- Aparência
- Temas e fragmentos
- Atalhos de teclado
- Lista de plugins nativos activos
- Definições dos plugins nativos

Para sincronizar plugins da comunidade, active manualmente **Active community plugin list** e **Installed community plugin list**.

### Alterar os tipos de ficheiros que pretende sincronizar

1. Abra **[[Configurações]] → Sync**.
2. Em **Selective sync**, active os tipos de ficheiros que pretende sincronizar.
3. Reinicie a aplicação para aplicar as novas definições. Em dispositivos móveis ou tablets, pode ser necessário forçar o fecho.

Note que o seu [[Planos e limites de armazenamento|plano Sync]] define o tamanho máximo de ficheiro que pode sincronizar. O plano Standard permite sincronizar ficheiros até 5 MB, enquanto o plano Plus suporta ficheiros até 200 MB.

> [!info]+ Os ficheiros excluídos permanecem no cofre remoto
> Adicionar um ficheiro à lista de **Excluded files** não o remove do cofre remoto se já tiver sido sincronizado. Configure as suas definições do Sync antes de sincronizar para evitar utilizar armazenamento desnecessário.

### Excluir uma pasta da sincronização

Por predefinição, o Obsidian sincroniza todos os ficheiros e pastas no seu cofre. Para excluir uma pasta específica da sincronização:
1. Abra **[[Configurações]] → Sync**.
2. Junto a **Excluded folders**, seleccione **Manage**.
3. Seleccione a pasta que pretende excluir da lista.
4. Seleccione **Done**.

Para remover uma pasta da lista de exclusões, seleccione o botão ![[lucide-x.svg#icon]] junto ao nome da pasta.

#### Sempre excluído da sincronização

##### Instantâneos de recuperação de ficheiros

Os instantâneos do plugin [[Recuperação de ficheiros]] não são sincronizados através do Obsidian Sync, uma vez que os instantâneos são mantidos nas [[Como o Obsidian armazena dados#Global settings|Definições globais]].

##### Ficheiros e pastas ocultos

Os ficheiros e pastas que começam com `.` são tratados como ocultos e excluídos da sincronização. A única excepção é a [[Pasta de configuração|pasta de configuração]] do cofre (`.obsidian`), que é sincronizada.

Exemplos comuns de ficheiros e pastas ocultos que não são sincronizados:
- `.vscode`
- `.git`
- `.idea`
- `.gitignore`

##### Definições do Sync

As definições do Sync não são sincronizadas entre dispositivos. É necessário configurá-las separadamente em cada dispositivo conforme necessário.

## Actualizar as definições do cofre sincronizado

Para modificar as definições de sincronização em vários dispositivos, siga estes passos:

> [!tip]- Dispositivos primário e secundários
> Os termos "primário" e "secundário" são apenas para clareza. O Sync não faz distinção entre eles.

### Dispositivo primário

O dispositivo primário actua como fonte de verdade. As alterações efectuadas aqui são sincronizadas para todos os outros dispositivos.

1. Vá a **[[Configurações]] → Sync**.
2. Active as definições desejadas em **Vault configuration sync**.
3. Recarregue ou reinicie o Obsidian. Em dispositivos móveis ou tablets, pode ser necessário forçar o fecho.
4. Aguarde algum tempo para que as definições sejam sincronizadas com o seu cofre remoto.

### Dispositivo(s) secundário(s)

Os dispositivos secundários (como o seu telemóvel) recebem actualizações do dispositivo primário.

1. Vá a **[[Configurações]] → Sync**.
2. Active as definições necessárias em **Vault configuration sync**.
3. Aguarde que as alterações sejam transferidas do cofre remoto.
4. Recarregue ou reinicie a aplicação para aplicar as definições sincronizadas. Em dispositivos móveis ou tablets, pode ser necessário forçar o fecho.

### Recarregamento de definições

Certas definições podem ser recarregadas em tempo real, enquanto outras requerem um reinício:

- **Recarregamento em tempo real**: A maioria das configurações do Obsidian, incluindo atalhos de teclado e propriedades, definições de aparência e configurações de plugins nativos já activados.
- **Requer recarregamento**: Alterações CSS (por exemplo, [[Fragmentos CSS]], [[Temas]]), configurações da vista de grafo e estados de plugins nativos (por exemplo, activar/desactivar Notas diárias).

Os plugins da comunidade normalmente não suportam recarregamento em tempo real e requerem um reinício quando são aplicadas novas definições.

> [!info]+ Para programadores de plugins
> Saiba como [integrar funcionalidade de recarregamento em tempo real com o Obsidian Sync](https://docs.obsidian.md/Reference/TypeScript+API/Plugin/onExternalSettingsChange).

## Perfis de definições

O Obsidian Sync pode sincronizar várias [[Pasta de configuração|pastas de configuração]] para o mesmo cofre remoto, permitindo-lhe criar perfis separados (por exemplo, um para dispositivos móveis, outro para o seu portátil).

### Criar um perfil de definições

Para criar um novo perfil de definições:

1. Abra **[[Configurações]] → Files and links**.
2. Em **Override config folder**, introduza um nome para o seu perfil, começando com um ponto (`.`), por exemplo, `.obsidian-mobile`.
3. Reinicie o Obsidian para aplicar as alterações.

> [!info]+ Evitar transferir novamente plugins e temas
> Alterar o perfil de definições irá requerer a reconfiguração das suas definições de sincronização. Para evitar transferir novamente plugins e temas, copie a sua pasta `.obsidian` existente e renomeie-a para corresponder ao seu novo perfil (por exemplo, `.obsidian-mobile`) antes de efectuar alterações.
