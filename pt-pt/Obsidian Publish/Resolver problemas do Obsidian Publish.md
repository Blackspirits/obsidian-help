---
permalink: publish/troubleshoot
publish: true
mobile: true
description: Esta página detalha alguns problemas comuns que pode encontrar ao utilizar o Obsidian Publish
---
Esta página lista problemas comuns que pode encontrar com o [[Introdução ao Obsidian Publish|Obsidian Publish]] e como resolvê-los.

Certifique-se de que consulta primeiro [[Ficheiros multimédia]] e [[Limitações do Publish|limitações do Publish]].

## Geral

### Publicar notas

**Estou a receber um erro de hash ao tentar publicar uma nota.**

Está a utilizar um [[Plugins da comunidade|plugin da comunidade]] que edita o tempo de modificação do ficheiro aquando da atualização? Se for o caso, este plugin pode estar em conflito com o Publish. Submeta um relatório de erro ao programador do plugin para resolver o problema.

**Estou a receber um erro de rede estranho e tenho um site Publish muito grande.**

É provável que seja necessário examinar a sua base de dados. [[Ajuda e suporte#Contact Obsidian support|Contacte o suporte do Obsidian]] para obter assistência.

## CSS e temas

**O meu CSS na minha [[Pasta de configuração]] não funciona no Publish. Porquê?**

O Publish não lê a partir da pasta de configuração. Em vez disso, terá de criar um ficheiro `publish.css` no diretório de nível superior do seu cofre de publicação. Pode saber mais sobre isto em [[Personalizar o seu site]].

**O meu CSS não tem o mesmo aspeto no Publish que na aplicação. Porquê?**

O CSS do Obsidian Publish não é exatamente igual ao da aplicação. Recomendamos [desenvolver qualquer CSS e temas](https://docs.obsidian.md/Themes/Obsidian+Publish+themes/About+Obsidian+Publish+themes) especificamente para o Publish de raiz.

Em _geral_, o que funciona para a [[Vistas e modo de edição#Reading view|Vista de leitura]] tem uma forte probabilidade de funcionar no Publish.
