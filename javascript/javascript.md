![javascript](https://aspblogs.blob.core.windows.net/media/dwahlin/Media/JavaScript-logo.png)
# JavaScript  

### O que é JavaScript?

JavaScript é uma Linguagem de Programação, criada por Brendan Eich, a pedido da empresa Netscape, em meados de 1995. No início, o JavaScript foi batizado com outro nome: LiveScript. No entanto, a Netscape não ficou sozinha com o desenvolvimento do JavaScript. A empresa SUN Microsystems interessou-se por ela e entrou de cabeça no desenvolvimento desta nova linguagem, uma vez que acreditava na ideia inovadora que era o JavaScript.
Com o sucesso inicial do JavaScript, a mudança do nome de LiveScript para JavaScript foi inevitável, e, com certeza, veio por influência da própria SUN, que mantém uma Linguagem de Programação chamada JAVA. É claro que as Linguagens de Programação JAVA e JavaScript são parecidas somente no nome, já que se diferem no conceito e no uso. [Caso queira saber mais](http://www.cpt.com.br/cursos-informatica-desenvolvimentodesoftwares/artigos/linguagem-de-programacao-javascript-um-breve-historico#ixzz47RSb1uaO).

### Adicionando JavaScript às páginas

+ JavaScript no código HTML  

	Código de JavaScript normalmente é colocado na Head e entre os marcadores `<script></script>`, não há uma proibição quanto a colocar o código na body, mas se tornou meio que um padrão. Há casos onde é melhor colocar no body, pois é necessário que o código seja ativado depois do carregamento da página.    

+ JavaScript externo  

	Caso seu código JavaScript se repita muito entre as páginas é recomendado que torne ele um código externo. Para isso usa-se:  
	```<script src="myScript.JavaScript"></script>. ```    

### Sintaxe

+ Constante

	Assim como a linguagem C, JavaScript tem contantes e são criadas pela palavra "const". É muito recomendado seu uso para dados que você absolutamente não quer que ele mude de valor.  Ex:  
```const piBilly = 3,141592;```    

+ Variável

	JavaScript é uma linguagem fracamente tipificada, muito diferente de C. As o tipo das variáveis não são determinadas quando se cria elas, e sim quando se atribui um valor a elas.  
	Para se declarar uma variavel é preciso de "var" antes do nome da variável.  
	Essas variáveis podem assumir três tipos: string (tem que estar entre aspas ou aspas simples), número (real ou não) ou um valor booleano. Ex:  
	```var caboBilly = 20;```  
	```var caboBilly = "ah não vei";```    
	Na hora de criar uma variável é possível defini-la. Nada de mais, mas a mágica acontece quando usa-se disso em strings. Ex:    
    ```var caboBilly = "feedback" + "é" + adjetivoLegal;```  
	**Obs:** operações entre números gera número e entre qualquer outra gera string. Ex:   
	```var caboBilly = "feedback" + 5;      ->       feedback5```  


+ Operadores

	Os operadores do JavaScript são identicos aos da linguagem C. Isso incluindo os operadores de comparação.    
	```+```	-> soma  
	```-```	-> subtração  
	```/```	-> divisão  
	```*```	-> multiplicação   
	```%```-> módulo (extrai o resto de uma divisão)    
	```==```	-> verifica se são iguais    
	```===```	-> verifica se são iguais  e se são do mesmo tipo  
	```!=```	-> verifica se são diferentes   
	```!==```	-> verifica se são diferentes e se não são do mesmo tipo   
	```?```	-> operador ternário  

+ Aritimética

	```++	``` ->	acrescimo de 1  
	```--```	->	decrescimo de 1  
	```x=```	-> sendo x: ```+```, ```-```, ```*```, ```/``` ou ```%```, realiza a operação escolhida dele mesmo com um outro termo e guardando o resultado nele mesmo.  

+ Comentarios
	
	São feitos usando de dupla barra ```//``` ou entre ```/* */``` como em C. Existe uma divergência em relação ao uso de comentários, alguns acham essencial e outros não. Mas por via das duvidas, comente. Ajuda a não se perder no próprio código.   

+ Identificadores
	
	O nome das variáveis (identificadores) tem que começar com letras, cifrão (```$```) ou underscore (```_```). Normalmente se coloca o underscore no começo de variáveis mais importantes para destaca-las e cifrão no começo de nome de objetos (confirmar isso com o Luis).    
	Assim como em C, eles são sensíveis a letras minúsculas e maiúsculas (Case Sensitive), logo cAboBilly é diferente de caboBilly.  
	Hifén (```-```) é uma letra reservada. Então nada de cabo-billy.  

+ Camel Case

	Uma espécie de padrão informal adotado no JavaScript é que quando o nome da variável é composto, adotamos o seguinte método: primeiro nome todo minúsculo e as outras palavras com a inicial em maiúsculo. Ex:  
	```var camelCase;```

+ Array

	Primeiramente arrays em JavaScript são Objetos, mas Objetos não são arrays (Arrays são indexados por número e objeto é indexado por nomes). Podem carregar diferentes tipos (string, numero, booleano, outros arrays e até mesmo funções) em um mesmo array. Esses arrays são dinâmicos, logo não é necessário dizer o tamanho deles. Declara-se um array:  
```var billyEnemies = [];```  
```var billyNetworking = ["Deus", "Buda", "JC"];```  
Por serem objetos, arrays tem métodos como:  
```.length``` (descobre o tamanho do array) .  
```.push``` (adiciona um elemento no fim do array)   
```.pop``` (retira o elemento do final do array)   
```.unshift``` (adiciona o primeiro elemento do array)  
```.shift``` (retira o primeiro elemento do array)  
```.sort``` (ordena em ordem alfabética)    
Com uma indexação parecida com a do C, começa em 0 a contagem de itens de um array, ou seja, o acesso ao primeiro item seria ```billyNetworking[0]```.  
Existem 3 meios de adicionar um elemento a um array:  
```billyLines.push("This is Sparta"); ```  
```billyLove[billyLove.length] = "CJR";```  
```billyNotes[10] = "Querido Diário, ...";```  
	
+ Condição && Switch && Loops

Identico à C.  

Ex1:   
```
if(billy == "Amor de pessoa"){
	abraça(billy);
}
else{
	ficadeboas();
}
```
Ex2:  
```
switch(Aique){
	case 0:
	default:
		Aique += "delicia";
		break;
}
```
Ex3:  
```
for (i = 0; i < infinito; i++) {
    billyAwesome++;
}
```
Ex4:  
```
while (zuera) {
	billyZuera *= zuera;
}
```
Ex5:   
```
do {
    pressF5();
}while (!matriculaWeb); 
```

+ Funções

	Funções são exatamente iguais as em C, somente com duas diferenças. JavaScript é uma liguagem fracamente tipificada, Logo na hora de declarar as variáveis que a função irá receber, não é se declara o tipo da variável (já que não há). E é necessário que haja function antes de toda função.  Ex:  
	```
	function Billy(tretas){  
		return "arco-íris"  
	} 	   
	```

### Eventos

+ onclick
+ onblur
+ onload
+ onchange

### Manipulação do DOM

####DOM 
É um padrão de acesso a documentos criado pela W3C e possui 3 diferentes partes:
+ Core DOM (Todos os tipos de documentos)
+ XML DOM (Documentos XML)
+ HTML DOM (Documentos HTML)

---
#### Interface de programação DOM

HTML DOM pode ser acessado pelo JavaScript e algumas outras linguagens, onde todos os elementos são definidos como objetos. 
A interface de programação são as propriedades (valores que podem ser definidos e alterados) e métodos (ações que podem ser realizadas) de cada objeto.

Quando uma página web é carregada, o navegador cria um HTML DOM (Document Object Model) da página. JavaScript permite manipular esse objeto, ou seja, dá ao senhor o poder de criar HTML dinâmico. 
![](http://tableless.com.br/wp-content/uploads/2011/07/dom_tree.gif)
O senhor poderá, na página:
+ Mudar, retirar e adicionar todos os elementos e atributos HTML.
+ Mudar todos os estilos CSS.
+ Reagir e criar eventos HTML.

---
O exemplo abaixo transforma o conteúdo de uma parte do site (innerHTML), mais especificamente o ```<p>``` com o "id" especificado pelo _getElementById_.
```HTML
<html>
  <body>
    <p id="billy"></p>
    <script>
      document.getElementById("billy").innerHTML = "Welcome to Billy World!";
    </script>
  </body>
</html>
```  
---
#### Métodos

Aqui vão alguns dos métodos mais usados.

##### Achar Elementos

+ _getElementById_ 
	+ Procura elementos a partir de id's.
```javascript
	var myElement = document.getElementById("intro");
```
+ _getElementByTagName_ 
	+ Procura elementos a partir de suas tags.
```javascript
	var x = document.getElementsByTagName("p");
```
+ _getElementByClassName_ 
	+ Procura elementos a partir de nome de Classes.
```javascript
	var x = document.getElementsByClassName("intro");
```
+ _querySelectorAll_  
	+ Procura elementos que tem a mesmo estilo CSS (concatenação com "."). No exemplo abaixo ele procura todos os ```<p>``` com ```class="intro"```
```javascript
	var x = document.querySelectorAll("p.intro");
```


Obs: getElementById é o método mais comum de acesso a elementos HTML.
Obs2:  Concatenação de métodos é bastante útil.
```javascript
var x = document.getElementById("main");
var y = x.getElementsByTagName("p");
```

---
##### Mudar Elementos 

+ _element.innerHTML_
	+ Permite atribuir um novo conteúdo ao elemento HTML.
	+ Conhecido por ser o jeito mais fácil de se conseguir o conteúdo de um elemento.
+ _element.attribute_
	+ Permite atribuir um novo valor ao elemento HTML.
	+ Possível usar para alterar imagens.
```javascript
document.getElementById("myImage").src = "landscape.jpg";
```
+ _element.setAttribute(attribute, value)_
	+ Muda o atributo de um elemento HTML para o dado valor. 
+ _element.style.property_
	+ Permite atribuir um estilo para um elemento HTML.
```javascript
<p id="p2">Hello World!</p>
<script>
  document.getElementById("p2").style.color = "blue";
</script>
```

---
##### Adicionar e Deletar Elementos

+ _document.createElement(element)_
	+ Cria um elemento HTML
+ _document.removeChild(element)_
	+ Remove um elemento HTML
+ _document.appendChild(element)_
	+ Adiciona um elemento HTML
+ _document.replaceChild(element)_
	+ Substitui um elemento HTML.
+ _document.write(text)_
	+ Simplesmente escreve no HTML Output Stream
	+ Não usar depois que o documento foi carregado, pois irá sobrescrever o documento.
```javascript
<!DOCTYPE html>
  <html>
    <body>
      <script>
        document.write(Date());
      </script>
    </body>
</html>
```

---
##### Adicionar Manipuladores de Eventos

+ _document.getElementById(id).onclick = function(){code}_
	+ 	Adiciona um código de manipulação de evento para o evento onclick().
```javascript
<h1 id="id1">My Heading 1</h1>
<button type="button" 
onclick="document.getElementById('id1').style.color = 'red'">
Click Me!</button>
```  

##### Achar Objetos HTML

DOM levels são como as versões das especificações da definição de como o DOM deveria funcionar. 

+ document.anchors (Level 1)
  + Returns all ```<a>``` elements that have a name attribute 
+ document.applets (Level 1)
  + Returns all ```<applet>``` elements (Deprecated in HTML5) 
+ document.baseURI (Level 3)
  + Returns the absolute base URI of the document
+ document.body (Level 1)
  + Returns the ```<body>``` element 
+ document.cookie (Level 1)
  + Returns the document's cookie
+ document.doctype (Level 3)
  + Returns the document's doctype 
+ document.documentElement (Level 3)
  + Returns the ```<html>``` element 
+ document.documentMode (Level 3)
  + Returns the mode used by the browser 
+ document.documentURI (Level 3)
  + Returns the URI of the document 
+ document.domain (Level 1)
  + Returns the domain name of the document server 
+ document.domConfig (Level 3)
  + Obsolete. Returns the DOM configuration 
+ document.embeds(Level 3)
  + Returns all ```<embed>``` elements 
+ document.forms (Level 1)
  + Returns all ```<form>``` elements
+ document.head(Level 3)
  + Returns the ```<head>``` element 
+ document.images (Level 1)
  + Returns all ```<img>``` elements 
+ document.implementation (Level 3)
  + Returns the DOM implementation 
+ document.inputEncoding (Level 3)
  + Returns the document's encoding (character set)
+ document.lastModified (Level 3)
  + Returns the date and time the document was updated 
+ document.links (Level 1)
  + Returns all ```<area>``` and ```<a>``` elements that have a href attribute 
+ document.readyState (Level 3)
  + Returns the (loading) status of the document 
+ document.referrer (Level 1)
  + Returns the URI of the referrer (the linking document) 
+ document.scripts (Level 3)
  + Returns all ```<script>``` elements 
+ document.strictErrorChecking (Level 3)
  + Returns if error checking is enforced 
+ document.title (Level 1)
  + Returns the ```<title>``` element 
+ document.URL (Level 1)
  + Returns the complete URL of the document 

Obs: Pegar elementos do form se torna relativamente fácil.
```javascript
var x = document.forms["frm1"];
var text = "";
var i;
for (i = 0; i < x.length; i++) {
    text += x.elements[i].value + "<br>";
}
document.getElementById("demo").innerHTML = text;
```

#### DOM Animation

Uma animação em DOM é realizada quando o efeito (estilo)  de algo muda quando um evento acontece. Então basicamente se trata de usar de eventos para mandar o DOM mudar o estilo de elementos HTML.

```HTML
<!DOCTYPE html>
<html>
<style>
#container {
  width: 400px;
  height: 400px;
  position: relative;
  background: yellow;
}
#animate {
  width: 50px;
  height: 50px;
  position: absolute;
  background-color: red;
}
</style>
<body>

<p>
<button onclick="myMove()">Click Me</button>
</p> 

<div id ="container">
<div id ="animate"></div>
</div>

<script>
function myMove() {
  var elem = document.getElementById("animate");   
  var pos = 0;
  var id = setInterval(frame, 5);
  function frame() {
    if (pos == 350) {
      clearInterval(id);
    } else {
      pos++; 
      elem.style.top = pos + 'px'; 
      elem.style.left = pos + 'px'; 
    }
  }
}
</script>

</body>
</html>

```
Esse código cria um botão que modifica o estilo (CSS) e sua posição ao longo de um espaço de tempo de um certo elemento. Para verificar o código funcionando, basta acessar [aqui](http://www.w3schools.com/js/tryit.asp?filename=tryjs_dom_animate_3).

### Expressões Regulares

##### O que são expressões regulares?

O JavaScript tem uma ferramenta predefinida extremamente poderosa chamada expressão regular. Essa ferramenta permite a seleção de cadeias de caracteres de interesse em um texto. Expressões regulares podem, também, serem conceituadas como uma sequência de caracteres que definem um padrão de busca.

##### Histórico

As expressões regulares surgiram no ano de 1956 quando Stephen Cole Kleene descreveu linguagens regulares usando notação matemática. A teoria definida pelo matemático ganhou enorme importância na área teórica da ciência da computação, principalmente na teoria dos autômatos e na teoria das linguagens formais. As expressões se tornaram populares em 1968 quando foram usadas para encontrar padrões de texto num editor de texto e quando foram usadas num compilador para facilitar a análise léxica. Hoje em dia as regexp são suportadas pela grande maioria das linguagens e são utilizadas em vários editores.

##### Domínio de Aplicação

Além do que já foi dito a respeito da utilidade das expressões regulares para encontrar padrões em texto elas são bastante úteis em outros tipos de aplicações. Elas podem ser usadas como forma de validação de dados, como ferramenta de scraping, para fazer parsing, e outros.

##### Sintaxe

Há duas maneiras de construir uma expressão regular no JavaScript. A primeira delas consiste no uso de uma expressão literal, a segunda consiste na chamada da função construtora do objeto RegExp. Na primeira, as expressões na forma literal são compiladas quando o script é carregado, logo, ela possui melhor performace quando a expressão utilizada é constante. Na segunda, a compilação é realizada em tempo de execução, logo, faz sentido o uso da função construtora quando souber que o padrão da expressão regular irá mudar ou quando o padrão for desconhecido. Segue o exemplo da utilização de ambas as formas explicitadas acima:

```
// Expressão literal
var re = /ab+c/;

// Função Construtora do Objeto
var re = new RegExp("ab+c");
```

Quando desejamos criar uma expressão regular em JavaScript devemos seguir certas regras da linguagem. A primeira delas é a seguinte: uma expressão regular deve sempre começar com `/` e terminar com `/`. Exemplo:

```
/ + regex + /
```

##### Tipos de Expressões Regulares

O conjunto de expressões que podem escrever pode ser composto por caracteres simples, ou por uma combinação entre caracteres simples e especiais.

###### Caracteres Simples

O conceito de caracteres simples é bem fácil. O caractere simples seria o caracter sem nenhum significado extra, ou seja, quando pensando no caracter `a` colocado em uma expressão regular como por exemplo `/a/`, esse caracter indica que a expressão regular aceita qualquer cadeia que possua uma ocorrência do símbolo `a`.

###### Caracteres Especiais

Quando for necessário buscar algo além de um padrão direto, como no caso se precisar encontrar uma ou mais ocorrências da letra 'b', ou encontrar um caracter de espaço, o padrão deverá utilizar caracteres especiais. Por exemplo, o padrão /ab*c/ selecionará qualquer combinação de caracteres que contenha o caractere 'a' seguido de zero ou mais caracteres 'b' (o caractere * seleciona zero ou mais ocorrências do item que o precede), seguido do caractere 'c'. Seguem vários exemplos de caracteres especiais que podem ser utilizados nas regexp.

+ .

Coincide com qqr caractere, exceto uma nov alinha.

```
/./
```

+ \s

Caractere de espaço em branco.

```
/a\sb/
```

+ \d 

Qualquer digito numerico.

```
/\d\d\d/
```

+ \w 

Qualquer caractere alfanumerico (letra ou numero).

```
/\w:\d/
```

+ ^ 

Aplica-se no início da entrada. Indica que a string deve iniciar com o padão (não pode ter nenhum texto antes do padrão).

```
/^abc/
```

+ $ 

Aplica-se no final da entrada. A string deve terminal com o padrão (não pode ter nenhum texto depois do padrão).

```
/abc$/
```

+ {  }

Os quantificadores permitem que as expressões regulares sejam escritas de modo muito mais consistente do que com metacaracteres apenas. Ao invés de repetir explicitamente os subpadrões, um quantificador pode especificar extamente quantas vezes um subpadrão pode aparecer. 

```
// Sem quantificador
/^\d\d\d\d\d-\d\d\d\d$/

// Com quantificador
/^\d{5}-\d{4}$/
```

O quantificador {} aceita um numero que determina quantas vezes um subpadrão pode aparecer em uma string. Há outra versão desse quantificador que requer dois números, que especifica o número mínimo e máximo de vezes que um subpadrão pode aparecer. Isso fornece uma maneira prática de ajustar a presença de um subpadrão.

```
// {min, max}
/^\w{5,8}$/
```

+ *

Coincide com qqr quantidade do caracter precedente, inclusive com uma string vazia.

```
/a*/
```

+ +

Coicide com um caracter precedente repetido uma ou mais vezes.

```
/a+/
```

+ \

Existem um caractere de escape que pode ser usado quando você deseja colocar um caractere que, por coincidência, já é um caracter especial. Em outras palavras, uma barra invertida que preceda um caractere não especial significa que o caractere seguinte é especial e não deve ser interpretado de forma literal. Quando a barra invertida preceder um caractere especial isso significará que o próximo caractere deve ser interpretado de forma literal.

```
/\^/
/\b/
```

+ |

Outro metacaractere muito útil na caixa de ferramentas da expressão regular é o metacaractere de alternação, que parece e funciona de modo muito parecido com o operador OR no JavaScript. Diferente do OR, o metacaractere de alternação envolve apenas uma barra vetical, mas permite um padrão para especificar uma lista de subpadrões alternativos. Em outras palavas, o padrão terá uma coicidência bem sucedida se qualquer um dos subpadrões alternativos coincidir.

```
este|aquele
um|outro
```

##### Exemplo de Expressões Regulares

####### Código Postal

Assumindo um código postal que segue o seguinte padrão #####-#### podemos criar uma expressão regular que represente o conjunto de todas as cadeias de entrada que um autômato iria aceitar.

```
/^\d\d\d\d\d-\d\d\d\d$/
```

No exemplo acima começamos escrevendo `/` para indicar o início da nossa expressão regular. Seguido da / temos o `^` para indicar que as cadeias que o autômato aceita são cadeias que devem necessariamente ter um início que esteja de acordo com o início da expressão regular. Depois seguimos com 5 `\d`\`s que indicam que teremos 5 dígitos seguidos. Depois temos um caracter simples, o `-`. Como qualquer caracter simples, ele não possui nenhum significado especial. Seguindo temos 4 `\d`\s, e por fim temos `$/`. O caracter `$` é parecido com `^` só que se refere ao final da cadeia. O `/` indica o final da expressão regular. Outra forma de escrever essa expressão regular seria a seguinte:

```
/^\d{5}-\d{4}$/
```

Desse exemplo tiramos a conclusão de que uma mesma expressão regular pode ser escrita de diversas formas distintas, assim como uma autômato.

####### Expressão Regular para datas

Assumimos agora que um campo de data deve seguir o padrão ##-##-#### ou ##-##-##. Nesse caso o campo de ano da data pode ser escrito com 2 caracteres ou com 4. Uma possível expressão que representaria nosso problema seria a seguinte:

```
/^d{2}\/\d{2}\/(\d{2}|\d{4})$/
```

####### Expressão Regular para o email

Por fim temos um exemplo que poderia ser usado para representar alguns emails que podemos ter.

```
/^\w+@+\.\w{2,3}$/
```

### Adicionando expressões regulares às páginas

Originalmente, as expressões regulares não tem relação alguma com a validação de dados. Podemos validar dados usando técnicas como testes ou podemos até mesmo validar se o usuário esqueceu de preencher um campo no formulário usando métodos do JavaScript. Podemos pensar nas expressões regulares como uma alternativa para a validação de dados, alternativa essa que é extremamente poderosa e enxuta.

Uma expressão regular no JavaScript é representada pelo objeto RegExp, que inclui um método chamado test() que é a chave para usar as expressões regulares para a validação dos dados. O método `test()` verifica a existência de um padrão dentro de uma string, caso o padrão seja satisfeito ele retorna true, caso contrário ele retorna false. Além do test existem outros como por exemplo o `exec`, `match`, `split`, e outros. Segue um exemplo da utilização do `test`.

```
var regex = /^\d{5}$/;

if(!regex.test(inputField.value)) {
	// o texto do input não corresponde ao valor que esperávamos
}
```

Embora possamos fazer uma chamada para o metodo test() dentro de cada função de validação diferente, há uma oportunidade para criar uma função de validacao geral baseada em expressões regulares que funções mais específicas poderão chamar para fazer o trabalho genérico de validação.

```
function validadeRegEx(regex, inputStr, helpText, helpMessage) {
	if(!regex.test(inputField.value)) {
		if(helpText != null) {
			helpText.innerHTML = helpMessage;
		}
		return false;
	} else {
		if(helpText != null) {
			helpText.innerHTML = "";
		}
		return true;
	}
}
```

### Debug

### JavaScript Design Patterns