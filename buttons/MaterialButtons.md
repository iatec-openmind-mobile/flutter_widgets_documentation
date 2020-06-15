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

A propriedade `elevation` recebe um `double` que descreve a eleveção visual do botão em relação ao pano de fundo. O seu valor padrão é 2, o que é próprio para RaisedButton. Quanto maior o valor, mais elevado será o botão. Quando zero (0), o botão não terá elevação nenhum, como um FlatButton.

### `color` e `disabledColor`

### `shape`

### `textColor` e `textTheme`
