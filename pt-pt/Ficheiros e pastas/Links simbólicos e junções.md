---
permalink: symlinks
---
Pode usar [links simbólicos](https://en.wikipedia.org/wiki/Symbolic_link) (symlinks) e [junções](https://learn.microsoft.com/en-us/windows/win32/fileio/hard-links-and-junctions#junctions) no seu cofre para armazenar ficheiros fora do cofre e da [[Como o Obsidian armazena dados#Global settings|pasta de sistema]].

> [!danger] Use por sua conta e risco
> Desaconselhamos vivamente o uso de links simbólicos. Ao usar links simbólicos e junções no seu cofre, corre o risco de perder ou corromper os seus dados, ou fazer o Obsidian encerrar inesperadamente. Certifique-se de que faz cópias de segurança regulares do seu cofre e das suas definições.

Abaixo encontram-se algumas limitações ou problemas conhecidos que poderá querer ter em consideração:

- Os loops de symlink são proibidos, para evitar que o Obsidian entre num loop infinito e encerre inesperadamente.
- Os destinos de symlink devem ser completamente disjuntos da raiz do cofre ou de quaisquer outros destinos de symlink. Disjunto significa que uma pasta não contém outra, ou vice-versa. O Obsidian ignora qualquer symlink para uma pasta mãe do cofre, ou de uma pasta no cofre para outra pasta no mesmo cofre. É uma salvaguarda para garantir que não acaba com ficheiros duplicados no seu cofre, o que poderia tornar os links ambíguos.
- Os symlinks podem não funcionar bem com o Obsidian Sync, ou _qualquer outro tipo de sincronização_. Se o destino de um symlink for em si uma pasta sincronizada por um cofre Obsidian diferente, poderá (potencialmente) acabar com conflitos de sincronização ou perda de dados. Algumas ferramentas de sincronização, como o Git, não seguem os symlinks, mas antes sincronizam o _caminho_ para o qual o symlink aponta, o que pode produzir resultados indesejáveis se partilhar o seu cofre dessa forma com outras pessoas.
- O gestor de ficheiros do Obsidian não consegue mover ficheiros entre limites de dispositivos, por isso, se criar um symlink para uma pasta numa unidade diferente do seu cofre, não poderá arrastar ficheiros entre essa pasta e outras pastas usando o explorador de ficheiros do Obsidian. (Terá de usar o explorador do seu SO para tais movimentos, e o Obsidian verá o movimento como uma eliminação e a criação de um novo ficheiro. Também _não_ atualizará quaisquer links que dependessem do caminho desse ficheiro.)
- Os symlinks de ficheiros (ao contrário dos symlinks de pastas) _podem_ funcionar, mas não são oficialmente suportados neste momento. As alterações realizadas fora do Obsidian não são monitorizadas, por isso, se alterar o ficheiro diretamente, o Obsidian não detetará a alteração, não atualizará os índices de pesquisa, etc.
- Criar symlinks de elementos dentro da pasta `.obsidian/` para partilhá-los entre cofres **tem uma grande probabilidade de corromper as suas definições**, a menos que saiba _muito bem_ o que está a fazer. Se decidir seguir este caminho, tenha pelo menos cópias de segurança.
