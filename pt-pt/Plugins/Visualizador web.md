---
permalink: plugins/web-viewer
---
O Visualizador web é um [[Plugins nativos|plugin nativo]] que lhe permite abrir ligações externas dentro do Obsidian no computador. Isto permite-lhe ler o conteúdo das ligações sem sair da aplicação e facilita a realização de várias tarefas em projetos de pesquisa na web.

As ligações externas abrem como um [[Separadores|separador]] que pode reorganizar, dividir e abrir numa [[Janelas destacáveis|janela destacável]]. Qualquer cartão de página web incorporado em ficheiros [[canvas]] pode ser aberto como separador do Visualizador web.

O Visualizador web não é um substituto para o seu navegador principal. O Visualizador web fornece uma forma rápida de aceder a páginas web para pesquisa dentro do Obsidian. No entanto, não oferece a funcionalidade completa, os controlos de segurança ou a extensibilidade de um navegador dedicado.

## Vista de leitor

Clique no ícone dos óculos para ver uma versão em texto simples da página web. Esta funcionalidade funciona através da limpeza do conteúdo usando a biblioteca Readability da Mozilla, desenvolvida para o Firefox.

## Guardar no cofre

Clique no ícone de mais ações para guardar uma página web no seu cofre. Pode personalizar a localização de guardação da página indo a **[[Configurações]]** → **Visualizador web**.

## Bloqueio de anúncios

O Visualizador web bloqueia anúncios por predefinição. Pode personalizar as regras de bloqueio de anúncios adicionando listas como o [Easylist](https://easylist.to/).

## Segurança

Se usar plugins de terceiros no Obsidian, recomendamos usar o seu navegador principal para tarefas sensíveis e sites protegidos por palavra-passe em vez do Visualizador web.

O Visualizador web baseia-se na mesma funcionalidade [Chromium](https://developer.chrome.com/docs/apps/reference/webviewTag) que permite incorporar páginas web no [[Canvas]]. O Visualizador web foi [auditado de forma independente](https://obsidian.md/blog/cure53-second-client-audit/) para verificar que foi implementado de forma segura.

Os plugins do Obsidian [[Segurança de plugins#Plugin capabilities|não estão em ambiente isolado]] e têm controlo profundo sobre a aplicação. Este design permite uma funcionalidade poderosa, mas também implica compromissos de segurança. Enquanto o Obsidian está em execução, plugins de terceiros têm acesso total aos cookies no Visualizador web.
