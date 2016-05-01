# jQuery

### O que é JQuery?

JQuery é uma biblioteca de JavaScript, ou seja, ela pode ser definida como um conjunto de código JavaScript. Seu propósito é facilitar a manipulação de estruturas html, facilitar o tratamento de eventos, e facilitar o uso do Ajax.

### Primeiros Passos

A primeira coisa que devemos fazer para utilizar o JQuery é ir até seu site oficial e baixar a versão mais recente. Para incluir o JQuery no projeto fazemos o seguinte:

```
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
    <title>Demo</title>
</head>
<body>
    <a href="http://jquery.com/">jQuery</a>
    <script src="jquery.js"></script>
    <script>
    // Your code goes here.
    </script>
</body>
</html>
```

Quando usamos JQuery, é uma boa prática garantir que nossas funções só sejam executadas depois que os elementos da página(`window`) estiverem carregados. Outra possibilidade é executar nossas funções depois que o `document` esteja pronto para ser manipulado. A diferença é que, se esperarmos a `window` carregar estamos esperando todas as imagens e os adds carregarem. Se esperarmos o `document` carregar ele não espera que as imagens e adds estejam prontos para chamar as funções. Podemos escolher uma opção desejada da seguinte forma:

```
// esperar todos os elementos do site carregarem
window.onload = function() {
};

// esperar apenas o document carregar
$( document ).ready(function() {
});
```

### Sintaxe

Você pode usar o JQuery como se fosse uma função

```
JQuery();
```

Você deve passar como argumento dessa função o elemento CSS que deseja manipular

```
JQuery(".warning");
```

Você pode chamar métodos nos elementos retornados

```
JQuery("warning").hide();
```

O detalhe aqui é que é bastante chato ter que repetir JQuery toda vez que precisamos chamar o objeto JQuery, por isso os criadores do JQuery disponibilizaram outra forma de acessarmos esse objeto. Ela é feita pelo uso do caracter `$`. Hoje em dia, a grande maioria dos usuários da biblioteca opta por usar o `$` ao invés do `JQuery`.

Como dito anteriormente, JQuery é uma biblioteca muito boa para manipulação do DOM. Para que essa manipulação do DOM seja efetiva devemos ser capazes de pegar elementos da nossa página e chamar funções em cima destes elementos. Essas funções devem poder mudar o comportamente do elemento, ou até mesmo mudar o comportamento de elementos pais ou filhos do elemento obtido. Resumindo, queremos selecionar elementos e fazer algo com esses elementos.

##### Selecionando Elementos

Existem algumas formas de selecionarmos elementos, as principais são as seguintes:

###### Selecionando o Elemento pelo ID

Quando selecionamos o elemento pelo ID temos que garantir que aquele ID é único, ou seja, não podemos ter 2 IDs representando coisas distintas.

```
$( "#myId" );
```

###### Elemento Selecionado usando o nome da Classe

Quando selecionamos o elemento pela classe não temos aquele problema de ter duas classes com mesmo nome na nossa página. Isso é completamente aceitável.

```
$( ".myClass" );
```

###### Elemento Selecionado usando seu atributo

```
$( "input[name='first_name']" );
```

###### Selecionando Elemento Usando seu Conjunto de Seletores

```
$( "#contents ul.people li" );
```

###### Selecionando Elemento Usando seus Seletores Separados por Virgula

```
$( "div.myClass, ul.people" );
```

###### Selecionando Elemento e usando Pseudo-Selectores

```
$( "a.external:first" );

$( "tr:odd" );

$( "div:visible" );

$( "div:animated" );
```

##### Manipulando Elementos

Podemos pegar elementos e mudar suas propriedades HTML da seguinte forma:

```
$( "button.continue" ).html( "Next Step..." )
```

Olhando esse exemplo nota-se que podemos chamar métodos no objeto que representa o JQuery. Esses métodos são os facilitadores que evitam a repetição de algumas linhas de JavaScript e permitem que o programador se preocupa apenas com o que mudança vai ocorrer após a chamada do método. Vamos estudar os métodos mais comumente usados.

###### Métodos Úteis

###### html()

Esse método pode ser usando para pegar o contúdo de qualquer elemento do seu HTML. Ele pode também ser usado para setar o conteúdo do mesmo.

```
// .html() get ou set conteúdo HTML
$( "div.demo-container" ).html();
```

###### attr()

Esse método age como um getter e um setter para atributos. Quando você deseja utilizá-lo como getter basta escrever o que você deseja que o método pegue. Segue o exemplo:

```
// .attr() getter:
$( "a" ).attr( "href" ); // Retorna o href do primeiro elemento 'a' do documento
```

Quando você deseja 'setar' algum valor você deve passar uma chave e um valor correspondente para essa chave.

```
// .attr() setter
$( "a" ).attr( "href", "allMyHrefsAreTheSameNow.html" );
$( "a" ).attr({
    title: "all titles are the same too!",
    href: "somethingNew.html"
});
```

Note que métodos setters afetam todos os elementos que foram retornados, já o get afeta apenas o primeiro elemento retornado.

###### text()

Esse método pode ser usado para pegar ou alterar o conteúdo textual de um elemento HTML. O restorno deste método é uma string que contém o texto de todos os elementos que correspondiam ao procurado.

```
// .text() 
$( "p:first" ).text();
```

###### val()

Esse método pega ou altera o valor atual de um elemento. Esse elemento pode ser um `input`, um `select`, e até mesmo `textareas`.

```
// .val()
$( "input:checkbox:checked" ).val();
```

###### remove()

O método remove é usado quando desejamos remover um elemento permanentemente da nossa página. Quando chamamos esse método o elemento alvo é retirado do DOM.

```
// .remove()
$( ".hello" ).remove();
```

Existem outros métodos similares ao remove como por exemplo o `empty()` e o `detach()`. Estes possuem uma ligeira diferença. O empty deixa o elemento na página mas remove todo seu conteúdo. O detach faz com que os dados e os eventos persistam, ou seja, ele retorna o elemento removido, de forma que, caso seja necessário, você consiga restaurar aquele elemento.

###### criando elementos com $()

Para criar elementos no jQuery podemos usar o mesmo operador `$` usado para selecionar elementos.

```
$( "<p>This is a new paragraph</p>" );

$( "<li class=\"bla\">new list item</li>" );

$( "<a/>", {
    html: "This is a <strong>new</strong> link",
    "class": "new",
    href: "foo.html"
});
```

Quando você cria um elemento, este não é adicionado à página automaticamente. Você deve programar para que este seja adicionado. Suas opções são as seguintes:

```
var myNewElement = $( "<p>New element</p>" );

myNewElement.appendTo( "#content" );

myNewElement.insertAfter( "ul:last" );
```

Outro detalhe é que o elemento não precisa necessariamente ser guardado em uma variável. Apesar de não precisar, é comum que você queira guardar aquela referência ao elemento.

##### Chamando Eventos

Como dito anteriormente, JQuery facilita o tratamento de eventos. Segue um exemplo:

```
var hiddenBox = $("#banner-message");
$("#button-container button").on("click", function(event) {
  hiddenBox.show();
});
```

O exemplo acima mostra o elemento cujo ID é #banner-message. O detalhe é que esse elemento só é mostrado quando o JQuery(JavaScript) detecta o evento de click.

##### Aplicando Traversing

Traversing é o nome dado quando queremos manipular elementos filhos ou elemento pai de certo elemento selecionado. Além de poder acessar pais e filhos podemos também acessar elementos irmãos. O jQuery vem com uma série de de métodos que facilitam o acesso e a manipulação destes.

+ Parents

Para encontrar o elemento pai podemos chamar um dos seguintes métodos

```
// .parent();
$( "span.subchild" ).parent();

// .parents();
$( "span.subchild" ).parents();

// .parentsUtil();
// .closest();
```

+ Children

Os métodos para encontar elementos filhos são `children()` e `find()`. O primeiro busca nos filhos diretos do elemento. Já o segundo busca recursivamente em todos os filhos até encontrar um elemento que corresponda a  uma folha do DOM.

```
// .children()
$( "div.grandparent" ).children( "div" );

// .find()
$( "div.grandparent" ).find( "div" );
```

##### Manipulando CSS

Uma das melhores qualidade do jQuery é a facilidade na manipulação de propriedades CSS dos elementos. Segue um exemplo de como ter acesso à essas propriedades:

```
$( "h1" ).css( "fontSize" );

$( "h1" ).css( "font-size" );
```

Podemos também alterar o valor dessas propriedades:

```
$( "h1" ).css( "fontSize", "100px" );

$( "h1" ).css({
    fontSize: "100px",
    color: "red"
});
```

Como visto anteriormente, para facilitar a escrita, podemos passar objetos como parâmentro dos setters. Passando em forma de objeto podemos setar multiplos valores de uma só vez.

Um detalhe importante é que as propriedades CSS são escritas com hifen, enquanto as variáveis JavaScript são escrita seguindo o padrão camelCase. Quando passamos o nome de uma propriedade CSS no método css() devemos usar camelCase.

__Evite utilizar o método .css() como setters. Sabemos que é importante a separação do código relacionado à interface do código relacionado à interatividade. Ao invés de alterar o CSS no JavaScript devemos esrever regras CSS para nossas classes que descrevem os diversos visuais possíveis. Quando necessário mudar o visual do elemento mude a classe usando JavaScript.__