---
permalink: sync/troubleshoot
cssclasses:
  - soft-embed
publish: true
mobile: true
description: This page lists uncommon issues you may encounter with Obsidian Sync and how to resolve them.
---

Esta página lista problemas pouco comuns que pode encontrar com o [[Introdução ao Obsidian Sync|Obsidian Sync]] e como resolvê-los. Antes de prosseguir, recomendamos a consulta das páginas [[Ícone de estado e mensagens]] e [[Perguntas frequentes]].

## Geral

### Resolução de conflitos

Um conflito ocorre quando altera o mesmo ficheiro em dois ou mais dispositivos antes de estes sincronizarem. Por exemplo, edita uma nota no computador. Antes de essa alteração ser carregada, altera também a mesma nota no telemóvel.

Os conflitos ocorrem com mais frequência quando trabalha sem ligação à internet. Há mais alterações e mais tempo entre sincronizações, o que aumenta a probabilidade de conflitos.

#### Como o Obsidian Sync gere os conflitos

Quando o Obsidian Sync detecta um conflito, o resultado depende do tipo de ficheiro:

- **Ficheiros Markdown**: O Obsidian Sync combina as alterações utilizando o algoritmo [diff-match-patch](https://github.com/google/diff-match-patch) da Google.
- **Outros tipos de ficheiro**: Para todos os outros ficheiros, incluindo canvas, o Obsidian utiliza a abordagem de "a última modificação prevalece". A versão modificada mais recentemente substitui as versões anteriores.

Para conflitos nas configurações do Obsidian, como as configurações de plugins, o Obsidian Sync combina os ficheiros JSON. Aplica as chaves do JSON local sobre o JSON remoto.

#### Opções de resolução de conflitos

A partir do Obsidian 1.9.7, pode escolher como gerir os conflitos. Para configurar esta definição:

1. Abra as **[[Configurações]]**.
2. Na barra lateral, seleccione **Sync**.
3. Em **[[Configurações do Sync e sincronização selectiva#Conflict resolution|Resolução de conflitos]]**, escolha a opção que preferir:
   - **Combinar automaticamente** (predefinição): O Obsidian Sync combina todas as alterações de diferentes dispositivos num único ficheiro. Isto guarda todas as edições, mas pode por vezes criar texto duplicado ou problemas de formatação. Terá de os corrigir manualmente.
   - **Criar ficheiro de conflito**: Quando o Obsidian detecta alterações em conflito, cria um ficheiro de conflito separado em vez de combinar automaticamente. Pode então rever ambas as versões e combiná-las manualmente. Isto dá-lhe controlo total sobre o resultado final.

> [!warning]+ Configurar em todos os dispositivos
> As definições de resolução de conflitos são específicas de cada dispositivo. Tem de configurar a opção pretendida em cada um dos seus dispositivos. Isto garante o mesmo comportamento em todos os dispositivos sincronizados.

**Padrão de nomenclatura do ficheiro de conflito**

Quando utiliza a opção "Criar ficheiro de conflito", o Obsidian cria um novo ficheiro com o seguinte padrão de nomenclatura:

```
original-note-name (Conflicted copy device-name YYYYMMDDHHMM).md
```

Por exemplo, se ocorrer um conflito numa nota chamada `Meeting notes.md`, o ficheiro de conflito pode ter o nome:

```
Meeting notes (Conflicted copy MyMacBook2 202411281430).md
```

O ficheiro de conflito contém as alterações do dispositivo onde o conflito foi detectado. O ficheiro original mantém a versão remota. Pode comparar ambos os ficheiros e combinar o conteúdo manualmente.

> [!info]+ Consultar o registo do Sync
> Para verificar quando ocorreram conflitos, abra o [[Ícone de estado e mensagens#Sync activity log|registo do Sync]]. Filtre por "Merge Conflicts" ou pesquise por "Conflict".

### O Sync eliminou uma nota que acabei de criar em dois dispositivos

O Obsidian Sync normalmente tenta [[#Resolução de conflitos|resolver conflitos]] combinando notas em conflito entre dispositivos. No entanto, podem ocorrer problemas com utilizadores que criam ou alteram notas automaticamente no arranque. Isto inclui as [[Notas diárias]] ou quando se utiliza o plugin da comunidade [Templater](https://github.com/SilentVoid13/Templater).

Se criar uma nota localmente num dispositivo e, ao fim de alguns minutos, o Sync transferir uma versão remota dessa mesma nota, o Sync manterá a versão remota sem combinar as duas. Neste caso, pode recuperar a versão local utilizando [[Recuperação de ficheiros]].

### O Sync não sincroniza as actualizações dos meus plugins e configurações

O Obsidian [[Perguntas frequentes#Does Obsidian Sync live-reload my settings?|não recarrega todas as configurações em tempo real]]. Depois de actualizar configurações ou plugins, tem de reiniciar o Obsidian nos outros dispositivos para ver as alterações. Nos dispositivos móveis, poderá ser necessário forçar o fecho da aplicação.

> [!example]- Alterar um tema
> - No seu dispositivo principal (normalmente um computador), muda o tema de volta para o predefinido a partir de um tema personalizado.
> - O registo do Sync confirma que os ficheiros actualizados foram enviados para o cofre remoto, mas o seu dispositivo móvel continua a mostrar o tema personalizado.
> - No dispositivo móvel, consulte o registo do Sync para confirmar a recepção do ficheiro `appearance.json` actualizado.
> - Recarregue ou reinicie o Obsidian no dispositivo móvel.
> - Após recarregar ou reiniciar, o dispositivo móvel deverá apresentar o mesmo tema que o computador.

### Os meus ficheiros continuam a desaparecer do Sync assim que os restauro

Este problema é mais comum no Windows. O Windows Defender pode colocar em quarentena ficheiros com blocos de código, o que faz com que determinadas notas desapareçam.

Outra causa comum é a dupla sincronização. Isto acontece quando o Obsidian Sync é executado em conjunto com outro serviço de sincronização.

![[Migrar para o Obsidian Sync#Move your vault out of your third-party syncing service or cloud storage]]

---

Por fim, isto pode acontecer quando restaura um ficheiro num dispositivo, mas este é depois removido de um dispositivo secundário. Isto ocorre quando o nome do ficheiro contém [[Ícone de estado e mensagens#Skipped messages|caracteres inválidos]].

## Android

**O meu dispositivo está a eliminar os anexos que recebo através do Sync**

Este problema deve-se provavelmente à gestão dos seus anexos pelo Google ou pelo Android Photos. Para evitar que o sistema altere os ficheiros recebidos via Sync, adicione um ficheiro `.nomedia` [ao seu cofre](https://support.google.com/android/thread/60342076/what-are-these-nomedia-files?hl=en) no seu dispositivo Android.

> [!tip]- Utilizar um plugin
> O plugin da comunidade [Android Nomedia](https://obsidian.md/plugins?id=android-nomedia) facilita este processo. Instale-o no seu telemóvel Android. Note que os ficheiros `.nomedia` não são sincronizados entre dispositivos através do Obsidian Sync.
