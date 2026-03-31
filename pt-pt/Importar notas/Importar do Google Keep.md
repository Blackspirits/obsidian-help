---
permalink: import/google-keep
---
O Obsidian permite-lhe migrar facilmente as suas notas do Google Keep utilizando o [[Importador|plugin Importer]]. Isto irá converter os seus dados do Google Keep em ficheiros Markdown duradouros, que pode utilizar com o Obsidian e muitas outras aplicações.

## Exportar os seus dados do Google Keep

1. Vá ao [Google Takeout](https://takeout.google.com/settings/takeout) e inicie sessão na sua conta Google.
2. Clique em **Desselecionar tudo** no canto superior direito.
3. Desloque-se para baixo e selecione **Keep** na lista.
4. Desloque-se até ao fundo da página e clique em **Próximo passo**.
5. No ecrã seguinte, clique no botão **Criar exportação**.
6. Descarregue o ficheiro `.zip` assim que estiver disponível.

## Importar os seus dados do Google Keep para o Obsidian

Precisará do plugin oficial do Obsidian [[Importador]], que pode [instalar aqui](obsidian://show-plugin?id=obsidian-importer).

1. Abra as **[[Configurações]]**.
2. Vá a **Plugins da comunidade** e [instale o Importer](obsidian://show-plugin?id=obsidian-importer).
3. Ative o plugin Importer.
4. Abra o plugin **Importer** utilizando a paleta de comandos ou o ícone da faixa de opções.
5. Em **Formato de ficheiro**, escolha **Google Keep (.zip)**.
6. Selecione a localização do seu ficheiro `.zip`.
7. Clique em **Importar** e aguarde até que a importação esteja concluída.
8. Concluído!

### Funcionalidades suportadas

- Todas as listas de verificação serão importadas como itens de nível superior porque o Google Keep não exporta informações de indentação.
- Os lembretes e atribuições de utilizador nas notas não serão importados porque estas funcionalidades não são suportadas pelo Obsidian.
- Todas as outras informações deverão ser importadas como uma combinação de conteúdo e etiquetas.
