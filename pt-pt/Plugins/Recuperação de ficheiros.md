---
permalink: plugins/file-recovery
publish: true
mobile: true
description: File Recovery helps protect your work from unintentional data loss by automatically saving snapshots of your notes at regular intervals.
---

A Recuperação de ficheiros é um [[Plugins nativos|plugin nativo]] que protege o seu trabalho de eliminações acidentais, corrupção de ficheiros ou alterações indesejadas, guardando automaticamente instantâneos completos das suas notas em intervalos regulares. A Recuperação de ficheiros não é uma solução de cópia de segurança completa, e recomendamos também [[Criar cópia de segurança dos seus ficheiros do Obsidian|fazer cópias de segurança]] dos seus ficheiros do Obsidian separadamente.

Para evitar ocupar [[#Storage and performance|demasiado espaço]], o Obsidian mantém os instantâneos durante um determinado número de dias antes de os eliminar. Os instantâneos capturam o conteúdo completo dos seus ficheiros, não apenas as alterações, permitindo-lhe restaurar qualquer versão anterior.

> [!info]+ Informação
> Por predefinição, os instantâneos são guardados com um intervalo mínimo de 5 minutos entre si e mantidos durante 7 dias. Pode configurar ambos os intervalos em **[[Configurações]] → Plugins nativos → Recuperação de ficheiros**.

Os instantâneos são mantidos nas [[Como o Obsidian armazena dados#Global settings|Definições globais]], fora do cofre, para ter em conta a perda de dados relacionada com o cofre. Isto significa que os instantâneos são armazenados com o caminho absoluto para a nota. Se moveu o seu cofre recentemente, poderá precisar de o mover de volta para o local onde estava quando o instantâneo foi tirado.

> [!tip] Se estiver a usar o [[Introdução ao Obsidian Sync|Obsidian Sync]] ou [[Sincronizar as suas notas entre dispositivos|outros serviços de sincronização]], os instantâneos da Recuperação de ficheiros não serão sincronizados entre dispositivos. Os instantâneos são específicos do dispositivo e permanecem locais em cada dispositivo.

## Recuperar um instantâneo

1. Abra as **[[Configurações]]**.
2. Na barra lateral, selecione **Recuperação de ficheiros** em **Plugins nativos**.
3. Em **Instantâneos**, selecione **Ver**.
4. No campo do nome do ficheiro, comece a escrever o nome do ficheiro que pretende recuperar e verá uma lista de sugestões.
5. Selecione o ficheiro, prima Enter e verá uma lista de instantâneos disponíveis.
6. Selecione o instantâneo que pretende recuperar.
    1. Se pretender copiar e colar numa nova nota, selecione o botão **Copiar**.
    2. Se pretender restaurar o ficheiro completamente, selecione o botão **Restaurar**.
7. Opcionalmente, pode mostrar as diferenças entre instantâneos alternando **Mostrar alterações**. Isto apresenta que conteúdo foi adicionado, removido ou modificado entre versões de instantâneos.

## Limpar o histórico de instantâneos

> [!danger] Limpar o histórico de instantâneos elimina irreversivelmente todos os instantâneos no seu cofre.

1. Abra as **[[Configurações]]**.
2. Na barra lateral, selecione **Recuperação de ficheiros** em **Plugins nativos**.
3. Em **Limpar histórico**, selecione **Limpar**.
4. Confirme que pretende eliminar todos os instantâneos clicando em **Limpar**.

## Armazenamento e desempenho

Os instantâneos da Recuperação de ficheiros tipicamente usam espaço mínimo em disco, pois apenas armazenam ficheiros alterados. No entanto, em cofres com muitos ficheiros grandes ou edições frequentes, os instantâneos podem acumular-se ao longo do tempo. Monitorize o uso do seu armazenamento e ajuste o período de retenção se necessário.

## Limitações

- **Modo de bloqueio da Apple**: Esta funcionalidade não está disponível em dispositivos Apple com o [modo de bloqueio](https://support.apple.com/en-us/105120) ativado, a menos que o Obsidian esteja isento.
- **Tipos de ficheiro**: Apenas os ficheiros `.md` e `.canvas` podem ser restaurados usando a Recuperação de ficheiros.
- **Localização do cofre**: Se mover o seu cofre para uma localização diferente sem usar o [[Gerir cofres#Move vault to a different folder|seletor de cofres]], os instantâneos existentes podem não estar acessíveis.
