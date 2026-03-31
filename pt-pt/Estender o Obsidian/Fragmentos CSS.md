---
permalink: snippets
publish: true
mobile: true
description: Learn how to change parts of the Obsidian app's appearance without creating a full theme.
---
Saiba como modificar aspetos da aparência da aplicação Obsidian sem necessitar de [criar um tema](https://docs.obsidian.md/Themes/App+themes/Build+a+theme).

> [!tip] Se estiver à procura de orientação sobre CSS para o [[Introdução ao Obsidian Publish|Obsidian Publish]], consulte [[Personalizar o seu site]].

CSS é uma linguagem que controla a aparência do HTML. Ao adicionar fragmentos CSS, pode alterar partes da interface do utilizador do Obsidian, como o tamanho e a cor dos cabeçalhos. O Obsidian dispõe de [variáveis CSS](https://docs.obsidian.md/Reference/CSS+variables/CSS+variables) que facilitam a personalização da interface.

O Obsidian procura fragmentos CSS dentro da [[Pasta de configuração|pasta de configuração]] do cofre.

## Adicionar um fragmento

Para adicionar um fragmento CSS no **Computador** ![[lucide-monitor-check.svg#icon]], siga estes passos:

1. Abra as **[[Configurações]]** ![[lucide-settings.svg#icon]].
2. Em **Aparência → Fragmentos CSS**, selecione **Abrir pasta de fragmentos** ![[lucide-folder-open.svg#icon]].
3. Na pasta de fragmentos, crie um ficheiro CSS com o seu fragmento.
4. No Obsidian, em **Aparência → Fragmentos CSS**, selecione **Recarregar fragmentos** ![[lucide-refresh-cw.svg#icon]] para ver o fragmento na lista.
5. Ative o fragmento clicando no botão de alternância.

Para adicionar um fragmento CSS no **Telemóvel/Tablet** ![[obsidian-icon-smartphone.svg#icon]], pode seguir estes passos:

1. Abra um gestor de ficheiros e localize o seu cofre. Pode verificar a localização do cofre em _Gerir cofres…_ tocando no seu cofre e consultando o caminho.
2. Abra a [[Pasta de configuração]] e crie uma pasta chamada `snippets` caso não exista.
3. Adicione o seu fragmento CSS a esta pasta.
4. Abra as **[[Configurações]]** do Obsidian ![[lucide-settings.svg#icon]].
5. Selecione **Aparência** no menu lateral.
6. Desloque-se para baixo até à secção **Fragmentos CSS**.
7. Toque em **Recarregar fragmentos** ![[lucide-refresh-cw.svg#icon]] para atualizar a lista.
8. Toque no botão de alternância para ativar o fragmento.

Em alternativa, pode:
- [[Sincronizar as suas notas entre dispositivos|Sincronizar]] quaisquer alterações com o seu serviço de sincronização.
- Utilizar um plugin da comunidade para criar um fragmento dentro do Obsidian.

Após a ativação, o Obsidian detetará automaticamente alterações nos fragmentos CSS e aplicá-las-á quando guardar o ficheiro.

> [!tip] Não é necessário reiniciar o Obsidian para que as alterações entrem em vigor. No entanto, poderá precisar de usar o comando [[Paleta de comandos]] para Recarregar o Obsidian sem guardar para ver as alterações no tema ou nota atual.

## Escrever CSS para o Obsidian

O Obsidian oferece vários métodos que tornam a escrita de CSS mais fácil e poderosa.

Dispõe de um conjunto de [variáveis CSS](https://docs.obsidian.md/Reference/CSS+variables/CSS+variables) para modificar facilmente partes do Obsidian e um [[Propriedades#Property types|tipo de propriedade]] integrado para alterar a aparência de uma ou várias notas.

> [!example] Variáveis
> Crie um ficheiro chamado `headers.css` com o seguinte conteúdo para alterar as cores dos seis [[Sintaxe de formatação básica#Headings|níveis de cabeçalho]] para um arco-íris:
>
> ```css
> body {
>   --h1-color: red;
>   --h2-color: orange;
>   --h3-color: yellow;
>   --h4-color: green;
>   --h5-color: blue;
>   --h6-color: pink;
> }
> ```

> [!example] Classes CSS
> Atribua o nome de uma classe CSS personalizada (ou uma lista de classes CSS) à [[Propriedades|propriedade]] predefinida `cssclasses` para fazer com que uma ou mais notas tenham uma aparência diferente das restantes.
>
> **CSS**:
> ```css
> .red-border img {
>    border-color: #ff0000;
>    border-style: solid;
> }
> ```
>
> **YAML/Propriedades**:
> ```yaml
> cssclasses:
>  - red-border
> ```
>
> Em cada nota que contenha o valor `red-border` na propriedade `cssclasses`, as imagens são apresentadas com uma borda vermelha.

Para garantir que o ficheiro CSS é válido e formatado corretamente, aconselhamos a sua validação com uma ferramenta como o [CSS Validation Service](https://jigsaw.w3.org/css-validator/), pois CSS inválido não funcionará.

## Saber mais

- Se for novo em CSS, consulte [Aprender a estilizar HTML com CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS) da Mozilla.
- Para mais informações sobre estilização do Obsidian, consulte:
  - [Sobre estilização](https://docs.obsidian.md/Reference/CSS+variables/About+styling)
  - [Criar um tema](https://docs.obsidian.md/Themes/App+themes/Build+a+theme)
  - [Criar um tema Publish](https://docs.obsidian.md/Themes/Obsidian+Publish+themes/Build+a+Publish+theme)
  - [Fluxo de trabalho do Inspetor CSS do Obsidian](https://forum.obsidian.md/t/obsidian-css-inspector-workflow/58178)
