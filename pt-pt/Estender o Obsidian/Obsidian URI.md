---
aliases:
  - Using Obsidian URI
  - Advanced topics/Using obsidian URI
  - Concepts/Obsidian URI
  - Extending Obsidian/Obsidian URI
permalink: uri
---
O Obsidian URI é um protocolo URI personalizado suportado pelo Obsidian que permite desencadear várias ações, como abrir uma nota ou criar uma nota. O Obsidian URI permite a automatização e fluxos de trabalho entre aplicações.

## Formato URI

Os URIs do Obsidian utilizam o seguinte formato:

```
obsidian://action?param1=value&param2=value
```

O parâmetro `action` é a ação que pretende executar. As ações disponíveis incluem:

- `open` para abrir uma nota.
- `new` para criar ou adicionar conteúdo a uma nota existente.
- `daily` para criar ou abrir a sua nota diária.
- `unique` para criar uma nova nota única.
- `search` para abrir uma pesquisa.
- `choose-vault` para abrir o gestor de cofres.

> [!warning] Codificação
> Certifique-se de que os seus valores estão corretamente codificados em URI. Por exemplo, os caracteres de barra `/` devem ser codificados como `%2F` e os espaços devem ser codificados como `%20`.
> 
 Isto é especialmente importante porque um carácter "reservado" incorretamente codificado pode quebrar a interpretação do URI. [Veja aqui para mais detalhes](https://en.wikipedia.org/wiki/Percent-encoding).

## Abrir nota

A ação `open` abre um cofre do Obsidian, ou abre um ficheiro dentro desse cofre.

### Exemplos

- `obsidian://open?vault=my%20vault`
  Abre o cofre `my vault`. Se o cofre já estiver aberto, foca a janela.
- `obsidian://open?vault=ef6ca3e3b524d22f`
  Abre o cofre identificado pelo ID `ef6ca3e3b524d22f`.
- `obsidian://open?vault=my%20vault&file=my%20note`
  Abre a nota `my note.md` no cofre `my vault`, assumindo que o ficheiro existe.
- `obsidian://open?path=%2Fhome%2Fuser%2Fmy%20vault%2Fpath%2Fto%2Fmy%20note`
  Procurará qualquer cofre que contenha o caminho `/home/user/my vault/path/to/my note`. De seguida, o restante do caminho é passado ao parâmetro `file`. Por exemplo, se existir um cofre em `/home/user/my vault`, isto seria equivalente ao parâmetro `file` definido como `path/to/my note`.


> [!tip] Abrir um cabeçalho ou bloco
> Com a codificação URI adequada, pode navegar para um cabeçalho ou bloco dentro de uma nota. `Note%23Heading` navegaria para o cabeçalho chamado "Heading", enquanto `Note%23%5EBlock` navegaria para o bloco chamado "Block".

### Parâmetros

- `vault` pode ser o nome do cofre ou o ID do cofre[^1].
- `file` pode ser o nome de um ficheiro ou um caminho desde a raiz do cofre até ao ficheiro especificado. Se a extensão do ficheiro for `md`, a extensão pode ser omitida.
- `path` um caminho absoluto do sistema de ficheiros para um ficheiro.
  - A utilização deste parâmetro substitui tanto `vault` como `file`.
  - Isto fará com que a aplicação procure o cofre mais específico que contenha o caminho de ficheiro especificado.
  - De seguida, o restante do caminho substitui o parâmetro `file`.
- `prepend` adicionará ao topo do ficheiro e tentará fundir as propriedades.
- `append` adicionará ao fim do ficheiro e também tentará fundir as propriedades.
- `paneType` (opcional) determina onde a nota será aberta na interface.
  - se não estiver presente, o último separador ativo é substituído.
  - `paneType=tab` abre num novo separador.
  - `paneType=split` abre num novo grupo de separadores.
  - `paneType=window` abre numa janela flutuante (apenas no computador).

## Criar nota

A ação `new` cria uma nova nota no cofre, opcionalmente com algum conteúdo.

### Exemplos

- `obsidian://new?vault=my%20vault&name=my%20note`
  Abre o cofre `my vault` e cria uma nova nota chamada `my note`.
- `obsidian://new?vault=my%20vault&file=path%2Fto%2Fmy%20note`
  Abre o cofre `my vault` e cria uma nova nota em `path/to/my note`.

### Parâmetros

- `vault` pode ser o nome do cofre ou o ID do cofre[^1]. Igual à ação `open`.
- `name` o nome do ficheiro a criar. Se especificado, a localização do ficheiro será escolhida com base nas suas preferências de "Localização predefinida para novas notas".
- `file` um caminho absoluto no cofre, incluindo o nome. Substituirá `name` se especificado.
- `path` um caminho absolutamente global. Funciona de forma semelhante à opção `path` na ação `open`, substituindo tanto `vault` como `file`.
- `paneType` (opcional) determina onde a nota será aberta na interface. Igual à ação `open`.
- `content` (opcional) o conteúdo da nota.
- `clipboard` (opcional) utiliza o conteúdo da área de transferência em vez de especificar `content`.
- `silent` (opcional) inclua este parâmetro se não quiser abrir a nova nota.
- `append` (opcional) inclua este parâmetro para acrescentar a um ficheiro existente, caso exista.
- `overwrite` (opcional) sobrescreve um ficheiro existente, caso exista, mas apenas se `append` não estiver definido.
- `x-success` (opcional) veja [[#Utilizar os parâmetros x-callback-url]].

## Criar ou abrir nota diária

A ação `daily` cria ou abre a sua nota diária. O plugin [[Notas diárias]] deve estar ativado.

### Exemplos

- `obsidian://daily?vault=my%20vault`
  Abre o cofre `my vault` e cria ou abre a nota diária.

### Parâmetros

A ação `daily` aceita os mesmos parâmetros que a ação `new`.

## Nota única

A ação `unique` cria uma nova nota única no cofre. O plugin [[Plugins/Criador de nota única|Unique note creator]] deve estar ativado.

### Exemplos

- `obsidian://unique?vault=my%20vault`
  Abre o cofre `my vault` e cria uma nova nota única.
- - `obsidian://unique?vault=my%20vault&content=Hello%20World`
  Abre o cofre `my vault` e cria uma nova nota única com o conteúdo `Hello World`.

### Parâmetros

- `vault` pode ser o nome do cofre ou o ID do cofre[^1]. Igual à ação `open`.
- `paneType` (opcional) determina onde a nota será aberta na interface. Igual à ação `open`.
- `content` (opcional) o conteúdo da nota.
- `clipboard` (opcional) utiliza o conteúdo da área de transferência em vez de especificar `content`.
- `x-success` (opcional) veja [[#Utilizar os parâmetros x-callback-url]].

## Abrir pesquisa

A ação `search` abre a [[Pesquisa]] no cofre especificado e, opcionalmente, executa um termo de pesquisa.

### Exemplos

- `obsidian://search?vault=my%20vault`
  Abre o cofre `my vault` e abre a [[Pesquisa]].
- `obsidian://search?vault=my%20vault&query=Obsidian`
  Abre o cofre `my vault`, abre a [[Pesquisa]] e executa uma pesquisa por `Obsidian`.

### Parâmetros

- `vault` pode ser o nome do cofre ou o ID do cofre[^1]. Igual à ação `open`.
- `query` (opcional) O termo de pesquisa a executar.

## Abrir o Gestor de Cofres

A ação `choose-vault` abre o [[Gerir cofres|gestor de cofres]].

### Exemplos

- `obsidian://choose-vault`

## Integrar com o Hook

Esta ação do Obsidian URI destina-se a ser utilizada com o [Hook](https://hookproductivity.com/). 

### Exemplo

`obsidian://hook-get-address`

### Parâmetros

- `vault` (opcional) pode ser o nome do cofre ou o ID do cofre[^1]. Se não fornecido, será utilizado o cofre atual ou o último cofre em foco.
- `x-success` (opcional) veja [[#Utilizar os parâmetros x-callback-url]].
- `x-error` (opcional) veja [[#Utilizar os parâmetros x-callback-url]].

Se `x-success` estiver definido, esta API utilizá-lo-á como x-callback-url. Caso contrário, copiará um link Markdown da nota atualmente em foco para a área de transferência, como um URL `obsidian://open`.

## Utilizar os parâmetros x-callback-url

Alguns endpoints aceitarão os parâmetros x-callback-url `x-success` e `x-error`. Quando fornecido, o Obsidian disponibilizará o seguinte ao callback `x-success`:

- `name` o nome do ficheiro, sem a extensão.
- `url` o URI `obsidian://` para este ficheiro.
- `file` (apenas no computador) o URL `file://` para este ficheiro.

Por exemplo, se o Obsidian receber
`obsidian://.....x-success=myapp://x-callback-url`, a resposta seria `myapp://x-callback-url?name=...&url=obsidian%3A%2F%2Fopen...&file=file%3A%2F%2F...`

## Formatos abreviados

Para além dos formatos acima, existem mais dois formatos "abreviados" disponíveis para abrir cofres e ficheiros:

1. `obsidian://vault/my vault/my note` é equivalente a `obsidian://open?vault=my%20vault&file=my%20note`.
2. `obsidian:///absolute/path/to/my note` é equivalente a `obsidian://open?path=%2Fabsolute%2Fpath%2Fto%2Fmy%20note`.

## Resolução de problemas

### Registar o Obsidian URI

No Windows e no macOS, executar a aplicação uma vez deverá ser suficiente para registar o protocolo Obsidian URI no seu computador.

No Linux, é um processo muito mais complexo:

1. Certifique-se de que cria um ficheiro `obsidian.desktop`. [Veja aqui para mais detalhes](https://developer.gnome.org/documentation/guidelines/maintainer/integrating.html#desktop-files).
2. Certifique-se de que o seu ficheiro desktop especifica o campo `Exec` como `Exec=executable %u`. O `%u` é utilizado para passar os URIs `obsidian://` à aplicação.
3. Se estiver a utilizar o instalador AppImage, poderá ter de o descompactar usando `Obsidian-x.y.z.AppImage --appimage-extract`. Em seguida, certifique-se de que a diretiva `Exec` aponta para o executável descompactado.


[^1]: O ID do cofre é o código aleatório de 16 caracteres atribuído ao cofre, por exemplo `ef6ca3e3b524d22f`. Este ID é único por pasta no seu computador. O ID pode ser encontrado abrindo o seletor de cofres e clicando em "Copiar ID do cofre" no menu de contexto do cofre pretendido.
