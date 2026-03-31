---
permalink: plugins/note-composer
---
O Compositor de notas é um [[Plugins nativos|plugin nativo]] que lhe permite fundir duas notas ou extrair parte de uma nota para uma nova nota.

## Fundir notas

Fundir notas adiciona uma nota a outra e remove a primeira. O Compositor de notas atualiza todas as ligações para referenciar a nota fundida.

Quando seleciona a nota para fundir, pode escolher entre os seguintes métodos:

- `Enter`: Adiciona a nota de origem no _final_ da nota de destino.
- `Shift+Enter`: Adiciona a nota de origem no _início_ da nota de destino.
- `Ctrl+Enter` (ou `Cmd+Enter` no macOS): Cria uma nova nota com o conteúdo da nota de origem.

Para fundir a nota ativa com outra nota do seu cofre:

**Explorador de ficheiros**

1. No Explorador de ficheiros, clique com o botão direito na nota que pretende fundir.
2. Clique em **Fundir ficheiro inteiro com...**.
3. Selecione a nota com a qual pretende fundir.
4. Clique em **Fundir** para confirmar.

**Paleta de comandos**

1. Abra a [[Paleta de comandos]].
2. Selecione **Compositor de notas: Fundir ficheiro atual com outro ficheiro...**.
3. Selecione a nota com a qual pretende fundir.
4. Clique em **Fundir** para confirmar.

> [!tip] Dica
> Por predefinição, o Compositor de notas pede-lhe confirmação ao fundir notas. Se desativar a confirmação e fundir uma nota por engano, ainda pode recuperá-la com o plugin [[Recuperação de ficheiros]].

## Extrair nota

Quando seleciona a nota para a qual pretende extrair a seleção, pode escolher entre os seguintes métodos:

- `Enter`: Adiciona o texto selecionado no _final_ da nota de destino.
- `Shift+Enter`: Adiciona o texto selecionado no _início_ da nota de destino.
- `Ctrl+Enter` (ou `Cmd+Enter` no macOS): Cria uma nova nota com o texto selecionado.

Para extrair texto para uma nova nota:

**Editor**

1. Enquanto está na **Vista de edição**, selecione o texto que pretende extrair.
2. Clique com o botão direito no texto selecionado.
3. Clique em **Extrair seleção atual...**.
4. Selecione a nota para a qual pretende extrair.

**Paleta de comandos**

1. Enquanto está na **Vista de edição**, selecione o texto que pretende extrair.
2. Abra a [[Paleta de comandos]].
3. Selecione **Compositor de notas: Extrair seleção atual...**.
4. Selecione a nota para a qual pretende extrair.

> [!tip] Dica
> Por predefinição, o Compositor de notas substitui o texto extraído por uma ligação para a nota de destino. Nas definições, também pode alterar para [[Incorporar ficheiros|incorporar]] a nota de destino ou para não deixar nada.

## Ficheiro de modelo

Ao configurar um modelo, pode personalizar o conteúdo antes de o adicionar à nova nota. Para usar um modelo, introduza uma **Localização do ficheiro de modelo** nas definições do plugin.

O modelo pode conter as seguintes variáveis:

| Variável          | Descrição                                                                                                                                                        |
|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `{{content}}`     | O conteúdo a fundir, ou a seleção de texto extraída. Se não incluir esta variável, o Compositor de notas adiciona o conteúdo no final do modelo. |
| `{{fromTitle}}`   | Nome da nota de origem.                                                                                                                                          |
| `{{newTitle}}`    | Nome da nota de destino. Por exemplo, para adicionar o nome do ficheiro como cabeçalho no início do ficheiro.                                                    |
| `{{date:FORMAT}}` | Data de criação da nova nota. Por exemplo, `{{date:YYYY-MM-DD}}`.                                                                                                |
