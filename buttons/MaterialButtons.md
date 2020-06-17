# Material buttons

Provavelmente os três widgets de botões mais usados do Flutter são os três que se referem aos botões descritos pela especificação do Material, a saber, (1) FlatButton, (2) OutlineButton e (3) RaisedButton.

![MaterialButtons](https://lh3.googleusercontent.com/WTxHKH2jzRSMpsFtwfL-FzlD2wpmFSclAEEx5x55hOpn4IaVcXuYg7DWk6ruqww8WCi-FOItzwz88LTMuTF_15zBTHxU22VCzvebDg=w1064-v0 "Material Buttons")

Estes três botões derivam da mesma classe do Flutter, `MaterialButton`, e portanto têm comportamento muito semelhante, sendo diferenciados, primariamente, pelo estilo.

## Propriedades comuns

### `child`

A propriedade `child` é primordial, e define o que vai ter dentro do botão. Como ela recebe um `Widget`, o botão pode, literalmente, conter qualquer widget do Flutter. O mais comum é que contenha texto ou ícone.

![ButtonWithTextAndIcon](https://lh3.googleusercontent.com/yjRu3RjIQIYo-PKVttrdKCnQxYQOlK8kVBBPViZn8VZN35lxOPNaxR-WtmngQljhQ43EfZmCNDKcDL2fRa_KncKC3o7pzqpROfVt2uw=w1064-v0 "Material button with both text and icon")

### `onLongPress`

Além da propriedade `onPressed`, os `MaterialButton`s possuem a propriedade `onLongPress`. Ela funciona de forma muito semelhante ao `onPressed`, tendo inclusive a mesma assintaura. A única semelhança é, de fato, o tempo de pressionamento. Enquanto o `onPressed` vai detectar um _tap_ rápido, o `onLongPress` apenas será executado se o botão for pressionado por um período mais longo de tempo.

### `enabled`

A propriedade `enabled` recebe um `bool` e, como o nome sugere, determina se o botão está ativado. Um botão desativado não pode ser interagido e, por padrão, será desehado com uma cor desaturada.

> **Observação:** Caso pelo menos uma das propriedades `onPressed` e `onLongPress` não seja provida, o botão ficará desativado independente da propriedade `enabled`.

![StatesExample](https://lh3.googleusercontent.com/co_h3A-dzFtAtGK_LSIgJHcWbQFnmDMdoWcFAs4FLiTCY1yrYFlyDNLNJvBRq22kSjHzl1kMezx9irP0iOiUdagTKacmkwqL4PIOtQ=w1064-v0 "Exemplos dos possíveis estados de um Material button")

### `elevation`

A elevação é um [conceito fundamental no design do Material](https://material.io/design/environment/elevation.html), e não poderia ficar de fora de seus componentes.

![ElevationSample](https://lh3.googleusercontent.com/LA3KMKKDDN_gzLu73HQhPw5nyA_vvP3kMOZp4gcznbCCHbcCXgB5hjmmUxfzpoJfxpAWyq2eQvIpHjSQ0IrDhdnFHpwIJGFC6vHc=w1064-v0 "Exemplo de diferentes elevações no Material")

A propriedade `elevation` recebe um `double` que descreve a eleveção visual do botão em relação ao pano de fundo. O seu valor padrão é `2.0`, o que é próprio para RaisedButton. Quanto maior o valor, mais elevado será o botão. Quando zero (0), o botão não terá elevação nenhum, como um FlatButton.

### `color` e `disabledColor`

Como o nome sugere, as propriedades `color` e `disabledColor` recebem `Color`s para definir, respectivamente, a cor do botão quando em seu estado normal e quando desativado. Caso você queira seguir o padrão Material, não há necessidade de passar um `disabledColor`, já que o padrão cinza do Material será usado.

A propriedade `color`, por sua vez, terá como valor _default_ a cor do tema definido no seu `MaterialApp`, e caso passado um valor, sobreescreverá essa cor padrão do tema para a cor passada para a propriedade.

### `shape`

Em alguns casos, você não quer que seu botão tenha o formato padrão retangular. Por exemplo, o design abaixo usa o botão com as bordas circulares:

![CircleBorderButton](https://lh3.googleusercontent.com/zs0pAN0RKgDtNfdpdzr3zvhHK_lMOFcHeInh9_VpZO4qt2th5I3MPH5z7T56tp0Q9reVlCBHpVNYkfBkDdSai-VDRm5G_1wIT-Dg=w1064-v0 "Botão com bordas circulares")

Para isso que a propriedade `shape` existe. Ela recebe um [`ShapeBorder`](https://api.flutter.dev/flutter/painting/ShapeBorder-class.html) que definirá a forma do botão.

Os valores predefinidos mais comumente usados são:

* [CircleBorder](https://api.flutter.dev/flutter/painting/CircleBorder-class.html)
* [RoundedRectangleBorder](https://api.flutter.dev/flutter/painting/RoundedRectangleBorder-class.html)
* [ContinuousRectangleBorder](https://api.flutter.dev/flutter/painting/ContinuousRectangleBorder-class.html)
* [BeveledRectangleBorder](https://api.flutter.dev/flutter/painting/BeveledRectangleBorder-class.html)

### `textColor` e `textTheme`

Para estilizar o texto do botão, `textColor` e `textTheme` são o caminho. Enquanto o primeiro, obviamente, recebe um `Color` para sere usado como cor do texto do botão, o segundo recebe um `ButtonTextTheme` para lidar com as demais propriedades do texto. Vale lembrar que esses parâmetros não precisam ser necessariamente passadas, e caso não o sejam, será usado os valores padrões do tema do `MaterialApp`.

## O construtor especial `.icon`

Além do construtor normal dos botões, todos os três botões podem ser usados com o construtor `.icon()`. Os parâmetros desse construtor são as mesmas que a do construtor normal, com uma exceção: em vez de passar um `child`, nesse construtor é necessário passar um `icon` e um `label`.

Como supracitado, um padrão comum no material para botões é usar um ícone e um texto dentro do botão. Este construtor serve justamente para isso. No parâmetro `icon` pode ser passado uma widget para servir de ícone. Normalmente essa widget vai ser um `Icon`, mas pode ser qualquer coisa. Da mesma forma, o parâmetro `label` será usado como "texto" do botão, e comumente será  uma widget `Text`, mas pode ser qualquer outra.

## Exemplo

O seguinte exemplo cria um botão de compra como o da última figura, mas com um ícone.

```dart
RaisedButton.icon(
	icon: Icon(Icons.shopping_cart),
	label: Text('FINALIZAR COMPRA'),
	color: const Color(0xFF5D1049),
	shape: RoundedRectangleBorder(
		borderRadius: BorderRadius.circular(double.maxFinite),
	),
	onPressed: () => print('Botão pressionado!'),
	onLongPress: () => print('Botão pressionado por mais tempo!'),
),
```
