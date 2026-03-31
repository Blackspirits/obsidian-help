---
permalink: publish/domains
mobile: true
description: "Pode configurar um domínio ou subdomínio personalizado para o seu site do Obsidian Publish."
---

Pode configurar um domínio ou subdomínio personalizado para o seu site do [[Introdução ao Obsidian Publish|Obsidian Publish]].

> [!warning] Aviso
> De momento, apenas suportamos a configuração de domínios personalizados através dos seguintes métodos:
>
> - [[#Configurar com CloudFlare]] usando o [modo Full](https://developers.cloudflare.com/ssl/origin-configuration/ssl-modes/full/).
> - [[#Configurar com um proxy]]
>
> Ainda não temos forma de providenciar um certificado SSL em seu nome.

## Configurar com CloudFlare

A forma mais fácil de configurar um domínio ou subdomínio personalizado é criar uma conta no [CloudFlare](https://cloudflare.com) e deixar o CloudFlare gerir o DNS do seu domínio.

Os passos seguintes usam o CloudFlare para configurar um domínio personalizado para o seu site do Obsidian Publish, seja usando um domínio raiz (`mysite.com`) ou um subdomínio (`notes.mysite.com`).

> [!important] Importante
> O CloudFlare é o **único fornecedor oficialmente suportado** para configurar domínios personalizados. Usar as instruções seguintes com outros fornecedores provavelmente não funcionará.

**CloudFlare:**

1. Abra o Cloudflare no domínio onde pretende alojar o seu site Publish, como `mysite.com`, mesmo que pretenda um subdomínio como `notes.mysite.com`.
2. Vá a **DNS** e clique em **Add Record**.
3. Selecione **CNAME**.
4. Em **name**, introduza o seu domínio ou subdomínio, por exemplo `notes.mysite.com`.
5. Em **target**, introduza `publish-main.obsidian.md`. Não inclua o seu sub-URL pessoal neste valor. O Obsidian Publish trata disso a partir da sua configuração.
6. Certifique-se de que o **proxy status** está ativado. Por predefinição, deve estar ativado.
7. Vá a **SSL/TLS** e defina o modo de encriptação SSL/TLS como "Full" para configurar o certificado SSL/TLS automaticamente.

> [!note] Nota
> Para redirecionar tanto `mysite.com` como `www.mysite.com` para o Obsidian Publish, precisa de criar uma [Page Rule](https://support.cloudflare.com/hc/en-us/articles/200172336-Creating-Page-Rules) com as seguintes definições:
>
> - URL match: `www.mysite.com/*`
> - Forward URL - 301 Permanent Redirect
> - Redirect URL: `https://mysite.com/$1`
>
> Depois de criar a page rule, crie um registo CNAME para `www.mysite.com` tal como fez para `mysite.com`.

**Obsidian:**

1. Abra o Obsidian no seu computador.
2. Na [[Faixa de opções]] à esquerda, clique em **Publish changes** ![[lucide-send.svg#icon]].
3. Em **Publish changes**, selecione **Change site options** ![[lucide-cog.svg#icon]].
4. Junto a **Custom domain**, selecione **Configure**.
5. Em **Custom URL**, introduza o URL do seu domínio ou subdomínio. Certifique-se de não colocar `www.` na caixa de URL personalizado.

> [!note] Nota
> Se a configuração do seu domínio personalizado resultar num ciclo de redirecionamento, é provável que o modo de encriptação no CloudFlare esteja definido como "Flexible" em vez de "Full".

## Configurar com um proxy

Também pode configurar SSL/TLS para o seu domínio personalizado usando o seu próprio servidor web.

Se já aloja um website no seu domínio ou subdomínio, pode também usar esta opção e configurar o seu website para carregar o seu site do Obsidian Publish num caminho de URL específico, em vez de alojar o site completo.

Redirecione por proxy todos os pedidos nesse caminho de URL para `https://publish.obsidian.md/serve?url=mysite.com/my-notes/...` e configure as opções do site no Obsidian para o mesmo caminho de URL, definindo **Custom URL** como `mysite.com/my-notes`.

Também pode configurar o Obsidian Publish como um sub-URL de um site que possui. Por exemplo, `https://mysite.com/my-notes/`. Para conseguir isto, deve alojar o seu próprio servidor e redirecionar por proxy todos os pedidos para o nosso servidor em `https://publish.obsidian.md/`.

Os exemplos de configuração de proxy a seguir não são exaustivos, mas fornecem métodos comuns para esta implementação.

### NGINX

Na sua configuração NGINX, adicione o seguinte:

```nginx
location /my-notes {
  proxy_pass https://publish.obsidian.md/serve?url=mysite.com/my-notes/;
  proxy_ssl_server_name on;
  proxy_set_header Host publish.obsidian.md;
}
```


Alguns utilizadores reportaram que pode ser necessário adicionar `$request_uri` ao proxy pass:

```nginx
location /my-notes {
  proxy_pass https://publish.obsidian.md/serve?url=mysite.com/my-notes$request_uri;
  proxy_ssl_server_name on;
  proxy_set_header Host publish.obsidian.md;
}
```

### Apache

Em `.htaccess`, adicione o seguinte:

```htaccess
RewriteEngine  on
RewriteRule    "^my-notes/(.*)$"  "https://publish.obsidian.md/serve?url=mysite.com/my-notes/$1"  [L,P]
```

> [!note] Nota
> O `mod_rewrite` deve estar ativado, e poderá também precisar de configurar o [SSLProxyEngine](https://stackoverflow.com/questions/40938148/reverse-proxy-for-external-url-apache)

### Netlify

Em `netlify.toml`, [configure os redirecionamentos](https://docs.netlify.com/routing/redirects/#syntax-for-the-netlify-configuration-file):

```plain
[[redirects]]
  from = "https://mysite.com/my-notes/*"
  to = "https://publish.obsidian.md/serve?url=mysite.com/my-notes/:splat"
  status = 200
  force = true
```

### Vercel

Em `vercel.json`, [configure as reescritas](https://vercel.com/docs/configuration#project/rewrites):

```json
{
  ...

  "rewrites": [
    {
      "source": "/my-notes/",
      "destination": "https://publish.obsidian.md/serve?url=mysite.com/my-notes"
    },
    {
      "source": "/my-notes/:path*",
      "destination": "https://publish.obsidian.md/serve?url=mysite.com/my-notes/:path*"
    }
  ]
}
```

### Caddy

```plain
mysite.com {
  encode zstd gzip
  handle /my-notes* {
    reverse_proxy https://publish.obsidian.md {
      header_up Host {upstream_hostport}
    }
    rewrite * /serve?url=mysite.com{path}
  }
}
```

### Traefik

Este excerto de configuração mínima redireciona `mysite.com` para o Obsidian Publish.
Consulte a [documentação do Traefik](https://doc.traefik.io/traefik/routing/overview/)
para um exemplo completo.

```yaml
http:
  routers:
    mysite:
      rule: Host(`mysite.com`)
      service: obsidian-publish
      middlewares:
        - "publish-headers"
  services:
    obsidian-publish:
      loadBalancer:
        servers:
          - url: https://publish.obsidian.md
  middlewares:
    publish-headers:
      headers:
        customRequestHeaders:
          Host: "publish.obsidian.md"
          x-obsidian-custom-domain: "mysite.com"
```

### Cabeçalhos HTTP X suportados

Se o seu serviço de proxy não permitir caminhos de consulta, pode usar `https://publish.obsidian.md/` com um cabeçalho personalizado `x-obsidian-custom-domain` definido como o URL do seu site `mysite.com/my-subpath`.

## Redirecionar o site antigo para o domínio personalizado

Se pretende redirecionar os seus visitantes do antigo site `publish.obsidian.md` para o seu novo domínio personalizado, ative a opção **Redirect to your custom domain** ao configurar o seu domínio personalizado.

## Resolução de problemas

Após configurar o seu domínio personalizado, se visitou o seu site através do link anterior `https://publish.obsidian.md/slug`, poderá ter de limpar a cache do browser para que determinados elementos (como fontes, grafos ou acesso por palavra-passe) funcionem corretamente. Isto deve-se às restrições de segurança entre domínios impostas pelos browsers modernos. A boa notícia é que os leitores do seu site nunca deverão ter este problema se permitir apenas que os visitantes usem o seu domínio personalizado.
