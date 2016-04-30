# SVG

### O que é SVG (Scalable Vector Graphics) e qual sua utilidade?

SVG é a abreviatura de Scalable Vector Graphics. Ela é uma linguagem baseada em XML cujo objetivo é descrever de forma vetorial desenhos e gráficos bidimensionais, quer de forma estática, quer dinâmica ou animada. Umas das principais características que faz com que esses gráficos sejam tão usados é que eles não perdem qualidade ao serem ampliados. 

### Histórico

O SVG foi desenvolvido em 1999 pela World Wide Web Consortium. A idéia é que além de proporcionar gráficos escaláveis, estes fossem fáceis de ler, ou seja, legíveis. Podemos ler o código svg em qualquer editor assim como editá-lo, mas o comum é usarmos um software que gere esse código para nós, dessa forma não perdemos tempo pensando em contas que o computador pode fazer por nós. Softwares famosos de desenho que utilizam esse formado são o Adobe Illustrator e Inkscape.

### Por que devemos aprender sobre SVG se existem programas que geram eles?

O principal foco desse breve tutorial é mostrar como podemos fazer animações interesantes conhecendo a base de como funciona essa linguagem. Ela permite que o usuário "programe" através de uma linguagem de script, ou seja, podemos usar a programação para ganharmos dinamicidade em nossos desenhos. Os SVGs apresentam algumas vantagens dependendo de onde for aplicado. A primeira é que ele pode ser editado em qualquer editor de texto, ele também pode ser comprimido. Como dito anteriormente, quando aumentamos uma imagem SVG ela não perde qualidade garantindo, assim, que impressões de imagens SVG saiam com ótimo qualidade. Justamente por esse ultimo motivo os SVG são populares em logos de empresas.


### Sintaxe 

As imagens SVG podem ser utilizadas de diferentes formas. A primeira delas seria colocar o SVG dentro do código HTML, chamamos isso de embeded SVG, segue um exemplo:

```
<!DOCTYPE html>
<html>
<body>

<svg></svg>

</body>
</html>
```

Podemos também adicionar SVG como `<img>`, segue o exemplo:

```
<!DOCTYPE html>
<html>
<body>

<img src="nome_da_imagem.svg"></img>

</body>
</html>
```

Outra opção é usá-lo como background-image

```
HTML

<!DOCTYPE html>
<html>
<body>

<a href="#" class="logo">Imagem</a>

</body>
</html>

CSS

.logo {
  background: url(nome_da_imagem.svg);
}
```

### Shapes

```
<!DOCTYPE html>
<html>
<body>
<h1>My first SVG</h1>
<svg width="100" height="100">
  <circle cx="50" cy="50" r="40" stroke="green" stroke-width="4" fill="yellow" />
</svg>
</body>
</html>
```

SVG Code explanation:
An SVG image begins with an <svg> element
The width and height attributes of the <svg> element define the width and height of the SVG image
The <circle> element is used to draw a circle
The cx and cy attributes define the x and y coordinates of the center of the circle. If cx and cy are omitted, the circle's center is set to (0, 0)
The r attribute defines the radius of the circle
The stroke and stroke-width attributes control how the outline of a shape appears. We set the outline of the circle to a 4px green "border"
The fill attribute refers to the color inside the circle. We set the fill color to yellow
The closing </svg> tag closes the SVG image

SVG Shapes
SVG has some predefined shape elements that can be used by developers:
Rectangle <rect>
Circle <circle>
Ellipse <ellipse>
Line <line>
Polyline <polyline>
Polygon <polygon>
Path <path>

SVG Rectangle - <rect>
<svg width="400" height="110">
  <rect width="300" height="100" style="fill:rgb(0,0,255);stroke-width:3;stroke:rgb(0,0,0)" />
</svg>

SVG Circle - <circle>
<svg height="100" width="100">
  <circle cx="50" cy="50" r="40" stroke="black" stroke-width="3" fill="red" />
</svg>
The cx and cy attributes define the x and y coordinates of the center of the circle. If cx and cy are omitted, the circle's center is set to (0,0)
The r attribute defines the radius of the circle

SVG Line - <line>
The <line> element is used to create a line:
<svg height="210" width="500">
  <line x1="0" y1="0" x2="200" y2="200" style="stroke:rgb(255,0,0);stroke-width:2" />
</svg>

SVG <polygon>
SVG Polygon - <polygon>
The <polygon> element is used to create a graphic that contains at least three sides.
Polygons are made of straight lines, and the shape is "closed" (all the lines connect up).
<svg height="210" width="500">
  <polygon points="200,10 250,190 160,210" style="fill:lime;stroke:purple;stroke-width:1" />
</svg>

SVG <path>
SVG Path - <path>
The <path> element is used to define a path.
The following commands are available for path data:
M = moveto
L = lineto
H = horizontal lineto
V = vertical lineto
C = curveto
S = smooth curveto
Q = quadratic Bézier curve
T = smooth quadratic Bézier curveto
A = elliptical Arc
Z = closepath
Note: All of the commands above can also be expressed with lower letters. Capital letters means absolutely positioned, lower cases means relatively positioned.
Example 1
The example below defines a path that starts at position 150,0 with a line to position 75,200 then from there, a line to 225,200 and finally closing the path back to 150,0:
<svg height="210" width="400">
  <path d="M150 0 L75 200 L225 200 Z" />
</svg>
Example 2
Bézier curves are used to model smooth curves that can be scaled indefinitely. Generally, the user selects two endpoints and one or two control points. A Bézier curve with one control point is called a quadratic Bézier curve and the kind with two control points is called cubic.
The following example creates a quadratic Bézier curve, where A and C are the start and end points, B is the control point:
<svg height="400" width="450">
  <path id="lineAB" d="M 100 350 l 150 -300" stroke="red"
  stroke-width="3" fill="none" />
  <path id="lineBC" d="M 250 50 l 150 300" stroke="red"
  stroke-width="3" fill="none" />
  <path d="M 175 200 l 150 0" stroke="green" stroke-width="3"
  fill="none" />
  <path d="M 100 350 q 150 -300 300 0" stroke="blue"
  stroke-width="5" fill="none" />
  <!-- Mark relevant points -->
  <g stroke="black" stroke-width="3" fill="black">
    <circle id="pointA" cx="100" cy="350" r="3" />
    <circle id="pointB" cx="250" cy="50" r="3" />
    <circle id="pointC" cx="400" cy="350" r="3" />
  </g>
  <!-- Label the points -->
  <g font-size="30" font-family="sans-serif" fill="black" stroke="none"
  text-anchor="middle">
    <text x="100" y="350" dx="-30">A</text>
    <text x="250" y="50" dy="-10">B</text>
    <text x="400" y="350" dx="30">C</text>
  </g>
</svg>

SVG Stroke Properties
SVG Stroke Properties
SVG offers a wide range of stroke properties. In this chapter we will look at the following:
stroke
stroke-width
stroke-linecap
stroke-dasharray
All the stroke properties can be applied to any kind of lines, text and outlines of elements like a circle.
SVG stroke Property
The stroke property defines the color of a line, text or outline of an element:
<svg height="80" width="300">
  <g fill="none">
    <path stroke="red" d="M5 20 l215 0" />
    <path stroke="black" d="M5 40 l215 0" />
    <path stroke="blue" d="M5 60 l215 0" />
  </g>
</svg>
SVG stroke-width Property
The stroke-width property defines the thickness of a line, text or outline of an element:
<svg height="80" width="300">
  <g fill="none" stroke="black">
    <path stroke-width="2" d="M5 20 l215 0" />
    <path stroke-width="4" d="M5 40 l215 0" />
    <path stroke-width="6" d="M5 60 l215 0" />
  </g>
</svg>
SVG stroke-linecap Property
The stroke-linecap property defines different types of endings to an open path:
<svg height="80" width="300">
  <g fill="none" stroke="black" stroke-width="6">
    <path stroke-linecap="butt" d="M5 20 l215 0" />
    <path stroke-linecap="round" d="M5 40 l215 0" />
    <path stroke-linecap="square" d="M5 60 l215 0" />
  </g>
</svg>
SVG stroke-dasharray Property
The stroke-dasharray property is used to create dashed lines:
<svg height="80" width="300">
  <g fill="none" stroke="black" stroke-width="4">
    <path stroke-dasharray="5,5" d="M5 20 l215 0" />
    <path stroke-dasharray="10,10" d="M5 40 l215 0" />
    <path stroke-dasharray="20,10,5,5,5,10" d="M5 60 l215 0" />
  </g>
</svg>


___

# SVG Line Animation (Drawing Effects)

Comaçamos criando uma logo no Adobe Illustrator. As imagens são bem auto explicativas então pretendo comentar apenas o essencial.

Salve como SVG
Abre uma janela SVG Options
CSS Properties -> Style Elements
SVG Code

Abra o SVG usando o editor de texto
Colocamos a embeded tag agora
Usamos a tag `<object>` que permite que adicionemos objetos dentro do nosso HTML. Isso nos possibilita adicionar elementos como video, Java applets, SVGs, e Flash.
No nosso caso adicionamos um SVG, e para isso usamos a tag `<embed>` que define um container para nossa applicação externa.

```
<body>
	<object>
		<embed src="path_da_imagem.svg">
	</object>
</body>
```

Quando olhamos nosso arquivo em um editor de texto notamos algumas coisas desnecessárias. Uma delas aparece logo no início do arquivo em:

```
<?xml version="1.0" encoding="iso-8859-1"?>
<!-- Generator: Adobe Illustrator 17.0.0, SVG Export Plug-In . SVG Version: 6.00 Build 0)  -->
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">
```

Podemos nos livrar dessas linhas. Um aspecto interessante é que podemos usar uma tag `<defs>` que permite que elementos gráficos definidos dentro dela não serão diretamente renderizados. Usamos ela pois dentro dessa tag vamos colocar elementos de animação.

```
<svg>
	<defs>
		<style>
		</style>
	</defs>
</svg>
```

Outro detalhe é a tag `<g></g>` que o ilustrador gera. Ela indica os grupos de layers do seu desenho.
Como vimos anteriormente, SVG é baseado em XLM. Nas tags do SVG podemos adicionar propriedades muito parecidas com a que usamos em html e css. Segue o exemplo:

```
<path id="logo_bom">
	
</path>
```

Ao adicionamos o id à nossa tag podemos referenciá-la sem maiores problemas. Agora que temos o acesso ao elemento que queremos manipular podemos fazer o seguinte:

```
<style>
	#logo_bom {
		stroke-dasharray: 800;
		stroke-dashoffset: 0;
	}
</style>
```

O legal é que ganhamos novas propriedades CSS para manipular a imagem SVG. 

A primeira delas é a `stroke-dasharray`. Essa propriedade controla o padrão de traços e vazios no nosso stroke. É mais facil entender vendo um exemplo de como o código funciona. Vamos pensar no SVG.

```
<line stroke-dasharray="5, 5" x1="10" y1="10" x2="190" y2="10" />
```

Nesse exemplo temos um stroke que a cada 5 pixels aparece e desaparece dando aquele efeito tracejado. Os outros paremetros especificam onde o stroke começa (x1 e y1), e onde o stroke acabada (x2, y2). 

A segunda propriedade foi a `stroke-dashoffset` especifica a distancia do inicio do traço até que o local onde o padrão especificado no dasharray começou.

Dando continuidade ao nosso exemplo temos:

```
<style type="text/css">
  #logo_bom {
    stroke-dasharray: 800;
    stroke-dashoffset: 0;
    -webkit-animation: dash 2s linear forwards;
    -o-animation: dash 2s linear forwards;
    -moz-animation: dash 2s linear forwards;
    animation: dash 2s linear forwards;
  }

  @-webkit-keyframes dash {
    from {
      stroke-dashoffset: 800;
    }
    to {
      stroke-dashoffset: 0;
    }
  }
</style>
```

Para tornar a imagem responsiva temos que deletar a seguinte parte do nosso svg:

```
<svg width="..." height="...">
```

Temos que adicionar o width e o height de algumar forma. Fazemos isso no próprio HTML.

```
<body>
  <object>
    <embed src="path_da_imagem.svg" width="...%" height="...%">
  </object>
</body>
```

##### Manipulando SVG

bla

```
#id_svg:hover .str0 {
  fill: #000;
}
```

bla

```
.str0 {
  fill: #fff;
}

#id_svg:hover .str0 {
  fill: #000;
  transition: 2s;
}
```