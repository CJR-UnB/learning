# TDD

## Gemas

+ Rspec
+ factory_girl_rails
+ faker
+ capybara-webkit

## Some fun

Instalando o RSpec

`rails g rspec:install`

E adicionar essas linhas ao `spec/rails_helper.rb`:

```
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

```
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

Create a folder within your spec/ folder called “factories” and create a file called “users.rb” in it:
```
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

Então nosso teste:
```

```


## Referências

[link 1](https://articles.startuprocket.com/how-to-setup-a-rails-app-for-test-driven-and-behavior-driven-development-with-rspec-and-capybara-28e879b67cb8#.ce8ofwemp)