---
permalink: import/apple-notes
---
O Obsidian permite-lhe migrar facilmente as suas notas do Apple Notes utilizando o [[Importador|plugin Importer]]. Isto irá converter os seus dados do Apple Notes em ficheiros Markdown duradouros, que pode utilizar com o Obsidian e muitas outras aplicações.

Atualmente, o Importer apenas suporta a migração do Apple Notes no macOS. Ainda não está disponível para iOS.

## Importar dados do Apple Notes para o Obsidian

Precisará do plugin oficial do Obsidian [[Importador]], que pode [instalar aqui](obsidian://show-plugin?id=obsidian-importer).

1. Abra as **[[Configurações]]**.
2. Vá a **Plugins da comunidade** e [instale o Importer](obsidian://show-plugin?id=obsidian-importer).
3. Ative o plugin Importer.
4. Abra o plugin **Importer** utilizando a paleta de comandos ou o ícone da faixa de opções.
5. Em **Formato de ficheiro**, escolha **Apple Notes**.
6. Clique em **Importar**.
7. Clique em **Abrir** na janela de diálogo que aparecer com o título `Select the "group.com.apple.notes" folder to allow Obsidian to read Apple Notes data`.
8. Aguarde até que a importação esteja concluída.
9. Concluído!

## Conteúdo suportado

O plugin Importer do Obsidian suporta praticamente todos os tipos de conteúdo do Apple Notes. Isto inclui tabelas, imagens, desenhos, digitalizações, PDFs e ligações introduzidas no iOS 17.

> [!Warning]
> As notas protegidas por palavra-passe são encriptadas pela Apple e devem ser desbloqueadas antes de serem importadas. Quaisquer notas bloqueadas serão ignoradas.

### Digitalizações

A Apple armazena digitalizações em vários formatos consoante a forma como foram criadas. Para preservar os dados originais, estas serão exportadas de forma diferente.

* As digitalizações criadas ou visualizadas em versões mais antigas do macOS ou iOS serão exportadas como uma série de imagens não recortadas.
* As digitalizações criadas ou visualizadas em versões mais recentes do macOS ou iOS serão normalmente exportadas como imagens recortadas.
* As digitalizações que foram editadas com as funcionalidades introduzidas no iOS 17 serão normalmente exportadas como PDFs.

## Métodos de exportação alternativos

A Apple não fornece uma opção nativa para exportar as suas notas. No entanto, existem várias ferramentas de terceiros, como o [Exporter](https://apps.apple.com/us/app/exporter/id1099120373) de Chintan Ghate. Tenha em atenção que a maioria das ferramentas é limitada nos dados que exporta do Apple Notes e pode não fornecer os dados de saída mais compatíveis. Estas ferramentas funcionam melhor se as suas notas do Apple Notes forem principalmente só de texto e tiverem poucos anexos ou funcionalidades especiais como desenhos e digitalizações.

Dependendo da ferramenta utilizada, a exportação pode estar em formato Markdown ou HTML. Siga as instruções consoante o formato de ficheiro para o qual exportou:

- [[Importar ficheiros HTML]]
- [[Importar ficheiros Markdown]]
