---
permalink: sync/plans
publish: true
mobile: true
description: Learn about the different plan options we have available for Obsidian Sync.
---

## Planos

Para sincronizar as suas notas com o [[Introdução ao Obsidian Sync|Obsidian Sync]], precisa de um plano de subscrição. Pode adquirir um plano do Sync iniciando sessão em [a sua conta](https://obsidian.md/account/sync). Consulte a [página do Sync](https://obsidian.md/sync) para ver os preços.

Em seguida, apresenta-se uma comparação entre o plano Standard e o plano Plus:

|                                                  | Sync Standard | Sync Plus       |
| ------------------------------------------------ | ------------- | --------------- |
| Cofres sincronizados                             | 1             | 10              |
| Tamanho máximo de ficheiro                       | 5 MB          | 200 MB          |
| Armazenamento total                              | 1 GB          | 10 GB a 100 GB  |
| [[Histórico de versões]]                         | 1 mês         | 12 meses        |
| Dispositivos                                     | Ilimitados    | Ilimitados      |
| [[Colaborar num cofre partilhado\|Cofres partilhados]] | Sim      | Sim             |

## Limites de armazenamento

A quantidade de dados que pode armazenar com o [[Introdução ao Obsidian Sync|Obsidian Sync]] depende do seu plano de subscrição. No plano Sync Plus, pode adquirir armazenamento adicional até 100 GB através do [painel da sua conta](https://obsidian.md/account/sync). Consulte as [[Perguntas frequentes]] para mais detalhes.

Existe um único limite de armazenamento a nível da conta para todas as notas em todos os seus cofres. O [[Histórico de versões]] e os [[Anexos]] também contam para o limite de armazenamento da conta.

Quando atingir o limite de armazenamento da conta, o plugin do Sync deixará de sincronizar ficheiros e ser-lhe-á solicitado que faça a limpeza do(s) seu(s) cofre(s) remoto(s).

### Identificar e eliminar ficheiros grandes

Para identificar e eliminar ficheiros grandes do cofre:

1. Abra **[[Configurações]] → Sync**.
2. Seleccione **Ver ficheiros maiores** junto a **Tamanho do cofre acima do limite**.
	1. Se não vir **Tamanho do cofre acima do limite**, significa que ==ainda não atingiu o limite de tamanho==.
3. Feche o modal **Ver ficheiros maiores**.
4. Elimine alguns dos ficheiros grandes de que já não necessita.
5. Aguarde que o Obsidian Sync conclua a tarefa. Isto pode demorar algum tempo.
6. Abra **[[Configurações]] → Sync**.
7. Seleccione **Limpar** junto a **Tamanho do cofre acima do limite**. Isto irá remover os ficheiros eliminados do cofre remoto para libertar espaço.

Após a limpeza ser sincronizada com o servidor, o Obsidian Sync deverá retomar o funcionamento normal.

### Criar um novo cofre remoto

Pode **criar um novo cofre remoto** para excluir ficheiros grandes antes de sincronizar. O histórico de versões dos seus ficheiros será reposto se criar um novo cofre remoto. Certifique-se de que não necessita do histórico de versões de ficheiros mais antigos antes de continuar.

Para sincronizar com um novo cofre remoto, siga estes passos:

1. Abra **[[Configurações]] → Sync**.
2. Seleccione **Gerir** junto a **Cofre remoto**.
3. Escolha **Criar novo cofre** e siga os passos para o criar. Se ficar sem cofres disponíveis, poderá ter de [[Configurar o Obsidian Sync#Disconnect from a remote vault|desligar]] do cofre remoto actual e [[Configurar o Obsidian Sync#Delete a remote vault|eliminá-lo]] primeiro.
4. Configure os ficheiros excluídos antes de iniciar a sincronização com o novo cofre remoto.
5. Reinicie o Obsidian para aplicar as suas alterações.
6. Abra **[[Configurações]] → Sync**.
7. Seleccione retomar para iniciar a sincronização com o novo cofre remoto.

O novo cofre remoto deverá ser mais pequeno do que o cofre anterior, devido à ausência de histórico de versões e de ficheiros excluídos.

## Actualizar o plano

Pode actualizar o seu plano iniciando sessão no [painel da sua conta](https://obsidian.md/account/sync). A partir daí, poderá actualizar o seu plano de Sync Standard para Sync Plus e aumentar o armazenamento até 100 GB.

## Reduzir o plano

Se pretender reduzir o seu plano do Sync, mas a sua utilização de armazenamento exceder o limite do novo plano, terá de libertar espaço no seu cofre remoto. Actualmente, não existe um método directo para remover rapidamente ficheiros específicos de um cofre remoto existente. Isto deve-se ao facto de os anexos serem conservados no histórico de versões até duas semanas, e o histórico de versões contar para o limite de armazenamento.

A forma mais rápida de reduzir a utilização do armazenamento do Sync é criar um novo cofre remoto com os anexos desactivados e, em seguida, eliminar o cofre remoto antigo que excede os limites de armazenamento. Tenha em atenção que perderá o histórico de versões ao fazê-lo.

Se estiver a reduzir do Sync Plus para o Sync Standard, também terá de reduzir o número de cofres para um antes de a redução ser permitida.

### Preservar o histórico de versões

Os anexos ficam retidos no seu [[Histórico de versões]] até duas semanas. Se planear reduzir o plano num futuro próximo, pode começar por remover os anexos do seu cofre local.

Após duas semanas, estes serão purgados do cofre remoto e deixarão de contar para o limite de armazenamento. Nessa altura, poderá reduzir o plano preservando o histórico de versões dos outros tipos de ficheiros, como os ficheiros Markdown.
