---
permalink: bases/views/map
---
Mapa é um tipo de [[Vistas|vista]] que pode usar em [[Introdução ao Bases|Bases]]. Requer a instalação do [plugin Maps](obsidian://show-plugin?id=maps).

Selecione ![[lucide-map.svg#icon]] **Map** no menu de vistas para apresentar ficheiros num mapa interativo com marcadores para cada ficheiro e uma pré-visualização que mostra as propriedades desse ficheiro.

![[bases-map-places.png#interface]]

## Instalar o plugin Maps

As vistas de mapa requerem o Obsidian 1.10. O [plugin Maps](obsidian://show-plugin?id=maps) é um [[Plugins da comunidade|plugin da comunidade]] oficial que pode descarregar separadamente.

1. Siga as instruções em [[Plugins da comunidade#Install a community plugin]]
2. Descarregue e ative o [Maps](obsidian://show-plugin?id=maps) a partir da lista

## Exemplo

Para começar, experimente criar uma nota chamada **Eiffel Tower** e copie as seguintes propriedades para ela:

```yaml
---
coordinates:
  - "48.85837"
  - "2.294481"
icon: "landmark"
color: "red"
tags:
  - places
---
```

Eis o que o código acima significa:

| Propriedade   | Valor                    |                                                                                                                                                      |
| ------------- | ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| `coordinates` | `48.85837`<br>`2.294481` | As coordenadas são armazenadas como `latitude, longitude`. Pode obter coordenadas clicando com o botão direito numa localização no mapa e selecionando **Copy coordinates**. |
| `icon`        | `landmark`               | O nome de um ícone da [biblioteca Lucide](https://lucide.dev/).                                                                                  |
| `color`       | `red`                    | Um valor CSS válido: hex, RGB, nome de cor, etc.                                                                                                       |
| `tags`        | `places`                 | A tag que usaremos para encontrar marcadores no mapa na nossa base.                                                                                   |

Agora crie uma vista de mapa com um filtro para a tag `places` e defina as coordenadas, ícone e cor dos marcadores usando as propriedades indicadas acima.

Também pode abrir estes [ficheiros de exemplo](https://github.com/obsidianmd/obsidian-maps/tree/master/examples) no Obsidian para ver vistas de mapa funcionais com marcadores, ícones e cores já configurados.

## Definições

As definições da vista de mapa podem ser configuradas nas [[Vistas#View settings|definições de vista]].

- Altura incorporada
- Coordenadas do centro
- Limites de zoom
- Coordenadas, cor e ícone dos marcadores
- Fundo

### Marcadores

#### Coordenadas

Para apresentar marcadores no mapa, vá às [[Vistas#View settings|definições de vista]] e selecione uma propriedade de **coordenadas do marcador**. A propriedade deve conter coordenadas de latitude e longitude. São aceites os seguintes formatos:

```yaml
# Propriedade de texto
coordinates: "lat, lng"

# Propriedade de lista
coordinates:
  - "lat"
  - "lng"
```

Se armazenar as coordenadas em propriedades `latitude` e `longitude` separadas, pode combiná-las com uma propriedade de [[Sintaxe de Bases#Formulas|fórmula]] definindo-a como um array de coordenadas com a seguinte fórmula: `[latitude, longitude]`.

#### Ícones

Adicione ícones aos marcadores definindo uma propriedade de **ícones de marcador**. Por exemplo, pode adicionar uma propriedade chamada `icon` às suas notas e dar-lhe valores como `landmark` ou `utensils` da [biblioteca Lucide](https://lucide.dev/icons/) integrada no Obsidian.

##### Usar uma fórmula para definir ícones

Suponha que quer que todos os restaurantes tenham o mesmo ícone no mapa:

1. Crie uma nota chamada **Restaurants** e adicione uma propriedade chamada `icon` com o valor `utensils`.
2. Dê às notas de restaurantes uma propriedade chamada `type` que ligue à nota `[[Restaurants]]`.
3. Adicione uma propriedade de fórmula chamada `Type icon` à sua base com o seguinte código:
	```js
	list(type)[0].asFile().properties.icon
	```
4. Escolha `Type icon` como ícone do marcador nas definições de vista.

Voilà! O seu mapa passará a apresentar ícones com base no *tipo* do local, não no próprio local.

#### Cores

Define a cor dos marcadores. Aceita valores como RGB `rgb(0,0,0)`, HEX `#000`, ou variáveis CSS como `var(--color-blue)`. Tal como no exemplo do ícone acima, pode usar uma propriedade de fórmula para definir cores dinamicamente.

### Fundo

#### Mosaicos do mapa

Os mosaicos de mapa são uma forma padrão de apresentar mapas digitais. Existem vários serviços que pode usar para personalizar mapas com estilos, cores e tipos de letra únicos. Os mapas suportam mosaicos raster e vetoriais, e aceitam a maioria dos URLs de mosaicos, incluindo URLs TileJSON.

O [OpenFreeMap](https://openfreemap.org/) oferece alguns estilos que pode usar gratuitamente. Experimente um dos seguintes URLs na definição **Map tiles**:

| Nome     | URL                                              |
| -------- | ------------------------------------------------ |
| Dark     | `https://tiles.openfreemap.org/styles/dark`      |
| Positron | `https://tiles.openfreemap.org/styles/positron`  |
| Liberty  | ``https://tiles.openfreemap.org/styles/liberty`` |

#### Ligações úteis

- [Maputnik](https://maputnik.github.io/) para personalizar mosaicos de mapa.
- [Protomaps](https://protomaps.com/) para alojar os seus próprios mosaicos de mapa.
- Outros serviços alojados com planos gratuitos incluem [MapTiler](https://www.maptiler.com/) e [Mapbox](https://www.mapbox.com/).


## Sugestões

Pode criar ligações para serviços de mapas populares usando [[Fórmulas]]. Por exemplo, o seu marcador pode mostrar uma ligação para o Google Maps com a seguinte fórmula:

```js
link("https://www.google.com/maps/search/" + file.name.replace(" ","+"),"Google Maps")
```

## Resolução de problemas

Se o mapa aparecer em branco quando carrega o plugin Maps pela primeira vez, experimente [[Atualizar o Obsidian|atualizar a versão do instalador do Obsidian]].

O [plugin Maps](https://github.com/obsidianmd/obsidian-maps) é open source. Pode ajudar contribuindo com relatórios de erros, pedidos de funcionalidades e pull requests.
