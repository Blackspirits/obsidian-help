---
permalink: publish/permalinks
---
Pode renomear o URL das suas notas usando _permalinks_.

Por exemplo, pode transformar isto:

```
https://publish.obsidian.md/username/Company/About+us
```

Nisto:

```
https://publish.obsidian.md/username/about
```

Para criar um permalink para uma nota, adicione a propriedade `permalink` às suas [[Propriedades]].

```yaml
---
permalink: about
---
```

Se alguém visitar uma nota usando o URL original, será automaticamente redirecionado para o permalink.

## Redirecionar notas antigas

Renomear e remover notas é uma parte natural da manutenção de um cofre em constante evolução. Embora o Obsidian atualize automaticamente os links quando move uma nota dentro do seu cofre local, outros websites podem ainda ter links para as suas notas antigas no seu site do [[Introdução ao Obsidian Publish|Obsidian Publish]] publicado. Pode redirecionar os leitores de uma nota para outra.

Imagine que pretende mover uma nota de uma pasta para outra:

- **Guides**
  - ~~Making friends.md~~ (removido)
- **Tutorials**
  - *How to make friends.md* (adicionado)

Depois de mover a nota, o Obsidian atualiza automaticamente todos os links dentro do cofre. No entanto, se publicar a alteração no seu site Publish, quaisquer links para `/Guides/Making+friends` resultarão num erro 404.

Para redirecionar os leitores de `/Guides/Making+friends` para `/Tutorials/How+to+make+friends`, precisa de adicionar um [[Apelidos|apelido]] em `How to make friends.md`, a nota para a qual pretende redirecionar.

```md
---
alias: Guides/Making friends
---

# How to make friends
```

> [!important] Importante
> Certifique-se de que inclui o caminho completo para a nota antiga no apelido. Embora usar apenas o nome da nota como apelido funcione no seu cofre local, o Publish precisa do caminho completo para a nota para conseguir redirecionar para ela.

Pode redirecionar múltiplas notas adicionando um apelido para cada uma.

```md
---
aliases:
  - Guides/Making friends
  - Developing friendships
---

# How to make friends
```
