---
permalink: publish/publish
publish: true
mobile: true
description: Saiba como publicar o seu conteúdo com o Obsidian Publish
---

Esta página explica como gerir o seu conteúdo publicado. Para saber como personalizar o estilo do seu site, consulte [[Personalizar o seu site]].

## Pré-requisitos

- Uma conta Obsidian. Se não tiver uma, [registe-se agora](https://obsidian.md/auth?returnto=%2Faccount%2Fpublish#signup).
- Uma subscrição ativa do Obsidian Publish. Se não tiver uma, subscreva a partir do [painel da sua conta](https://obsidian.md/account/publish).
- O plugin base **Publish** está [[Configurar o Obsidian Publish#Enable Obsidian Publish|ativado]].
- Um [[Gerir sites#Create a new site|site Publish]] foi criado.

## Publicar notas

1. Na **Faixa de opções**, selecione **Publicar alterações** ![[lucide-send.svg#icon]].
2. Na caixa de diálogo **Publicar alterações**, selecione **NOVO** para ver todas as notas não publicadas.
3. Selecione as notas que pretende publicar.
4. Selecione **Publicar**.

## Retirar publicação de notas

As notas permanecem no seu cofre local mesmo depois de retirar a sua publicação.

1. Na **Faixa de opções**, selecione **Publicar alterações** ![[lucide-send.svg#icon]].
2. Na caixa de diálogo **Publicar alterações**, selecione **SEM ALTERAÇÕES** para ver todas as notas publicadas.
3. Selecione as notas cuja publicação pretende retirar.
4. Selecione **Publicar**.

## Atualizar uma nota publicada

1. Na **Faixa de opções**, selecione **Publicar alterações** ![[lucide-send.svg#icon]].
2. Na caixa de diálogo **Publicar alterações**, selecione **ALTERADO** para ver todas as notas modificadas desde a última publicação.
3. Selecione as notas que pretende atualizar.
4. Selecione **Publicar**.

> [!hint] A eliminação de notas e imagens renomeadas ou removidas do Publish acontece neste passo. Deve selecionar manualmente a caixa de verificação para eliminar estes dados, pois não são selecionados automaticamente por segurança.

## Publicar dados com links

Ao publicar notas que contêm links para outras notas ou imagens incorporadas, podem ocorrer links quebrados a não ser que as notas ligadas também sejam publicadas. O **Obsidian Publish** ajuda a evitar isto ao selecionar automaticamente os ficheiros multimédia ligados a partir das notas que já escolheu.

Para incluir todas as notas ligadas, selecione **Adicionar ligadas** na caixa de diálogo **Publicar alterações**.

Antes de publicar, reveja a seleção atualizada para garantir que não inclui dados que ainda não está pronto para publicar.

> [!tip] A função **Adicionar ligadas** respeita todas as exclusões definidas em [[#Ignorar dados]].

## Selecionar automaticamente dados para publicar

Defina `publish: true` nas [[Propriedades]] de uma nota para a incluir automaticamente para publicação como nota nova ou alterada.

Também pode selecionar automaticamente notas e imagens ligadas em pastas específicas adicionando-as como pastas **Incluídas**:

1. Na **Faixa de opções**, selecione **Publicar alterações** ![[lucide-send.svg#icon]] ou abra a [[Paleta de comandos]] e escreva **Publish: Publish changes...**.
2. Selecione o ícone **Gerir filtros de publicação** ![[lucide-filter.svg#icon]].
3. Na secção **Pastas incluídas**, selecione **Gerir**.
4. Escolha as pastas que pretende incluir a partir do seletor.
5. A pasta é adicionada à lista de inclusão.
6. Selecione **Concluído** quando terminar.

### Ignorar dados

Para ignorar uma nota no Obsidian Publish, defina `publish: false` nas [[Propriedades]] da nota. A nota deixa de aparecer na lista de notas para publicar.

Também pode ignorar automaticamente notas e imagens em pastas específicas adicionando-as como pastas **Excluídas**:

1. Na **Faixa de opções**, selecione **Publicar alterações** ![[lucide-send.svg#icon]] ou abra a [[Paleta de comandos]] e escreva **Publish: Publish changes...**.
2. Selecione o ícone **Gerir filtros de publicação** ![[lucide-filter.svg#icon]].
3. Na secção **Pastas excluídas**, selecione **Gerir**.
4. Escolha as pastas que pretende excluir a partir do seletor.
5. A pasta é adicionada à lista de exclusão.
6. Selecione **Concluído** quando terminar.

> [!note] `publish: true` substitui as pastas excluídas
> Se um ficheiro tiver `publish: true`, continuará a ser publicado mesmo que esteja numa pasta ou filtro excluído. Isto deve-se ao facto de `publish: true` conferir um controlo mais específico.
