---
permalink: resources
publish: true
mobile: true
description: ‘Encontre recursos de suporte, reporte violações de segurança ou da comunidade, e saiba como contribuir para o Obsidian.’
---

Encontre recursos de suporte, reporte violações de segurança ou da comunidade, e saiba como contribuir para o Obsidian.

## Perguntas e conselhos

Se tiver uma pergunta sobre como utilizar o Obsidian, ou quiser conhecer outros utilizadores do Obsidian, pode juntar-se a um dos nossos canais da comunidade:

- [[Cofre sandbox|Explorar o cofre Sandbox]]
- [Entrar no nosso servidor Discord](https://discord.gg/obsidianmd)
- [Visitar o fórum](https://forum.obsidian.md/)

### Reportar erros e solicitar funcionalidades

> [!tip]- Verificar duplicados primeiro
> Antes de solicitar uma nova funcionalidade ou reportar um erro, consulte as outras publicações para se certificar de que alguém ainda não o submeteu.

Se pretender sugerir uma funcionalidade no Obsidian, aceda a [Pedidos de funcionalidades](https://forum.obsidian.md/c/feature-requests/8).

Se pretender reportar um erro no Obsidian, aceda a [Relatórios de erros](https://forum.obsidian.md/c/bug-reports/7). Os relatórios de erros são movidos para o [Cemitério de erros](https://forum.obsidian.md/c/bug-graveyard/12) assim que forem resolvidos.

### Recolher informações de depuração

Quando encontrar um erro ou precisar de assistência do [[#Contact Obsidian support|suporte do Obsidian]], fornecer informações de depuração pode ser muito útil. Eis como obtê-las:

1. Abra a [[Paleta de comandos]].
2. Escreva **Show debug info**.
3. Selecione a opção destacada **Show debug info**.
4. Selecione **Copy to clipboard**.
5. Cole as informações copiadas no seu relatório de erro ou no email de suporte do Obsidian.

### Verificar o tempo de arranque

Pode verificar quanto tempo o Obsidian demora a arrancar utilizando a funcionalidade **Startup time**.

1. Abra **[[Configurações]] → General → Advanced**.
2. Junto a **Notify if startup takes longer than expected**, selecione o **ícone de temporizador**.
3. Será apresentada uma janela **Startup time** com informações detalhadas de tempo:
   - **Total app startup**: Tempo total de arranque.
   - **Initialization**: Tempo gasto a carregar a própria aplicação.
   - **Vault**: Tempo para carregar os ficheiros do cofre.
   - **Workspace**: Tempo para restaurar separadores e o layout.
   - **Core plugins**: Tempo utilizado pelos plugins nativos ativos.
4. Pode selecionar **Copy to clipboard** para copiar o relatório para resolução de problemas ou partilha.

Adicionalmente, pode ativar ou desativar **Notify if startup takes longer than expected** para receber um aviso se o arranque for invulgarmente lento.

### Capturar registos da consola

Quando precisar de reportar um erro relacionado com um plugin do Obsidian ou quando solicitado pelo [[#Contact Obsidian support|suporte do Obsidian]] para fornecer informações de registo, pode precisar de aceder à consola do Obsidian a partir da aplicação. Eis como fazê-lo consoante o sistema operativo:

- **Windows/Linux**: `Ctrl+Shift+I`
- **macOS**: `Command+Option+I`

> [!info]+ Método de acesso alternativo
> Se estiver a utilizar o estilo de moldura de janela **Obsidian frame**, também pode aceder à consola do Obsidian através do menu de título.

Após abrir a consola de programador:

1. Selecione **console** no menu superior.
2. Escolha a opção **errors** no menu lateral. Quaisquer erros serão apresentados como `# errors`.
3. Selecione uma das mensagens de erro a vermelho.
4. Escolha a opção **Save as...** Isto irá guardar todos os erros da consola.
5. Guarde o ficheiro de registo no seu dispositivo.
6. Anexe o ficheiro de registo ao seu relatório de erro ou ao email de suporte do Obsidian.

![[help-support-console-menu.png#interface|600]]

> [!warning]+ Acesso à consola em dispositivos móveis
> Os dispositivos móveis e tablets têm acesso limitado às suas consolas de programador. Para estes utilizadores, recomendamos a utilização do plugin da comunidade [Logstravaganza](https://obsidian.md/plugins?id=logstravaganza) para gerar automaticamente os dados do registo da consola numa nota Markdown.

### Contactar o suporte do Obsidian

O Obsidian oferece suporte por email apenas para questões relacionadas com [[Licença comercial|licenças comerciais]], a sua conta, pagamentos e serviços adicionais ([[Introdução ao Obsidian Sync|Obsidian Sync]] e [[Introdução ao Obsidian Publish|Obsidian Publish]]). Se precisar de ajuda com algum desses tópicos, [envie um email à equipa do Obsidian](mailto:support@obsidian.md).

## Reportar um problema de segurança

Se descobriu um problema de segurança no Obsidian, ou se suspeita que um plugin é malicioso, [envie um email à equipa do Obsidian](mailto:support@obsidian.md).

## Reportar uma violação do Código de Conduta

Seja vítima ou testemunha de uma violação do nosso [[Código de conduta da comunidade]], pode reportar o incidente à nossa equipa de moderadores.

Reporte o incidente num dos seguintes canais da comunidade:

- [[Código de conduta da comunidade#Report on Discord|Reportar no Discord]]
- [[Código de conduta da comunidade#Report on the forum|Reportar no fórum]]

## Contribuir para o Obsidian

Interessado em aplicar as suas competências e tempo livre ao Obsidian? Eis onde a sua ajuda seria muito bem-vinda:

- Ajude outros utilizadores do Obsidian respondendo a perguntas no nosso [servidor Discord](https://discord.gg/obsidianmd), no nosso [fórum](https://forum.obsidian.md/), ou no reddit [ObsidianMD](https://old.reddit.com/r/ObsidianMD/).
- [[Desenvolvedores]], a sua ajuda para expandir a nossa [Documentação para Programadores do Obsidian](https://github.com/obsidianmd/obsidian-developer-docs) seria muito valiosa.
- Conhece algum idioma escrito além do inglês? Considere ajudar com as nossas [[Traduções]] para outros idiomas.
- Há algo nesta documentação de ajuda que esteja desatualizado ou confuso? Consulte o [[Guia de estilo]] e submeta um [issue e pull request](https://github.com/obsidianmd/obsidian-help/issues?q=is%3Aissue+is%3Aopen+sort%3Aupdated-desc).
- Se possível, pode [[Contribuições financeiras|contribuir financeiramente]] utilizando um dos nossos serviços pagos.
