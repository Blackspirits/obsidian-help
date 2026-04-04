---
permalink: web-clipper/interpreter
---
O Interpretador é uma funcionalidade do [[Introdução ao Obsidian Web Clipper|Web Clipper]] que permite interagir com páginas web usando linguagem natural. O Interpretador ajuda-o a capturar e modificar dados que pretende guardar no Obsidian. Por exemplo:

- Extrair fragmentos de texto específicos.
- Resumir ou explicar informações.
- Converter texto de um formato para outro.
- Traduzir texto para um idioma diferente.

O Interpretador utiliza modelos de linguagem para processar informações numa página web e devolver resultados usando [[Variáveis]] que pode adicionar aos seus [[Obsidian Web Clipper/Modelos|modelos do Web Clipper]].

![[web-clipper-interpreter-demo.mp4#interface]]

## Exemplos de prompts

Os prompts usam a sintaxe de [[Variáveis|variável]] `{{"o seu prompt"}}`. Pode usar esta sintaxe com qualquer consulta em linguagem natural, por exemplo:

- `{{"um resumo da página"}}` para extrair um resumo da página.
- `{{"um resumo em três pontos, traduzido para francês"}}` para extrair pontos sobre a página e traduzi-los para francês.
- `{{"un resumé de la page en trois points"}}` para extrair três pontos usando um prompt em francês.

O resultado dos seus prompts pode ser manipulado com [[Filtros]]. Os filtros são processados depois de a resposta do prompt ser recebida do modelo. Por exemplo: `{{"um resumo da página"|blockquote}}` irá transformar a resposta numa citação.

## Começar a usar

O Interpretador funciona com quase qualquer fornecedor de modelos de linguagem, incluindo opções que correm de forma privada no seu dispositivo. Para configurar o Interpretador:

1. Aceda à secção **Interpretador** nas definições do Web Clipper.
2. Ative **Ativar Interpretador**.
3. Configure o seu fornecedor e modelo, consulte a secção de [[Interpretar páginas web#Models|modelos]] abaixo.
4. Adicione [[Variáveis|variáveis de prompt]] aos seus [[Obsidian Web Clipper/Modelos|modelos]].
5. Se o seu modelo incluir variáveis de prompt, a secção Interpretador ficará visível quando [[Capturar páginas web|capturar uma página]]. Clique em **interpretar** para processar as variáveis de prompt.

## Como funciona

Quando o Interpretador está ativado *e* o seu modelo contém [[Variáveis#Prompt variables|variáveis de prompt]], uma nova secção Interpretador é exibida na janela da extensão, acima do botão **Adicionar ao Obsidian**. Esta secção permite-lhe selecionar um modelo e executar o Interpretador para a página atual.

Quando clica em **interpretar**, o Interpretador envia o contexto da página para o modelo selecionado, juntamente com *todos* os prompts do seu modelo num único pedido. Dependendo do fornecedor de modelos que escolher, pode ser uma chamada externa ou local ao seu dispositivo. O modelo avalia os seus prompts em relação ao contexto da página e devolve as suas respostas. O Interpretador substitui então as variáveis de prompt pelos dados da resposta.

Todo o processo pode demorar milissegundos ou mais de 30 segundos, dependendo do modelo que usar e da quantidade de dados que está a processar.

## Contexto

O termo *contexto* refere-se aos dados da página que o Interpretador usa para processar prompts. Quanto menor for o contexto, mais rápido o Interpretador corre.

Por defeito, o Interpretador usa o HTML completo da página como contexto, no entanto isso pode tornar os prompts mais lentos e mais caros do que o necessário.

Pode substituir o contexto predefinido nas **Definições avançadas** do Interpretador e definir o contexto por [[Obsidian Web Clipper/Modelos|modelo]].

Para definir um contexto mais específico, use [[Variáveis#Selector variables|variáveis selector]] (ou outros tipos de variável) para interpretar uma secção da página. Por exemplo, pode usar a seguinte variável selector no contexto do Interpretador do seu modelo:

```
{{selectorHtml:#main}}
```

Isto executaria o Interpretador apenas no elemento `#main` de uma página web, se existir. Os [[Filtros#HTML processing|filtros de processamento HTML]] como `remove_html`, `strip_tags` e `strip_attr` podem ser úteis para reduzir ainda mais o comprimento do contexto e acelerar o processamento.

## Modelos

> [!warning] Privacidade
> Ao usar um fornecedor de modelos de terceiros, concorda com os seus termos e política de privacidade. Os pedidos do Interpretador são enviados diretamente para o fornecedor que escolher. O Obsidian não recolhe nem armazena quaisquer dados sobre os seus pedidos.

### Fornecedores predefinidos

O Interpretador inclui vários fornecedores predefinidos. Para usar estes fornecedores, precisa de uma chave API que pode obter ao iniciar sessão na conta do seu fornecedor. Também precisará de decidir qual(is) modelo(s) usar.

| Fornecedor         | Chave&nbsp;API                                              | Modelos                                                                              |
| ------------------ | ----------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Anthropic          | [Chave&nbsp;API](https://console.anthropic.com/settings/keys) | [Modelos](https://docs.anthropic.com/en/docs/about-claude/models)                  |
| Azure&nbsp;OpenAI  | [Chave&nbsp;API](https://oai.azure.com/portal/)             | [Modelos](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models) |
| DeepSeek           | [Chave API](https://platform.deepseek.com/api_keys)         | [Modelos](https://api-docs.deepseek.com/quick_start/pricing)                         |
| Google&nbsp;Gemini | [Chave&nbsp;API](https://aistudio.google.com/apikey)        | [Modelos](https://ai.google.dev/gemini-api/docs/models/gemini)                       |
| Hugging Face       | [Chave API](https://huggingface.co/settings/tokens)         | [Modelos](https://huggingface.co/models?pipeline_tag=text-generation&sort=trending)  |
| Meta               | [Chave API](https://llama.developer.meta.com)               | [Modelos](https://llama.developer.meta.com/docs/models)                              |
| Ollama             | n/d                                                         | [Modelos](https://ollama.com/search)                                                 |
| OpenAI             | [Chave&nbsp;API](https://platform.openai.com/api-keys)      | [Modelos](https://platform.openai.com/docs/models)                                   |
| OpenRouter         | [Chave&nbsp;API](https://openrouter.ai/settings/keys)       | [Modelos](https://openrouter.ai/models)                                              |
| Perplexity         | [Chave API](https://www.perplexity.ai/settings/api)         | [Modelos](https://docs.perplexity.ai/guides/model-cards)                             |
| xAI Grok           | [Chave API](https://console.x.ai/team/default/api-keys)     | [Modelos](https://docs.x.ai/docs/models)                                             |

### Escolher um modelo

Em geral, recomendamos o uso de modelos pequenos com o Web Clipper porque são mais rápidos e têm um desempenho razoavelmente preciso para esta tarefa. Exemplos de modelos menores incluem o **Claude Haiku da Anthropic**, o **Google Gemini Flash**, o **Llama** com parâmetros 3B ou 8B, ou a série de modelos **Mini da OpenAI**.

### Fornecedores e modelos personalizados

Para adicionar um fornecedor e/ou modelo personalizado, aceda às **[[Configurações]]** do Web Clipper → **Interpretador**:

- **Adicionar fornecedor** para configurar fornecedores predefinidos e personalizados.
- **Adicionar modelo** para configurar modelos predefinidos e personalizados.

Ao adicionar um fornecedor personalizado, recomendamos que use o endpoint de completions de chat para o **URL base** — normalmente termina com `/chat/completions`.

### Modelos locais

O Interpretador pode usar modelos locais que oferecem maior privacidade e compatibilidade offline. Existem várias opções para executar modelos locais. Uma das mais fáceis de configurar é o Ollama.

#### Ollama

O [Ollama](https://ollama.com/) permite executar modelos de linguagem localmente e de forma privada no seu dispositivo.

Depois de descarregar e instalar o Ollama, adicione o Ollama usando **Adicionar fornecedor** nas definições do Interpretador. O Ollama não requer uma chave API. Em seguida, escolha um modelo da [lista de modelos](https://ollama.com/search). Por exemplo, se pretender usar o [Llama 3.2](https://ollama.com/library/llama3.2), clique em **Adicionar modelo** e então:

- **Fornecedor:** Ollama
- **Nome de exibição:** Llama 3.2, este valor é personalizável.
- **ID do modelo:** `llama3.2`, deve corresponder exatamente ao ID do modelo do Ollama.

**Iniciar o servidor Ollama**

Para permitir que uma extensão de browser interaja com o Ollama, deve [dar-lhe uma instrução explícita](https://github.com/ollama/ollama/issues/2308) ao executar o servidor, caso contrário verá um erro `403`.

Feche a aplicação Ollama e execute o seguinte comando no seu terminal. O protocolo deve ser alterado para o protocolo de extensão do seu browser se não usar o Chrome ou Firefox.

```
OLLAMA_ORIGINS=moz-extension://*,chrome-extension://*,safari-web-extension://* ollama serve
```

Em seguida, execute o seu modelo com o Ollama da forma normal, por exemplo:

```
ollama run llama3.2
```

**Comprimento do contexto**

A janela de contexto do Ollama tem por defeito 2048 tokens. Este é o número máximo de tokens para a mensagem e resposta. Ao capturar uma página web longa, pode facilmente ultrapassar este limite. O Ollama irá falhar silenciosamente e devolver resultados irrelevantes. Algumas opções:

- Aumente o parâmetro `num_ctx` do Ollama. Tenha em atenção que um contexto mais longo requer mais memória.
- Use o campo [[#Context|Contexto]] no seu modelo para fornecer uma secção mais específica da página, ou reduza o contexto usando um [[Filtros|filtro]], por exemplo `{{content|slice:0,1000}}`.
