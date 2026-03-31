---
permalink: sync/version-history
cssclasses:
  - soft-embed
publish: true
mobile: true
description: Obsidian Sync keeps a record of all changes made to your notes and regularly checks for updates and creates new versions of your notes.
---
O [[Introdução ao Obsidian Sync|Obsidian Sync]] verifica regularmente se existem actualizações nos seus [[Configurações do Sync e sincronização selectiva|ficheiros sincronizados]], registando todas as alterações. Estas ficam armazenadas como novas entradas no [[#Histórico de versões]]. Pode aceder a esta informação de várias formas:

- [[#Histórico do Sync]]
- [[#Histórico de versões]]

Embora não faça parte do Obsidian Sync, um histórico de versões local também está disponível em cada dispositivo se o plugin [[Recuperação de ficheiros]] estiver activo.

## Histórico do Sync

A funcionalidade de histórico do Sync (ou barra lateral do Sync), introduzida na versão 1.7 do Obsidian, permite-lhe consultar rapidamente as notas e anexos criados ou modificados recentemente que foram sincronizados. Pode também encarar isto como um histórico de _edição_.

Na barra lateral, pode seleccionar um item para abrir o ficheiro correspondente na janela activa. Os itens também dispõem de menus de contexto que permitem realizar acções como mover o ficheiro ou consultar o seu [[#Notas e anexos|histórico de versões]].

> [!compatibility] Funcionalidade exclusiva para desktop
> Ao passar o rato sobre um ficheiro sincronizado na barra lateral, pode ver quem editou o ficheiro pela última vez. Isto é especialmente útil se estiver a [[Colaborar num cofre partilhado|colaborar]] num cofre partilhado.

> [!tip] 
> As configurações e os itens eliminados não aparecem na barra lateral do histórico do Sync. Estes podem ser encontrados no [[#Notas e anexos|histórico de versões]].

### Mostrar o histórico do Sync

Quando activa o plugin de base [[Introdução ao Obsidian Sync|Sync]], o histórico do Sync é automaticamente activado, mas não aparece na barra lateral por omissão. Terá de o adicionar manualmente através de um comando ou de um atalho de teclado.

#### Activar através da Paleta de comandos

> [!info] Esta opção requer que o plugin de base [[Paleta de comandos]] esteja activo.

**Desktop/Tablet** ![[lucide-monitor-check.svg#icon]]

1. Abra a **Paleta de comandos**. ![[lucide-terminal.svg#icon]]
2. Escreva "Sync".
3. Seleccione a opção "Sync: Show Sync history".

O histórico do Sync aparecerá então na [[Barra lateral|barra lateral direita]].

**Móvel** ![[obsidian-icon-smartphone.svg#icon]]

1. Abra a [[Faixa de opções]] ![[lucide-menu.svg#icon]].
2. Abra a **Paleta de comandos**. ![[lucide-terminal.svg#icon]]
3. Escreva "Sync".
4. Seleccione a opção "Sync: Show Sync history".

O histórico do Sync aparecerá então como uma opção de lista pendente na [[Barra lateral|barra lateral direita]].

#### Activar através de um atalho de teclado

1. Abra as **[[Configurações]]**.
2. Na categoria **Opções**, seleccione **Atalhos de teclado**.
3. Na barra de pesquisa de atalhos, escreva "Sync".
4. Junto a "Sync: Show Sync history", atribua o atalho de teclado que preferir.

## Histórico de versões

Para além do [[#Histórico do Sync]], o Obsidian também mantém um histórico de versões para restaurar notas e anexos. Se eliminar uma nota por engano ou quiser reverter para uma versão anterior, pode restaurá-la a partir do histórico de versões.

O período de retenção do histórico de versões depende do seu [[Planos e limites de armazenamento|plano do Obsidian Sync]]. No plano Standard, as notas são conservadas durante 1 mês; no plano Plus, são mantidas durante 12 meses. Após este período, as versões mais antigas das notas são eliminadas.

Para os [[Anexos|anexos]], as versões mais antigas são armazenadas durante <u>duas semanas</u>.

![[Colaborar num cofre partilhado#^version-history-image]]

### Notas e anexos

O processo de restauro é igual tanto para notas como para anexos.

#### Ver o histórico de versões de um ficheiro

**Desktop/Tablet** ![[lucide-monitor-check.svg#icon]]
1. No **Explorador de ficheiros**, seleccione a nota que pretende restaurar.
2. Seleccione **Abrir histórico de versões**.
3. Seleccione a versão da nota que pretende ver à esquerda. O conteúdo será apresentado à direita.

**Móvel** ![[obsidian-icon-smartphone.svg#icon]]
1. No **Explorador de ficheiros**, seleccione a nota que pretende restaurar.
2. Mantenha premido para abrir o menu de contexto.
3. Seleccione **Abrir histórico de versões**.
4. No menu de contexto, seleccione a versão da nota que pretende ver.
5. Após a selecção, o conteúdo da nota ficará disponível para revisão.

#### Ver o histórico de versões de um ficheiro eliminado ou renomeado

1. Abra as **[[Configurações]]**.
2. Na barra lateral, em **Plugins de base***, seleccione **Sync**.
3. Junto a **Ficheiros eliminados**, seleccione **Ver**.
4. Seleccione a nota cujo histórico de versões pretende consultar.
5. No painel do histórico de versões, seleccione a versão da nota que pretende ver à esquerda.

#### Restaurar uma versão anterior de um ficheiro

**Desktop/Tablet** ![[lucide-monitor-check.svg#icon]]
1. No **Explorador de ficheiros**, seleccione a nota que pretende restaurar.
2. Seleccione **Abrir histórico de versões**.
3. Seleccione a versão da nota que pretende restaurar à esquerda. O conteúdo será apresentado à direita.
4. Seleccione o botão **Restaurar**.
5. O conteúdo da nota será substituído pela versão restaurada.

**Móvel** ![[obsidian-icon-smartphone.svg#icon]]
1. No **Explorador de ficheiros**, seleccione a nota que pretende restaurar.
2. Mantenha premido para abrir o menu de contexto.
3. Seleccione **Abrir histórico de versões**.
4. No menu de contexto, seleccione a versão da nota que pretende restaurar.
5. Após a selecção, o conteúdo da nota ficará disponível para revisão.
6. Seleccione o botão **Restaurar**.
7. O conteúdo da nota será substituído pela versão restaurada.

#### Restaurar um ficheiro eliminado

1. Abra as **[[Configurações]]**.
2. Na barra lateral, em **Plugins de base***, seleccione **Sync**.
3. Junto a **Ficheiros eliminados**, seleccione **Ver**.
4. Escolha a nota que pretende restaurar.
5. Na lista de versões à esquerda, seleccione a versão que pretende restaurar.
6. Seleccione o botão **Restaurar** à direita.
7. A nota será restaurada para a sua localização original no sistema de ficheiros.

> [!tip] Pode seleccionar várias notas com **restauro em massa** marcando as caixas de selecção, ou utilizando `shift+clique`. Estes ficheiros não poderão ser revistos neste menu.

### Histórico de configurações

O Obsidian Sync também regista as alterações feitas às configurações do cofre.

#### Ver o histórico de versões de uma configuração

1. Abra as **[[Configurações]]**.
2. Na barra lateral, em **Plugins de base***, seleccione **Sync**.
3. Navegue até **Sincronização de configuração do cofre**.
4. Seleccione o botão **Ver** junto a **Histórico de versões de [[Configurações]]**.
5. Na janela de contexto **Ficheiro de [[Configurações]]**, escolha o ficheiro de configurações que pretende ver.

#### Restaurar uma versão anterior de uma configuração

1. Abra as **[[Configurações]]**.
2. Na barra lateral, em **Plugins de base**, seleccione **Sync**.
3. Navegue até **Sincronização de configuração do cofre**.
4. Seleccione o botão **Ver** junto a **Histórico de versões de [[Configurações]]**.
5. Na janela de contexto **Ficheiro de [[Configurações]]**, escolha o ficheiro de configurações que pretende ver.
6. Na janela de alterações, seleccione o botão **Restaurar**.
7. Recarregue ou reinicie o Obsidian para que a configuração entre em vigor. Para mais detalhes, consulte as instruções em [[Configurar o Obsidian Sync#Adjust Obsidian Sync settings|Ajustar as configurações do Obsidian Sync]].
