---
permalink: sync/switch
cssclasses:
  - soft-embed
publish: true
mobile: true
description: Learn how to transition from your current syncing solution to Obsidian Sync.
---
Saiba como fazer a transição da sua solução de sincronização atual para o Obsidian Sync.

> [!warning] Evite utilizar várias soluções para sincronizar os mesmos ficheiros
> [[Perguntas frequentes#Can I use a third-party sync with Obsidian Sync?|Não recomendamos]] a utilização do Obsidian Sync em conjunto com serviços de armazenamento em nuvem (por exemplo, iCloud, Dropbox, OneDrive, Google Drive), pois pode originar conflitos. No entanto, os serviços de armazenamento em nuvem podem ter um papel na sua estratégia de [[Criar cópia de segurança dos seus ficheiros do Obsidian|cópias de segurança]].

## Mover o seu cofre para fora do serviço de sincronização de terceiros ou armazenamento em nuvem

Se o seu cofre estiver armazenado em algum dos seguintes locais, é provável que esteja a ser sincronizado por um serviço de terceiros:

- **Windows**: `C:\Users\Username\Desktop` ou `C:\Users\Username\Documents`
- **macOS**: `/users/username/Desktop` ou `/users/username/Documents`
- **iOS**: A pasta **iCloud** na aplicação Ficheiros
- **Outros**: Qualquer pasta sob um serviço de sincronização, como `Drive/my-vault`, `Dropbox/my-vault`, `pSync/my-vault`, etc.

Embora o Android e o Linux tendam a ter menos problemas com isto, ainda vale a pena verificar a localização do cofre nesses dispositivos.

> [!tip] Se o seu cofre local atual estiver ligado a um cofre remoto, o Obsidian tentará detectar se o cofre está num serviço de sincronização. Se estiver, verá uma mensagem no topo das configurações do Obsidian Sync.

Para evitar conflitos com serviços de sincronização, recomendamos armazenar os seus cofres do Obsidian nos seguintes locais:

- **Windows**: Locais recomendados por ordem de preferência:
    1. `D:\` ou qualquer outra unidade que não seja C: nem de rede no seu dispositivo
    2. `C:\Vaults` (se tiver permissões para utilizar a unidade C:\\)
    3. `C:\Users\Username\Vaults` (se tiver de manter o cofre em C:\Users\Username, certifique-se de que o OneDrive está configurado para não remover ficheiros. O OneDrive é geralmente menos agressivo fora das pastas `Desktop` e `Documents`.)
- **macOS**: `/users/username/vaults`
- **Linux**: Sem recomendação específica devido à variedade de sistemas de ficheiros. Garanta apenas que o Obsidian tem acesso total de leitura/escrita e que nenhum serviço de sincronização gere a pasta.
- **iOS/iPadOS**: Armazene o cofre **No meu iPhone** ou **No dispositivo**.
- **Android**: Utilize a pasta `Documents/` no seu dispositivo.

## Mover o seu cofre com o Obsidian no desktop

![[Gerir cofres#Move vault to a different folder]]

## Mover o seu cofre em dispositivos móveis

Nos dispositivos móveis, o Obsidian funciona num ambiente isolado (sandbox), o que significa que não é possível mover cofres dentro da aplicação como se faz no desktop.

### Android

Os sistemas de ficheiros do Android variam muito consoante o dispositivo, mas, de modo geral, siga os mesmos passos que seguiria para mover o cofre manualmente, garantindo que este é removido de qualquer serviço de sincronização no seu dispositivo.

### iOS e iPadOS

Para mover um cofre existente no iCloud para o seu dispositivo, siga estes passos:

> [!note] Se já tiver os dados noutro dispositivo e tiver configurado o Obsidian Sync, recomenda-se [[Configurar o Obsidian Sync#Sync a remote vault on another device|configurar um novo cofre local a partir do Sync]].

- [[Criar cópia de segurança dos seus ficheiros do Obsidian|Faça uma cópia de segurança]] do seu cofre.
- Crie um novo cofre no seu dispositivo, garantindo que **Guardar no iCloud Drive** está desactivado.
- Force o encerramento da aplicação Obsidian em todos os dispositivos para pausar o Sync.
- Abra a aplicação **Ficheiros** no seu dispositivo iOS/iPadOS.
- Mantenha premida a pasta do cofre em **iCloud Drive → Obsidian** e seleccione **Mover**.
- Mova o cofre para **No meu iPhone/Dispositivo → Obsidian** e confirme que está visível.
- Toque em **Copiar**.
- Regresse a **iCloud Drive → Obsidian** e elimine a pasta do cofre antigo.

Quando reabrir o Obsidian, o cofre deverá mostrar um ícone de cofre em vez de um ícone de nuvem, confirmando que já não está no iCloud Drive. O Obsidian Sync também deixará de apresentar a mensagem de aviso nas suas configurações.

## Próximos passos

- Quer começar a utilizar o Obsidian Sync? [[Configurar o Obsidian Sync]]
- Ainda precisa de ajuda? Consulte [[Resolução de problemas do Obsidian Sync]]
