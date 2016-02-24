<!-- **************************
							HTML
 ************************** -->

# HTML
	
### O que é HTML(HyperText Markup Language) e qual sua utilidade?
		
O HTML é uma linguagem de marcação utilizada na construção de páginas Web. Ele é a responsável por definir a estrutura das suas páginas. Para que as páginas possam ser exibidas, é necessário que tenhamos algum software capaz de ler esses arquivos HTML e interpretá-los gerando um output visual para o usuário. É ai que entram os Web Browsers.

O HTML pode ser estruturado a partir de dois pilares, o __hipertexto__ e a __marcação__. 

##### Hipertexto

É um texto ao qual se agregam outros conjuntos de informações. Ele facilita a navegação dos internautas. Na web, um texto pode ter diversas palavras que, ao serem clicadas, são remetidos para outra página onde se esclarece com mais precisão o assunto do link anterior.

##### Marcação
	
Não adianta nada linkar e relacionar informações na web se essas informações não tiverem significado. Os browsers precisam de ajuda para diferenciar um parágrafo de um título Marcação 
	
### Web Browsers
		
Para entender como browsers funcionam é preciso que saibamos alguns conceitos básicos:
	
##### Servidor Web
				
Um servidor nada mais é do que um programa que fornece serviços. Um dos serviços que um servidor Web provê é aceitar pedidos, geralmente de navegadores, e servi-los com respostas. O servidor mais popular e mais utilizado é o servidor Apache.
			
##### Protocolo
				
Um protocolo pode ser definido como um conjunto de regras que governam a sintaxe e a semântica envolvidas na comunicação entre duas ou mais entidades. Dentre os protocolos famosos temos os seguintes:

+ HTTP (Hypertext Transfer Protocol)

	É um protocolo de comunicação utilizado na troca ou transferencia de hipertexto.Esse protocolo utiliza o modelo cliente-servidor, como a maioria dos protocolos de rede, baseando-se no paradigma de requisição e resposta. Um programa requisitante (cliente) estabelece uma conexão com um outro programa receptor (servidor) e envia-lhe uma requisição.

+ FTP (File Transfer Protocol)

	Seu uso possibilita uma forma rápido e versátil de tranferir arquivos sendo uma das mais usadas na Internet. A transferência de arquivos dá-se entre um computador chamado "cliente" (aquele que solicita a conexão para a transferência de dados) e um servidor (aquele que recebe a solicitação de transferência). O utilizador, através de software específico, pode selecionar quais arquivos enviar ou receber do servidor. Para existir uma conexão ao servidor,caso o servidor exija, o utilizador informa um nome de utilizador e uma senha password, bem como o nome correcto do servidor ou seu endereço IP. Se os dados foram informados corretamente, a conexão pode ser estabelecida.

##### Como os Web Browsers funcionam?

Os navegadores apresentam conteúdo escolhido pelos desenvolvedores por meio de uma solicitação ao servidor. Um dos conteúdos mais comuns escolhido é um documento HTML. A forma como o navegador interpreta e exibe arquivos HTML é apresentadas nas especificações de HTML e CSS. Essas especificações são mantidas pelo W3C (Consórcio World Wide Web), a organização que controla os padrões para a web. Por muitos anos, os navegadores mantiveram-se parcialmente de acordo com as especificações e desenvolveram as próprias extensões. Isso causou sérios problemas de compatibilidade para autores da web. Hoje a maioria dos navegadores está relativamente de acordo com as especificações.

<!-- Web browsers comunicam-se com servidores Web usando, geralmente, o protocolo de transferência de hiper-texto HTTP. Qualquer aplicação que se comunica com um web server pode ser chamada de web client. -->
			
+ WebSockets

http:// www.blabla.com / blublublu.html
			
+ directory tree

web client sends request
web server sends response

+ plain-text vs hiper-text

o hiper-texto funcionava da seguinte forma: se vc clicar em uma palavra, são mostrador detalhes sobre aquela palavra.
send http request get http response
url -> uniform resource locator
http é um protocolo que usa TCP

A forma como o navegador interpreta e exibe arquivos HTML é apresentadas nas especificações de HTML e CSS. Essas especificações são mantidas pelo W3C (Consórcio World Wide Web), a organização que controla os padrões para a web. 
Por muitos anos, os navegadores mantiveram-se parcialmente de acordo com as especificações e desenvolveram as próprias extensões. Isso causou sérios problemas de compatibilidade para autores da web. Hoje a maioria dos navegadores está relativamente de acordo com as especificações

### Histórico

Guerra dos Navegadores

	
### O que são tags HTML?

`<nomedatag atributos>conteudodatag</nomedatag>`
Diferentes versões
	HTML / HTML 2.0 / HTML 3.2 / HTML 4.01 / XHTML / HTML5 

### Primeira linha
		
`<!DOCTYPE html>`
	
### Tags HTML

##### Html

O texto dentro dessa tag descreve o conteúdo HTML do documento.

`<html></html>`

##### Head

Essa tag é usada para prover informações sobre o documento.

`<head></head>`

##### Body

Essa tag é usada para definir o conteúdo visível para o usuário.

`<body></body>`

##### Comment

O texto dentro dessa tag não é interpretado pelo browser, sua única utilidade é documentar o código em desenvolvimento para facilitar o entendimento.

`<!-- ... -->`

##### Meta

Essa tag define metadados. Metadados são dados sobre outros dados, ou seja, um item de um metadado pode dizer do que se trata aquele dado, geralmente uma informação inteligível por um computador. Os metadados facilitam o entendimento dos relacionamentos e a utilidade das informações dos dados. Eles não são renderizados na página.
Tais elementos costumam ser usados para especificar uma descrição, keywords, autores do documento, e outros metadados. Os metadados podem ser usados pelos browsers e por serach engines.

Obs: Metatags são sempre usadas dentro da <head>

```
<meta>
<meta charset="UTF-8">
<meta name="description" content="tutorial">
<meta name="keywords" content="HTML">
<meta name="author" content="luiz">
```

##### Title

Essa tag define um título que será mostrado na toolbar e que será usado pelas search-engines.

`<title>Titulo</title>`

##### Heading

Essas tag são usadas para definir os headings. A tag `<h1>` corresponde ao maior heading, enquanto a tag `<h6>` corresponde ao menor.

```
<h1></h1>
<h2></h2>
<h3></h3>
<h4></h4>
<h5></h5>
<h6></h6>
```

##### Paragraph

Essas tag são usadas para representar parágrafos.

`<p></p>`

##### Break

Essa tag é utilizada para quebrar a linha.

Obs: No HTML a tag `<br>` nao tem a `/`, no XHTML a tag é escrita com a `/`. Seguem ambas:

`<br> vs <br/>`

##### Hr

Essa tag adiciona uma linha que serve como divisor dos conteúdos na sua página.

`<hr> vs <hr/>`

##### Anchor

Essas ancoras permitem que o usuário navegue entre diversas páginas ao clicá-las. Elas são uma das tags mais importantes e usadas no HTML.

```
<a></a>
<a href="url">link</a>
```

##### Form

Essas tags permitem coletar inputs dos usuários. Dentro delas podemos definir outras tags como por exemplo checkboxes, radio buttons, submit buttons, e outros. Dentre os diversos elementos que podemos adicionar dentro de um form, o mais utilizado é o `<input>` que será mostrado mais adiante. Segue um exemplo da sintaxe da tag:

```
<form>
	<!-- form elements -->
</form>
```

##### Input

A tag input adiciona um campo no qual o usuário pode adicionar dados. Eles são usados dentro de tags `<form>` como explicado anteriormente.

```
<form>
	First name: <input type="text"><br>
	Last name: <input type="text"><br>
</form>
```

##### TextArea

Essa tag define um texto que pode possuir várias linhas. Podemos colocar um numero ilimitado de characters dentro dessas textareas.

```
<textarea>
	Muito texto texto texto texto texto
	texto texto texto texto texto texto
	texto texto texto texto texto texto
</textarea>
```

##### Button

A tag `button` define botões clicáveis. Podemos adicionar elementos como texto e imagens dentro dessas tags.

Obs: Sempre coloque o atributo `type` dentro do elemento `button`.

```
<button type="button">
	Click!!!
</button>
```

##### Select & Option

A tag `<select>` é usada para criar uma lista drop-down, e a tag `<option>` disponibiliza as opções que o usuário pode escolher dentro daquela lista drop-down.

```
<select>
	<option value="oi">Oi</option>
	<option value="tim">Tim</option>
	<option value="vivo">Vivo</option>
	<option value="claro">Claro</option>
</select>
```

##### Label

A tag `<label>` costuma ser usada como label para um campo de input.

```
<form>
	<label for="firstname">Firstname: </label><input type="text"><br>
	<label for="firstname">Last name: </label><input type="text"><br>
</form>
```

##### Img

Define uma imagem que será mostrada no navegador do usuário. Essa tag é usada com dois outros atributos, o src e o alt.

```
<img src="path_da_imagem.png" alt="texto_caso_nao_carregue">
```

##### Span

A tag span é uma pouco diferente das demais tags vistas até aqui. Ela por si não apresenta nenhuma mudança visível ao documento. Apesar do q foi dito, ela pode ser usada para diferentes propósitos. O mais comum é usá-la como hook para uma determinada parte do documento relacionando-a com o Javascript e o CSS.

```
<p><span>Texto</span></p>
```

Obs: O `<span>` é muito parecido com o elemento `<div>` , entretando `<div>` é um elemento de nível de bloco enquanto `<span>` é um elemento em linha.


##### Div

Essa tag é muito utilizada. Ela define um divisor para diferentes seções do documento HTML. Ela é usada para agrupar em nível de bloco os elementos. Geralmente ela está relacionada diretamente a uma classe CSS.

Obs: Se possível evite o uso da tag. É sempre preverível que as tags do HTML5 seram utilizadas se fizerem sentido naquele contexto pois elas são mais semanticas.

```
<div>
	<p>Texto</p>
</div>
```

##### Unordered List

Como o próprio nome ja diz, a tag define uma lista não ordenada. Essa lista é mostrada com "bolinhas" ao invés de números.

```
<ul>
	<li>html</li>
	<li>css</li>
	<li>js</li>
</ul>
```

##### Ordered List

Parecia com a unordered list mas mostra o número dos elementos da lista, ou seja, se aquele for o primeiro elemento da lista será mostrado o número 1 ao lado dele.

```
<ol>
	<li>html</li>
	<li>css</li>
	<li>js</li>
</ol>
```

##### List Item

Essa tag é usada dentro das tags `<ol>` e `<ul>` para representar os diversos itens que podem estar contidos dentro dessas listas.

```
<ul>
	<li>typescript</li>
	<li>coffeescript</li>
	<li>javascript</li>
</ul>
```

```
<ol>
	<li>typescript</li>
	<li>coffescript</li>
	<li>javascript</li>
</ol>
```

##### Table, Table Headings, Table Row, Table Data

O elemento Table é usado para representar dados em duas dimensões. Ele cria uma tabela que pode ter diversas row representadas pela tag `<tr>` com vários dados representados pela tag `<td>`. É possível adicionar headings que mostram o que o dado na coluna X especifica, e para isso usamos a tag `<th>`.

```
<table>
	<tr>
		<th>Nome</th>
		<th>País</th>
	</tr>
	<tr>
		<td>Luiz</td>
		<td>Brasil</td>
	</tr>
</table>
```

##### Table Head, Table Body, Table Footer

É interessante podermos separar cada setor da tabela em diferentes tags para aumentar a legibilidade do código. Por isso temos tags como `<thead> <tbody> <tfoot>`. A `<thead>` especifica a primeira row da nossa tabela e é nela que colocamos o significado das colunas. A `<tbody>` agrupa os dados da tabela (`<td>`). Já a `<tfoot>` além de aceitar os `<td>` é localizada na ultima row da tabela.

```
<table>
  <thead>
  <tr>
    <th>Month</th>
    <th>Savings</th>
  </tr>
  </thead>
  <tfoot>
  <tr>
    <td>Sum</td>
    <td>$180</td>
  </tr>
  </tfoot>
  <tbody>
  <tr>
    <td>January</td>
    <td>$100</td>
  </tr>
  <tr>
    <td>February</td>
    <td>$80</td>
  </tr>
  </tbody>
</table>
```

### Tags HTML5

##### Header

Essa tag é usada para marcar o cabeçalho de uma página. Justamente por isso ela costuma ser escrita junto da tag `<h1>` que indica um título. 

```
<header>
	<h1>Titulo</h1>
</header>
```

##### Footer

Essa tag geralmente destina-se a marcar o rodapé de uma seção ou da página como um todo. É bastante comum colocarmos nome do autor, links relacionados ao tema, direitos autorais, e outros. Uma página pode ter diversos redapés. Seguem exemplos do footer como rodapé da uma seção e de uma página, respectivamente.
	
```
	<section>
		<article>
			<!-- ... -->
			<footer>
			</footer>
		</article>
	</section>
```

```
	<section>
		<article>
		</article>
	</section>
	<footer>
	</footer>
```

##### Main

Essa tag define o main content do documento. Dentro dela não deve-se colocar conteúdo que será reutilizado durante o desenvolvimento, como por exemplo: sidebars, navigation links, logos, e outros.

```
<main>
	<h1> Titulo </h1>
	<article>
		<!-- ... -->
	</article>
	<article>
		<!-- ... -->
	</article>
</main>
```

##### Nav

Essa tag é usada para definir links para outras páginas ou links para outros locais daquela mesma página. Não devemos colocar nav em tm todos os links, apenas nos grandes agrupamentos de links.

```
<nav>
	<ul>
		<li><a href="">1</a></li>
		<li><a href="">2</a></li>
		<li><a href="">3</a></li>
	</ul>
</nav>
```

##### Section

Essa tag é usada para marcar uma seção na página. Entende-se como seção um grupamento de conteúdos tratando de um mesmo tema e tipicamente contendo um cabeçalho. São exemplos de seções capítulos de um livro, abras de uma caixa de diálogo, informações de contato. 

Obs: Não deve se considerar o elemento section como um container gen´rico. Quando precisamos de um elemento container gen´rico a ser usado para fins de estilização ou para ser manipulado por script, devemos empregar o elemento div.

```
<section>
	<h1>nome: Luiz</h1>
	<p>telefone: 9999-9999</p>
</section>
```

##### Article

Essa tag é usada para marcar um conteúdo autossuficiente em uma página. O conteúdo marcado é reusável e pode ser distribuiído de forma independente. Alguns exemplos de conteúdos para serem marcados com esse elemento são: um post em um fórum, um artigo em uma revista, e outros.

```
<article>
  <h1>Teste</h1>
  <p>Teste teste teste teste</p>
</article>
```

##### Figure & Figcaption

Enquanto o elemento figure serve como um container para conteúdos relacionados como por exemplo imagens, ilustrações, diagramas, fotos, vídeos o elemento figcaption destina-se a marcar uma legnda para o conteúdo inserido com uso do elemento figure. Segue um exemplo com ambos:

```
<figure>
  <img src="teste.jpg" alt="teste">
  <figcaption>Fig1. - Primeira Figura.</figcaption>
</figure>
```
