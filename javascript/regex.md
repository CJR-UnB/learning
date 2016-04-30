# Expressões Regulares

### O que são expressões regulares?

O JavaScript tem uma ferramenta predefinida extremamente poderosa chamada expressão regular. Essa ferramenta permite a seleção de cadeias de caracteres de interesse em um texto. Expressões regulares podem, também, serem conceituadas como uma sequência de caracteres que definem um padrão de busca.

### Histórico

As expressões regulares surgiram no ano de 1956 quando Stephen Cole Kleene descreveu linguagens regulares usando notação matemática. A teoria definida pelo matemático ganhou enorme importância na área teórica da ciência da computação, principalmente na teoria dos autômatos e na teoria das linguagens formais. As expressões se tornaram populares em 1968 quando foram usadas para encontrar padrões de texto num editor de texto e quando foram usadas num compilador para facilitar a análise léxica. Hoje em dia as regexp são suportadas pela grande maioria das linguagens e são utilizadas em vários editores.

### Domínio de Aplicação

Além do que já foi dito a respeito da utilidade das expressões regulares para encontrar padrões em texto elas são bastante úteis em outros tipos de aplicações. Elas podem ser usadas como forma de validação de dados, como ferramenta de scraping, para fazer parsing, e outros.

### Sintaxe

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