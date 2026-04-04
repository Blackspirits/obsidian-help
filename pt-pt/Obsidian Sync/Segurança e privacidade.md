---
permalink: sync/security
publish: true
mobile: false
description: Learn about the security and privacy considerations for Obsidian Sync.
---

## Encriptação

Para a sua segurança, o [[Introdução ao Obsidian Sync|Obsidian Sync]] encripta o seu [[Cofres locais e remotos|cofre remoto]] e todas as comunicações com os servidores da Obsidian.

Quando cria um novo cofre remoto, tem duas opções:

- **Encriptação ponta a ponta (predefinição)** oferece a maior segurança, mas exige que guarde a sua palavra-passe de encriptação em lugar seguro. Isto garante que ninguém — nem sequer a equipa da Obsidian — pode aceder às suas notas.
- **Encriptação padrão** utiliza uma chave de encriptação gerida pela Obsidian para proteger os seus dados em trânsito e no servidor.

Recomendamos a encriptação ponta a ponta para todos os utilizadores, pois é a opção mais privada e segura. No entanto, tenha em atenção que, se se esquecer ou perder a sua palavra-passe de encriptação, os seus dados permanecerão encriptados e inutilizáveis para sempre. Não é possível recuperar a sua palavra-passe nem quaisquer dados encriptados.

A sua escolha afecta apenas o cofre remoto. O Obsidian não encripta o seu cofre local.

### O que significa encriptação ponta a ponta?

A encriptação ponta a ponta significa que os dados são encriptados desde o momento em que saem do seu dispositivo, e só podem ser desencriptados com a sua chave de encriptação quando chegam a um dos seus dispositivos.

Não podemos ler os seus dados. Tampouco qualquer potencial interceptador, como o seu fornecedor de acesso à internet.

No caso improvável de uma violação completa do servidor, os seus dados permanecem encriptados — ninguém pode desencriptar os seus ficheiros sem conhecer a sua palavra-passe.

### Quais são os riscos de utilizar a encriptação padrão?

A encriptação padrão é fundamentalmente menos segura do que a encriptação ponta a ponta, mas pode ser uma opção conveniente se não esperar que os dados que está a sincronizar sejam completamente privados. Por exemplo, se o seu cofre sincronizado estiver [[Introdução ao Obsidian Publish|publicado]] num site público como este site de ajuda, a encriptação ponta a ponta não é necessária.

A encriptação padrão é o mesmo método de encriptação utilizado por empresas de armazenamento em nuvem e plataformas de software como serviço, como o Google Docs, o Dropbox e o iCloud (sem Protecção de Dados Avançada). A sua chave de encriptação é gerada pela aplicação e usada para proteger os seus dados em trânsito e no servidor. Como a chave de encriptação está armazenada nos servidores da empresa, pode ser usada para desencriptar os seus dados, por exemplo, no caso de a empresa ser sujeita a uma ordem de busca, ou no caso de querer aceder aos seus dados através de um navegador web.

A encriptação ponta a ponta garante que a Obsidian nunca pode aceder aos seus dados e deve ser sempre utilizada para sincronizar dados que pretende que permaneçam completamente privados e seguros.

### Que encriptação é utilizada?

Para a segurança dos dados, implementamos protocolos de encriptação padrão da indústria. Especificamente, utilizamos [AES-256](https://www.nist.gov/publications/advanced-encryption-standard-aes-0), o padrão de encriptação mais robusto, amplamente utilizado em contextos como a banca online. O processo de encriptação envolve os seguintes detalhes técnicos:

- **Função de derivação de chave:** [scrypt](https://en.wikipedia.org/wiki/Scrypt) com salt
- **Algoritmo de encriptação:** AES-256 usando [Galois/Counter Mode (GCM)](https://en.wikipedia.org/wiki/Galois/Counter_Mode)

### Posso verificar se os meus dados têm encriptação ponta a ponta?

Sim. Consulte o nosso guia, [como verificar a encriptação ponta a ponta do Obsidian Sync](https://obsidian.md/blog/verify-obsidian-sync-encryption/). Este guia fornece instruções passo a passo para verificar de forma autónoma a encriptação ponta a ponta dos seus dados quando são enviados e recebidos através dos servidores do Sync.

### O Obsidian realizou uma auditoria de segurança por terceiros?

Sim. O Obsidian foi auditado de forma independente. Visite a nossa [página de Segurança](https://obsidian.md/security) para ver os relatórios de auditoria. As auditorias regulares por empresas de segurança externas garantem que o código e os procedimentos do Obsidian cumprem os mais elevados padrões de segurança.

### O que acontece se me esquecer da palavra-passe de encriptação?

Se perder ou se esquecer da palavra-passe de encriptação, não conseguirá ligar cofres adicionais ao seu cofre remoto. Como a palavra-passe de encriptação não está guardada em nenhum lugar, estará perdida para sempre.

Os seus dados, no entanto, estão geralmente armazenados em segurança localmente em cada um dos seus dispositivos.

Para continuar a utilizar o Obsidian Sync, sugerimos uma reconfiguração completa para poder adicionar novos dispositivos ao seu sistema do Sync:

1. Faça uma cópia de segurança completa do cofre no seu dispositivo principal, por precaução. Pode ser tão simples como fazer uma cópia da pasta do cofre ou criar um ficheiro zip a partir do cofre.
2. Desconecte o cofre remoto em cada um dos seus dispositivos. Pode fazê-lo acedendo a **[[Configurações]] → Sync → Seleccionar cofre remoto → Desligar**.
3. [[Configurar o Obsidian Sync#Create a new remote vault|Crie um novo cofre remoto]] no seu dispositivo principal a partir da mesma página de Configurações. Opcionalmente, pode eliminar o cofre remoto anterior, uma vez que já não tem a palavra-passe. (Poderá ter de eliminar o cofre remoto anterior se tiver atingido o [[Perguntas frequentes#How many remote vaults can I have?|limite de cofres]])
4. Aguarde que o seu dispositivo principal sincronize. Observe o indicador de sincronização no canto inferior direito do ecrã até que apresente uma marca verde.
5. Ligue cada um dos seus dispositivos ao mesmo cofre remoto recém-criado. Ao ligar, ser-lhe-á mostrado um aviso sobre a combinação do cofre, o que é esperado e pode prosseguir. Aguarde que cada dispositivo sincronize completamente antes de passar para o seguinte. Isto reduz a probabilidade de problemas.
6. Agora todos os seus dispositivos deverão estar ligados ao novo cofre remoto.

## Alojamento

### Onde estão alojados os servidores do Obsidian Sync?

Os nossos centros de dados, alimentados pela [DigitalOcean](https://www.digitalocean.com), disponibilizam opções de alojamento de cofres remotos por região geográfica nas seguintes localizações:

> [!abstract] Regiões do Sync
> **Automático**: O centro de dados é escolhido com base na sua localização IP, no momento em que configura o Sync pela primeira vez.
> 
> **Ásia**: Singapura
> **Europa**: Frankfurt, Alemanha
> **América do Norte**: São Francisco, EUA
> **Oceânia**: Sydney, Austrália
^sync-geo-regions

### Onde posso encontrar o meu servidor do Sync atual e onde está alojado?

Para localizar o seu servidor do Obsidian Sync, siga estes passos:
1. Aceda a **[[Configurações]]** → **Sync** → **Copiar informações de depuração**.
2. Cole a informação copiada numa nota ou ficheiro.
3. Procure uma linha semelhante a esta: `Host server: wss://sync-xx.obsidian.md`

Esta linha indica o servidor onde o seu cofre remoto está alojado. Para mais detalhes sobre as localizações dos servidores e o tempo de atividade, visite a nossa [página de estado](https://status.obsidian.md/).

## Rede e acesso

### Gerir o acesso ao Obsidian Sync na sua rede

Para regular o acesso ao Obsidian Sync na sua rede, precisa de gerir os seguintes domínios:

`sync-xx.obsidian.md`

O `xx` representa neste caso um número entre `1 - 100`.

> [!tip] Se o seu sistema de firewall suportar, recomendamos colocar `sync-*.obsidian.md` na lista de permissões para ter em conta o crescimento contínuo dos números de subdomínio.

## Limitações

O Obsidian Sync foi concebido para manter as suas notas privadas e seguras. Para proporcionar uma sincronização rápida e fiável, assim como um armazenamento eficiente entre dispositivos, fazemos algumas opções deliberadas na forma como a encriptação é aplicada.

### Encriptação determinística de hash de ficheiros

Encriptamos os hashes de ficheiros de forma determinística: o mesmo conteúdo de ficheiro, usando a mesma chave de encriptação e salt, produz sempre o mesmo hash encriptado no servidor. Isto ajuda o Sync a detectar duplicados e a evitar carregar ou armazenar novamente dados idênticos, o que poupa largura de banda e armazenamento remoto, especialmente no histórico de versões ou quando ficheiros grandes se repetem.

No entanto, se um atacante comprometer um servidor do Sync, e tiver uma forma separada de forçar um utilizador a carregar ficheiros à sua escolha, poderá forçar o utilizador a carregar ficheiros específicos e determinar se o ficheiro corresponde a um ficheiro que o utilizador carregou anteriormente.

### Sem ligação criptográfica entre caminho e conteúdo

Alguns metadados não têm encriptação ponta a ponta: qual o dispositivo que carregou ou eliminou um ficheiro, quando foi carregado, e o *mapeamento* entre os caminhos de ficheiros encriptados e o conteúdo encriptado. Estes dados são legíveis pelo servidor para que possa encaminhar as alterações, determinar o histórico de versões de um ficheiro e manter os dispositivos sincronizados.

Se um servidor do Sync fosse comprometido, um atacante poderia manipular esse mapeamento, fazendo com que o conteúdo de um ficheiro encriptado fosse entregue sob um caminho de ficheiro diferente. Isso não revela os seus dados em texto simples — estes permanecem encriptados.
