---
permalink: publish/customize
publish: true
description: Saiba como personalizar a aparência e o estilo do seu site do Obsidian Publish.
---
Esta página explica como pode personalizar o aspeto e a experiência do seu site do [[Introdução ao Obsidian Publish|Obsidian Publish]].

## Recursos estáticos

Pode personalizar o seu site [[Publicar o seu conteúdo#Publish notes|publicando]] os seguintes ficheiros:

- `publish.css` para adicionar CSS personalizado
- `publish.js` para adicionar JavaScript personalizado
- `favicon-32x32.png` para definir o favicon

**Notas:**

- As [variáveis CSS para o Publish](https://docs.obsidian.md/Reference/CSS+variables/Publish/Publish) estão disponíveis no nosso site de Documentação.
- Como o Obsidian não suporta ficheiros CSS ou JavaScript, precisa de usar outra aplicação para os criar e editar.
- Tanto `publish.css` como `publish.js` devem estar localizados no diretório raiz (`/`) do seu cofre.
- Por predefinição, `publish.css` e `publish.js` não aparecem no explorador de ficheiros, mas pode publicá-los a partir da caixa de diálogo **Publish changes**.
- Para usar JavaScript personalizado com `publish.js`, precisa de [[Domínios personalizados]].

Para favicons, o Obsidian Publish suporta as seguintes convenções de nomenclatura, onde `32` representa as dimensões do ícone em píxeis:

- `favicon-32.png`
- `favicon-32x32.png`
- `favicon.ico`

Recomendamos que forneça uma ou mais das seguintes dimensões:

- `favicon-32x32.png`
- `favicon-128x128.png`
- `favicon-152x152.png`
- `favicon-167x167.png`
- `favicon-180x180.png`
- `favicon-192x192.png`
- `favicon-196x196.png`

Tem flexibilidade para colocar os favicons em qualquer lugar dentro do cofre, desde que sejam publicados no seu site.

## Usar um tema da comunidade

Para usar um dos temas da comunidade no seu site:

1. Abra o seu cofre no explorador de ficheiros predefinido do seu sistema operativo.
2. Vá à pasta de configurações do cofre (predefinição: `.obsidian`).
3. Abra a pasta `themes`.
4. Copie o ficheiro CSS do tema que pretende usar para o seu site.
5. Cole o ficheiro na pasta raiz do seu cofre.
6. Renomeie o ficheiro CSS para `publish.css`.
7. [[Publicar o seu conteúdo#Publish notes|Publique]] `publish.css`.

**Notas:**

- Se o estilo não atualizar dentro de alguns minutos, tente limpar a cache do browser.
- Pode alternar entre modo claro e escuro nas [[Gerir sites#View site options|opções do site]].
- Muitos temas da comunidade usam **Style Settings** para estilização personalizada, mas estas definições não funcionam no Obsidian Publish.

> [!tip] Desenvolver temas
> Não encontrou o tema adequado? Aprenda a [criar um tema Publish](https://docs.obsidian.md/Themes/Obsidian+Publish+themes/Build+a+Publish+theme) você mesmo.

## Ativar funcionalidades de interface

Pode ativar e desativar várias funcionalidades de interface no seu site, como a vista de grafo ou um índice.

Explore as funcionalidades de interface disponíveis nas secções **Reading experience** e **Components** nas [[Gerir sites#View site options|opções do site]].

### Personalizar a navegação

No Obsidian Publish, tem a possibilidade de personalizar a ordem de navegação e a apresentação de ficheiros e pastas no [[Explorador de ficheiros]] do Publish. Os itens de navegação são listados por ordem de publicação por predefinição. As notas não publicadas não aparecerão neste painel.

#### Aceder às opções de personalização da navegação

1. Na [[Faixa de opções]], selecione **Publish changes** ![[lucide-send.svg#icon]] ou abra a [[Paleta de comandos]] e escreva **Publish: Publish changes...**
2. Na caixa de diálogo **Publish changes**, selecione **Change site options** ![[lucide-cog.svg#icon]].
3. Em **Components settings**, junto a **Customize navigation**, selecione o botão **manage**.

Uma nova janela pop-up intitulada **Navigation** aparecerá sobre a janela **Change site options**.

#### Ajustar os itens de navegação

Na secção com o título **Navigation preview**, pode ajustar a ordem de apresentação do seu conteúdo publicado.

1. Selecione a pasta ou nota que pretende ajustar.
2. Arraste a nota ou pasta para cima ou para baixo até à posição desejada.
3. No canto inferior direito da janela **Navigation**, selecione **Done**.

O Publish enviará as suas alterações de navegação para o seu site.

#### Ocultar e mostrar itens de navegação

Se existirem notas ou pastas que publicou, mas que não pretende que sejam visíveis na sua Navegação, pode optar por ocultá-las.

1. Selecione a pasta ou nota que pretende ajustar.
2. Clique com o botão direito e selecione **Hide in navigation**. O item deverá desaparecer da **Navigation preview**.
3. No canto inferior direito da janela **Navigation**, selecione **Done**.

O Publish enviará as suas alterações de navegação para o seu site.

> [!tip] Pode **mostrar os ficheiros ocultos** selecionando a caixa de seleção à direita do título **Navigation Preview**

## FAQ

**Posso mover ficheiros de uma pasta para outra dentro da Navegação?**

Não. A estrutura de navegação de ficheiros para notas dentro de pastas tem de ser mantida. Pode ajustar a ordem das notas dentro das pastas (incluindo a raiz do cofre), e a ordem das pastas dentro de outras pastas.

**Posso editar a ordem de múltiplas notas e pastas antes de selecionar Done?**

Sim.

**Como reverter estas alterações?**

- **Ordem de apresentação**: Selecione o ícone **Restore Default** (seta de rotação no sentido anti-horário) junto a **Navigation item display order**. Isto restaurará os seus itens de navegação para ordem alfabética.
- **Estado de ocultação**: Selecione o ícone **Restore Default** (seta de rotação no sentido anti-horário) junto a **Hide pages or folders from navigation**. Isto tornará novamente visíveis os itens de navegação ocultos.
