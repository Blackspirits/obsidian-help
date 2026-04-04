---
permalink: android
---

A aplicação móvel do Obsidian para Android traz capacidades poderosas de tomada de notas para o seu dispositivo Android. Pode descarregá-la a partir do [Google Play](https://play.google.com/store/apps/details?id=md.obsidian) ou como [ficheiro APK](https://obsidian.md/download).
Suporta versões Android 5.1 e superiores.

Esta página abrange as funcionalidades específicas do Android, incluindo widgets, integração com as Definições Rápidas e atalhos.

## Sincronização

Para sincronizar as suas notas com o Obsidian no Android, consulte [[Sincronizar as suas notas entre dispositivos]].

## Localização do cofre

Quando inicia o Obsidian no Android, ser-lhe-á pedido que escolha onde os dados do seu cofre devem ser armazenados. Pode escolher **armazenamento do dispositivo** (recomendado) ou **armazenamento da aplicação**.

### Armazenamento do dispositivo

Com a opção de **armazenamento do dispositivo**, os seus dados são armazenados numa localização partilhada no seu dispositivo. Isto permite que o seu cofre do Obsidian seja acedido por outras aplicações e serviços, como ferramentas de [[Sincronizar as suas notas entre dispositivos|sincronização]] de terceiros.

Esta é a opção recomendada porque oferece melhor compatibilidade com ferramentas de sincronização e garante que os seus dados persistem mesmo que desinstale a aplicação. No entanto, esta opção requer permissões adicionais para aceder aos ficheiros do seu dispositivo.

Devido a limitações do Android, o Obsidian solicitará acesso a "Todos os ficheiros" para funcionar de forma fiável. O Google recomenda isto para aplicações como o Obsidian, que são consideradas "aplicações de gestão de documentos". [Saiba mais](https://developer.android.com/training/data-storage/manage-all-files).

A aplicação usa esta permissão apenas para o ajudar a aceder aos seus dados no seu dispositivo. Os seus dados nunca nos são acessíveis. Para saber mais sobre como protegemos os seus dados e garantimos a sua privacidade, visite a nossa [página de Segurança](https://obsidian.md/security).

### Armazenamento da aplicação

Com a opção de **armazenamento da aplicação**, os seus dados são armazenados no armazenamento privado da aplicação do Obsidian. Isto mantém os seus dados isolados de outras aplicações para maior privacidade.

Esta é uma boa opção se não estiver a usar ferramentas de sincronização externas e preferir um isolamento mais rigoroso ao nível da aplicação para as suas notas.

Com esta opção pode usar o [[Introdução ao Obsidian Sync|Obsidian Sync]] e plugins de sincronização de terceiros disponíveis através dos [[Plugins da comunidade]], mas não pode usar ferramentas como o Syncthing que dependem de armazenamento partilhado.

> [!warning] Desinstalar o Obsidian irá apagar as suas notas locais se estiver a usar o armazenamento da aplicação
> Se usar a opção de **armazenamento da aplicação**, os dados do seu cofre local serão apagados se desinstalar a aplicação. Os dados do seu cofre do Obsidian noutros dispositivos não serão apagados.

## Widgets

O Obsidian para Android oferece várias opções de widgets para aceder rapidamente aos seus cofres e notas a partir do ecrã inicial. Os widgets disponíveis incluem:

- **Abrir nota** — Abre uma nota específica
- **Nova nota** — Cria uma nova nota
- **Pesquisa** — Inicia uma pesquisa
- **Nota diária** — Abre a sua nota diária
- **Abrir Obsidian** — Abre a aplicação

> [!note] Nota
> Estes widgets são estáticos e não mostram pré-visualizações da nota ou cofre selecionado.

Para adicionar widgets ao seu ecrã inicial:
1. Toque e mantenha premido em qualquer lugar do ecrã inicial
2. Selecione "Widgets"
3. Encontre o Obsidian e selecione o widget que pretende usar.

> [!note] Nota
> Os widgets do Obsidian podem ser redimensionados. Para redimensionar um widget, toque e mantenha premido nele, depois arraste os pontos de redimensionamento.

Pode adicionar vários widgets do mesmo tipo para abrir ficheiros diferentes ou acionar pesquisas diferentes.

Para configurar um widget, prima longamente sobre ele no ecrã inicial e encontre uma opção "Editar" ou "Configurar". Isto permitir-lhe-á especificar os parâmetros específicos necessários para a ação ao tocar no widget funcionar, como o Ficheiro ou Caminho, Consulta de pesquisa e Nome do cofre.

Consulte este [artigo de suporte do Google](https://support.google.com/android/answer/9450271?hl=pt) para mais informações sobre os Widgets do Android.

## Mosaicos de Definições Rápidas

Requer Android 7.0 ou superior.

Adicione um mosaico de Definições Rápidas do Obsidian para acesso rápido à aplicação a partir da sombra de notificações. Funciona no Ecrã Inicial e no Ecrã de Bloqueio.

> [!note] Nota
> Ao contrário dos widgets de aplicações, só pode adicionar um mosaico de Definições Rápidas do mesmo tipo.

Para adicionar um mosaico de definições rápidas à sua sombra de notificações:

1. Aceda à sua sombra de notificações, normalmente deslizando para baixo a partir da barra de estado. Nota: pode precisar de deslizar mais uma vez para ver mais opções.
2. Nos mosaicos de Definições Rápidas, selecione "Editar" — normalmente é a mesma secção onde estão os botões de alternância como Wi-Fi, Bluetooth e Bloqueio de Orientação.
3. Encontre e selecione um mosaico de Definições Rápidas do Obsidian e reorganize-o a seu gosto.
4. Para configurar um mosaico de Definições Rápidas, toque e mantenha premido nele para abrir o ecrã de configuração.

Consulte este [artigo de suporte do Google](https://support.google.com/android/answer/9083864?hl=pt) para mais informações sobre as Definições Rápidas do Android.

## Atalhos

Requer Android 7.1 ou superior.

O Obsidian fornece atalhos de aplicação que podem ser acedidos de várias formas:

- Prima longamente o ícone da aplicação Obsidian
- Arraste o ícone do atalho para o seu ecrã inicial
- Aceda através da barra de pesquisa do seu iniciador (disponível na maioria dos fabricantes de dispositivos)

Atalhos disponíveis:

- **Abrir nota** — Abre uma nota específica no seu cofre
- **Nota diária** — Vai diretamente para a nota diária de hoje

> [!note] Nota
> Os atalhos no Obsidian 1.11 não são configuráveis e serão reformulados em versões futuras para oferecer opções mais dinâmicas adaptadas às suas notas específicas.
