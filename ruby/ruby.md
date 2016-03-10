[Preview GitBook](https://rafaelalvescjr.gitbooks.io/learning-ruby/content/index.html)

Introdução ao Ruby
=======

### História

O Ruby é uma linguagem de programação interpretada multiparadigma, de tipagem forte e dinâmica e gerenciamento de memória automático, criada em 1995 pelo japonês Yukihiro Matsumoto.

Matsumoto inspirou-se no Python, Perl, Smaltalk, Eiffel, Ada e Lisp, mas queria que desenvolver uma linguagem de script mais poderosa que Perl e mais orientada a objetos que Python.

Atualmente, o Ruby é a 10ª linguagem de programação mais popular do mundo.

### Linguagem interpretada e classes abertas

Como o Ruby é uma linguagem interpretada, não há um processo de compilação para um binário executável, como acontece na linguagem C, por exemplo. Em Ruby, existe um arquivo com a extensão ```.rb``` e um programa cujo papel é interpretar o código deste arquivo, transformando em instruções de máquina e as executando.

Ao instalar o Ruby, você pode verificar sua versão através da linha de comando.

    $ ruby -v
    ruby 2.2.3p173 (2015-08-18 revision 51636) [x86_64-linux]

Além de executar o interpretador Ruby:

    $ irb
    irb(main):001:0>
    
O interpretador permite que métodos sejam usados em tempo real.

    $ irb
    irb(main):001:0> puts "Seja bem vindo a CJR!"
    Seja bem vindo a CJR!
    => nil

O Ruby possui um diferencial em relação a suas classes, elas são abertas. Podemos ilustrar a resolução de um problema envolvendo classes com um exemplo:
    
```ruby
def plural(palavra)
  "#{palavra}s"
end
    
puts plural "caneta"
puts plural "carro"
```

Executando o arquivo pela linha de comando, usando `ruby nome_do_arquivo.rb`, temos a seguinte saída:

    $ ruby plural.rb
    canetas
    carros

Caso queiramos usar um método no próprio objeto, alterando a sintaxe. No lugar de

```ruby
plural "caneta"
```

usassemos

```ruby
"caneta".plural
```

Caso executássemos esse código, obteriamos o seguinte erro:

    irb(main):002:0> "caneta".plural
    NoMethodError: undefined method `plural' for "caneta":String
    	from (irb):2
    	from /usr/local/bin/irb:11:in `<main>'
    	
Isso aconteceu porque não há um método definido que possa ser usado no objeto string. Podemos corrigir isso da seguinte forma:

```ruby
class String

  def plural
    "#{self}s"
  end

end

puts "caneta".plural
```

Executando o arquivo pela linha de comando:

    $ ruby correcao.rb
    canetas

Você não precisa se preocupar neste exato momento sobre classes e métodos, apenas veja como as classes, que são entidades muito importantes em Ruby, podem ser modificadas, apenas reabrindo-a e adicionando mais métodos, o que, em geral, não é possível em outras linguagens.

### Onde usar o Ruby?

O Ruby é uma linguagem muito comum de ser encontrada para criação de scripts de leitura e processamento de arquivos, automização de builds e deploys, etc.

Sem dúvidas os maiores cases de sucesso da linguagem Ruby estão ligados a aplicações web. A criação do Rails foi, sem dúvidas, o que mais alavancou o sucesso da linguagem. Ele é um framework web que segue o padrão MVC *(Model - View - Controller)*.

O importante é que o mercado em torno da linguagem Ruby é muito grande atualmente, e a tendência é que continue crescendo nos próximos anos. 

Tenha em mente que o quanto mais você dominar a linguagem Ruby, mais fácil será para você conhecer profundamente o próximo passo do curso, Ruby on Rails e suas diversas bibliotecas.

Pronto para começar?

# Orientação a objetos

A programação orientada a objetos refere-se ao paradigma de programação onde o desenvolvimento do software é regido pelas definições e relacionamentos entre os objetos que compõem o mesmo.

### Abstração

A abstração consiste em separar objetos de uma totalidade, a segmentação proporciona uma melhor utilização dos recursos da orientação a objetos. Nesse modo de pensar, nós isolamos os objetos que queremos representar do ambiente complexo em que se situam, e nesses objetos representamos somente as características que são relevantes para o problema em questão.

### Encapsulamento

O encapsulamento tem como característica ocultar partes da implementação de uma entidade da orientação a objetos, desta forma construindo softwares que atinjam suas funcionaliddes e escondam os detalhes de implementação do mundo exterior. Os objetos encapsulados funcionam como uma caixa preta, sabemos sua interface externa, mas não precisamos nos preocuparmos com o que acontece dentro dela.

### Classe

A classe representa um conjunto de objetos (um modelo), apesar deles possuirem atributos iguais, eles têm valores diferentes em seus atributos.

Em Ruby, temos um exemplo de uma classe:

```ruby
# classe.rb

class Pessoa
  
  @@quantidade_de_pessoas = 0

  def initialize(nome, endereco, data_de_nascimento)
    @nome = nome
    @endereco = endereco
    @data_de_nascimento = data_de_nascimento

    @@quantidade_de_pessoas += 1
  end

end
```

Os detalhes dessa classe serão explicados melhor após o próximo tópico.


### Objetos e Métodos


Um objeto é uma instanciação de uma classe, cada instância tem seus próprios valores de atributos, mas compartilha o nome e os comportamentos dos atributos com a outras instâncias da classe.

Em Ruby, a instanciação de uma classe é feita da seguinte forma.

```ruby
# classe.rb
aluno_do_pt = Pessoa.new("Gustavo", "SQN 209")
```

Métodos são 'funções' que podem ser usadas em objetos de classe. Como, por exemplo:

    $ irb
    irb(main):001:0> puts "aluno_do_pt".capitalize
    => "Aluno_do_pt"
    
```capitalize``` é um método que pode ser usado em um objeto da classe String.

    irb(main):002:0> "aluno_do_pt".class
    => String

Para saber se um método pode ser usado em um objeto de uma determinada classe, podemos usar o método ```respond_to?```

    irb(main):003:0> "aluno_do_pt".respond_to? :capitalize
    => true

### Estrutura da classe

As variáveis que começam com ```@``` são atributos de instância, ou seja, é diferente para cada novo objeto. Já as que começam com ```@@``` são atributos de classe, e é igual para todos objetos de uma classe.

O método ```initialize``` é um método construtor da classe. Ele cria uma instância com os argumentos que são passados a ele.

```ruby
# classe.rb

def initialize(nome, endereco)
  @nome = nome
  @endereco = endereco

  @@quantidade_de_pessoas += 1
end
```

Ao fazermos ```@nome = nome```, estamos atribuindo à variável de instância ```@nome``` o conteúdo da variável ```nome``` passada como argumento do método ```initialize```. Assim como todos os outros atributos.

Na última linha, o código ```@@quantidade_de_pessoas += 1``` incrementa em um a variável de classe que representa a quantidade total de pessoas criadas.

Com um objeto criado, como podemos acessar seus atributos? No exemplo acima, se tentarmos acessar o atributo ```nome``` do objeto ```aluno_do_pt``` não conseguiremos:

```ruby
# classe.rb
puts aluno_do_pt.nome
```
Executando o arquivo via linha de comando:

    $ ruby classe.rb
    ruby.rb:17:in `<main>': undefined method `nome' for #<Pessoa:0x0055cd41226fc8> (NoMethodError)
    
Não há um método ```nome``` que possa ser usado num objeto da classe ```Pessoa```. O Ruby é bem eficiente na resolução desse problema, há métodos que auxiliam o acesso a atributos:

```ruby
attr_reader :atributo
# permite que o atributo seja lido

attr_writer :atributo
# permite que o atributo seja alterado

attr_accessor :atributo
# permite que o atributo seja lido e alterado

```

No nosso caso, queremos apenas ler o ```nome``` do ```aluno_do_pt```. Logo, adicionaremos apenas o método ```attr_reader```.

```ruby
class Pessoa

  attr_reader :nome
  
  ...

end

...

puts aluno_do_pt.nome
```

    $ ruby classe.rb
    Gustavo


### Herança

A herança é uma das principais características da orientação a objetos. Ela permite o reaproveitamento de métodos e atributos diminuindo o tempo de desenvolvimento, ainda reduzindo as linhas de código e facilitando manutenções futuras do mesmo.

Em Ruby, a herança é feita assim:

```ruby
class PessoaFisica < Pessoa
    
  attr_accessor :cpf
  
  @cpf
    
end
```

```ruby
class PessoaJuridica < Pessoa
    
  attr_accessor :cnpj
  
  @cnpj
    
end
```

```ruby
# classe.rb

outro_aluno = PessoaFisica.new("Carlos", "SQS 108")
outro_aluno.cpf = "32.833.782-31"

cjr = PessoaJuridica.new("Empresa Júnior de Computação - CJR", "UnB, CiC/EST, AT 12/11")
cjr.cnpj = "03.632.310.000-117"

puts outro_aluno.nome
puts outro_aluno.cpf

puts cjr.nome
puts cjr.cnpj

```

    $ ruby classe.rb
    Carlos
    32.833.782-31
    Empresa Júnior de Computação - CJR
    03.632.310.000-117


Observe que o atributo ```nome``` não está definido nas classes ```PessoaFisica``` e ```PessoaJuridica```. O que acontece é que elas herdaram da classe ```Pessoa``` esse atributo. A herança também permite que métodos sejam herados.
