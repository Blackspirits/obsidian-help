---
permalink: teams/security
cssclasses:
  - soft-embed
---
A nossa página de [Segurança](https://obsidian.md/security) reúne informações sobre a forma como o Obsidian aborda a proteção dos seus dados. É também onde se encontram as auditorias de segurança realizadas por terceiros.

## Considerações

O Obsidian foi concebido para funcionar como uma aplicação offline e autónoma. O Obsidian também suporta plugins e temas personalizados. Adicionalmente, fornecemos suporte oficial e não oficial para vários serviços de sincronização de ficheiros.

Se não tencionar utilizar plugins ou temas da comunidade, nem o [[Introdução ao Obsidian Sync|Obsidian Sync]] ou o [[Introdução ao Obsidian Publish|Obsidian Publish]], os seus procedimentos habituais de segurança de aplicações serão aplicáveis. No entanto, se planear utilizar alguma destas funcionalidades, recomendamos que avalie cuidadosamente a sua adequação ao ambiente de trabalho.

## Plugins e temas da comunidade

Consulte também a página [[Segurança de plugins]], além desta secção.

A equipa do Obsidian analisa todos os plugins e temas da comunidade submetidos ao diretório oficial, através do nosso [repositório de publicações](https://github.com/obsidianmd/obsidian-releases/pulls?q=is%3Apr+is%3Aopen+sort%3Aupdated-desc). Não analisamos itens da comunidade que não tenham sido submetidos ao diretório oficial.

Não dispomos de uma loja da comunidade para [[Fragmentos CSS]]. Estes ficheiros são geralmente obtidos na nossa [Comunidade Obsidian](https://obsidian.md/community) ou em repositórios públicos do GitHub.

Exigimos a integração de recursos nos fragmentos CSS e nos temas. No entanto, fizemos uma exceção para as [Google Fonts](https://fonts.google.com/) de modo a manter o desempenho em dispositivos móveis, onde o impacto da integração de tipos de letra é mais notório.

## Rede e acesso

Embora priorizando a abordagem local-first da nossa aplicação, o Obsidian realiza ligações de rede com base nos serviços e funcionalidades que utiliza. Estas ligações de rede podem ser desativadas através de uma firewall de domínio ou de um bloqueio de aplicação.

O Obsidian realiza estas ligações de rede na porta HTTPS 443.

Em seguida apresenta-se uma lista das ligações de rede efetuadas pelo Obsidian.

### Ligações originadas pelo Obsidian

- **Atualizações de acesso antecipado**: Utiliza `releases.obsidian.md`.
- **Gestão de conta e licença**: Ao aceder à sua conta Obsidian nas Configurações e ao aplicar uma Licença Comercial, chamamos `api.obsidian.md`.
- **Obsidian Sync**: Utilizado para sincronizar as suas notas entre dispositivos.
	- `sync-xx.obsidian.md`, onde `xx` é um número entre 01 e 100.
- **Obsidian Publish**:
    1. Backend: `publish-main.obsidian.md` e `publish-xx.obsidian.md`, onde `xx` é um número.
    2. Frontend: `publish.obsidian.md`.

### Ligações originadas pelo GitHub

O Obsidian realiza pedidos de rede tanto para `github.com` como para `raw.githubusercontent.com`.

- **Publicações públicas**: Se as atualizações automáticas estiverem ativadas, o Obsidian verifica o GitHub para publicações públicas.
- **Temas e plugins de terceiros**:
    - É efetuada uma verificação uma vez a cada 12 horas a partir da hora de arranque da aplicação para obter um ficheiro alojado no GitHub utilizado para "descontinuações de plugins". Este ficheiro ajuda a desativar remotamente versões específicas de plugins conhecidos por funcionar incorretamente, causar perda de dados ou ser potencialmente vulneráveis ou maliciosos.
    - Os plugins ativados podem gerar tráfego de rede fora do controlo do Obsidian e do GitHub.

### Outras ligações

- **Conteúdo online incorporado**: Ao abrir notas que incorporam conteúdo online, tal como uma imagem (`![gato](https://upload.wikimedia.org/wikipedia/commons/0/0b/Cat_poster_1.jpg)`).
- **Pedidos DNS**: Se for necessário resolver um nome de anfitrião antes de estabelecer uma ligação, incluindo DNS over HTTPS. Consulte a [documentação do Chromium](https://source.chromium.org/chromium/chromium/src/+/main:net/dns/public/doh_provider_entry.cc;l=120?q=chrome.cloudflare-dns.com&ss=chromium) para mais informações.

## Perguntas frequentes

### Segurança de conta

**O Obsidian suporta Single Sign-On (SSO)?**
O Obsidian não suporta SSO. Na maioria dos casos de utilização, o Obsidian não requer uma conta nem inicio de sessão no ambiente de trabalho, a menos que esteja a utilizar o [[Introdução ao Obsidian Publish|Obsidian Publish]] ou o [[Introdução ao Obsidian Sync|Obsidian Sync]].

**O Obsidian suporta Autenticação Multi-Fator (MFA)?**
O Obsidian suporta [[Autenticação de 2 fatores]] (2FA) para contas Obsidian, mas não suporta 2FA para abrir e utilizar a aplicação base. Os utilizadores do [[Introdução ao Obsidian Sync|Obsidian Sync]] e do [[Introdução ao Obsidian Publish|Obsidian Publish]] que tenham o 2FA ativado serão obrigados a confirmar a chave 2FA quando iniciarem sessão pela primeira vez na aplicação.

### Avaliações e certificações

**Aceitam avaliações de segurança da nossa empresa?**
Exigimos um valor mínimo de ordem de compra antes de considerarmos realizar uma avaliação de segurança. Estas avaliações são frequentemente morosas e podem não ser aplicáveis a aplicações offline como o Obsidian, pois são tipicamente direcionadas a serviços baseados na nuvem.

No entanto, pode dispensar este valor mínimo de ordem de compra ao concordar com o pagamento de uma taxa de retenção. Contacte o [[Ajuda e suporte#Contact Obsidian support|suporte do Obsidian]] para obter informações sobre esta opção.

**Possuem certificações reconhecidas relacionadas com Segurança da Informação ou normas de qualidade, como ISO27001, NIST, COBIT ou outras certificações ISO ou CSA?**
De momento, não. É algo que poderemos explorar no futuro, mas por agora o nosso foco está nas nossas [auditorias de segurança](https://obsidian.md/security).
