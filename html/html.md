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
	
Não adianta nada linkar e relacionar informações na web se essas informações não tiverem significado. Os browsers precisam de ajuda para diferenciar um parágrafo de um título, e é ai que vem a marcação. Ela inclui tags que possibilitam a diferenciação dos elementos da página.
	
### Web Browsers
		
Para entender como browsers funcionam é preciso que saibamos alguns conceitos básicos:
	
##### Servidor Web
				
Um servidor nada mais é do que um programa que fornece serviços. Um dos serviços que um servidor Web provê é aceitar pedidos, geralmente de navegadores, e servi-los com respostas. O servidor mais popular e mais utilizado é o servidor Apache.
			
##### Protocolo
				
Um protocolo pode ser definido como um conjunto de regras que governam a sintaxe e a semântica envolvidas na comunicação entre duas ou mais entidades. Dentre os protocolos famosos temos os seguintes:

+ HTTP (Hypertext Transfer Protocol)

	É um protocolo de comunicação utilizado na troca ou transferencia de hipertexto. Esse protocolo utiliza o modelo cliente-servidor, como a maioria dos protocolos de rede, baseando-se no paradigma de requisição e resposta. Um programa requisitante (cliente) estabelece uma conexão com um outro programa receptor (servidor) e envia-lhe uma requisição.

+ FTP (File Transfer Protocol)

	Seu uso possibilita uma forma rápido e versátil de tranferir arquivos sendo uma das mais usadas na Internet. A transferência de arquivos dá-se entre um computador chamado "cliente" (aquele que solicita a conexão para a transferência de dados) e um servidor (aquele que recebe a solicitação de transferência). O utilizador, através de software específico, pode selecionar quais arquivos enviar ou receber do servidor. Para existir uma conexão ao servidor, caso o servidor exija, o utilizador informa um nome de utilizador e uma senha password, bem como o nome correto do servidor ou seu endereço IP. Se os dados foram informados corretamente, a conexão pode ser estabelecida.

##### Como os Web Browsers funcionam?

Os navegadores apresentam conteúdo escolhido pelos desenvolvedores por meio de uma solicitação ao servidor. Um dos conteúdos mais comuns escolhido é um documento HTML. A forma como o navegador interpreta e exibe arquivos HTML é apresentadas nas especificações do HTML e do CSS. Essas especificações são mantidas pelo W3C (Consórcio World Wide Web), a organização que controla os padrões para a web. Por muitos anos, os navegadores mantiveram-se parcialmente de acordo com as especificações e desenvolveram as próprias extensões. Isso causou sérios problemas de compatibilidade para autores da web. Hoje a maioria dos navegadores está relativamente de acordo com as especificações.
			
### Histórico

##### Guerra dos Navegadores

O primeiro navegador criado foi o WorldWideWeb em 1990. Tal navegador mostrava os dados de forma textual, ou seja, as interfaces daquela época eram completamente diferente daquilo que vemos hoje. Esse navegador rodava em cima da sistema NeXTSTEP (sistema operacional que foi criado por Stave Jobs). Um fato curioso é que este sistema foi comprado pela Apple e foi usado como base para seu nome sistema operacional, o famoso Mac OS X.

A Web, entretanto, só explodiu realmente em com a introdução do NCSA Mosaic, que era um navegador gráfico (em oposição a navegadores de modo texto). Esse navegador foi o primeiro navegador a rodar no sistema operacional Windows. Marc Andreessen, o líder do time que desenvolveu o Mosaic, saiu da NCSA e, com Jim Clark, um dos fundadores da Silicon Graphics, Inc. (SGI) e outros quatro estudantes formados e nomeados da Universidade de Illinois, iniciaram o Mosaic Communications Corporation. Mosaic Communications finalmente se tornou a Netscape Communications Corporation, produzindo o Netscape Navigator.

A Netscape lançou o seu produto líder Navigator em Outubro de 1994, e este tornou-se o mais popular navegador no ano seguinte. A Microsoft, que até então havia ignorado a Internet, entrou na briga com o seu Internet Explorer, comprado às pressas da Splyglass Inc. Isso marca o início da Guerra dos Browsers, que foi a luta pelo mercado dessas aplicações entre a gigante Microsoft e a companhia menor largamente responsável pela popularização da Web, a Netscape.

A microsoft estava acabando com a netscape até que a netscape disponibilizou o codigo fonte do seu navegador e nomeou o produto mozilla. Quando Bill Gater e a Microsoft viram que aquela era uma possível ameaça decidiram deixar seu navegador gratuito. Por essa e outras atitudes a Microsoft foi acusada de práticas ilegais para iludir usuários a usar seu navegador.

Enquanto isso, o time do mozila sofria porque os desenvolvedores nao tinham tempo de reler todas as linhas do codigo para garantir que não haviam bugs no código. Além disso nem todo os membros da empresa estavam familiarizados como todo o código, logo, não tinham conhecimento para consertar possíveis bugs de funcionalidades que eles não dominavas. Daí a manutenção ficou dificultada.

Quando o o código estava quase pronto para ser disponibilizado para o público a netscape teve de explicar a importância daquele projeto para a emprensa. O sonho era que aquele projeto fosse visto da mesma forma e com o mesmo entusiasmo de quando a empresa entrou no mercado.

Outro fator que dificultou o lançamento do mozilla para o público foi o fato de que um pequeno pedaço de código da Apple foi utilizado, e esse pedaço nao havia sido liberado para public license. Os programadores tiveram que substituir aquela parte do código da Apple pelo seu proprio código para poder disponibilizar o navegador ao público. No fim a Apple até permitiu que usassem o código regular.

Em 95 os stocks da netscape subiram para 108% do valor inicial. Mas mesmo assim os problemas continuaram. A netscape não tinha um framework para escrever o software, eles apensar escreviam tudo sem muito planejamento. Quando o source foi finalmente liberado um rapaz de 16 anos olhou o código e ficou apavorado com o quão confuso e mal feito aquilo era. Por isso ele decidiu refazer o codigo do zero.

Pouco depois, quando a microsoft decidiu investir em internet, os stocks da netscape cairam. O mercado do browser que antes era a maior fonte de renda da empresa se tornou um dos menos lucrativos, dai tiveram que investir em outras coisas. Foi em 1998 que a microsoft foi culpada de ter praticado ilegalmente táticas de mercado. A justiça americana considerou a prática de agregação do internet explorer ao sistema operacional Windows uma pratica monopolista e ilegal. No entanto, a decisão veio muito tarde para a Netscape que já não era tão forte como anteriormente e seu código havia se tornado gigantesco. Com poucas pessoas para arrumar os bugs os empregados tiveram que trabalhar cada vez mais para manter a idéia viva.

Quando notaram que a briga estava praticamente perdida venderam a empresa para outra chamada AOL (American on line). Muitos dos empregados da netscape se recusaram a trabalhar para a AOL e saíram. Quando a compra da empresa foi finalizada, em 99, as ações da netscape mais que duplicaram. Curioso que enquanto muitos executivos venderam seus stocks quando a netscape chegou ao seu ultimo ano outros ganharam uma fortuna.

Por volta de Junho de 2002, o projeto Mozilla havia produzido um navegador útil e conformante com os padrões web, que funcionava em múltiplos sistemas operacionais incluindo Linux, Mac OS, Windows e Solaris. A versão 1.0 do Mozilla, liberada em 5 de Junho de 2002 foi elogiada por introduzir características que nem mesmo no seu rival, o Internet Explorer, possuía, incluindo um suporte melhor para as preferências de privacidade do usuário e algumas melhorias na interface gráfica. Adicionalmente, o navegador tornou-se a implementação de referência de facto dos vários padrões do World Wide Web Consortium, devido ao seu forte suporte aos mesmos.

Em 5 de Julho de 2003, a AOL anunciou que fecharia a sua divisão de navegadores, o que, em essência, era o Mozilla. Longe de ser o fim da platafoma, este foi o começo da Fundação Mozilla, formada por ex-veteranos da Netscape/Mozilla que tomaram sobre si a responsabilidade do desenvolvimento do projeto. Como consolação, a AOL prometeu investir 2 milhões de dólares da recém-formada fundação.

Mozilla, um produto que originalmente visava desenvolvedores ao invés de usuários finais, agora enfrenta o desafio do marketing para as massas. Dentre os diversos browsers que a Fundação desenvolveu o browser Mozilla Firefox se destacou. Hoje cerca de 19,25% de todos os usuários da Internet do mundo utilizam o Firefox, sendo o terceiro navegador mais utilizado no mundo, atrás do Google Chrome que aparece com 49,18% dos usuários, e do Internet Explorer que aparece com 22,62%

### O que são tags HTML?

`<nomedatag atributos>conteudodatag</nomedatag>`
Diferentes versões
	HTML / HTML 2.0 / HTML 3.2 / HTML 4.01 / XHTML / HTML5 

### Primeira linha

Para começar é recomendado um editor de texto. Alguns editores recomendados são: Sublime Text, Atom, Brakets, etc. Você deve salvar seu arquivo como .html. Ao adicionar essa extensão ao seu arquivo passará a ser possível clicar em cima do mesmo para abrir aquele arquivo. Aquele arquivo clicado será aberto em seu navegador default e será mostrado para o usuário o resultado daquilo que foi adicionado ao seu arquivo HTML pelo editor.
		
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
