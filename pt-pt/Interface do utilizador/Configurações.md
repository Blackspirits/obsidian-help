---
aliases:
  - Obsidian settings
description: Aprenda a personalizar o Obsidian através da interface de Configurações.
mobile: true
permalink: settings
publish: true
---

As configurações permitem-lhe personalizar a sua experiência com o Obsidian. Configure opções gerais, preferências do editor, aparência, atalhos de teclado e gerencie plugins nativos e da comunidade.

## Abrir Configurações

### Computador

Na [[Barra lateral#Open hidden sidebars|barra lateral esquerda]], selecione **[[Configurações]]** ![[lucide-cog.svg#icon]]. Também pode abrir as Configurações com a [[Paleta de comandos]].

### Dispositivo móvel

Na barra lateral esquerda, selecione **[[Configurações]]** ![[lucide-cog.svg#icon]].

## Organização das Configurações

As configurações estão organizadas nas seguintes categorias:

- **Opções** — Configurações principais da aplicação, incluindo [[#General|Geral]], [[#Editor]], [[#Files and links|Ficheiros e ligações]], [[#Appearance|Aspeto]] e [[#Hotkeys|Teclas de atalho]].
- **[[Plugins nativos]]** — Plugins integrados que acompanham o Obsidian.
- **[[Plugins da comunidade]]** — Plugins de terceiros instalados pela comunidade.

## Geral

A página Geral contém informações de versão, definições de atualização, preferências de idioma e gestão de conta.

### Versão e atualizações

Veja a sua versão atual do Obsidian e a versão do instalador no topo da página. Selecione **Verificar atualizações** para verificar manualmente novas versões, ou selecione **[Ler o registo de alterações](<https://obsidian.md/changelog/>)** para ver as notas de lançamento.

**Atualizações automáticas**

Quando ativado, o Obsidian verifica automaticamente novas versões e notifica-o quando há atualizações disponíveis.

**Receber versões de acesso antecipado**

Atualizar automaticamente para as [[Versões de acesso antecipado]] mais recentes. Estas versões incluem novas funcionalidades mas podem ser menos estáveis.

> [!info]+ Licença Catalyst necessária
> Esta opção só está disponível para utilizadores com uma [[Licença Catalyst]].

### Idioma

Selecione o seu idioma preferido para a interface do Obsidian. Selecione **[[Traduções|Saiba como adicionar um novo idioma ao Obsidian]]** para contribuir com uma tradução.

### Ajuda

Selecione **[[Início|Abrir]]** para aceder aos recursos de ajuda, incluindo documentação, fóruns da comunidade e guias de resolução de problemas.

### Conta

Gira a sua conta e licenças do Obsidian.

**A sua conta**

Veja as informações da sua conta, incluindo nome de utilizador e email. Selecione **[Gerir](https://obsidian.md/account)** para aceder às definições da conta, ou selecione **Terminar sessão** para sair da aplicação.

**Licença Catalyst**

Veja o estado da sua licença Catalyst. Se tiver uma [[Licença Catalyst]] ativa, o seu nível de licença aparece aqui.

**Licença Comercial**

Se suporta o [Obsidian para trabalho](<https://obsidian.md/blog/free-for-work/>), selecione **Ativar** para introduzir uma chave de licença comercial, ou selecione **[Comprar](https://obsidian.md/account/commercial)** para adquirir uma licença. Selecione **[[Licença comercial|Saber mais]]** para informações sobre licenças Comerciais.

### Avançadas

#### Notificar se o arranque demorar mais do que o esperado

Quando ativado, o Obsidian apresenta uma notificação se o arranque for invulgarmente lento. A notificação inclui informações de diagnóstico sobre o que está a causar o atraso. Selecione o ícone do temporizador ![[lucide-timer.svg#icon]] junto a esta definição para [[Ajuda e suporte#Check startup time|verificar o tempo de arranque]].

## Editor

A página Editor contém definições sobre como visualiza e edita notas.

### Focar sempre novos separadores

Quando abre uma ligação num novo separador, muda para ele imediatamente.

### Vista predefinida para novos separadores

A vista predefinida em que um novo separador de ficheiro Markdown é aberto. Escolha entre [[Vistas e modo de edição#Reading view|Vista de leitura]] ou [[Vistas e modo de edição#Editing view|Vista de edição]].

### Modo de edição predefinido

O modo de edição predefinido com que um novo separador começa. Escolha entre [[Vistas e modo de edição#Live Preview|Live Preview]] ou [[Vistas e modo de edição#Source mode|Modo de código-fonte]].

### Mostrar modo de edição na barra de estado

Mostra o alternador de modo de edição na [[Barra de estado|barra de estado]].

### Apresentação

#### Comprimento de linha legível

Limita o comprimento máximo da linha. Menos conteúdo cabe no ecrã, mas os blocos de texto longos são mais legíveis.

#### Quebras de linha estritas

As especificações Markdown ignoram [[Sintaxe de formatação básica#Line breaks|quebras de linha]] únicas na vista de leitura. Desative para tornar as quebras de linha únicas visíveis.

#### Propriedades no documento

Escolha como as [[Propriedades|propriedades]] são apresentadas no topo das notas. Selecione **código-fonte** para mostrar as propriedades em YAML em bruto.

#### Dobrar cabeçalho

[[Dobramento|Dobra]] todo o conteúdo sob um cabeçalho selecionando o ícone de recolher ao lado.

### Dobrar indentação

[[Dobramento|Dobra]] parte de uma indentação, como listas, selecionando o ícone de recolher.

#### Mostrar números de linha

Mostra números de linha na margem.

#### Mostrar guias de indentação

Mostra linhas verticais de relação entre itens de lista.

#### Direita para a esquerda (RTL)

Define a direção de texto predefinida das notas como da direita para a esquerda.

#### Auto-emparelhar parênteses

Emparelha parênteses e aspas automaticamente.

#### Auto-emparelhar sintaxe Markdown

Emparelha símbolos automaticamente para negrito, itálico, código e mais.

#### Listas inteligentes

Define automaticamente a indentação e posiciona os itens de lista corretamente.

#### Indentar usando tabulações

Usa tabulações para indentar premindo a tecla Tab. Desative para indentar usando 4 espaços.

#### Converter HTML colado para Markdown

Converte automaticamente HTML para Markdown ao colar e arrastar e largar de páginas web.

Use `Ctrl/Cmd+Shift+V` para colar HTML sem converter.

### Comportamento

#### Verificação ortográfica

Ativa o verificador ortográfico. Selecione o ícone de engrenagem para remover itens guardados do dicionário personalizado.

#### Idiomas de verificação ortográfica

**Windows e Linux:**

Escolha os idiomas que o verificador ortográfico deve usar. Selecione o ícone de mais (+) para adicionar idiomas. Para remover um idioma, selecione o X ao lado.

**macOS:**

O verificador ortográfico nativo deteta automaticamente o idioma usado pelo sistema operativo.

#### Largura visual de indentação

Número de espaços que um carácter de tabulação renderiza.

### Avançadas

#### Ligações de teclas Vim

Usa ligações de teclas Vim ao editar.

## Ficheiros e ligações

A página Ficheiros e ligações contém definições para gestão de ficheiros, ligações e comportamento do cofre.

### Localização predefinida para novas notas

Onde as notas recentemente criadas são colocadas. As opções incluem:

- **Pasta do cofre** — As notas são criadas na raiz do seu cofre.
- **Mesma pasta que o ficheiro atual** — As notas são criadas na mesma pasta que a nota atualmente ativa.
- **Na pasta especificada abaixo** — As notas são criadas numa pasta específica que escolhe.

### Localização predefinida para novos anexos

Onde os [[Anexos|anexos]] recentemente adicionados são colocados. As opções incluem:

- **Pasta do cofre** — Os anexos são colocados na raiz do seu cofre.
- **Na pasta especificada abaixo** — Os anexos são colocados numa pasta específica que escolhe.
- **Mesma pasta que o ficheiro atual** — Os anexos são colocados na mesma pasta que a nota atualmente ativa.
- **Em subpasta sob a pasta atual** — Os anexos são colocados numa subpasta dentro da pasta da nota atual.

### Ligações

#### Formato de nova ligação

Que ligações inserir ao gerar automaticamente [[Links internos|ligações internas]]. As opções incluem:

- **Caminho mais curto quando possível** — Usa o caminho único mais curto para o ficheiro ligado.
- **Caminho relativo ao ficheiro** — Usa um caminho relativo ao ficheiro atual.
- **Caminho absoluto no cofre** — Usa o caminho completo a partir da raiz do cofre.

#### Atualizar automaticamente ligações internas

Quando ativado, o Obsidian atualiza automaticamente as ligações internas quando renomeia um ficheiro. Desative para ser questionado sobre atualizar as ligações após renomear.

#### Usar Wikilinks

Gera automaticamente Wikilinks para `[[ligações]]` e `![[imagens]]` em vez de ligações e imagens Markdown. Desative esta opção para gerar ligações Markdown em vez disso.

#### Mostrar todos os tipos de ficheiro

Mostra ficheiros com qualquer extensão mesmo que o Obsidian não possa abri-los nativamente, para que possa criar ligações para eles e vê-los no Explorador de ficheiros e no Alternador rápido.

### Lixo

#### Confirmar eliminação de ficheiro

Perguntar antes de eliminar um ficheiro.

#### Ficheiros eliminados

O que acontece a um ficheiro após o eliminar. As opções incluem:

- **Mover para o lixo do sistema** — Os ficheiros são movidos para o lixo do seu sistema operativo.
- **Mover para o lixo do Obsidian** — Os ficheiros são movidos para a pasta `.trash` no seu cofre.
- **Eliminar permanentemente** — Os ficheiros são eliminados permanentemente e não podem ser recuperados.

### Avançadas

#### Ficheiros excluídos

Os ficheiros excluídos serão ocultados na [[Pesquisa]], na [[Vista de grafo]] e em Menções não ligadas ([[Links inversos]] e [[Links de saída]]), e menos visíveis no [[Alternador rápido]] e nas sugestões de ligações. Selecione **Gerir** para configurar ficheiros excluídos.

#### Substituir pasta de configuração

Use uma [[Pasta de configuração|pasta de configuração]] diferente da predefinida. Deve começar com um ponto.

#### Permitir callbacks URI

Ativa o uso de x-callback-url através de x-success ou x-error ao processar [[Obsidian URI|URIs do Obsidian]].

#### Reconstruir cache do cofre

Reconstrói a [[Como o Obsidian armazena dados#Metadata cache|cache de metadados]] do cofre. A reconstrução da cache pode demorar alguns segundos a alguns minutos dependendo do tamanho do seu cofre. Selecione **Reconstruir** para iniciar o processo.

## Aspeto

A página Aspeto contém definições para personalizar a aparência do Obsidian.

### Esquema de cores base

Escolha o esquema de cores predefinido do Obsidian. As opções incluem:

- **Adaptar ao sistema** — Corresponde ao modo claro ou escuro do seu sistema operativo.
- **Claro** — Usa o modo claro.
- **Escuro** — Usa o modo escuro.

### Cor de destaque

Escolha a cor de destaque usada em toda a aplicação. Selecione o seletor de cor ou o ícone de repor para personalizar.

### Temas

Gira [[Temas|temas]] instalados e navega por temas da comunidade. Selecione **Gerir** para ver e instalar temas. O menu pendente mostra o seu tema atualmente ativo. O ícone de pasta ![[lucide-folder-open.svg#icon]] abre a pasta de temas na sua [[Pasta de configuração|pasta de configuração]].

### Temas da comunidade atuais

Apresenta o número de temas da comunidade que tem instalados.

### Tipo de letra

#### Tipo de letra da interface

Define o tipo de letra base para todo o Obsidian. Selecione **Gerir** para escolher um tipo de letra personalizado ou introduzir um nome de tipo de letra.

#### Tipo de letra de texto

Define o tipo de letra para as vistas de edição e leitura. Selecione **Gerir** para escolher um tipo de letra personalizado ou introduzir um nome de tipo de letra.

#### Tipo de letra monoespaçado

Define o tipo de letra para locais como blocos de código e frontmatter. Selecione **Gerir** para escolher um tipo de letra personalizado ou introduzir um nome de tipo de letra.

#### Tamanho do tipo de letra

Tamanho do tipo de letra em píxeis que afeta as vistas de edição e leitura. Ajuste usando o controlo de deslize.

#### Ajuste rápido do tamanho do tipo de letra

Ajuste o tamanho do tipo de letra usando `Ctrl+Scroll` (Windows/Linux) ou `Cmd+Scroll` (macOS), ou usando o gesto de aproximar dedos no trackpad.

### Interface

#### Mostrar título inline

Apresenta o nome do ficheiro como título editável inline com o conteúdo do ficheiro. O título inline atua como um cabeçalho dentro do Obsidian, mas não adiciona um cabeçalho à sua nota.

#### Mostrar barra de título do separador

Apresenta o cabeçalho no topo de cada separador.

#### Mostrar faixa de opções

Apresenta a barra de ferramentas vertical no lado da janela. Saiba mais sobre a [[Faixa de opções|faixa de opções]].

#### Configuração do menu da faixa de opções

Configure que comandos aparecem no menu da faixa de opções. Selecione **Gerir** para personalizar.

> [!info]+ Configuração da faixa de opções em dispositivos móveis
> Em dispositivos móveis, a personalização da faixa de opções funciona de forma diferente. Consulte [[Faixa de opções#Mobile|Personalização da faixa de opções em dispositivos móveis]] para mais detalhes.

### Avançadas

#### Nível de zoom

Controla o nível de zoom geral da aplicação. Ajuste usando o controlo de deslize.

#### Menus nativos

Os menus em toda a aplicação corresponderão ao sistema operativo. Não serão afetados pelo seu tema.

#### Estilo do frame da janela

Determina o estilo da barra de título das janelas do Obsidian. Requer um reinício completo para ter efeito. As opções incluem:

- **Frame do Obsidian** — Usa o frame de janela personalizado do Obsidian.
- **Frame nativo** — Usa o frame de janela predefinido do seu sistema operativo.
- **Frame oculto** — Oculta completamente a barra de título.

#### Ícone personalizado da aplicação

Define um ícone personalizado para a aplicação. Selecione **Escolher** para selecionar um ficheiro de ícone (`.icns`, `.ico`, `.png` ou `.svg`). Saiba mais sobre [[Aparência#Custom app icon|ícones de aplicação personalizados]].

#### Janela translúcida

Ativa o efeito de translucidez para melhorar a sensação de profundidade. Melhor usado com o modo escuro. Não suportado no Linux.

> [!info]+ Apenas macOS
> Esta funcionalidade é principalmente concebida para macOS. Saiba mais sobre [[Aparência#Translucency|translucidez]].

#### Aceleração de hardware

Ativa a Aceleração de Hardware, que usa a sua GPU para tornar o Obsidian mais fluido. Se desativar, o desempenho da aplicação pode ser severamente degradado, mas pode resolver alguns problemas raros.

### Fragmentos CSS

Gira e veja [[Fragmentos CSS|fragmentos CSS]] armazenados no seu cofre. Os fragmentos CSS são armazenados em `/cofre/.obsidian/snippets/`. Selecione o ícone de atualizar para recarregar fragmentos, ou o ícone de pasta ![[lucide-folder-open.svg#icon]] para abrir a pasta de fragmentos.

## Teclas de atalho

A página [[Teclas de atalho]] permite-lhe ver, definir e personalizar [[Atalhos de edição|atalhos de teclado]] para comandos no Obsidian.

Use a barra de pesquisa para filtrar comandos e selecione o ícone de filtro para mostrar apenas comandos com teclas de atalho atribuídas. Para adicionar uma tecla de atalho, selecione o ícone de mais (+) ao lado de um comando. Para remover uma tecla de atalho, selecione o ícone X ao lado da combinação de teclado.

## Plugins nativos

Os [[Plugins nativos]] são plugins integrados que acompanham o Obsidian. Cada plugin adiciona funcionalidade específica à aplicação.

Para ativar ou desativar um plugin nativo, selecione o alternador ao lado do nome do plugin. Selecione o ícone de mais ![[lucide-plus-circle.svg#icon]] para ver as [[Teclas de atalho]] do plugin. Selecione o ícone de definições ![[lucide-settings.svg#icon]] para abrir a página de definições do plugin.

Use a barra de pesquisa para filtrar plugins por nome.

## Plugins da comunidade

Os [[Plugins da comunidade]] são plugins de terceiros criados pela comunidade Obsidian. Navegue e instale plugins selecionando **Navegar**.

### Modo restrito

O [[Segurança de plugins#Restricted mode|Modo restrito]] desativa todos os plugins da comunidade por razões de segurança. Selecione **Ativar e recarregar** para ativar o modo restrito.

### Plugins atuais

Apresenta o número de plugins da comunidade que tem instalados. Selecione **Verificar atualizações** para verificar atualizações de plugins.

### Plugins instalados

Veja e gira os seus plugins da comunidade instalados. Use a barra de pesquisa para filtrar plugins por nome. Cada plugin tem ícones para definições, teclas de atalho, financiamento, desinstalação e um alternador para ativar ou desativar.
