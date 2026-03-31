---
permalink: import/notion
---
O Obsidian permite-lhe migrar facilmente as suas notas do Notion utilizando o [[Importador|plugin Importer]]. Isto irá converter os seus dados do Notion em ficheiros Markdown duradouros que pode utilizar offline com o Obsidian e muitas outras aplicações.

O Obsidian oferece duas formas de importar os seus dados do Notion:

1. A **importação via API** preserva toda a sua área de trabalho, incluindo Bases de Dados e fórmulas que são convertidas em [[Introdução ao Bases|Bases]], mas requer um token de integração do Notion e uma ligação à internet.
2. A **importação de ficheiros** não preserva Bases de Dados, mas não requer um token de API nem ligação à internet.

## Importação via API

### Criar um token de integração da API do Notion

Para aceder aos seus dados do Notion através da API, precisa de um token de integração. Este passo demora cerca de 2 minutos a concluir.

O token é uma longa sequência de números e letras que começa tipicamente com `ntn_...` e permitirá descarregar os seus dados do Notion.

1. Inicie sessão no painel de [Integrações do Notion](https://www.notion.so/profile/integrations/internal).
2. Escolha **Nova integração**.

![[notion-integration.png#interface]]

2. Dê um nome à sua integração, por exemplo, "Pessoal". Pode utilizar qualquer nome.
3. Escolha a área de trabalho que pretende exportar.
4. Clique em **Guardar** e continue para **Configurar definições de integração**.
5. No separador **Configuração**, o seu token de API está acessível no campo **Internal Integration Secret**.
6. Selecione **Mostrar** e depois **Copiar**.
7. Guarde o token num local seguro, como o seu gestor de palavras-passe.

![[notion-token.png#interface]]

Em seguida, conceda à sua integração acesso às páginas e bases de dados do Notion que pretende importar.

1. Vá ao separador **Acesso** da integração que acabou de criar.
2. Clique em **Editar acesso**.
3. Adicione as páginas e bases de dados que pretende importar.

Agora pode converter os seus dados utilizando o Obsidian Importer.

### Importar os seus dados do Notion via API

Precisará do plugin oficial do Obsidian [[Importador]], que pode [instalar aqui](obsidian://show-plugin?id=obsidian-importer).

1. Abra as **[[Configurações]]**.
2. Vá a **Plugins da comunidade** e [instale o Importer](obsidian://show-plugin?id=obsidian-importer).
3. Ative o plugin Importer.
4. Abra o plugin **Importer** utilizando a paleta de comandos ou o ícone da faixa de opções.
5. Em **Formato de ficheiro**, selecione **Notion (API)**.
6. Em **Token de API**, cole o seu **Internal Integration Secret** do Notion.
7. Clique em **Carregar** para escolher as bases de dados e páginas que pretende importar.
8. Reveja e edite as opções de importação.
9. Selecione **Importar** e aguarde até que a importação esteja concluída.
10. Concluído!

### Limitações

> [!info] A importação via API é nova
> O importador da API do Notion é novo. Devido à complexidade das áreas de trabalho do Notion, alguns casos extremos podem não ter sido considerados. Se encontrar problemas com a conversão, [submeta um relatório de erros](https://github.com/obsidianmd/obsidian-importer/issues) para que possamos melhorá-lo.

Devido aos limites de taxa da API do Notion, a importação de áreas de trabalho grandes pode demorar um tempo considerável. Tenha paciência.

Devido a limitações na API do Notion, alguns dados não estão disponíveis ou não podem ser convertidos:

- Apenas a vista principal de cada base de dados é importada.
- As [fontes de dados ligadas](https://developers.notion.com/docs/working-with-databases#additional-types-of-databases) não são importadas: *"A API do Notion não suporta atualmente fontes de dados ligadas. Ao partilhar uma base de dados com a sua integração, certifique-se de que contém a fonte de dados original!"*
- Funções `People`: `name()` e `email()`
- Funções `Text`: `style()` e `unstyle()`

Adicionalmente, o Importer fará as seguintes alterações:

- As páginas sem páginas filhas ou bases de dados serão importadas como `[filename].md` em vez de `[filename]/[filename].md`.
- As bases de dados são sempre representadas como pastas com o nome `[nome da base de dados]` com um ficheiro `[nome da base de dados].base` dentro.

## Importação de ficheiros

A importação de ficheiros é uma forma alternativa de importar os seus dados do Notion. Este método não preserva Bases de Dados, mas não requer um token de API nem ligação à internet.

### Exportar os seus dados do Notion

Para preparar os seus dados para importação, precisará de exportar toda a sua área de trabalho utilizando o formato de exportação HTML do Notion. Recomendamos que não utilize a exportação Markdown do Notion, pois omite dados importantes. Deve ter acesso de administrador à área de trabalho do Notion para exportar todo o conteúdo da área de trabalho.

1. Vá a **[[Configurações]]** no topo da barra lateral do Notion.
2. Em **Área de trabalho**, selecione **Geral**.
3. Localize e selecione **Exportar todo o conteúdo da área de trabalho**.
4. Em **Formato de exportação**, selecione **HTML**.
5. Escolha **Incluir tudo**.
6. Ative **Criar pastas para subpáginas**.
7. Receberá um ficheiro `.zip` por e-mail ou diretamente no navegador.

![[notion-export.png#interface]]

![[notion-export-2.png#interface]]

### Importar o seu ficheiro .zip do Notion

Precisará do plugin oficial do Obsidian [[Importador]], que pode [instalar aqui](obsidian://show-plugin?id=obsidian-importer).

1. Abra as **[[Configurações]]**.
2. Vá a **Plugins da comunidade** e [instale o Importer](obsidian://show-plugin?id=obsidian-importer).
3. Ative o plugin Importer.
4. Abra o plugin **Importer** utilizando a paleta de comandos ou o ícone da faixa de opções.
5. Em **Formato de ficheiro**, selecione **Notion (.zip)**.
6. Escolha o ficheiro `.zip` com os ficheiros do Notion que pretende importar. *Recomenda-se importar todo o seu Notion de uma vez para que as ligações internas possam ser reconciliadas corretamente.*
7. _Opcionalmente_, selecione uma pasta para a importação. As suas páginas e bases de dados do Notion serão aninhadas dentro desta pasta.
8. Ative **Guardar páginas principais em subpastas** para manter a estrutura do Notion. *Note que no Notion pode escrever conteúdo em Pastas, o que não é possível no Obsidian, e estas páginas serão adicionadas como uma subpágina sob a pasta.*
9. Selecione **Importar** e aguarde até que a importação esteja concluída.
10. Concluído!

### Resolução de problemas

Se encontrar problemas ao importar do Notion:

- Certifique-se de que utiliza **HTML** como formato de exportação no Notion, **não Markdown**.
- Se o Obsidian parecer bloquear durante a importação, desative os plugins da comunidade e tente novamente.

Encontrou algo diferente? Pesquise [o repositório do Importer](https://github.com/obsidianmd/obsidian-importer/issues) para ver se outros já passaram pela mesma situação.

#### Importar áreas de trabalho grandes

Se estiver a importar uma área de trabalho com vários gigabytes de dados, a exportação do Notion pode conter ficheiros `.zip` aninhados. Nesse caso, pode ver uma mensagem de erro de importação com o seguinte aspeto:

```
Import failed {id}.zip/{id}-Part-1.zip undefined.
```

Se vir este erro, pode descomprimir o ficheiro do Notion e, em seguida, importar os ficheiros `Export-{id}-Part-1.zip` aninhados.
