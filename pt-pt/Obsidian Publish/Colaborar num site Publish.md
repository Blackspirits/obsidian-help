---
permalink: publish/collaborate
publish: true
mobile: true
description: Saiba como colaborar com outros utilizadores do Obsidian no seu site Obsidian Publish.
---
Saiba como colaborar no seu site [[Introdução ao Obsidian Publish|Obsidian Publish]] com outros utilizadores do Obsidian. Ao adicionar amigos e colegas como colaboradores, estes podem publicar alterações no seu site.

Apenas o proprietário do site precisa de uma subscrição ativa do Obsidian Publish. Os colaboradores apenas necessitam de uma [conta Obsidian](https://obsidian.md/account).

> [!warning] Antes de publicar alterações num site partilhado, certifique-se de que [[#Sincronizar alterações entre colaboradores|sincroniza as alterações entre colaboradores]]. Caso contrário, corre o risco de sobrescrever alterações de outros colaboradores.

## Adicionar um colaborador a um site

1. Em [[Faixa de opções]], selecione **Publicar alterações** ![[lucide-send.svg#icon]] ou abra a [[Paleta de comandos]] e escreva **Publish: Publish changes...**
2. Na caixa de diálogo **Publicar alterações**, clique em **Alterar opções do site** ![[lucide-cog.svg#icon]].
3. Junto a **Colaboração no site**, selecione **Gerir**.
4. Em **Convidar utilizador**, introduza o e-mail do colaborador.
5. Selecione **Adicionar**.

## Remover um colaborador de um site

1. Em [[Faixa de opções]], selecione **Publicar alterações** ![[lucide-send.svg#icon]] ou abra a [[Paleta de comandos]] e escreva **Publish: Publish changes...**
2. Na caixa de diálogo **Publicar alterações**, clique em **Alterar opções do site** ![[lucide-cog.svg#icon]].
3. Junto a **Colaboração no site**, selecione **Gerir**.
4. Junto ao colaborador que pretende remover, selecione **Remover utilizador** ![[lucide-x.svg#icon]].

## Sincronizar alterações entre colaboradores

O Obsidian Publish não sincroniza automaticamente as alterações publicadas entre cofres locais. Em vez disso, os colaboradores precisam de sincronizar manualmente as alterações de outros colaboradores.

Para atualizar uma nota local com alterações do site em direto:

1. Em [[Faixa de opções]], selecione **Publicar alterações** ![[lucide-send.svg#icon]] ou abra a [[Paleta de comandos]] e escreva **Publish: Publish changes...**
2. Clique com o botão direito ou mantenha premida a alteração que pretende sincronizar e selecione **Usar versão em direto**. **Esta ação irá sobrescrever a nota no seu cofre local.**

> [!tip] Recomendamos que utilize outra ferramenta para sincronizar as alterações entre cofres, como o [[Introdução ao Obsidian Sync|Obsidian Sync]] ou o [git](https://git-scm.com/).

## Permissões

A tabela seguinte lista as permissões de site disponíveis para proprietários e colaboradores:

| Ação                                        | Colaborador | Proprietário |
|---------------------------------------------|:-----------:|:------------:|
| Publicar novas páginas                      | ✓           | ✓            |
| Publicar alterações em páginas publicadas   | ✓           | ✓            |
| Retirar publicação de páginas               | ✓           | ✓            |
| Configurar opções do site                   |             | ✓            |
| Gerir permissões                            |             | ✓            |
