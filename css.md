# CSS

### O que é CSS(Cascading Style Sheets) e qual sua utilidade?

O CSS, assim como o HTML, é uma linguagem. Ele difere das demais por definir a forma como os dados escritos em uma linguagem de marcação serão apresentados. No decorrer dos anos muitas mudanças foram feitas no CSS para suprir a necessidade crescente dos desenvolvedores web. Ela foi feita com o objetivo de separar o ceunteúdo de uma página da forma como este conteúdo será apresentada para os visitantes. Por meio do CSS é possível customizar cores, fontes, posições, e outros. Antes do CSS, para customizar uma página web era comum utilizar o atributo `style=""` do HTML, mas logo foi possível notar que esse atributo não era o suficiente. Ao separar os arquivos CSS aumentamos a flexibilidade e o controle das páginas além de permitir compartilhamento do estilos para diferentes partes do seu site.

### Histórico

A primeira versão do CSS foi lançada em 1994. Como não havia nenhuma forma de estilizar documentos Håkon Wium Lie achou que seria útil criar um linguagem capaz de solucionar o problema. Na época, a idéia de separar conteúdo de estrutura não era uma idéia tão inovadora. Tim Berners-Lee escreveu seu navegador NeXT de forma que ele poderia determinar os estilos pelo style Sheets. Um fato curioso é que o mesmo não publicou a sintaxe e deixou que cada browser apresentasse a estrutura da forma que o desenvolvedor daquele browser achasse melhor. Todos os browsers daquela época limitavam a estilização das páginas. Em 1993 quando o Mosaic foi lançado ele só permitia a mudaça de cor e alguns aspectos das fontes. Em 1994 Marc Andreessen anunciou que o primeiro beta do Mozila (que acabou se tornando o NetScape) estava aberto para teste. Esse navegador veio com tags que até então não eram conhecidas.

Tres dias antes desse acontecimento Håkon publicou um artigo sobre [Cascading HTML Style Sheets](http://www.w3.org/People/howcome/p/cascade.html). O CSS se destacava em relação aos demais concorrentes pois ele levava em conta tanto aquilo que o autor queria fazer quanto as capacidades to dispositivo e do browser que estavam sendo utilizados para "rodar" o CSS. Ao fim de 1995 a W3C aprovou o HTML Editorial Review Board (HTML ERB) para ratificar o futuro das especificações HTML. Na mesma época, como o interesse no CSS por parte dos membros do grupo cresceu, a especificação do CSS foi trabalhada para se tornar uma recomendação. Quando a microsoft sinalizou que iria adicionar supotre ao CSS em seu browser IE3(Internet Explorer 3) o sucesso do CSS aumentou consideravelmente. Foi ai que a Netscape começou a pensar em aceitar o CSS em seus navegadores. Ela implementou seu o CSS internamente transformando regras CSS em pedaços de código Javascript que depois seriam executado juntamente a scripts. Além disso ela deicidiu deixar desenvolvedores escreverem [JSSS](http://www.w3.org/Submission/1996/1/WD-jsss-960822) como forma de evitar que os desenvolvedores escrevessem CSS. Em 1996 foi lançada a primeira recomendação do CSS 1. 

https://en.wikipedia.org/wiki/Cascading_Style_Sheets
http://www.w3.org/People/howcome/p/cascade.html
http://www.w3.org/Style/LieBos2e/history/
http://www.w3.org/Submission/1996/1/WD-jsss-960822
http://www.w3schools.com/css/

### Especificidade

### O que são seletores?

### Como seletores são interpretados?

selector::pseudo-element {
    property:value;
}

### Seletores CSS

### O que são Id's?

### Classes

```
.nomeDaClasse {
  
}
```

### Tags

```
.nomeDaTag {
  
}
```

### Não use ID's como seletor

### Propriedades

##### Color

A cor dos elementos pode ser escrita usando o nome da cor. O problema é que dessa forma temos um número muito pequeno de possíveis cores. Para aumentar a diversidades de cores podemos utilizar o valor rgb daquela cor ou o valor hexadecimal.

```
p {
	color: red;
}
```

```
p {
	color: rgb(255,0,0);
}
```

```
p {
	color: #FF0000;
}
```

##### Background

+ Background Color

  + Como o próprio nome diz, essa propriedade define a cor do background daquele elemento. Assim  como na propriedade `color` podemos especificar a cor usando um nome válido, um valor hexadecimal, ou o RGB correspondente.

```
body {
	background-color: pink;
}
```

+ Background Image

  + Essa propriedade define uma imagem para ser usada como plano de fundo do elemento selecionado.

```
body {
	background-image: url("path.jpg");
}
```

##### Width

Essa propriedade define o width de um elemento. Ela pode assumir diferentes valores como por exemplo: auto, length, initial, inherit. Quando usamos auto o browser calcula o width do elemento. Length corresponde a passar o tamanho do width, seja com pixels, ems, ou porcentagens. Initial utiliza o valor igual ao default daquele elemento. Inherit faz aquele elemento herdar o width do elemento pai.

```
img {
	width: 100px;
}
```

```
img {
	width: 10em;
}
```

```
img {
	width: 50%;
}
```

##### Height

Essa propriedade é similar ao width. A diferença é que, enquanto o width define da largura do elemento a propriedade height define a altura do elemento. Com relação aos valores que o height pode assumir são exatamente os mesmos que o widht.

```
img {
	height: 100px;
}
```

```
img {
	height: 10em;
}
```

```
img {
	height: 50%;
}
```


##### Margin

Essa propriedade é usada para definir o espaço ocupado pelo elemento fora de sua borda. Não confunda ela com a propriedade `padding` que define o espaço ocupado pelo elemento dentro de sua borda. Ambos os exemplos abaixo causam o mesmo efeito ao documento.

```
p {
  margin: 10px 20px 30px 40px;
}
```

```
p {
  margin-top: 10px; 
  margin-right: 20px;
  margin-bottom: 30px;
  margin-left: 40px;
}
```

##### Padding

Essa propriedade gera um espaço entre o conteúdo do elemento e sua borda. Assim como na `margin` podemos utiliza-la de diferentes formas.

```
p {
  padding: 10px 20px 30px 40px;
}
```

```
p {
  padding-top: 10px;
  padding-right: 20px;
  padding-bottom: 30px;
  padding-left: 40px;
}
```

##### Border

A propriedade da borda permite que seja especificado o estilo, o tamanho e a cor da borda do elemento

```
p {
  border: 2px solid green;
}
```

```
p {
  border-width: 2px;
  border-style: solid;
  border-color: green;
}
```

##### Text 

+ Text Color

  + Define a cor de um elemento.

```
body {
  color: green;
}
```

+ Text Align
  
  + Um texto pode estar alinhado com o centro (center), com as bordas (right/left), ou pode estar definido para que suas linhas ocupem exatamente o mesmo tamanho (justified).

```
h3 {
  text-align: justify;
}
```

+ Text Decoration

  + Vários elementos HTML vem com estilos predefinidos. Dentre eles, um dos mais irritantes para desenvolvedores novatos é o text-decoration de elementos como por exemplo links. Aqueles underlines raramente são necessários e por isso é possível se livrar deles da seguinte forma:

```
a {
  text-decoration: none;
}
```

  Além de tirá-lo é possível substituí-lo por outros estilos que se adequam `a situação. Seguem exemplos uteis:

```
h1 {
  text-decoration: overline;
  text-decoration: underline;
  text-decoration: line-through;
}
```

##### Fonts

Podemos serparar os tipos de fontes basedo nas generic families das fontes. As usadas são as Serifs, as Monospace, e as Sans-serifs. As propriedades que cuidam das fontes do css se chamam `font-family` e `font-style` e elas pode ser usadas da seguinte forma:

```
body {
  font-family: "Times New Roman", Times, serif;
  font-style: italic;
}
```

Obs: Existem outras propriedades que não cobrimos aqui.

##### Position

A propriedade `position` indica que tipo de posicionamento foi usado para ajustar o elemento. Existem quatro tipos de posicionamento. O primeiro é o posicionamento estático, ou seja, dizemos exatamente onde queremos que o elemento apareça na tela. Existe também o posicionamento relativo cujo elemento será posicionado de acordo com sua posição natural. Quando posicionamos um elemento usando posicionamento fixo o mesmo é posicionado em relação ao viewport, ou seja, independente se o usuário planeja dar scroll na página aquele elemento será mostrado sempre no mesmo local do viewport. Um exemplo de situação em que esse tipo de posicionamento é usado é em navigations fixas. Por ultimo temos o posicionamento absoluto. Nele o elemento com posicionamento absoluto é posicionado relativo ao elemento pai.

```
div {
  position: static;
  position: relative;
  position: fixed;
  position: absolute;
}
```

##### Float

A propriedade float permite que um elemento flutue para uma determinada posição. Quando usamos `float: left;` o elemento flutua para esquerda da página. O oposto ocorre ao usarmos `float: right;`. Muitas vezes é interessante o uso do `clear:` para corrigir comportamentos de alguns elementos que flutuam. Essa propriedade define qual lado daquele elemento não permite que outros elementos flutuem. Outra tática que é usada para solucionar problemas relacionados a floats é  usar a propriedade `overflow: auto` para impedir que elementos maiores do que aqueles que os contém saiam das bordas do elemento pai. A seguir são mostrados exemplos de todas essas propriedades faladas:

```
div {
  float: right;
}

div {
  clear: left;
}

.clearfix {
  overflow: auto;
}
```

##### Display

O Display de um elemento especifica como aquele elemento será mostrado na página. Elementos a nível de bloco começam no inicio da um linha e ocupam todo o width possível até o final daquela mesma linha. Elementos a nível de bloco não começam no início da linha e tomam apenas o espaço necessário.

```
li {
  display: inline;
}

img {
  display: block;
}

p {
  display: none;
}
```

+ Inline-block

  + É essecial que seja entendido o conceito dessa propriedade. Elementos que utilizar ela são como elementos inline mas eles possuem width e height. Essa propriedade soluciona um dos mais comuns problemas no desenvolvimento web, a falta de grids por padrão.

```
.float-elem {
  display: inline-block;
  width: 100px;
  height: 50px;
  margin: 10px;
}
```

### Pseudo-class

As pseudo-classes são usadas para estilizar os elementos baseados em ações que foram realizadas naquele mesmo elemento. A sintaxe segue o seguinte padrão:

```
selector:pseudo-class {
    property:value;
}
```

É comum usamos as pseudo-classes em elementos como links, veja o exemplo:

```
a:visited {
  ... aqui colocamos o estilo do link 
  depois que ele foi visitado ...
}

a:link {
  ... aqui colocamos o estilo do link 
  antes dele ser visitado ...
}

a:hover {
  ... aqui colocamos o estilo do link 
  quando o mouse estiver em cima dele ...
}
```

### Pseudo-element

Os pseudo-elementos são usados com menos frequência que as pseudo-classes, mas podem ser muito úteis. A sintaxe deles é semelhante a sintaxe das pseudo-classes. Segue um exemplo:

```
selector::pseudo-element {
    property:value;
}
```

Note que entre o seletor e o pseudo-elemento temos `::` diferente das pseudo-classes onde temos `:`. Os próximos exemplos mostram alguns pseudo-elementos úteis:

```
p::before {
  
}

p::after {
  
}

p:first-child { 

}

p:nth-child(2) {

}
```

# CSS3

##### Borders

+ Border Radius

If you specify only one value for the border-radius property, this radius will be applied to all 4 corners.

Four values: first value applies to top-left, second value applies to top-right, third value applies to bottom-right, and fourth value applies to bottom-left corner
Three values: first value applies to top-left, second value applies to top-right and bottom-left, and third value applies to bottom-right
Two values: first value applies to top-left and bottom-right corner, and the second value applies to top-right and bottom-left corner
One value: all four corners are rounded equally

border-radius: 10px 10px 10px 10px;
border-radius: 10px 10px 10px;
border-radius: 10px 10px;
border-radius: 10px;

+ Border Image

With the CSS3 border-image property, you can set an image to be used as the border around an element.

The CSS3 border-image property allows you to specify an image to be used instead of the normal border around an element.

The property has three parts:

The image to use as the border
Where to slice the image
Define whether the middle sections should be repeated or stretched

```
#borderimg {
    -webkit-border-image: url(border.png) 30 round; /* Safari 3.1-5 */
    -o-border-image: url(border.png) 30 round; /* Opera 11-12.1 */
    border-image: url(border.png) 30 round;
}
```

```
#borderimg {
    -webkit-border-image: url(border.png) 30 stretch; /* Safari 3.1-5 */
    -o-border-image: url(border.png) 30 stretch; /* Opera 11-12.1 */
    border-image: url(border.png) 30 stretch;
}
```

##### Color

RGBA color values are an extension of RGB color values with an alpha channel - which specifies the opacity for a color.

An RGBA color value is specified with: rgba(red, green, blue, alpha). The alpha parameter is a number between 0.0 (fully transparent) and 1.0 (fully opaque).

 #p1 {background-color: rgba(255, 0, 0, 0.3);}  /* red with opacity */

##### Gradients

CSS3 gradients let you display smooth transitions between two or more specified colors.

Earlier, you had to use images for these effects. However, by using CSS3 gradients you can reduce download time and bandwidth usage. In addition, elements with gradients look better when zoomed, because the gradient is generated by the browser.

CSS3 defines two types of gradients:

Linear Gradients (goes down/up/left/right/diagonally)
Radial Gradients (defined by their center)

Linear Gradients
To create a linear gradient you must define at least two color stops. Color stops are the colors you want to render smooth transitions among. You can also set a starting point and a direction (or an angle) along with the gradient effect.

Syntax
background: linear-gradient(direction, color-stop1, color-stop2, ...);

Linear Gradient - Top to Bottom (this is default)
 #grad {
    background: red; /* For browsers that do not support gradients */
    background: -webkit-linear-gradient(red, yellow); /* For Safari 5.1 to 6.0 */
    background: -o-linear-gradient(red, yellow); /* For Opera 11.1 to 12.0 */
    background: -moz-linear-gradient(red, yellow); /* For Firefox 3.6 to 15 */
    background: linear-gradient(red, yellow); /* Standard syntax */
}

Linear Gradient - Left to Right
 #grad {
  background: red; /* For browsers that do not support gradients */
  background: -webkit-linear-gradient(left, red , yellow); /* For Safari 5.1 to 6.0 */
  background: -o-linear-gradient(right, red, yellow); /* For Opera 11.1 to 12.0 */
  background: -moz-linear-gradient(right, red, yellow); /* For Firefox 3.6 to 15 */
  background: linear-gradient(to right, red , yellow); /* Standard syntax */
}

##### Shadows

##### Text

##### Font

##### Transform

##### Transition

##### Animation

##### Image

##### Resizing

### Media Query

### Flex-box

Flexible boxes, or flexbox, is a new layout mode in CSS3.

Use of flexbox ensures that elements behave predictably when the page layout must accommodate different screen sizes and different display devices.

For many applications, the flexible box model provides an improvement over the block model in that it does not use floats, nor do the flex container's margins collapse with the margins of its contents.


### OOCSS

	Separar estrutura e skin
		Repetir caracteristica visual como skin que pode ser combinada em uma variada gama de objetos por exemplo background e estilos de borda
	Separar container de conteúdo
		Um objeto deve permanecer igual independente da sua localizacao na pagina, ou seja, nao queremos que as classes pai do css influenciem as classes filho

### SMACSS

### BEM
