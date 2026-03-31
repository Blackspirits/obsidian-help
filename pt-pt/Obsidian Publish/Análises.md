---
permalink: publish/analytics
---
## Pré-requisitos

Para utilizar análises no seu site [[Introdução ao Obsidian Publish|Obsidian Publish]], precisa de um [[Domínios personalizados|domínio personalizado]].

> [!important] Importante
> Antes de ativar as análises, certifique-se de que as leis e regulamentos locais permitem o rastreio dos seus visitantes. Dependendo das ferramentas que utiliza, poderá ter de adicionar um banner de consentimento ao seu site.

## Google Analytics

Para ativar o Google Analytics no seu site Obsidian Publish:

1. Na faixa de opções, à esquerda da janela da aplicação, clique em **Publicar alterações** ![[lucide-send.svg#icon]].
2. Na caixa de diálogo **Publicar alterações**, clique em **Alterar opções do site** ![[lucide-cog.svg#icon]].
3. Em **Código de rastreio do Google Analytics**, introduza o seu código de rastreio.

Para utilizar o Google Tag Manager em vez do Google Analytics, use JavaScript personalizado para adicionar os seus próprios scripts.

## Plausible, Fathom e outros serviços de análise

Pode adicionar a maioria dos serviços de análise ao seu site através do seu ficheiro [[Personalizar o seu site|publish.js]]. Certifique-se de substituir `yourdomain.com` pelo seu domínio, e o `src` do script pelo script do seu fornecedor de análises.

Aqui está um exemplo com [Plausible Analytics](https://plausible.io/)

```js
var analyticsScript = document.createElement('script');
analyticsScript.defer = true;
analyticsScript.setAttribute('data-domain', 'yourdomain.com');
analyticsScript.src = 'https://plausible.io/js/plausible.js';
document.head.appendChild(analyticsScript);
```

A mesma abordagem pode ser utilizada para o [Fathom Analytics](https://usefathom.com/). Note a alteração de `data-domain` para `data-site` — diferentes fornecedores de análises podem ter um formato diferente para a forma como o script deve ser inserido.

```javascript
var fathom = analyticsScript.createElement('script');
analyticsScript.defer = true;
analyticsScript.setAttribute('data-site', 'yourdomain.com');
analyticsScript.src = 'https://cdn.usefathom.com/script.js';
document.head.appendChild(analyticsScript);
```

## Resolução de problemas

Para verificar se o seu site está a utilizar o serviço de análise, desative quaisquer extensões de bloqueio de anúncios no navegador, como o uBlock Origin, que possam impedir a execução do script de rastreio.
