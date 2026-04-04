---
permalink: import/onenote
---
O Obsidian permite-lhe migrar facilmente as suas notas do Microsoft OneNote utilizando o [[Importador|plugin Importer]]. Isto irá converter os seus dados do OneNote em ficheiros Markdown duradouros, que pode utilizar com o Obsidian e muitas outras aplicações.

> [!Warning]
> Apenas podem ser importados cadernos pertencentes à sua conta pessoal. Notas partilhadas ou contas de trabalho e escolares não são suportadas.

## Importar os seus dados do OneNote para o Obsidian

Precisará do plugin oficial do Obsidian [[Importador]], que pode [instalar aqui](obsidian://show-plugin?id=obsidian-importer).

1. Abra as **[[Configurações]]**.
2. Vá a **Plugins da comunidade** e [instale o Importer](obsidian://show-plugin?id=obsidian-importer).
3. Ative o plugin Importer.
4. Abra o plugin **Importer** utilizando a paleta de comandos ou o ícone da faixa de opções.
5. Em **Formato de ficheiro**, escolha **Microsoft OneNote**.
6. Clique em **Iniciar sessão** para abrir o seu navegador web na página de início de sessão da Microsoft. Introduza as credenciais da sua conta Microsoft que contém os seus Cadernos do OneNote. Mais informações sobre o processo de início de sessão da Microsoft estão disponíveis abaixo.
7. Clique em **Aceitar** para conceder ao Obsidian permissão para ver os seus Cadernos do OneNote.
8. Clique em **Abrir Ligação** para permitir que o seu navegador o redirecione para a aplicação Obsidian.
9. Na aplicação Obsidian, a caixa de diálogo do Importer irá agora mostrar que tem sessão iniciada e listar os seus Cadernos e Secções do OneNote. Marque as secções que pretende importar.

![[OneNote-Importer-Select-Sections.png]]

10. Clique em **Importar** e aguarde até que a importação esteja concluída.
11. Concluído!

## Resolução de problemas

### Não aparecem secções ou cadernos

Certifique-se de que os cadernos que está a tentar importar estão sincronizados com o OneDrive e visíveis no OneNote Web. Devem ser da sua propriedade (cadernos partilhados escritos por outros não são suportados).

Se uma secção específica estiver em falta, certifique-se de que não é uma secção bloqueada — essas são invisíveis sem remover o bloqueio primeiro.

### As notas importadas estão vazias ou com conteúdo em falta

Este problema pode ocorrer em cadernos que raramente utiliza. Para resolver o problema, siga estes passos:

1. Abra o [OneNote Web](https://onenote.com/notebooks) no seu navegador.
2. **Clique com o botão direito** nos Cadernos com conteúdo em falta.
3. Selecione **Exportar Caderno** no menu.
4. **Descomprima** o ficheiro que acabou de descarregar numa pasta.
5. Carregue os seus cadernos do OneNote [aqui](https://www.onenote.com/notebooks/exportimport?toImport=true).
6. Abra o **Obsidian Importer** e tente importar novamente.

Se seguiu estas sugestões e o seu problema continuar por resolver, é possível que haja um problema temporário nos servidores da Microsoft. Nesse caso, aguarde alguns minutos e tente novamente. Se o problema persistir, abra um problema no [repositório GitHub do Obsidian Importer](https://github.com/obsidianmd/obsidian-importer/issues).

## Privacidade

O plugin Importer do Obsidian utiliza [OAuth](https://learn.microsoft.com/en-us/azure/ative-directory/develop/v2-oauth2-auth-code-flow) para autenticar com a sua conta Microsoft e importar os seus cadernos do OneNote. Isto concede um token de acesso de curta duração à sua conta, que é utilizado apenas a partir do seu computador e nunca é armazenado. Após a conclusão da importação, pode opcionalmente revogar o token na [página de aplicações e serviços da Microsoft](https://account.live.com/consent/Manage).
