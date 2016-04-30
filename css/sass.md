# Sass

### O que é Sass e qual sua utilidade?

CSS extension language that compiles into plain old CSS
First of the modern transcompiler languages
Compiladores recebem um input e retornam um output
No caso do sass o compilador recebe como input um codigo sass e retorna um codigo css
Browsers entendem CSS mas nao entendem Sass

### Configurando Sass

O sass original era escrito em ruby
A forma mais facil de se instalar o sass é através de ruby gems
Mac já vem com ruby instalado, entao a unica coisa que falta vc fazer para baixar o sass é escrever no terminal - gem install sass
Os demais sistemas não vem com ruby configurado, entao vc precisa configurar isso antes

sass --version
sass nome_do_arquivo.scss
sass --watch .

Existem duas versoes do sass
	A primeira é chamada libsass - mais portavel
	A segunda é a versão padrão de sass

http://sass-lang.com/install
http://sass-lang.com/documentation/file.SASS_REFERENCE.html#features

### Nesting

This helps avoid repetition of parent selectors

Try not to get carried away with nesting

parent selector -> &
& eh basicamente todos os seletores que voce ja colocou ate aquele ponto

Sometimes it’s useful to use a nested rule’s parent selector in other ways than the default. For instance, you might want to have special styles for when that selector is hovered over or for when the body element has a certain class. In these cases, you can explicitly specify where the parent selector should be inserted using the & character.

### Partials

### Import

### Variáveis

### Mixins

### Extend

### Funções

### Media Queries no Sass

### if / else

### @for @each

// Advanced

### Manifest

### Globbing

### Source Maps

### Scoping

### List-maps

### &-suffix

### Introspection

### @content

### @at-root






### sass meister

### comentarios

/* vs //

invisible comments // -> vai ficar no codigo sass mas nao vai pro css
visible comments /**/ -> vai para o arquivo css gerado



