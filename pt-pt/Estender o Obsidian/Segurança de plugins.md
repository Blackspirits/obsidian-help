---
permalink: plugin-security
---
A equipa do Obsidian leva a segurança a sério. Esta página explica os riscos envolvidos na instalação de plugins da comunidade e o que a equipa do Obsidian faz para os minimizar.

## Modo restrito

Por predefinição, o Obsidian funciona em Modo restrito para impedir a execução de código de terceiros. Desative o Modo restrito apenas se confiar nos autores dos plugins que instala.

Para desativar o Modo restrito:

1. Abra as **[[Configurações]]**.
2. No menu lateral, selecione **Plugins da comunidade**.
3. Selecione **Ativar plugins da comunidade**.

Para ativar o Modo restrito:

1. Abra as **[[Configurações]]**.
2. No menu lateral, selecione **Plugins da comunidade**.
3. Junto a **Modo restrito**, selecione **Ativar**.

Os plugins instalados permanecem no seu cofre mesmo que ative o Modo restrito, mas são ignorados pelo Obsidian.

## Capacidades dos plugins

Devido a limitações técnicas, o Obsidian não consegue restringir de forma fiável os plugins a permissões ou níveis de acesso específicos. Isto significa que os plugins herdarão os níveis de acesso do Obsidian. Como resultado, considere os seguintes exemplos do que os plugins da comunidade podem fazer:

- Os plugins da comunidade podem aceder a ficheiros no seu computador.
- Os plugins da comunidade podem ligar-se à internet.
- Os plugins da comunidade podem instalar programas adicionais.

> [!tip]
> Se trabalha com dados sensíveis e pretende instalar um plugin da comunidade, recomendamos que realize uma auditoria de segurança independente ao plugin antes de o utilizar.

## Processo de revisão de plugins

Os plugins da comunidade passam por uma revisão inicial quando são submetidos à loja de plugins. Todos os plugins devem cumprir as [Políticas para Programadores do Obsidian](https://docs.obsidian.md/Developer+policies).

A equipa do Obsidian é pequena e não consegue rever manualmente cada nova versão dos plugins da comunidade. Em vez disso, contamos com a ajuda da comunidade para identificar e reportar problemas com plugins.

- Se descobrir alguma vulnerabilidade de segurança menor num plugin da comunidade, consulte o `security.md` ou `readme.md` do autor do plugin para saber como reportá-la. Para falhas de categoria Crítica, reporte o problema também ao [[Ajuda e suporte#Contact Obsidian support|suporte do Obsidian]].
- Se suspeitar que um plugin da comunidade é malicioso, reporte-o ao [[Ajuda e suporte#Contact Obsidian support|suporte do Obsidian]], ou enviando uma mensagem direta aos nossos moderadores.


