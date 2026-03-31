---
permalink: import/zettelkasten
---
Se tem usado o método Zettelkasten para nomear e ligar as suas notas, poderá ter de converter os links de `[[UID]]` para `[[UID My note title]]`.

Por exemplo, se tiver uma nota com o nome `202301011230 My note title` e ligar a ela a partir de outra nota usando apenas o UID, `[[202301011230]]`. Como o Obsidian usa o nome completo da nota para resolver os links internos, links como estes deixarão de funcionar.

Para atualizar todos os links `[[UID]]` no seu cofre para usar o nome completo da nota, use o [[Conversor de formato]].

1. Abra **[[Configurações]]**.
2. Em **Plugins nativos**, ative o **Conversor de formato** e feche a janela de Definições.
3. Na barra de ferramentas, no lado esquerdo da janela da aplicação, selecione **Abrir o conversor de formato** ![[lucide-binary.svg#icon]].
4. Ative **Corretor de links Zettelkasten**.
5. Selecione **Iniciar conversão**. Isto converterá todas as notas no seu cofre inteiro.

> [!tip] Embelezador de links Zettelkasten
> O [[Conversor de formato]] também pode embelezar os seus links removendo o UID do nome de exibição. Por exemplo, `[[UID]]` converte-se em `[[UID My note title|My note title]]`.
>
> Para embelezar os seus links Zettelkasten, ative o **Embelezador de links Zettelkasten** na janela do conversor de formato.

Também pode usar o [[Criador de nota única]] para criar notas Zettelkasten no Obsidian.
