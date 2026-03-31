---
permalink: publish/sites
---
Esta página explica como gerir sites do [[Introdução ao Obsidian Publish|Obsidian Publish]].

Um site é uma coleção de notas alojadas pelo Obsidian Publish e disponíveis online, seja através de um endereço do Obsidian Publish ou de um [[Domínios personalizados|domínio personalizado]].

## Criar um novo site

> [!note] O número de sites que pode ter simultaneamente é determinado pela sua subscrição do Obsidian Publish. Antes de criar um novo site, certifique-se de que a sua subscrição o permite.

1. Na faixa de opções, à esquerda da janela da aplicação, clique em **Publish changes** ![[lucide-send.svg#icon]].
2. Se já tiver um site existente, clique em **Switch site** ![[lucide-repeat.svg#icon]].
3. Em **Site ID**, introduza o caminho que pretende para o seu site. Por exemplo, um site com o ID `my-amazing-site` estará disponível em publish.obsidian.md/my-amazing-site.
4. Clique em **Create**.

## Eliminar um site existente

> [!note] As notas permanecem no seu cofre mesmo depois de eliminar um site.

1. Na faixa de opções, à esquerda da janela da aplicação, clique em **Publish changes** ![[lucide-send.svg#icon]].
2. Clique em **Switch site** ![[lucide-repeat.svg#icon]].
3. Clique em **Delete site** ![[lucide-x.svg#icon]] à direita do site que pretende eliminar.
4. Clique em **Delete** para confirmar.

## Alternar entre sites

1. Na faixa de opções, à esquerda da janela da aplicação, clique em **Publish changes** ![[lucide-send.svg#icon]].
2. Clique em **Switch site** ![[lucide-repeat.svg#icon]].
3. Clique em **Choose** à direita do site para o qual pretende mudar.

## Alterar o ID do site

1. Na faixa de opções, à esquerda da janela da aplicação, clique em **Publish changes** ![[lucide-send.svg#icon]].
2. Clique em **Switch site** ![[lucide-repeat.svg#icon]].
3. Clique em **Edit site ID** ![[lucide-edit-3.svg#icon]] à direita do site que pretende editar.
4. Em **Site ID**, introduza o novo ID para o seu site.
5. Clique em **Change**.

## Ver as opções do site

1. Na faixa de opções, à esquerda da janela da aplicação, clique em **Publish changes** ![[lucide-send.svg#icon]].
2. Na caixa de diálogo **Publish changes**, clique em **Change site options** ![[lucide-cog.svg#icon]].

## Opções do site

### Geral

| Opção                           | Tipo    | Descrição                                                                                                                          |
| ------------------------------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| Site Name                       | Entrada | O nome público e título do seu site do Obsidian Publish.                                                                           |
| Homepage File                   | Entrada | A localização do ficheiro markdown que pretende que seja a sua página de entrada.                                                  |
| Logo                            | Entrada | A imagem que pretende usar como banner do site. A imagem deve [[Publicar o seu conteúdo#Publish notes\|estar publicada]].      |
| Site Collaboration              | Botão   | Declare outros utilizadores a quem pretende dar acesso para editar as suas notas publicadas. Os utilizadores devem ter uma conta Obsidian. |
| Custom Domain                   | Botão   | [[Domínios personalizados]]                                                                                                        |
| Disallow search engine indexing | Toggle  | Impede que motores de busca que respeitam as diretivas rastreiem o seu site ao adicionar um ficheiro `robots.txt`.                 |

### Aparência

| Opção             | Tipo       | Descrição                                                                                          |
|-------------------|------------|----------------------------------------------------------------------------------------------------|
| Theme             | Lista      | Escolha como o tema é apresentado no seu site; **Light**, **Dark** ou **Adapt to System**.         |
| Light/Dark Toggle | Toggle     | Permite que os utilizadores alternem entre o modo **Light**/**Dark** com um botão no seu site.     |

## Experiência de leitura

| Opção                | Tipo    | Descrição                                                                                                   |
|----------------------|---------|-------------------------------------------------------------------------------------------------------------|
| Show hover preview   | Toggle  | Ativa ou desativa a pré-visualização de página ao passar o cursor sobre uma ligação interna ativa.          |
| Hide page title      | Toggle  | Ativa ou desativa a apresentação do título em linha de uma nota publicada.                                  |
| Readable line length | Toggle  | Ativa ou desativa o comprimento de linha legível no seu site.                                               |
| Strict line breaks   | Toggle  | Ativa ou desativa a apresentação de quebras de linha simples no seu site.                                   |
| Stack Pages          | Toggle  | Ativa ou desativa os [[Separadores#Stack tab groups\|separadores empilhados]] no seu site.         |

### Componentes

| Opção                  | Tipo    | Descrição                                                                                                                                    |
|------------------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Show navigation        | Toggle  | Ativa ou desativa a vista do [[Explorador de ficheiros]] no seu site Publish.                                                                        |
| Customize navigation   | Botão   | [[Personalizar o seu site#Customize navigation\|Personalizar]] a ordem de apresentação dos seus ficheiros quando **Show navigation** está ativado. |
| Show search bar        | Toggle  | Ativa ou desativa uma barra de pesquisa no seu site.                                                                                         |
| Show graph view        | Toggle  | Ativa ou desativa a vista de grafo na barra lateral direita do seu site.                                                                     |
| Show table of contents | Toggle  | Ativa ou desativa a vista [[Outline\|Índice]] no seu site.                                                                                   |
| Show backlinks         | Toggle  | Ativa ou desativa os [[Links inversos]] no seu site.                                                                                               |

### Outras definições do site

| Opção                          | Tipo    | Descrição                                                                         |
| ------------------------------ | ------- | --------------------------------------------------------------------------------- |
| Passwords                      | Botão   | [[Obsidian Publish/Segurança e privacidade#Add a site password\|Definir uma palavra-passe]] para restringir o acesso a todo o site. |
| Google Analytics tracking code | Entrada | **Apenas URL de Domínio Personalizado**. Coloque aqui o código de rastreio do Google Analytics para o seu site.                    |
