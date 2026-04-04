---
permalink: web-clipper/templates
description: Aprenda a criar modelos que capturam e organizam metadados de páginas web automaticamente com o Web Clipper.
---
O [[Introdução ao Obsidian Web Clipper|Web Clipper]] permite criar modelos que capturam e organizam automaticamente metadados de páginas web. Modelos de exemplo estão disponíveis no [repositório clipper-templates](https://github.com/kepano/clipper-templates).

## Criar ou editar um modelo

Para **criar** um modelo, aceda às definições do Web Clipper e clique no botão **Novo modelo** na barra lateral. Também pode **duplicar** um modelo no menu de ações **Mais** no canto superior direito.

Para **editar** um modelo, escolha um modelo na barra lateral. As suas alterações serão guardadas automaticamente.

Os modelos fazem uso de [[Variáveis]] e [[Filtros]], que permitem personalizar como o conteúdo será guardado.

## Importar e exportar modelos do Web Clipper

Para importar um modelo:

1. Abra a extensão e clique no ícone de engrenagem das **[[Configurações]]**.
2. Aceda a qualquer modelo na lista.
3. Clique em **Importar** no canto superior direito ou arraste e largue o(s) seu(s) ficheiro(s) de modelo `.json` em qualquer lugar da área de modelos.

Para exportar um modelo, clique em **Exportar** no canto superior direito. Isto irá descarregar o ficheiro `.json` do modelo. Também pode copiar os dados do modelo para a área de transferência através do menu **Mais**.

## Definições do modelo

### Comportamento

Defina como o conteúdo do Web Clipper será adicionado ao Obsidian:

- **Criar uma nova nota**
- **Adicionar a uma nota existente**, no início ou no fim
- **Adicionar à nota diária**, no início ou no fim (requer que o plugin [[Notas diárias]] esteja ativo)

### Acionar automaticamente um modelo

Os acionadores de modelos permitem selecionar automaticamente um modelo com base no URL da página atual ou nos dados do [schema.org](https://schema.org/). Pode definir múltiplas regras para cada modelo, separadas por uma nova linha.

A primeira correspondência na sua lista de modelos determina qual o modelo usado. Pode arrastar os modelos para cima e para baixo nas definições do Web Clipper para alterar a ordem em que os modelos são correspondidos.

#### Correspondência simples de URL

A correspondência simples aciona um modelo se o URL da página atual *começar com* o padrão fornecido. Por exemplo:

- `https://obsidian.md` corresponderá a qualquer URL que comece com este texto.

#### Correspondência por expressão regular

Pode acionar modelos com base em padrões de URL mais complexos usando expressões regulares. Envolva o seu padrão regex em barras (`/`). Lembre-se de escapar os caracteres especiais nos padrões regex (como `.` e `/`) com uma barra invertida (`\`). Por exemplo:

- `/^https:\/\/www\.imdb\.com\/title\/tt\d+\/reference\/?$/` corresponderá a qualquer página de referência do IMDB.

#### Correspondência de Schema.org

Pode acionar modelos com base em dados do [schema.org](https://schema.org/) presentes na página. Use o prefixo `schema:` seguido da chave de schema que pretende corresponder. Pode opcionalmente especificar um valor esperado. Por exemplo:

- `schema:@Recipe` corresponderá a páginas onde o tipo de schema é "Recipe".
- `schema:@Recipe.name` corresponderá a páginas onde `@Recipe.name` está presente.
- `schema:@Recipe.name=Cookie` corresponderá a páginas onde `@Recipe.name` é "Cookie".

Os valores do Schema.org também podem ser usados para [[Variáveis#Schema.org variables|pré-preencher dados em modelos]].

### Contexto do Interpretador

Quando o [[Interpretar páginas web|Interpretador]] está ativado, pode usar [[Variáveis#Prompt variables|variáveis de prompt]] para extrair conteúdo de páginas com linguagem natural. Para cada modelo pode definir o [[Interpretar páginas web#Context|contexto]] a que o Interpretador tem acesso.
