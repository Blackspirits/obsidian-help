---
permalink: import/csv
---
O Obsidian permite-lhe importar dados de ficheiros CSV usando o plugin oficial [[Importador|Importer]]. Isto é útil se tiver dados tabulares armazenados em aplicações como Excel, Google Sheets, Numbers, Notion ou Airtable.

A importação de CSV gera ficheiros Markdown para cada linha e um ficheiro [[Introdução ao Bases|Base]] que apresenta todos os ficheiros importados como uma tabela.

Se estiver a importar notas de uma aplicação específica, poderá querer primeiro consultar a lista de aplicações suportadas pelo [[Importador|plugin Importer]] para verificar se existe um conversor específico que preserve melhor os dados que está a migrar.

## Criar notas a partir de dados CSV no Obsidian

Necessitará do plugin oficial [[Importador]] do Obsidian, que pode [instalar aqui](obsidian://show-plugin?id=obsidian-importer).

1. Abra **[[Configurações]]**.
2. Vá a **Plugins da comunidade** e [instale o Importer](obsidian://show-plugin?id=obsidian-importer).
3. Ative o plugin Importer.
4. Abra o plugin **Importer** usando a paleta de comandos ou o ícone na barra de ferramentas.
5. Em **Formato do ficheiro**, escolha **CSV (.csv).**
6. Selecione a localização do seu ficheiro CSV.
7. Clique em **Importar** para configurar como os dados do seu ficheiro CSV serão convertidos em notas com [[Propriedades]].
8. Clique em **Continuar** e aguarde até a importação estar concluída.
9. Concluído!

## Configurar como os campos CSV são importados

No segundo passo da importação de CSV, pode escolher como os dados são importados usando um modelo.

Cada coluna no seu ficheiro CSV recebe uma variável chamada `{{column_name}}` que representa o nome do cabeçalho no seu ficheiro. Pode usar esta variável para definir o título, localização, conteúdo e [[Propriedades|propriedades]] da nota.
