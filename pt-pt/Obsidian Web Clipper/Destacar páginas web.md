---
permalink: web-clipper/highlight
---
O [[Introdução ao Obsidian Web Clipper|Web Clipper]] permite-lhe destacar texto em páginas web e selecionar os elementos que pretende guardar no Obsidian. Os seus destaques são guardados, pelo que os pode rever quando regressar a uma página.

Os destaques podem ser [[Capturar páginas web|capturados]] e guardados no Obsidian quando abre a extensão.

## Ativar o marcador

Pode ativar o marcador de várias formas, consoante o seu navegador:

- O ícone do marcador no painel da extensão.
- Atalhos de teclado, para ativar a extensão a partir do teclado.
- Menu de contexto, clicando com o botão direito na página web que está a visitar.

Assim que o marcador estiver ativo, pode selecionar texto, imagens e elementos que pretende destacar.

## Definições do marcador

Pode alterar o comportamento do marcador acedendo às definições do Web Clipper. Aqui também pode exportar os seus destaques para um ficheiro `.json`.

Existem três opções para os destaques serem inseridos na nota capturada através da [[Variáveis|variável]] `{{content}}`:

- **Destacar o conteúdo da página** — adiciona os destaques diretamente ao texto com a [[Obsidian Flavored Markdown|sintaxe]] `==destacar==`.
- **Substituir o conteúdo da página** — devolve uma lista de destaques, sem qualquer conteúdo da página.
- **Não fazer nada** — devolve o conteúdo original sem destaques.

Pode adicionar destaques diretamente ao seu modelo utilizando a variável `{{highlights}}`, por exemplo:

```
{{highlights|map: item => item.text|join:"\n\n"}}
```
