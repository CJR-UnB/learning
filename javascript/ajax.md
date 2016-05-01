# Introduction to AJAX
AJAX (Asynchronous JavaScript And XML) é basicamente uma tecnologia criada para permitir carregamento em segundo plano de certas partes do script, assim não tendo que esperar que uma parte do script ocorra para iniciar a próxima. A maior implicação disso é um dinamismo muito maior em sites. 
Falando em termos mais "computacionais", digamos assim, seu código JavaScript continua normal, com o servidor respondendo cada solicitação  exatamente como fazia antes de usar AJAX. Porém a resposta do servidor agora retornará apenas os dados que a página precisa sem qualquer marcação ou apresentação. Aos olhos de quem está acessando a página, vai apenas perceber que grande parte da página não foi alterada quando algo foi solicitado, mas sim partes que necessitaram de atualização. Antigamente a página inteira era carregada, porém AJAX muda esse paradigma.
Para aprender, só precisará de duas coisas:  
> HTML
> JavaScript

## Let's Start

A essência do AJAX mora no XMLHttpRequest Object. Esse nome lindo se refere ao objeto usado para trocar dados com o servidor (em segundo plano). Isso que torna possível atualizar somente parte da página. Quanto a portabilidade disso, todos os navegadores atuais suportam eles, então relaxe.

##Criando um XMLHttpRequest Object

Para criar  XMLHttpRequest object é simples como:
```javascript
variable = new XMLHttpRequest();
```
##Pedindo Informação para o Servidor

É necessário o uso da função _xhttp.open()_ para estabelecer o que será enviado para o servidor, ela tem 3 argumentos:  
+ método: "GET" ou "POST".
+ url: localização de um arquivo no servidor (pode ser .txt, .asap, .xml, .php, entre outros), sabendo que alguns desses arquivos podem realizar ações antes da resposta do servidor.
+ Assíncrono: true ou false (true para realizar um pedido assíncrono e false para um não assíncrono).  
Também é necessário o uso de _xhttp.send()_.  Ele é quem envia o que o _xhttp.open()_ preparou. Só possui argumento se foi usado POST e o argumento é uma _string_.

Então para solicitar algo ao servidor basta usar:
```javascript
xhttp.open("GET", "ajax_info.txt", true);
xhttp.send();
```
No primeiro argumento de _xhttp.open()_, usa-se GET ou POST. 
GET quando a informação não é confidencial e é necessário que seja rápido (mais usado com arquivos pequenos). 
POST quando é necessário esconder a informação do usuário ou mandar um arquivo relativamente grande (ele é mais confiável). 

###GET Request

Usando dessa maneira, GET mantém o arquivo guardado no cache do navegador.
```javascript
xhttp.open("GET", "demo_get.asp", true);
xhttp.send();
```
Usando desse outra maneira, evita-se isso.
```javascript
xhttp.open("GET", "demo_get.asp?t=" + Math.random(), true);
xhttp.send();
```
Para mandar informações, adicione elas a URL.
```javascript
xhttp.open("GET", "demo_get2.asp?fname=Billy&lname=Joshua", true);
xhttp.send();
```

###POST Request

O jeito mais simples de realizar um POST Request é:
```javascript
xhttp.open("POST", "demo_post.asp", true);
xhttp.send();
```
Mas caso queira enviar dados como um form HTML, adicione o HTTP Header usando _setRequestHeader()_ (dois argumentos: nome do header e o seu valor). Use antes de _xhttp.send()_ e coloque nele os dados que quer enviar.
```javascript
xhttp.open("POST", "ajax_test.asp", true);
xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
xhttp.send("fname=Henry&lname=Ford");
```

###Assíncrono -> true

Ao usar true, XMLHttpRequest Object se comporta como AJAX. É possível especificar uma função para executar quando a resposta estiver pronta. Não se preocupe agora com _onreadystatechange_, voltaremos a ele.  
```javascript
xhttp.onreadystatechange = function() {
  if (xhttp.readyState == 4 && xhttp.status == 200) {
    document.getElementById("demo").innerHTML = xhttp.responseText;
  }
};
xhttp.open("GET", "ajax_info.txt", true);
xhttp.send();
```

###Assíncrono -> false

Assim, o código deixa de se comportar como AJAX e começa a esperar o servidor responder para continuar. Nesse caso não se usa  _onreadystatechange_ e sim a função logo abaixo.
```javascript
xhttp.open("GET", "ajax_info.txt", false);
xhttp.send();
document.getElementById("demo").innerHTML = xhttp.responseText;
```

##Resposta do Servidor

É possível receber a resposta do servidor de duas formas, como uma _string_ ou como um dado XML, respectivamente _responseText_ e _responseXML_. 
Exemplo _responseText_:
```javascript
document.getElementById("demo").innerHTML = xhttp.responseText;
```
Exemplo _responseXML_:
```javascript
xmlDoc = xhttp.responseXML;
txt = "";
x = xmlDoc.getElementsByTagName("ARTIST");
for (i = 0; i < x.length; i++){
  txt += x[i].childNodes[0].nodeValue + "<br>";
 }
document.getElementById("demo").innerHTML = txt;
```
Obs:  Quando o resposta do servidor for em XML, use das propriedades de _responseXML_ e o transforme em objeto XML. "childNodes[]" são os nodos filho do elemento atual no DOM.

## Evento onreadystatechange



Três pripriedades importantes do Objeto XMLHttpRequest são:
+ readyState: possui o estado do XMLHttpRequest. Possui valores de 0 a 4 (0: Request não realizado; 1: conexão com o servidor feita; 2: Request recebido; 3: processando Request; 4: Request terminado e resposta pronta).
+ onreadystatechange: é capaz de armazenar em si uma função que é ativada toda vez que readyState muda.
+ status: 200 significa "OK" e 404 "página não encontrada"


```javascript
function loadDoc() {
  var xhttp = new XMLHttpRequest();
  xhttp.onreadystatechange = function() {
  if (xhttp.readyState == 4 && xhttp.status == 200) {
    document.getElementById("demo").innerHTML = xhttp.responseText;
  }
};
```
Obs: por executar toda vez que readyStatus muda (ou seja, cinco vezes) que a função começa com um if deixando passar somente quando readyState for 4 e status for 200, ou seja, a resposta esta pronta para ser processada e não temos problema com o status da página.

### Função Callback 

É quando se passa uma função como argumento. Bastante útil e auxilia na manutenabilidade do código. Se usar mais de uma vez AJAX no código, crie uma função padrão para criar o Objeto XMLHttpRequest para ser reusada.

```javascript
function loadDoc(cFunc) {
  var xhttp = new XMLHttpRequest();
  xhttp.onreadystatechange = function() {
  if (xhttp.readyState == 4 && xhttp.status == 200) {
    cFunc(xhttp);
  }
```

## Exemplos

### Exemplo de Database

Um uso bastante interessante seria buscar informações específicas da database. Seria possível montar um seletor que mostrasse todas as informações do membro selecionado. A partir dos conhecimentos adquiridos, tente entender como a função abaixo funciona.

```javascript
function showCJRMember(str) {
  var xhttp; 
  if (str == "") {
    document.getElementById("txtHint").innerHTML = "";
    return;
  }
  xhttp = new XMLHttpRequest();
  xhttp.onreadystatechange = function() {
    if (xhttp.readyState == 4 && xhttp.status == 200) {
    document.getElementById("txtHint").innerHTML = xhttp.responseText;
    }
  };
  xhttp.open("GET", "getmember.asp?q="+str, true);
  xhttp.send();
}
```

+ Checa se o membro foi selecionado.
+ Cria um objeto XMLHttpRequest.
+ Cria uma função e a atribui ao evento _onreadystatechange_.
+ Pede informação para o servidor. Note que a informação colocada no form é adicionada na URL.

--------

### Exemplo de XML

XML permite uma compilação de informações grande. Um uso bom dele seria para pegar uma grande quantidade de informações como o nome de todos os membros da CJR. A partir dos conhecimentos adquiridos, tente entender como a função abaixo funciona.
```javascript
function loadDoc() {
  var xhttp = new XMLHttpRequest();
  xhttp.onreadystatechange = function() {
    if (xhttp.readyState == 4 && xhttp.status == 200) {
    myFunction(xhttp);
    }
  };
  xhttp.open("GET", "cd_catalog.xml", true);
  xhttp.send();
}
function myFunction(xml) {
  var i;
  var xmlDoc = xml.responseXML;
  var table="<tr><th>Artist</th><th>Title</th></tr>";
  var x = xmlDoc.getElementsByTagName("CD");
  for (i = 0; i <x.length; i++) { 
    table += "<tr><td>" +
    x[i].getElementsByTagName("ARTIST")[0].childNodes[0].nodeValue +
    "</td><td>" +
    x[i].getElementsByTagName("TITLE")[0].childNodes[0].nodeValue +
    "</td></tr>";
  }
  document.getElementById("demo").innerHTML = table;
}
```
+ Cria um objeto XMLHttpRequest.
+ Na quinta execução do _onreadystatechange_ chama uma função.
+ Pega a resposta em XML e começa a extrair as informações que interessam e cria uma string para ser mostrada ao usuário final.

Caso queira saber como é dentro de um arquivo XML aqui está um [exemplo](http://www.w3schools.com/ajax/cd_catalog.xml).

--------

**Para mais exemplos, [clique aqui](http://www.w3schools.com/ajax/ajax_examples.asp).**

##Referências

[w3schools.com](http://www.w3schools.com/ajax/default.asp)