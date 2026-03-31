---
permalink: publish/limitations
---

> [!tip] Membros da nossa fantástica comunidade desenvolveram soluções alternativas para algumas destas limitações. Para mais informações, visite o nosso tópico [Publish Resources](https://forum.obsidian.md/t/obsidian-publish-resources/74582) nos fóruns do Obsidian.

## Plugins da comunidade

O Obsidian Publish tem suporte mínimo para [[Plugins da comunidade]].

Os plugins que produzem conteúdo em markdown simples, como o plugin Waypoint, são compatíveis com o Publish porque não requerem a aplicação para renderizar os seus dados.

Por outro lado, um plugin que requeira um bloco de código de plugin para renderizar, como o Dataview ou Fantasy Statblocks, não funcionará por predefinição no Publish.

## Grafo

O Publish oferece personalização básica de cores para a sua vista de grafo através de CSS. Pode modificar as cores dos nós no seu ficheiro `publish.css` utilizando as [variáveis CSS da Vista de Grafo](https://docs.obsidian.md/Reference/CSS+variables/Plugins/Graph).

Note que o grafo publicado não suporta as opções abrangentes de ordenação e visualização disponíveis na [[Vista de grafo]] da aplicação.

## Ficheiros multimédia

O Obsidian Publish não está otimizado para transmissão de vídeo ou ficheiros de áudio de grande dimensão. Incluímos algumas boas práticas para gerir os seus [[Ficheiros multimédia|ficheiros multimédia]] nestes documentos.

Para melhorar a experiência dos seus visitantes, recomendamos que use um serviço de alojamento de vídeo, como o YouTube ou o Vimeo.

Pode carregar ficheiros com **até 50 MB** de tamanho para o seu site Publish. ^publish-media-limit

## PDFs

Em dispositivos móveis, tablets e computadores com ecrãs pequenos, pode encontrar problemas em que um PDF incorporado não carrega ou apenas a primeira página é apresentada. Isto deve-se a limitações do renderizador de PDF em dispositivos móveis.

Para conteúdo destinado a utilizadores móveis, sugerimos fornecer links para PDFs alojados externamente ou incluir links internos que permitam aos utilizadores descarregar o PDF diretamente para o seu dispositivo.

## Pesquisa

O Publish tem suporte básico para pesquisa de texto simples no conteúdo publicado. A prioridade nos resultados de pesquisa é dada a:

- Nomes de ficheiros
- Apelidos
- Nomes de cabeçalhos

Após pesquisar os itens acima para correspondências, a pesquisa incluirá o texto simples das notas publicadas.

Para melhorar a capacidade de pesquisa do seu site publicado, recomenda-se o uso de nomes de ficheiros descritivos, a incorporação de múltiplos apelidos e a escolha de nomes de cabeçalhos que reflitam com precisão o conteúdo.

Adicionalmente, o Publish não suporta atualmente a funcionalidade de [[Pesquisa#Embed search results in a note|resultados de pesquisa incorporados]] da aplicação.
