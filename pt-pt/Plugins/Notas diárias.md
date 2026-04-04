---
permalink: plugins/daily-notes
---

As Notas diárias são um [[Plugins nativos|plugin nativo]] que abre uma nota baseada na data de hoje, ou cria-a se não existir. Use as notas diárias para criar diários, listas de tarefas ou registos diários das coisas que descobriu durante o dia.

Para abrir a nota diária de hoje, pode:

- Clicar em **Abrir a nota diária de hoje** ![[lucide-calendar.svg#icon]] na [[Faixa de opções|faixa de opções]].
- Executar **Abrir a nota diária de hoje** a partir da [[Paleta de comandos]].
- [[Teclas de atalho#Set a hotkey|Usar um atalho de teclado]] para o comando **Abrir a nota diária de hoje**.

Por predefinição, o Obsidian cria uma nova nota vazia com o nome da data de hoje no formato YYYY-MM-DD.

> [!tip] Se preferir ter as suas notas diárias numa pasta separada, pode definir a <u>Localização do novo ficheiro</u> nas opções do plugin para alterar o local onde o Obsidian cria novas notas diárias.

> [!example]- Subpastas automáticas
> Pode organizar automaticamente as suas notas diárias em pastas usando a funcionalidade **Formato de data**.
> 
> Por exemplo, se definir o formato de data como `YYYY/MMMM/YYYY-MMM-DD`, as suas notas serão criadas como `2023/January/2023-Jan-01`. 
> 
> Pode explorar mais opções de formatação no site de documentação do [momentJS](https://momentjs.com/docs/#/displaying/format/).

## Criar uma nota diária a partir de um modelo

Se as suas notas diárias tiverem a mesma estrutura, pode usar um [[Plugins/Modelos|modelo]] para adicionar conteúdo predefinido às suas notas diárias quando as cria.

1. Crie uma nova nota com o nome "Modelo diário" com o seguinte texto (ou o que fizer sentido para si!):

   ```md
   # {{date:YYYY-MM-DD}}

   ## Tarefas

   - [ ]
   ```

2. Abra as **[[Configurações]]**.
3. Na barra lateral, clique em **Notas diárias** em **Opções do plugin**.
4. Na caixa de texto junto a **Localização do ficheiro de modelo**, selecione a nota "Modelo diário".

O Obsidian usa o modelo da próxima vez que criar uma nova nota diária.

## Notas diárias e propriedades

Quando o plugin Notas diárias está ativado e uma propriedade de data está presente em qualquer nota, o Obsidian tentará automaticamente gerar uma ligação para a nota diária desse dia específico. Por exemplo, se uma nota com o nome `exemplo.md` incluir uma propriedade de data como `2023-01-01`, esta data transformar-se-á numa ligação clicável na secção de [[Vistas e modo de edição#Live Preview|pré-visualização em direto]].

![[daily-notes-and-date-properties.png#interface|300]]
^daily-notes-date
