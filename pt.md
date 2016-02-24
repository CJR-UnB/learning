# HTML
	
+ O que é HTML e qual sua utilidade?
		
HTML é uma linguagem de marcação utilizada na construção de páginas Web. HTML é uma abreviação de HyperText Markup Language. Documentos HTML podem ser interpretados por navegadores, ou seja, código escrito em HTML é entendido por browsers.
O HTML é o foco de tudo que se faz em desenvolvimento web. Seus dois pilares são o hipertexto e a marcação. O hipertexto é um texto ao qual se agregam outros conjuntos de informação. Hipertexto é uma ligação que facilita a navegação dos internautas. Um texto pode ter diversas palavras que, ao serem clicados, são remetidos para outra página onde se esclarece com mais precisão o assunto do link anterior. Marcação 
	
+ Web Browsers
		
Para entender como browsers funcionam é preciso que saibamos alguns conceitos básicos:
	
+ Servidor Web
				
Um servidor nada mais é do que um programa que fornece serviços. Um dos serviços que um servidor Web provê é aceitar pedidos, geralmente de navegadores, e servi-los com respostas. O servidor mais popular e mais utilizado é o servidor Apache.
			
+ Protocolo
				
Um protocolo pode ser definido como um conjunto de regras que governam a sintaxe e a semântica envolvidas na comunicação entre duas ou mais entidades.

+ E como funcionam os web browsers? 

Web browsers comunicam-se com servidores Web usando, geralmente, o protocolo de transferência de hiper-texto HTTP. Qualquer aplicação que se comunica com um web server pode ser chamada de web client.
		
+ protocol

+ HTTP
			
+ FTP
			
=======
<!-- **************************
							GIT
 ************************** -->

# Git

+ O que é git?

+ O que é github?

+ Repositórios

+ Branch

+ Git ignore

###Comandos Básicos

Inicializa repositório git: 
`$ git init`

Clona o repositório remoto para sua máquina:
`git clone`

Adiciona os arquivos não monitorados:
`git add`

Salva as auterações que foram monitoradas e identifica esse número:
`git commit`

Pega todas as auterações locais commitadas e coloca no repositório remoto:
`git push`

Pega os arquivos ainda não atualizados no repositório local:
`git pull`

Muda de branch:
`git checkout`

Cria um novo branch e muda pra ele:
`git checkout -b <nome_do_branch>`

Faz uma requisição de merge com o branch selecionada:
`pull request`

Problemas identificados no repositório. Lá é criado um fórum para discussão:
`issues`

Para de monitorar um arquivo no repositório e apaga ele:
`git rm`

Faz a gestão de URLs onde é direcionado ao repositório remoto:
`git remote`

### Links Uteis

[Roger Dudler](http://rogerdudler.github.io/git-guide/)
[Atlassian](https://www.atlassian.com/git/tutorials/)

<!-- **************************
							HEROKU
 ************************** -->

# Heroku

+ O que é Heroku?

+ Subindo a Aplicação

+ Comandos Básicos

+ O Bug da Root
  
+ rake asset:precompile

+ Atributos

`src`
`data-*`

# CSS

# Javascript

# Git

# Ruby

# Ruby on Rails

# SQL

# Ferramentas

## Heroku

## Taiga

## Trello

## Slack


https://www.youtube.com/watch?v=aor29pGhlFE
https://www.youtube.com/watch?v=RsQ1tFLwldY






Atributos

https://www.youtube.com/watch?v=aor29pGhlFE
https://www.youtube.com/watch?v=RsQ1tFLwldY

# CSS

### Especificidade

### O que são seletores?

### Como seletores são interpretados?

### Seletores CSS

### O que são Id's?

### Classes

### Tags

### Não use ID's como seletor

### Propriedades básicas

`width`
`max-width`
`min-width`
`height`
`max-height`
`min-height`
`margin`
`background`
`color`
`text-decoration`
`padding`
`border`
`display`

### Media Query

### OOCSS

	Separar estrutura e skin
		Repetir caracteristica visual como skin que pode ser combinada em uma variada gama de objetos por exemplo background e estilos de borda
	Separar container de conteúdo
		Um objeto deve permanecer igual independente da sua localizacao na pagina, ou seja, nao queremos que as classes pai do css influenciem as classes filho

### SMACSS

### BEM

### Flex-box

# JavaScript

### O que é JavaScript?

client side
exemplos

### Histórico

### Domínio de Aplicação

### Adicionando JavaScript `as páginas

+ js no head
+ js no body
+ js externo

### Sintaxe

+ variável
	+ tipos de variáveis

+ operadores

+ comentarios

+ Case Sensitive
+ Camel Case

+ array

+ condição

+ switch

+ loop

+ funcoes

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

### Js Design Patterns

+ Ajax

+ JQuery

# NodeJS

### npm

+ O que é npm ?

É um package manager para JavaScript. Ele serve para facilitar a utilização de ferramentas de command line e incluir código de terceiros em suas aplicações.

De forma padronizada ele permite que vc instale, faça update, ou remova pacotes. Tais pacotes geralmente são usados para aplicações Node.js e são chamados modules, mas isso não significa que não possam ser usados fora do Node.

npm
npm install -h
npm install nome_pacote
npm install nome_pacote -g

+ Onde os pacotes estão instalados ?

npm cria um folder especial chamado node_modules
dentro desse folder teremos um folder referente ao módulo instalado

managing package dependencies
package.json

npm init


# AngularJS

+ ionic

# TypeScript

+ Bla

app.js -> app.ts

Uma linguagem estaticamente tipada requer que o programador declare o tipo da variável antes de usá-la. Em Java poderiamos declarar uma string da seguinte forma:
 
	String name = "Luiz";

Já uma linguagem com tipagem opcional (optionally typed) como o TypeScript, iria se comportar da seguinte forma:

	var name:string = 'Luiz';
	var name = 'Luiz';

Por ser opcional, não precisamos necessariamente colocar :string depois de name no exemplo mostrado acima. Vamos analisar outros exemplos:

function sendEmail(contact) {
	console.log(contact.name + "<" + contact.email + ">");
}

Quando olhamos para este código, a primeira coisa que assumimos é que contact é um objeto. Infelizmente nem sempre nosso código será tão intuitívo a ponto de sabermos o tipo daquela variável naquele momento. Quanto maior e mais complexo for o código, é mais dificil e trabalhoso para o desenvolvedor saber como a variável está se comportando.

///

function sendEmail(contact: Object) {
	console.log(contact.name + "<" + contact.email + ">");
}

sendEmail({fullName: "Luiz", emailAddress: "luiz@cjr.org.br"});

O problema aqui é que passamos um objeto como parametro da funcao. Por ser um objeto e a funcao esperar um objeto não será apontado erro algum até que o programa seja executado. Quando ele for executado será possível notar que o atributo name de contact não foi assigned. 

///

Para resolver o problema descrito anteriormente fazemos o seguinte: 

interface IEmailable {
	name: string,
	email: string
}

function sendEmail(contact: IEmailable) {
	console.log(contact.name + "<" + contact.email + ">");
}

sendEmail({fullName: "Luiz", emailAddress: "luiz@cjr.org.br"});

///

Da forma que o código está, será mostrado um erro na ultima linha falando que fullName e emailAddress não são os campos definidos pela interface. Daí mudaremos o código para o seguinte:

interface IEmailable {
	name: string,
	email: string
}

function sendEmail(contact: IEmailable) {
	console.log(contact.name + "<" + contact.email + ">");
}

sendEmail({name: "Luiz", email: "luiz@cjr.org.br"});

///

Seguindo o exemplo podemos chegar ao seguinte:

class Company implements IEmailable {
	name: string;
	email: string;
	phoneNumber: int;
	constructor(companyName: string, emailAddress: string) {
		this.name = companyName;
		this.email = emailAddress;
	}
}

var treehouse = new Company("Treehouse", "bla@cjr.org.br");

sendEmail(treehouse);

Aqui uma classe funciona como se fosse um blueprint para uma instancia de um objeto.

Apresentamos duas formas de declarar o construtor

class Song {
	title: string;
	isPlaying: boolean;
	constructor(
		title:string,
		isPlaying: boolean) {
		this.title = title;
		this.isPlaying: isPlaying;
	}
}

class Song {
	constructor(
		public title: string,
		public isPlaying: boolean = false) {
	)
}

Para declarar os métodos de uma classe não precisamos colocar function() {}, podemos fazer o seguinte:

class Song {
	play() {
		this.isPlaying = true;
	}
}

Quando temos classes definidas em diferentes arquivos e queremos acessar aquela classe e usá-la como atributo podemos fazer o seguinte:

`/// <reference path="song.ts" />`

`class Playlist {`
	`songs: Song[];`
`}`

Quando temos muitos arquivos fica trabalhoso usar os comandos para precompilação pelo terminal, por isso podemos criar um arquivo typings.d.ts e colocar as referencias lá

typings.d.ts
	`/// <reference path="playlist.d.ts" />`
	`/// <reference path="	song.d.ts" />`

Obs: esse arquivos .d são arquivos que contém a declaração das classes, por exemplo:

declare class Playlist {
	songs: Song[];
	nowPlayingIndex: number;
	constructor();
	add(song: Song): void;
}

()()()() Detalhes alheios
tsc *.ts -t es5 -d
tsc *.ts -t es5 -d --watch


+ O que é TypeScript?

TypeScript é uma linguagem que quando pré-processada é transformada em JavaScript.

+ Por que usar TypeScript e não JavaScript?

O TypeScript é capaz de adicionar tipagem estática (static typing) e orientação a objetos baseada em classe ao JavaScript.

+ Por que usar TypeScript e não CoffeScript?

O TypeScript possui uma sintaxe muito parecida com o JavaScript, logo, a curva de aprendizado quando comparada ao CoffeScript é bem menor. Outro motivo muito bom para utilizar TypeScript ao invés de Coffe é que o programador não necessita reescrever o código inteiro que antes estava em js ao mudar a extensão do arquivo para .ts. Pelo fato do TypeScript ser optionally typed podemos começar mudando alguns arquivos e mudar os demais conforme refatoramos os projetos.

+ Histórico

A linguagem foi criada pela Microsoft

+ Configurando o ambiente

Instalando TypeScript
`$npm install -g typescript`

Instalando DefinitelyTyped definition manager tsd
`$npm install tsd -g`

# CoffeScript

# Build Systems 

+ Gulp 

+ Guard 

+ Grunt

# Ember.js

# React

# Ruby

### Sintaxe

+ Variáveis

+ Arrays

+ Estrutura Sequencial

+ Estrutura Condicional

+ Estrutura de Repetição

+ Blocos

+ Hash

### Orientação a Objetos

+ Encapsulamento

+ Classes

+ Atributos

+ Métodos

+ Herança

+ SOLID

+ TDD

# Slim

+ Configurando o ambiente

+ Sintaxe

# Sass

+ O que é Sass?

+ Qual a diferença da extensão .sass para .scss?

+ Por que decidimos usar scss?

+ Configurando o ambiente

+ Variáveis

+ Nesting

+ Partials

+ Import

+ Mixins

+ Extend/Inheritance


# SQL

+ O que é um Banco de Dados

+ O que é um Sistema Gerenciador de Banco de Dados

+ Modelagem do Banco de Dados

+ Comandos Básicos

`select`

`insert`

`update`

`alter`

`delete`

`where`

`join`

# Ruby on Rails 

