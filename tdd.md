# TDD

## Testes de Unidade:

"Testa de maneira isolada, geralmente simulando as prováveis dependências que aquela unidade tem. Em sistemas orientados a objetos, é comum que a unidade seja uma classe. Ou seja, quando queremos escrever testes de unidade para a classe Pedido, essa bateria de testes testará o funcionamento da classe Pedido, isolada, sem interações com outras classes."


## Testes de Integração:

"É aquele que testa a integração entre duas partes do seu sistema." [...] "Testes que garantem que suas classes comunicam-se bem com serviços web, escrevem arquivos texto, ou mesmo mandam mensagens via socket são considerados testes de integração."

## Testes de Sistema:

"Garante que o sistema funciona como um todo. Este nível de teste está interessado se o sistema funciona como um todo, com todas as unidades trabalhando juntas. Ele é comumente chamado de teste de caixa preta, já que o sistema é testado “com tudo ligado”: banco de dados, serviços web, batch jobs, e etc."

## Gemas para Rails

+ **Rspec**: testes de unidades
+ **Factory Girl**: geração de objetos de teste
+ **Faker**: gerar conteúdo de teste para seus objetos
+ **Capybara**: teste de integração

## Instalando o RSpec

Adicione ao seu `Gemfile` e rode `$ bundle install`:

```ruby
group :development, :test do
  gem 'rspec-rails', '~> 3.4', '>= 3.4.2'
  gem 'factory_girl_rails'
end
group :test do
  gem 'faker'
  gem 'capybara'
  gem 'capybara-webkit'
end
```

Depois:

```console
$ rails g rspec:install
```

E adicionar essas linhas ao `spec/rails_helper.rb`:

```ruby
. . . 
# add this line under the other ones like it up top  
require "capybara/rspec"
# set the default driver 
Capybara.javascript_driver = :webkit
. . .  
RSpec.configure do |config|
  . . .
  #add this line at the bottom of the config section 
  #it saves us time when using FactoryGirl methods. 
  config.include FactoryGirl::Syntax::Methods
end
```

Adicionar essas linhas `config/application.rb`:

```ruby
module OurAgendaApp
  class Application < Rails::Application
    #add these lines
    config.generators do |g|
      g.stylesheets false
      g.javascripts false
      g.test_framework :rspec,
        :fixtures => true,
        :view_specs => false,
        :helper_specs => false,
        :routing_specs => false,
        :controller_specs => true,
        :request_specs => true
      g.fixture_replacement :factory_girl, :dir => "spec/factories"
    end    
  end
end
```

Create a folder within your spec/ folder called `factories/`. É aqui onde armazenaremos todas as nossas factories que são responsáveis por fazer nossos objetos de teste como o exemplo de Usuário abaixo.

```ruby
#spec/factories/users.rb
require 'faker'
FactoryGirl.define do
  factory :user do 
    email {Faker::Internet.email}
    password '123'
    password_confirmation '123'
  end
end
```

Esse processo de configuração é chata porém é muito importante para o melhor desempenho do projeto.

## Como fazer um teste?

### Estrutura de testes

Ao instalar o RSpec, uma pasta `spec/` irá ser criada na raiz do seu projeto. É nessa pasta que nossos teste serão armazenados. Ele possui a seguinte estrutura:

```console
spec/
	controllers/
	factories/
	features/
	models/
	requests/
	rails_helper.rb
	spec_helper.rb
```

Cada pasta tem o seguinte proposito:

+ Controllers: aqui serão armazenados os testes responsáveis pelos seus controllers. Ambiguia.

+ Factories: aqui é "fabrica" de dummies para executar nossos teste.

+ Features: aqui são armazenados nossos testes de nossas features. Os nomes dos arquivos seguem uma breve descrição de qual feature eles testam.
Exemplo: "admin_see_dashboard.rb"

+ Model: os testes de unidade dos models são armazendados aqui.

+ Requests: as routas são testadas aqui.

### Teste de Unidades

```ruby
# a valid test
it "has a valid factory" do
	expect(build(:item)).to be_valid
end
```

### Teste de Integração

```ruby
RSpec.describe "Home page" do
  it "should have the 'Hello title'" do
    visit pages_home_path
    expect(page).to have_content "Hello"
  end
end
```

### Teste de Rotas

```ruby
RSpec.describe "Pages", type: :request do
  describe "GET /pages/home" do
    it "works!" do
      get pages_home_path
      expect(response).to have_http_status(200)
    end
  end
end
```

## RSpec

"RSpec uses the words "describe" and "it" so we can express concepts like a conversation:"

```ruby
# Coments are show into terminal for semantic error identification
# "Describe an order."
RSpec.describe Order do

# "It sums the prices of its line items."
  it "sums the prices of its line items" do
    order = Order.new

    order.add_entry(LineItem.new(:item => Item.new(
      :price => Money.new(1.11, :USD)
    )))
    order.add_entry(LineItem.new(:item => Item.new(
      :price => Money.new(2.22, :USD),
      :quantity => 2
    )))

    expect(order.total).to eq(Money.new(5.55, :USD))
  end

  # we can also determine context for nested groups
  context "with no items" do
    it "behaves one way" do
      # ...
    end
  end

  context "with one item" do
    it "behaves another way" do
      # ...
    end
  end
end
```

+ [To Do](http://rspec.info/documentation/3.4/rspec-core/#Get_Started)

Another example:

```ruby
RSpec.describe "Using an array as a stack" do
  # we can also define functions, but is not good 
  # because we may also use functions in development and production
  def build_stack
    []
  end

  # we can use "before" for prepare for something and 
  # avoid too much writing
  before(:example) do
    @stack = build_stack
  end

  it 'is initially empty' do
    expect(@stack).to be_empty
  end

  # again we define another context for our object in test
  context "after an item has been pushed" do
    before(:example) do
      @stack.push :item
    end

    it 'allows the pushed item to be popped' do
      expect(@stack.pop).to eq(:item)
    end
  end
end
```

## Homework

+ [1](http://tutorials.jumpstartlab.com/projects/contact_manager.html)

## Referências

+ [How to setup a Rails app for Test-Driven- and Behavior-Driven Development with Rspec and Capybara-Webkit](https://articles.startuprocket.com/how-to-setup-a-rails-app-for-test-driven-and-behavior-driven-development-with-rspec-and-capybara-28e879b67cb8#.ce8ofwemp)
+ [Unidade, integração ou sistema? Qual teste fazer?](http://blog.caelum.com.br/unidade-integracao-ou-sistema-qual-teste-fazer/)
+ [RSpec](http://rspec.info/)
+ [Koans](http://rubykoans.com/)
+ [Edapx](http://edapx.com/2013/01/12/tdd-in-rails/)
+ [A good stackoverflow post](http://stackoverflow.com/questions/1386562/how-to-get-started-on-tdd-with-ruby-on-rails)
+ [RSpec Doc's 3.4 Core](http://rspec.info/documentation/3.4/rspec-core/)
+ **Apresentar em aula:** [RSpec Doc's 3.4 Rails](http://rspec.info/documentation/3.4/rspec-rails/)