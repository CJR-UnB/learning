# Active Record Basics

Active Record is the **M** in **MVC** - the model - which is the layer of the
system responsible for representing business **data** and **logic**. Active 
Record facilitates the creation and use of **business objects** whose data 
requires persistent storage to a database.

### O que é ORM?

Object-relational mapping is a programming technique for converting data between
incompatible type systems in object-oriented programming languages. This 
creates, in effect, a "virtual object database" that can be used from within 
the programming language.

+ Represent models and their data.
+ Represent associations between these models.
+ Represent inheritance hierarchies through related models.
+ Validate models before they get persisted to the database.
+ Perform database operations in an object-oriented fashion.

### Naming Conventions

For example, a class Book, you should have a database table called books. The 
Rails pluralization mechanisms are very powerful, being capable to pluralize 
(and singularize) both regular and irregular words. When using class names 
composed of two or more words, the model class name should follow the Ruby 
conventions, using the CamelCase form, while the table name must contain the 
words separated by underscores.

+ Database Table - Plural with underscores separating words (e.g., book_clubs).
+ Model Class - Singular with the first letter of each word capitalized 
(e.g., BookClub).

![Naming Conventions](../images/table1.png)

### Schema Conventions

+ **Foreign keys** - These fields should be named following the pattern 
`singularized_table_name_id` (e.g., item_id, order_id). These are the fields 
that Active Record will look for when you create associations between your 
models.

+ **Primary keys** - By default, Active Record will use an integer column named 
id  as the table's primary key. When using Active Record Migrations to create 
your tables, this column will be automatically created.

+ `created_at` - Automatically gets set to the current date and time when the 
record is first created.

+ `updated_at` - Automatically gets set to the current date and time whenever 
the record is updated.

### Creating Active Record Models

It is very easy to create Active Record models. All you have to do is to 
subclass the ActiveRecord::Base class and you're good to go:

```console
$ rails generate model Product
```

That command will create:

```console
invoke  active_record
      create    db/migrate/20160223194525_create_products.rb
      create    app/models/product.rb
      invoke    test_unit
      create      test/models/product_test.rb
      create      test/fixtures/products.yml
```

Isso irá criar tanto uma migração, um model e os testes correspondentes a esse model.

Quanto a migração, teremos no final, em SQL: 

```sql
CREATE TABLE products (
   id int(11) NOT NULL auto_increment,
   name varchar(255),
   PRIMARY KEY  (id)
);
```

### CRUD's Operations

"CRUD is an acronym for the four verbs we use to operate on data: Create, Read, Update and Delete. Active Record automatically creates methods to allow an application to read and manipulate data stored within its tables."

Criando usuários:

+ `Model.create`

> `user = User.create(name: "David", occupation: "Code Artist")`

+ `Model.save`

```ruby
user = User.new
user.name = "David"
user.occupation = "Code Artist"
user.save
```

Verificando se é possível salvar o usuário. Se ele possui todos os campos necessários foram preenchidos.

+ `save?`

"If the model is new a record gets created in the database, otherwise the existing record gets updated."

+ `save!`

Como selecionar todos os Model do banco
```ruby
# return a collection with all users
users = User.all
```

Como recuperar o primeiro registro salvado. Com o menor id.
```ruby
# return the first user
user = User.first
```

Recuperar um modelo conforme um id passado como parâmetro:

```ruby
u = User.find(:id)
```

Recuperar um modelo por qualquer outro atributo:
```ruby
# return the first user named David
david = User.find_by(name: 'David')
```

Atualizar um registro, temos 3 maneiras diferentes:
```ruby
user = User.find_by(name: 'David')
user.name = 'Dave'
user.save
```

```ruby
user = User.find_by(name: 'David')
user.update(name: 'Dave')
```

```ruby
User.update_all "max_login_attempts = 3, must_change_password = 'true'"
```

Apagando um registro:
```ruby
user = User.find_by(name: 'David')
user.destroy
```

### Validations

Active Record allows you to validate the state of a model before it gets written into the database. There are several methods that you can use to check your models and validate that an attribute value is not empty, is unique and not already in the database, follows a specific format and many more.

```ruby
class User < ActiveRecord::Base
  validates :name, presence: true
end
 
user = User.new
user.save  # => false
user.save! # => ActiveRecord::RecordInvalid: Validation failed: Name can't be blank
```

### Migrations

"Rails provides a domain-specific language for managing a database schema called migrations. Migrations are stored in files which are executed against any database that Active Record supports using rake. Here's a migration that creates a table:"

```ruby
class CreatePublications < ActiveRecord::Migration
  def change
    create_table :publications do |t|
      t.string :title
      t.text :description
      t.references :publication_type
      t.integer :publisher_id
      t.string :publisher_type
      t.boolean :single_issue
 
      t.timestamps null: false
    end
    add_index :publications, :publication_type_id
  end
end

```

### Referências

http://apidock.com/rails/ActiveRecord/Base/save!
https://en.wikipedia.org/wiki/Object-relational_mapping
http://guides.rubyonrails.org/
http://guides.rubyonrails.org/active_record_basics.html