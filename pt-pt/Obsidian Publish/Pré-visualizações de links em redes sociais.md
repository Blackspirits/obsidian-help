---
permalink: publish/social-share
---
Muitas redes sociais apresentam uma pré-visualização rica do seu site quando um utilizador partilha um link para o mesmo. Utilizando [[Propriedades]], pode personalizar a forma como as suas notas aparecem na pré-visualização.

> [!warning] Aviso
> As tags substituídas nesta secção são visíveis **apenas** por crawlers web. Os navegadores web normais recebem a página não modificada por razões de desempenho.

## Descrição

O Obsidian gera automaticamente uma descrição com base no conteúdo da nota, mas pode fornecer a sua própria usando `description`.

```yaml
---
description: Uma introdução ao nosso sistema solar.
---
```

> [!note] Meta tags
> `description` substitui a descrição gerada automaticamente em `<meta name="description" content="...">` e os equivalentes para `og:description` e `twitter:description`.

## Imagem

Pode utilizar uma imagem personalizada para a pré-visualização do link, adicionando `image` ou `cover` com um caminho para a imagem. A imagem deve ser carregada para o Publish.

O caminho pode ser um caminho absoluto a partir da raiz do seu cofre:

```yaml
---
cover: "Attachments/Cover image.png"
---
```


O caminho para a imagem é sensível a maiúsculas e minúsculas. No exemplo anterior, temos um caminho para uma imagem com o nome `Cover image.png`. O caminho seguinte não funcionará porque está a usar maiúsculas/minúsculas incorretas.

```yaml
---
cover: "Attachments/cover Image.png"
---
```


Em alternativa a um caminho absoluto no seu cofre, também pode utilizar um URL externo:

```yaml
---
image: "https://example.com/cover%20image.png"
---
```


`image` e `cover` são idênticos. Utilize apenas um deles.

> [!note] Meta tags
> `image` e `cover` substituem a imagem gerada automaticamente em `<meta property="og:image" content="...">`.
