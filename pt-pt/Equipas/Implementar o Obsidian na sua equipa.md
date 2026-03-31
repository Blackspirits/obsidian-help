---
permalink: teams/deploy
cssclasses:
  - soft-embed
---
O Obsidian é executado como uma aplicação local em cada dispositivo dos membros da sua equipa. Foi concebido para funcionar tanto online como offline, de forma segura e privada, dando-lhe total controlo sobre os dados da sua equipa. O Obsidian não está disponível como aplicação web, pelo que terá de implementar a aplicação nos dispositivos dos membros da equipa.

## Instalar e atualizar o Obsidian

A sua equipa pode descarregar o Obsidian a partir da nossa [página de descarregamento](https://obsidian.md/download). As versões também estão disponíveis na nossa [página de publicações do GitHub](https://github.com/obsidianmd/obsidian-releases/releases), que inclui ligações para [o registo de alterações](https://obsidian.md/changelog/).

> [!tip] Para utilizadores de Windows que necessitem de um instalador de sistema, o ficheiro `.exe` Universal inclui a opção de instalar o Obsidian para todos os utilizadores.

Se as atualizações automáticas estiverem ativadas na aplicação, as versões futuras serão instaladas automaticamente quando os utilizadores reiniciarem o Obsidian. Adicionalmente, recomendamos realizar periodicamente [[Atualizar o Obsidian#Installer updates|atualizações do instalador]] para receber as atualizações mais recentes da framework Electron, incluindo correções de segurança.

Se pretender saber como limitar o acesso de rede ao Obsidian durante este processo, consulte [[Considerações de segurança para equipas#Network and access|rede e acesso]].

## Personalizar o Obsidian

O Obsidian é fácil de modificar para satisfazer as necessidades da sua equipa. Com uma API abrangente e um grande ecossistema de utilizadores, o Obsidian oferece acesso a numerosos plugins, temas e ferramentas complementares.

Para questões relacionadas com segurança relativamente a estes tópicos, consulte [[Considerações de segurança para equipas]].

### Pastas de configuração

A [[Pasta de configuração]] é onde um [[Glossário#Vault|cofre]] do Obsidian armazena as suas configurações de aplicação. Por predefinição, esta pasta tem o nome `.obsidian`, mas tem a flexibilidade de [[Pasta de configuração#Change your configuration folder|alterar o nome da pasta de configuração]] conforme a sua preferência.

Recomendamos criar um modelo padronizado da pasta de configuração para ser implementado nos dispositivos da sua equipa.

### Plugins

Os [[Plugins nativos]] são funcionalidades opcionais criadas pela equipa do Obsidian. Estas funcionalidades estão integradas no código da aplicação principal e podem ser ativadas ou desativadas.

Os [[Plugins da comunidade]] são funcionalidades de terceiros adicionadas à aplicação Obsidian, e podem ser instaladas através do diretório da comunidade. Os plugins de terceiros utilizam a [API do Obsidian](https://github.com/obsidianmd/obsidian-api). Os plugins estão localizados na pasta `.obsidian/plugins` dentro de um cofre, e podem ser instalados manualmente nessa localização.

### Temas e fragmentos

Os [[Temas]] alteram visualmente a interface do Obsidian. Tal como os plugins, os temas podem ser descarregados do nosso diretório da comunidade. Os temas estão localizados na pasta `.obsidian/themes` dentro de um cofre.

Os [[Fragmentos CSS|Fragmentos]] são pequenos ficheiros `.css` que modificam visualmente aspetos da interface do Obsidian. Em alguns casos, também podem adicionar melhorias funcionais. Os fragmentos estão localizados na pasta `.obsidian/snippets` dentro de um cofre.

## Perguntas frequentes

Para questões sobre gestão de contas e segurança, consulte [[Considerações de segurança para equipas#Account security|segurança de conta]].

### Implementação

**Posso implementar licenças em múltiplas instalações?**
De momento, não suportamos a implementação de licenças através de um script de implementação, tal como num ficheiro `.json`. Se tiver interesse nesta funcionalidade para a sua equipa, submeta um [pedido de funcionalidade](https://forum.obsidian.md/c/feature-requests/8).

**O Obsidian pode bloquear determinadas funcionalidades ou configurações através de uma definição ou um sinalizador de aplicação?**
De momento, pode fazê-lo bloqueando o acesso de edição à pasta `.obsidian`, ou a ficheiros e pastas específicos dentro dela, conforme descrito acima. Se tiver interesse em mais controlos de acesso para a sua equipa, submeta um [pedido de funcionalidade](https://forum.obsidian.md/c/feature-requests/8).
