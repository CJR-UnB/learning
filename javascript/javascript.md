![javascript](https://aspblogs.blob.core.windows.net/media/dwahlin/Media/JavaScript-logo.png)
# JavaScript  

### O que é JavaScript?

client side
exemplos

### Histórico

### Domínio de Aplicação

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
```.sort``` (ordena em ordem alfabética).
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

### Expressões Regulares

### Orientação de Objetos

literais de objetos
prototipo

+ Objetos Nativos

+ Objetos de Host

### JSON

### Manipulação do DOM

innerHtml
getElementById

### Debug

### Validação de Dados

	dar uma lida no capitulo do livro 

### JavaScript Design Patterns
