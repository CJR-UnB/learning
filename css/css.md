# CSS

### O que é CSS (Cascading Style Sheets) e qual sua utilidade?

O CSS, assim como o HTML, é uma linguagem. Ele difere das demais por definir a forma como os dados escritos em uma linguagem de marcação serão apresentados. No decorrer dos anos muitas mudanças foram feitas no CSS para suprir a necessidade crescente dos desenvolvedores web. Ela foi feita com o objetivo de separar o conteúdo de uma página da forma como este conteúdo era apresentado para os visitantes. Por meio do CSS é possível customizar cores, fontes, posições, e outros. Antes do CSS, era possível customizar fontes e cores usando o atributo `style=""` do HTML, mas foi notado que esse atributo não era o suficiente para suprir as necessidades dos desenvolvedores pois eles teriam que repetir muito código para customizar uma página. Se quiséssemos 2 títulos com cor vermelha teríamos que entrar no HTML e adicionar o mesmo código para cada um dos títulos. O atributo surgiu na versão 3.2 do HTML juntamente com o termo Web Designer. Ao separar os arquivos CSS aumentamos a flexibilidade e o controle das páginas além de permitir compartilhamento do estilos para diferentes partes do seu site.

### Histórico

A primeira versão do CSS foi lançada em 1994. Como não havia nenhuma forma de estilizar documentos Håkon Wium Lie achou que seria útil criar um linguagem capaz de solucionar o problema. Na época, a idéia de separar conteúdo de estrutura não era uma idéia tão inovadora. Tim Berners-Lee escreveu seu navegador NeXT de forma que ele poderia determinar os estilos pelo Style Sheets. Um fato curioso é que Tim não publicou a sintaxe e deixou que cada browser apresentasse a estrutura da forma que o desenvolvedor daquele browser achasse melhor. Todos os browsers daquela época limitavam a estilização das páginas. Em 1993 quando o Mosaic foi lançado ele só permitia a mudaça de cor e alguns aspectos das fontes. Em 1994 Marc Andreessen anunciou que o primeiro beta do Mozila (que acabou se tornando o NetScape) estava aberto para teste. Esse navegador veio com tags que até então não eram conhecidas.

Três dias antes desse acontecimento Håkon publicou um artigo sobre [Cascading HTML Style Sheets](http://www.w3.org/People/howcome/p/cascade.html). O CSS se destacava em relação aos demais concorrentes pois ele levava em conta tanto aquilo que o autor queria fazer quanto as capacidades do dispositivo e do browser que estavam sendo utilizados para "rodar" o CSS. Ao fim de 1995 a W3C aprovou o HTML Editorial Review Board (HTML ERB) para ratificar o futuro das especificações HTML. Na mesma época, como o interesse no CSS por parte dos membros do grupo cresceu, a especificação do CSS foi trabalhada para se tornar uma recomendação. Quando a microsoft sinalizou que iria adicionar suporte ao CSS em seu browser IE3(Internet Explorer 3) o sucesso do CSS aumentou consideravelmente. Foi ai que a Netscape começou a pensar em aceitar o CSS em seus navegadores. Ela implementou seu o CSS internamente transformando regras CSS em pedaços de código Javascript que depois seriam executado juntamente a scripts. Além disso ela deicidiu deixar desenvolvedores escreverem [JSSS](http://www.w3.org/Submission/1996/1/WD-jsss-960822) como forma de evitar que os desenvolvedores escrevessem CSS. Em 1996 foi lançada a primeira recomendação do CSS 1. 

##### Links Complementares

[História do CSS](http://www.w3.org/Style/LieBos2e/history/)

### Sintaxe 

Uma regra no CSS consiste em um seletor e sua respectiva declaração. Um bloco de declaração é composto por propriedades e valores, segue um exemplo:

|  Seletor |   | Propriedade  |   |  Valor |  |  |
|---|---|---|---|---|---|---|
| h1  | {  | color  | :  |  green | ;  |  } |

### O que são seletores?

Seletores são usados para encontrar elementos HTML baseado em nome, id, classe, atributo, e outros. Os estilos declarados no CSS serão aplicados quando as tags e atributos existirem no HTML. Os seletores podem ser:

+ Elementos de um tipo específico
+ Atributos
  ++ IDs
  ++ Classes
+ Elementos relativos a outros elementos

##### Elementos de um tipo específico

O seletor por elemento seleciona elementos baseado no nome daquele elemento.

```
h1 {
}
```

##### Atributos -> IDs

O seletor por ID usa o atributo id do HTML para selecionar um elemento específico. Ele deve ser único, ou seja, não podemos ter 2 ids com mesmo valor.

```
#id_qqr {
}
```

##### Atributos -> Classes

O seletor por classe seleciona um elemento cujo atributo class corresponda ao nome da classe usada no CSS. Diferente dos IDs, não tem problema repetir nome de classes pelo arquivo HTML. 

```
.classe_qqr {
}
```

##### Elementos relativos a outros elementos

```
ul:first-child {
}
```

##### Observações Importantes

Classes podem ser aplicadas em diversos elementos, sem restrição. Já os IDs só podem ser aplicados em um único elemento. O objetivo deles é poder identificar um elemento unicamente para que mudanças naquele elemento não afetem outros elementos. Seletores podem ser combinados de diversas formas para alcançar um grande nível de especificidade. Multiplos seletores podem ser juntados para especificar elementos baseado em sua localização, em seu tipo, em seu id, em sua classe, ou em qualquer combinação destes. A ordem dos seletores é extremamente importante. Escrever `div .nomeDaClasse {color:red;}` corresponde a customizar a cor do texto dos elementos da classe `nomeDaClasse` que estão contidos dentro de uma div, ou seja, elementos que usam a classe `nomeDaClasse` mas não estão dentro de uma div não são estilizados. Ao escrever `.nomeDaClasse div {color:red;}` os elementos afetados serão as `divs` que estão dentro de classes `nomeDaClasse`. 

### Como seletores são interpretados?

Seletores são lidos da direita para a esquerda pelos navegadores. É mais eficiente para um navegador começar sua procura por combinações a partir do elemento mais a direita (o que ele sabe que receberá o estilo) e trabalhar o seu caminho de volta através da árvore de DOM, do que comçar no alto dessa árvore e percorrer o caminho para baixo, pois poderia nem mesmo acabar no seletor que precisa receber a estilização (também conhecido como seletor-chave).

### Especificidade

A especificadade é o que determina qual regra CSS tem precedência quando várias podem ser aplicadas ao mesmo elemento. Existem 4 categorias que definem o nível de especificidade de um seletor, seguem:

+ Estilos inline
+ IDs
+ Classes, pseudoclasses e atributos
+ Elementos e pseudoelementos

Quando pensamos na especificidade de um elemento `div` temos:

div = (Estilos inline = 0), (IDs = 0), (Classes, pseudoclasses e atributos = 0), (Elementos e pseudoelementos = 1)
div = 0, 0, 0, 1
div = 0001

Se o seletor fosse #id_qualquer div teríamos:

\#id_qqr div = 0, 1, 0, 1
\#id_qqr div = 0101

Imaginando que ambas as regras estivessem sendo usadas para estilizar uma página `#id_qqr div` teria precedência em relação a `div` pois 0101 > 0001. Essa matemática só serve para mostrar a lógica que é usada para interpretar seu arquivo CSS.

Pensando em outro exemplo para fixar o conteúdo pense qual das regras CSS tem maior peso, `#id_qqr article ul` ou `#id_qqr .list`?

Fazendo os cálculos temos:
`#id_qqr article ul` = 0102  
`#id_qqr .list` = 0110

No seletor `#id_qqr article ul` temos 1 ID e 2 elementos. Já no `#id_qqr .list` temos 1 ID e 1 classe. Como 0110 > 0102 a regra com seletor `#id_qqr .list` teria precedência sobre `#id_qqr article ul`. Além disso, a regra `#id_qqr .list` será mais eficiente em questão de performace.

Quando acontecer um empate, ou seja, duas regras terem mesmo peso, temos que usar `!important` naquela que deve ser priorizada. Havendo conflito entre `!important`, entra em ação o efeito cascata, com precedência das CSS de usuário às de autor.

### Não use ID's como seletor

Um dos motivos pelo qual desenvolvedores Web usam IDs como seletores é a performace. É provado que IDs são mais rápidos que classes, porém a diferença é absurdamente minuscula, ou seja, este critério não deve ser usado para priorizar o uso de IDs sobre classes. Outra coisa que muitas vezes as pessoas esquecem é que ao acessarmos `#id a {}` a ordem que o browser busca o elemento é a seguinte: ele pega todos os elementos `a` e verifica se são descendentes imediatos de `#id`, caso não seja vai checando os ascendentes até chegar a `<html>`. Agora que sabemos como os seletores são interpretados é lógico pensar que IDs são os seletores mais rápidos somente se forem os seletores-chave, ou seja, `#id` é mais rápido que `.cls` que é mais rápido que `#id a`. É interessante usarmos classes como seletores pois o conteúdo daquela classe pode ser reutilizado sem precisar replicar o código CSS, basta adicionar aquela classe ao elemento HTML. Isso garante maior manutenibilidade e flexibilidade ao nosso código. É indicado que os desenvolvedores usem IDs para como identificadores que serão usados pelo JavaScript.

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

Essa propriedade gera um espaço entre o conteúdo do elemento e sua borda. Assim como na `margin` podemos utilizá-la de diferentes formas.

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

Eles permitem que o desenvolvedor especifique um estilo em certa parte de um elemento que não está presente no documento, ou seja, permite que elementos lógicos sejam definidos sem que estes estejam no Document Element Tree.

### Pseudo-class vs Pseudo-element

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

selector:pseudo-class {
    property:value;
}

selector::pseudo-element {
    property:value;
}

##### Links Complementares

[pseudo-class vs pseudo-element](http://www.d.umn.edu/~lcarlson/csswork/selectors/pseudo_dif.html)

# CSS3

##### Borders

+ Border Radius

Essa propriedade adiciona bordas aredondadas ao elemento. Quando especificamos apenas um valor, esse valor será aplicado para cada borda do elemento. Quando usamos quatro valores, estes serão aplicados para o topo esquerdo, topo direito, canto inferior direito, e canto inferior esquerdo daquele elemento.

```
border-radius: 10px 10px 10px 10px;
border-radius: 10px 10px 10px;
border-radius: 10px 10px;
border-radius: 10px;
```

+ Border Image

A propriedade Border Image permite a utilização de uma imagem como borda de um elemento. A propriedade permite uma imagem que será usada como borda, um argumento dizendo onde aquela imagem será cortada, e um argumento dizendo se aquela imagem deve se repetir ou se deve ser alongada para caber dentro do espaço delimitado.

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

É possível definirmos as cores de elementos como por exemplo texto. O RGBA são uma extensão do RGB. Além de permitir que o usuário especifique os valores de Red Green e Blue ele permite que o usuário insira um valor para o canal alpha. Esse canal alpha é o responsável por ditar a opacidade da cor. Quando o valor está mínimo significa que a cor será transparente, e quando o valor corresponde ao valor máximo temos a cor completamente opaca.

color values are an extension of RGB color values with an alpha channel - which specifies the opacity for a color.

```
#p1 {
 background-color: rgba(0, 255, 0, 1.0);
}

#p1 {
 background-color: rgba(0, 255, 0, 0.5);
}

#p1 {
 background-color: rgba(0, 255, 0, 0.0);
}
```

##### Shadows

Essa é uma das propriedades mais legais. Ela adiciona sombra ao elemento alvo. Essa sombra dá uma sensação de profundidade muito interessante e ela é muito usada em frameworks CSS. No exemplo a seguir utilizamos box-shadow passando os seguintes argumentos: sombra-horizontal sombra-vertical blur cor; 

```
div {
  box-shadow: 8px 8px 4px #A1A1A1;
}
```

Ele pode assumir os seguintes valores:

+ none: Aqui a sombra não será mostrada.
+ inherit: Atribui ao valor dessa propriedade o valor do elemento pai.
+ initial: Utiliza o valor default de shadow daquele elemento.

##### Transition

As transitions permitem que você altere as propriedades de um elemento de forma transitiva. Elas podem ser ativadas por eventos e podem mudar, por exemplo, a cor de um texto quando o usuário dér `hover` em um elemento. Além disso, podemos definir um delay até que a transição comece e um tempo para sua duração. Para que elas funcionem é necessário que o programador diga o estado inicial e o estado final de certo elemento. Segue o conjunto de propriedades que tornam possível a transição de elementos:

+ transition property
+ transition duration
+ transition timing function
+ transition delay

Abaixo temos um exemplo de uma transição de cor do background de um elemento:

```
.button {
  color: #fff;
  background: #4a89ca;
  transition-duration: 1s;
}

.button:hover {
  background: #d36a62;
}

.button:active {
  background: #a33830;
}
```

####### Transition Property

No exemplo acima a transition é aplicada para todas as propriedades na regra CSS. Para definirmos com precisão quais propriedades serão afetadas pela transition usamos o `transition-property`. Segue o exemplo:

```
.button {
  color: #fff;
  background: #4a89ca;
  transition-duration: 1s;
  transition-property: background;
}

.button:hover {
  background: #d36a62;
}
```

Obs: por default `transition-property` vem definida como `all`.

É importante notar que nem todos os elementos do HTML podem sofrer transições. Apenas elementos animáveis cujas propriedades possuem halfway points podem aproveitar esse recuso do CSS3.

####### Delay

A propriedade `transition-delay` deixa você começar uma transição alguns segundos depois do evento ser disparado. Isso pode ser útil quando você desejar que uma animação comece depois que outra termina.

####### Transition Timing Function

Uma coias legal de se fazer é mudar a velocidade de uma transição durante sua duração, ou seja, enquanto ela está sendo executada.
Esse efeito é alcançado com o uso da propriedade `transition-timing-function`.

Por default, quando criamos uma transition ela segue uma curva de aceleração. A mudança na função de tempo resulta em uma curva de aceleração distinta. Dependendo da curva, algumas partes da sua animação podem ser executadas mais rápidamente que outras. Para mudar o valor da `transition-timing-function` podem usar os seguintes valores:

+ ease        -> Começa de vagar de acelera.
+ linear      -> Mantem uma velocidade constrante por toda a duração da transição.
+ ease-in     -> Começa de vagar e para rapidamente.
+ ease-out    -> Começa rapido e para aos poucos.
+ ease-in-out -> Começa e termina lento.

####### Abreviação

É comum abreviarmos a nomeclatura das transitions colocando transition-property, transition-duration, transition-timing-function, e transition-delay em uma só linha da seguinte forma:

```
.btn {
  transition: <transition-property> <transition-duration> <transition-timing-function> <transition-delay>;
}
```

Obs: Note que no exemplo, o primeiro tempo passado como argumento corresponde ao transition-duration e o segundo ao transition-delay.

####### Cubic Bezier

As funções de tempo que usamos até aqui são simples. Usando `transition-timing-function: cubic-bezier()` podemos criar timing-functions mais complexas adicionando diversos níveis de aceleração durante a transição.

```
.elem {
  transition: transform .5s cubic-bezier(.5, -0.5, .3, 1);
}
```

##### Links Complementares

[Cubic Bezier](http://cubic-bezier.com/#.17,.67,.83,.67,)

##### Transform

Essa propriedade aplica transformações nos elementos. Essas transformações podem variar em um espaço 2D ou 3D. Os valores que a propriedade pode assumir são os seguintes:

+ rotate
+ scale
+ move
+ skew
+ translate

###### Rotate

O `transform: rotate(ang);` rotaciona o elemento selecionado. É passado como parâmetro o quanto aquele elemento deve ser rotacionado. Além disso, saiba que a rotação é aplicada tendo como ponto de rotação o centro do elemento. Segue o exemplo:

```
img {
  transform: rotate(25deg);
}
```

###### Skew

O `transform: skew(x,y);` aplica um efeito parecido com o efeito itálico que é aplicado em fontes, a diferença é que o skew pode ser aplicado em elementos que não são fontes.

```
img:hover {
  transform: skew(15deg, 15deg);
}
```

###### Scale

Como o próprio nome diz, `transform: scale(x,y);` escala o elemento. Ele escala o elemento sem mudar o centro do mesmo, ou seja, depois de escalado sua posição central permanece a mesma.

```
img {
  transform: scale(2, 2);
}
```

###### Translate

O `transform: translate(x,y);` é um dos mais legais. Ele permite que você modifique a posição X e Y do elemento. Se você colocar 100px no valor de x significa que ele vai mover para direita 100px relativos ao centro daquele elemento. Se você colocar -100px o mesmo vai ocorrer porém o elemento irá para esquerda.

```
img:hover {
  transform: translate(100px, 0px);
}
```

###### Transform Origin

Até então os exemplos usavam o ponto central do elemento como base para aplicar as transformações. Muitas vezes queremos alterar esse comportamento e aplicar transformações relativas ao canto de um elemento. Para modificar essa posição relativa podemos usar a propriedade `transform-origin: x y;`.

```
img {
  transform-origin: 50% 50%; // nesse exemplo a posição será relativa ao centro
}

img {
  transform-origin: 0 0;      // nesse exemplo a posição será relativa ao canto superior esquerdo do elemento
  transform-origin: top left; // exatamente a mesma coisa do exemplo logo acima
}
```

###### Combinando Transforms

Outra coisa que podemos fazer é combinar transforms para evitar duplicação de código, fazemos da seguinte forma:

```
img:hover {
  transform: rotate(-10deg) scale(5);
}
```

###### Adicionando Efeitos 3D

Para adicionarmos efeitos 3D em nossos transforms precisamos usar a propriedade `perspective`. É ela que prepara o ambiente para que nossos transforms ajam sobre um espaço 3D, em outras palavras , os filhos do elemento que possui a propriedade `perspective` terão transforms realizados sobre um espaço 3D.

```
.pai {
  perspective: 300px;
}
```

Quanto maior o valor de perspective mais distânte a perspectiva será aplicada. Pense como se uma câmera estivesse observando um cenário 3D. Aumentando o valor de perspective essa câmera iria se afastar do cenário, e diminuindo ela iria se aproximar. Agora que temos `perspective` podemos realizar as transformações.

```
.pai {
  perspective: 300px;
}

.filho {
  transform: rotate(20deg, 20deg);
}

```

### Media Query

As media queries são capazes de extrair dados sobre o dispositivo no qual o usuário está acessando a página. Um dos dados é o tamanho e largura do dispositivo. Além desse é possível descobrir a orientação de um telefone ou tablet, sua resolução, e outros. A sintaxe das media queries se assemelha a seguinte:

```
@media not|only mediatype and (media feature) {
  CSS-Code;
}
```

Elas são extremamente importantes pois elas além de muitas coisas, também permitem a mudança de estilos da página quando o usuário acessa em um ambiente mobile. O próximo exemplo mostra essa mudança de estilo aplicada sobre um classe.

```
.nomeDaClasse {
  float: left;
  width: 25%;
}

@media (max-width: 400px) {
  .nomeDaClasse {
    float: none;
    width: 100%;
  }
}
```

No exemplo anterior usamos o valor `400px` para definir o ponto em que nosso layout iria se adaptar `aquela resolução. Esse ponto é chamado __breakpoint__ . É possível adicionarmos diversos breakpoints para tornar o site adaptavel não só para desktop e mobile, mas para ipads e outros. Optamos também por usar max-width, mas existe uma outra media feature chamda min-width que costuma ser usada.

```
@media screen and (min-width: 480px) {
  body {
    background-color: lightgreen;
  }
}
```

### Flex-box

##### O que é? Para que serve? Por que devo usar?

Flex-box é um modelo criado no CSS3 que substitui o block-model. Ele disponibiliza uma nova forma para distribuir elementos nas suas páginas. Além disso, o uso do flex-box pode facilitar a responsividade das suas páginas.

Ele consiste de containers e items. Containers possuem uma main axis que atravessa-os de forma horizontal, e uma cross axis que atravessa-os de forma vertical. Dentro desses containers temos itens que serão posicionados utilizando novas técnicas que aprenderemos aqui.

##### Primeiros Passos

Tudo começa com a propriedade display. Quando atribuimos ao display a propriedade flex ou inline-flix mudamos o modelo de renderização. Aquele elemento que possui a propriedade display pode, também, ser chamado de container. É possível adicionarmos diversos itens àquele elemento/container. É interessante notar que os elementos que não estão no escopo daquele container não serão afetados pelo `display: flex`, logo, serão renderizados normalmente.

##### Justify-content

O justify-content posiciona um item relativo ao main axis.
  
  + flex-start: posiciona os itens no inicio da main axis
  + flex-end: posiciona os itens ao final da main axis
  + center: posiciona os itens no centro
  + space-between: posiciona os itens de forma igualmente distribuida tal que o primeiro item corresponda ao start da axis e o ultimo ao end
  + space-around: posiciona os itens de forma igualmente distribuida tal que o primeiro item tenha um espaçamento em relação a "borda", assim como o ultimo.

##### Align-items

O align-items posiciona os itens relativos ao cross axis

  + flex-start: posiciona os itens no inicio da cross axis
  + flex-end: posiciona os itens ao final da cross axis
  + center: posiciona os itens no centro da cross axis
  + baseline: alinha de forma que seus baselines ficam alinhados
  + stretch: estica os itens no cross axis

##### Flex-direction

A propriedade flex-direction permite mudar o comportamento das axis. Apesar de, por default, a main axis aparecer horizontal e a cross axis vertical é possível inverte-las quando usamos tal propriedade.
  
  + row: main axis da esquerda para direita
  + row-reverse: main axis mostra os items da direita para esquerda
  + column: main axis se transforma numa column com ordenação de cima para baixo
  + column-reverse: main axis se transforma numa column com ordenação de baixo para cima

##### Flex

Essa propriedade dita o tamanho de cada item dentro do container. O valor é relativo aos demais itens daquele mesmo container, ou seja, se o valor de um item for 2 e dos demais 1 aquele com valor 2 ocupará o dobro do tamanho dos demais.

##### Flex-wrap

A propriedade flex-wrap soluciona o seguinte caso: Algumas vezes não sobra espaço para outros itens em uma certa linha pois a mesma está cheia, daí é necessário que especifiquemos se aqueles itens irão para proxima linha ou se eles irião ultrapassar a barreira do container.
  nowrap: Por default os itens não serão "empilhados"
  wrap: permite que os itens sejam "empilhados"
  wrap-reverse: será wrap em order reversa

##### Ordering

Essa propriedade é capaz de mudar a ordem com que os items são renderizados dentro de um certo container. Itens com order superior aparecer por ultimo e itens com order inferior aparecem primeiro.

##### Margin

Essa propriedade pode ser usada para posicionar itens em diferentes posições, por exemplo, se atribuirmos margin-right: auto a um item, este irá mostrar um espaço em branco a sua direita. Seguindo a mesma lógica, para centralizar um item, bastaria colocar sua margin como auto.

### OOCSS

Object Orientes CSS é uma forma padronizada para organização do seu código CSS criada por Nicole Sullivan. Pense nele como um guia que dita a arquitetura do seu CSS. Assim como o OOCSS existem outras arquiteturas famosas no CSS. Iremos falar delas mais adiante. 

O princípio básico do CSS Orientado a Objetos é a separação de __estrutura__ e __skin__ e a separação de __container__ e __conteúdo__.

Separar __estrutura__ e __skin__ consiste em repetir característica visual como skin que pode ser combinada em uma variada gama de objetos por exemplo background e estilos de borda. Separar container de conteúdo segue o princípio de que um objeto deve permanecer igual independente da sua localizacao na página, ou seja, não queremos que as classes pai do css influenciem as classes filho. É bastante comum o uso de classes para nomear objetos e componentes, em vez de confiar somente na semantica HTML. Por exmplo, um objeto de mídia com class="media" e seus componentes com class="img" (para componentes de imagem e video) e class="bd" (para componentes de texto). Ao referenciar essas classes nas folhas de estilo, o HTML ganhavuma flexibilidade maior; ou seja, se um novo elemento de mídia surgir nos próximos anos (como <svg>), ele pode receber a estilização sem que seja preciso mexer em uma linha de CSS.

Separar __container__ e __conteúdo__ significa não use estilos que dependam de localização. Um objeto deve parecer-se igual, independentemente de onde estiver na página. Em vez de estilizar um título secundário específico com `.myObject h2 {}`, crie e aplique uma classe que descreva o elemento em questao, como `<h2 class="category-title">`. Isso garante que:

+ Todos os `h2` sem a classe não sejam afetados inadvertidamente.
+ Todos os `h2` com a classe tenham o mesmo estilo.
+ Não é preciso criar estilos extras para os casos em que seja preciso que um `.myObject` se pareca com um `h2` não estilizado.

Para deixar bem claro, vamos observar como o CSS Orientado a Objetos pode ajudar o desenvolvedor garantindo maior manutenibilidade e menor repetição de código.

Imagine o seguinte cenário.

```
#weather h3 {
  font-size: 1.2em;
}
#tweets h3 {
  font-size: 1.1em;
}
```

Aqui temos um weather __module__. Queremos estilizar esse weather, e para isso adicionamos uma font-size ao id. Vamos pensar no código que acabamos de escrever. Todos os `h3` dentro de `#weather` __modules__ recebem uma `font-size de 1.2em`. Mas o que acontece com um __module__ diferente? Temos o __module__ tweets. O que fazer com ele? Adicionamos font-size com valor 1.2em novamente? E se o font-size desse elemento for diferente? Com essas poucas linhas de código já temos um sério problema: nosso `h3` possui valores diferentes dependendo do __module__ que o contém. Voltamos a dizer que o nosso font-size dentro de tweets seja 1.2em para facilitar o raciocínio.

```
#weather h3 {
  font-size: 1.2em;
}
#tweets h3 {
  font-size: 1.2em;
}
```
Uma forma de facilitar a legibilidade desse código seria fazer o seguinte:

```
#weather h3,
#tweets h3 {
  font-size: 1.2em;
}
```

O problema aqui é que cada vez que quiséssemos adicionar h3 com tamanho 1.2em cujo pai não seja weather e tweets, teremos que voltar ao CSS e escrever mais uma linha para satisfazer esse caso.

```
#weather h3,
#tweets h3,
#comments h3 {
  font-size: 1.2em;
}
```

Agora que vimos os problemas de codar dessa forma precisamos pensar em uma solução para deixar nosso código mais modular, manutenível, e legível. A coisa mais óbvia a se fazer seria parar de usar IDs no seu CSS. Já sabemos que essa não é uma boa prática.
Poderíamos resolver o problema dos ids colocando uma classe no seu lugar. Além disso, podemos mudar o próprio valor default do h1.

```
h1, .h1 {
  font-size: 1.6em;
}
h2, .h2 {
  font-size: 1.4em;
}
h3, .h3 {
  font-size: 1.2em;
}
```

Muitas pessoas questionam o uso de classes cujo nome é igual a de um identificador. Não tem problema nenhum usarmos `.h1` para representar o elementos h1, pelo contrário, essa metodologia é bem flexível. Agora podemos modificar o font-size da forma como gostariamos desde o início e essas mudanças não são limitadas ao __module__ ou um __id__ ou __container__. Vamos analisar o seguinte código:

```
HTML
  <div id="box">
    <h3>Oi</h3>
  </div>

CSS
  #box h3 {

  }
```

Como vimos, essa não é uma forma muito boa de manter seu código. No exemplo acima estamos codificando em termos de __modules__ específicos. Quando adicionarmos uma nova div com id="box2" e com h3 dentro teríamos que entrar no arquivo CSS e adicionar mais linhas de código sempre que uma nova div fosse adicionada.

Usando os conceitos que aprendemos até aqui teríamos o seguinte código:

```
HTML
  <div>
    <h3>Oi</h3>
  </div>
  <div class="tweets">
    <h3 class="h4">Oi</h3>
  </div>
CSS
  h1, .h1 {
    font-size: 1.6em;
  }
  h2, .h2 {
    font-size: 1.4em;
  }
  h3, .h3 {
    font-size: 1.2em;
  }
  h4, .h4 {
    font-size: 1.1em;
  }
```

No caso acima ambos os h3 herdam a mesma estilização, mas como adicionamos a classe h4 ao segundo h3 ele se comporta de forma visualmente diferente. O legal aqui é que a tag h3 era a tag semanticamente correta, mas ela precisava de uma estilização diferente da estilização da anterior.

Por estarmos usando essa metodologia orientada a objetos, podemos usar base styling, mas quando realmente precisamos de visuais especificos podemos aplicar essas classes adicionais, assim conquistamos a manutenibilidade que desejavamos. Observe esse outro exemplo:

```
HTML
  <div class="notice">Here is a notice.</div>
CSS
  .notice {
    border: 1px dotted #666;
    padding: 1em;
    color: #101010;
  }
```

Digamos que queremos adicionar uma imagem ao `.notice`, fariamos o seguinte:

```
HTML
  <div class="notice">Here is a notice.</div>
CSS
  .notice {
    border: 1px dotted #666;
    padding: 1em;
    color: #101010;
    background: url(icon.png) no-repeat 0 50%;
  }
```

Agora queremos outra notificação, só que agora ela possui uma aparência de warning.

```
HTML
  <div class="notice">Here is a notice.</div>
  <div class="warning">Here is a warning.</div>
CSS
  .notice {
    border: 1px dotted #666;
    padding: 1em;
    color: #101010;
    background: url(icon-notice.png) no-repeat 0 50%;
  }
  .warning {
    border: 1px dotted #666;
    padding: 1em;
    color: #101010;
    background: url(icon-warning.png) no-repeat 0 50%;
  }
```

Repetimos muito código desnecessário no exemplo acima. Como resolver esse problema? Acompanhe a solução:

```
HTML
  <div class="message notice">Here is a notice.</div>
  <div class="message warning">Here is a warning.</div>
CSS
  .message {
    border: 1px dotted #666;
    padding: 1em;
    color: #101010;
  }
  .notice {
    background: url(icon-notice.png) no-repeat 0 50%;
  }
  .warning {
    background: url(icon-warning.png) no-repeat 0 50%;
  }
```

Resolvemos o problema de repetição de código, e agora, quando quisermos mudar uma propriedade para todos os diferentes tipos de messagem, basta mudarmos a classe `.message`.

####### Resumo

O OOCSS prega que devemos criar componentes reutilizáveis. Pense como se você tivesse uma coleção de legos. Misture componentes para construir seus sites.

##### Links Complementares

[Livro que explica CSS Orientado a Objetos](https://www.casadocodigo.com.br/products/livro-css-eficiente)

[Video que explica CSS Orientado a Objetos](https://www.youtube.com/watch?v=8FLWwZw5wQg)

### SMACSS

style guide that help organize and structure CSS for projects on any scale

identify repeating pattern that are going to combine into modular code

Cateories
  Base
  Layout
  Modules
  States
  Themes

Base
  what elements look by default

Layout
  define layout for major parts of the page
  header
  footer
  sidebar
  grid

Modules
  majority of the project

States
  element states
  hidden
  active
  collapsed

Theme
  define diferent color to give our project diferent colors

scss
  application.scss  -> import all indexes
  base
    _base.scss      -> styles for base element selectors (ex: h1, h2, body, *, ...)
    _index.scss     -> import others
    _normalize.scss -> reset styles
  layout
    _container.scss   -> 
    _extends.scss     -> 
    _index.scss       -> import others
    _panel.scss       -> 
  modules
    _buttons.scss
    _extends.scss
    _forms.scss
    _headlines.scss
    _icons.scss
    _img.scss
    _index.scss
    _nav.scss
    _navbar.scss
  states
    _index.scss
  theme
  utilities
    _config.scss
    _functions.scss
    _helpers.scss
    _index.scss
    _mixins.scss

application
  @import utilities
  @import base
  @import layout
  @import module
  @import state
  @import theme

### BEM

Block Element Modifier

.bloq__element--modifier

Block Classes
  Root
  Highest level of abstraction
  Contain child elements that help form a block

Element Classes
  Form a Block

Modifier Classes
  Variation of the existing classes

.list__item {
  padding: 5px;
  border-bottom: 1px solid;
}

.list__item--end {
  border-bottom: nome;
}

.list__item--highlight {
  color: white;
  background: yellow;
}

<ul class="list">
  <li class="list__item">Item 1</li>
  <li class="list__item list__item--highlight">Item 2</li>
  <li class="list__item list__item--end">Item 3</li>
</ul>

Obs: O problema de usar o bem é que ele é subjetivo. Sua definição de um Modulo pode ser diferente da definicao de outros. O importante é pensar que o bloco é o maior nivel de abstracao. Qualquer bloco definido pode ser usado livremente em diversas paginas ou ate mesmo projetos sem dependencias extras. 

Devemos dividir as partes em bloco apenas se aquela parte puder ser reutilizada entre projetos.

Um dos pontos negativos do BEM é aumentar consideravelmente o tamanho das suas classes usadas no html tornando o codigo um pouco mais "sujo", podem garantindo maior manutenibilidade.

One of the big advantages of using the BEM convention is: We communicate what a block of HTML does just front its naming convention, and selectors are easier to understand because we provide the context directly into the selector