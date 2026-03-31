---
permalink: import/apple-journal
---
O Obsidian permite-lhe migrar facilmente as suas entradas do Apple Journal utilizando o [[Importador|plugin Importer]].
Isto irá converter os seus diários em ficheiros Markdown duradouros, que pode utilizar com o Obsidian e muitas outras aplicações.

## Exportar os seus dados do Apple Journal

### No iPhone
Siga as instruções para [Imprimir e exportar entradas no Journal no iPhone](https://support.apple.com/guide/iphone/print-and-export-entries-iph4cad323fe/ios#iph1edf66806):

1. Abra a aplicação Journal no seu iPhone.
2. Escolha um diário ou toque em Todas as Entradas.
3. Toque no botão Mais no topo do ecrã.
4. Toque em Exportar e, em seguida, escolha Exportar.
5. Escolha uma localização e toque no botão Selecionado.

### No Mac (Tahoe)
Siga as instruções para [Imprimir e exportar entradas no Journal no Mac](https://support.apple.com/guide/journal/print-and-export-entries-dev883fc2329/mac#devc24a8f09a):

1. Abra a aplicação Journal no seu Mac.
2. Vá a Ficheiro > Exportar e, em seguida, escolha Exportar.

## Importar dados do Apple Journal para o Obsidian

Precisará do plugin oficial do Obsidian [[Importador]], que pode [instalar aqui](obsidian://show-plugin?id=obsidian-importer).

1. Abra as **[[Configurações]]**.
2. Vá a **Plugins da comunidade** e [instale o Importer](obsidian://show-plugin?id=obsidian-importer).
3. Ative o plugin Importer.
4. Abra o plugin **Importer** utilizando a paleta de comandos ou o ícone da faixa de opções.
5. Em **Formato de ficheiro**, escolha **Apple Journal (HTML Export)**.
6. Em **Ficheiros a importar**, selecione a pasta com os dados exportados, normalmente _AppleJournalEntries_, ou ficheiros individuais de _Entries_.
7. Reveja e edite as restantes opções de importação.
8. Selecione Importar e aguarde até que a importação esteja concluída.
9. Concluído!


## Conteúdo suportado

O plugin pode importar metadados do Journal como frontmatter, tais como _state-of-mind_, _contacts_, _location_ e _workout-route_.

> [!note] Nota
> O plugin não importa recursos. Anexos como fotografias, vídeos e gravações de áudio são ignorados.
