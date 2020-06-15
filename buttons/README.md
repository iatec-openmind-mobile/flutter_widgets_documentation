# Botões

O Flutter possui tipos diferentes de botões. Apesar de, em termos gerais, todos terem o mesmo objetivo final, é importante entender cada um separadamente e a diferença entre todos eles.

Farei a separação dos botões em duas categorias: (1) botões genéricos e (2) botões especiais.

## Botões Genéricos

Os botões genéricos têm um funcionamento similar. Todos eles fundamentam-se na ideia óbvia de que uma funcionalidade específica deve ser executada ao ser pressionado. Desta forma, faz sentido agrupá-los e descrever, primeiramente, o comportamento comum de todos.

O parâmetro que define o comportamento de um botão ao ser pressionado é o `onPressed`. Ele recebe um `VoidCallback`, isto é, uma função com a assinatura `void Function()`.

Exemplo de um botão que retorna à tela anterior da **stack** do Navigator:
```dart
RaisedButton(
	child: const Text('Voltar para a tela anterior'),
	onPressed: Navigator.of(context).pop,
);
```

Descrita a principal semelhança entre eles, considera-se que a diferença entre eles está, principalmente, em seu design, já que são implementações do Material. Portanto, essas diferenças vão ser documentadas na página individual de cada um deles.

São estes:

* Material buttons
  * RaisedButton
  * FlatButton
  * OutlineButton

![MaterialButtons](https://lh3.googleusercontent.com/WTxHKH2jzRSMpsFtwfL-FzlD2wpmFSclAEEx5x55hOpn4IaVcXuYg7DWk6ruqww8WCi-FOItzwz88LTMuTF_15zBTHxU22VCzvebDg=w1064-v0 "Material Buttons")

* IconButton

![IconButton](https://flutter.github.io/assets-for-api-docs/assets/material/icon_button.png "IconButton")

* FloatingActionButton (FAB)

![FloatActionButton](https://lh3.googleusercontent.com/No_ydlqwIpqgKAVQ-Y8CwDDvWJWYgnRIebYu3TzFM7FyFxOkKrMwWzDVhpoX-KMDssWcCP_n05a-2dr3zzw8xWeE4rsuFisw1r-ycw=w1064-v0 "Mateiral Floating Action Button")


## Botões Especiais

Os botões especiais são chamados dessa forma porque, em vez de ter o comportamento ao ser pressionado definido pelo `onClick`, possuem seu próprio contexto diferenciado.

São estes:

* ToggleButtons
* PopupMenuButton
* DropdownButton


## ButtonBar

Ainda relacionado com os botões, a widget ButtonBar pode ser usada como uma forma Material de agrupar botões.

* ButtonBar
