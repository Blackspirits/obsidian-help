---
permalink: backup
---
Se ainda não criou uma cópia de segurança do seu computador, comece agora! O plugin [[Recuperação de ficheiros]] do Obsidian é útil, mas tem limitações. Só consegue recuperar uma determinada quantidade de dados e armazena as informações de recuperação por dispositivo. Para uma proteção mais robusta, recomendamos que implemente um sistema de cópia de segurança adequado.

**Porquê criar cópia de segurança dos seus dados?**

Por predefinição, o Obsidian armazena as suas notas **localmente** no seu dispositivo, não na nuvem. Isto significa que os [dados são totalmente seus](https://obsidian.md/about), dando-lhe controlo sobre eles. No entanto, o armazenamento local pode ser afetado por problemas como corrupção ou perda de dados. A questão não é se isso acontecerá, mas quando. Criar cópia de segurança dos seus dados protege-o contra estas inevitabilidades e garante que mantém o controlo das suas notas.

## Sincronizar não é o mesmo que criar cópia de segurança

Serviços como o [[Introdução ao Obsidian Sync|Obsidian Sync]], iCloud, OneDrive e Dropbox ajudam-no a sincronizar as suas notas entre dispositivos. Embora possam oferecer funcionalidades como [[Histórico de versões|restauro de notas]], **não foram concebidos para cópias de segurança**. A sincronização mantém as suas notas atualizadas, mas não protege contra a perda de dados.

- **Sincronização:** A sincronização garante que os seus ficheiros são iguais em todos os dispositivos. Quando altera um ficheiro num dispositivo, este é atualizado em todos os dispositivos sincronizados. Os serviços de sincronização não têm um dispositivo "principal".
- **Cópia de segurança:** Uma cópia de segurança guarda uma cópia dos seus dados numa localização diferente para ajudar a recuperá-los em caso de perda ou corrupção de dados. As cópias de segurança não se destinam a atualizações em tempo real nem a colaboração.

Para criar corretamente uma cópia de segurança do seu cofre, utilize uma ferramenta dedicada que crie uma cópia unidirecional dos seus dados. Esta ferramenta enviará os seus dados para uma localização de cópia de segurança segura sem alterar os dados no seu dispositivo.

Se utilizar vários dispositivos com sincronização, escolha **um dispositivo** como dispositivo de cópia de segurança. Este é normalmente o seu dispositivo principal ou "primário", aquele que utiliza com mais frequência. Note que a maioria dos serviços de sincronização não reconhece nenhum dispositivo como "principal"; este é apenas um conceito para o ajudar a gerir as cópias de segurança.

> [!Example] Utiliza o Obsidian Sync no seu portátil, tablet, telemóvel e computador do trabalho. Utiliza o cofre principalmente no computador do trabalho, às vezes no portátil e raramente no tablet ou telemóvel. Neste caso, o computador do trabalho seria o seu "dispositivo principal" para cópia de segurança.

## Utilizar plugins da comunidade

Embora a equipa do Obsidian não possa recomendar oficialmente nenhum plugin específico, reconhecemos dois plugins da comunidade que se tornaram populares entre os utilizadores para criação de cópias de segurança dos seus ficheiros:

- **[Obsidian Git](https://obsidian.md/plugins?id=obsidian-git):** Utilize este plugin para criar uma cópia de segurança do seu cofre ao submeter o seu conteúdo para um [repositório Git](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository). É uma forma eficaz de gerir versões das suas notas e garantir a sua segurança num servidor remoto. No entanto, tenha em atenção que os seus dados podem ser armazenados numa [[#Use cloud-based services|plataforma de alojamento externa]] com este método.
- **[Local Backup](https://obsidian.md/plugins?id=local-backup):** Este plugin permite criar cópias locais do seu cofre numa pasta à sua escolha, com opções de arquivo. Pode até utilizar uma pasta de sincronização, como uma pasta do Dropbox, para combinar cópias de segurança locais e na nuvem. Este método **combina bem** com as opções de cópia de segurança descritas abaixo.

## Utilizar serviços baseados na nuvem

> [!info] Não é recomendado manter a localização do seu cofre no serviço de cópia de segurança escolhido.

Manter a cópia de segurança na nuvem é uma alternativa e um complemento ao armazenamento físico de dados, em vez de um disco externo ou uma pen USB. Um disco externo ou uma pen USB podem ser perdidos ou danificados. A maior vantagem de armazenar ficheiros na nuvem é que estão disponíveis a qualquer momento e em qualquer lugar. A desvantagem é que a maioria dos serviços de cópia de segurança pertence a uma empresa privada.

Em termos de segurança, deve prestar sempre muita atenção ao acesso e à segurança das cópias de segurança na nuvem. O [Worldbackupday](https://www.worldbackupday.com/en) mantém uma lista atualizada de serviços de cópia de segurança online a considerar.

## Utilizar discos externos

**Discos rígidos e discos SSD**
As cópias de segurança em disco rígido externo continuam a ser valiosas num mundo cada vez mais baseado na nuvem, e são utilizadas principalmente para armazenamento de dados e cópias de segurança de computadores. A maior desvantagem de um disco externo é que pode avariar ou ser perdido. A maior vantagem é que o espaço de armazenamento só precisa de ser adquirido uma vez. A utilização de um disco rígido externo é muitas vezes combinada com uma [[#Use computer backups|cópia de segurança do computador]].

**Pens USB**
As pens USB (também chamadas drives USB, memory sticks ou pen drives) são um método simples e eficaz para cópias de segurança rápidas.

1. Insira a pen USB no seu computador ou portátil.
2. Certifique-se de que o dispositivo é reconhecido e montado no seu sistema de ficheiros. Se necessário, formate a pen USB para que seja compatível com o seu sistema de ficheiros.
3. Copie a pasta do seu cofre da sua localização atual para a pen USB.
4. Desmonte a pen USB em segurança.
5. Retire a pen USB do seu dispositivo.

**Cópia de segurança em NAS**
Para utilizadores experientes, criar cópias de segurança dos dados num servidor NAS (Network Attached Storage) é um método seguro e eficaz, pois dispõe de vários discos rígidos e de mecanismos de recuperação adicionais.

> [!tip] Se o seu disco externo contiver informações sensíveis, recomenda-se que o guarde em segurança, por exemplo numa sala protegida.

## Utilizar cópias de segurança do computador

O próprio sistema operativo oferece a capacidade de criar cópias de segurança, seja online na nuvem ou num disco externo.

- **[Windows](https://www.microsoft.com/en-us/windows/learning-center/back-up-files)**: Cópia de segurança com OneDrive ou disco externo.
- **[Mac](https://support.apple.com/en-us/104984)**: Cópia de segurança para um dispositivo externo com o Time Machine.
- **[Linux](https://linuxize.com/post/how-to-use-rsync-for-local-and-remote-data-transfer-and-synchronization/)**: `rsync` para um diretório ou disco à sua escolha.

## Próximos passos

Esta página de ajuda fornece uma visão geral das opções de cópia de segurança, mas não é exaustiva. Para informações mais aprofundadas, visite [Worldbackupday.com](https://www.worldbackupday.com/en) ou pergunte a outros utilizadores do Obsidian na [nossa comunidade](https://obsidian.md/community) sobre as suas estratégias de cópia de segurança!
