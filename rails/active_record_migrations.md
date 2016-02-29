# Active Record Migrations

### What's a migration?

"Migrations are a convenient way to alter your database schema over time in a consistent and easy way. They use a Ruby DSL so that you don't have to write SQL by hand, allowing your schema and changes to be database independent."

"You can think of each migration as being a new 'version' of the database. A schema starts off with nothing in it, and each migration modifies it to add or remove tables, columns, or entries. Active Record knows how to update your schema along this timeline, bringing it from whatever point it is in the history to the latest version. Active Record will also update your `db/schema.rb` file to match the up-to-date structure of your database."

Here's an example of a migration:

```ruby
# Nome da Migration: um explicação do que a Migration faz
class CreateProducts < ActiveRecord::Migration
  
  # Método que altera o db/schema.rb
  def change

  	# This migration adds a table called products with a string column called
  	# name and a text column called description.
    create_table :products do |t|
      
      # atributos da tabela
      t.string :name
      t.text :description
 
      t.timestamps null: false
    end
  end
end
```

"A primary key column called id will also be added implicitly, as it's the default primary key for all Active Record models. The timestamps macro adds two columns, created_at and updated_at. These special columns are automatically managed by Active Record if they exist."

Migrations podem ter métodos reversíveis caso o desenvolvedor deseje desfazer o que foi feito. Existem duas maneiras para isso:

```ruby
class ChangeProductsPrice < ActiveRecord::Migration
  def change
    reversible do |dir|
      change_table :products do |t|
        dir.up   { t.change :price, :string }
        dir.down { t.change :price, :integer }
      end
    end
  end
end
```

```ruby
class ChangeProductsPrice < ActiveRecord::Migration
  def up
    change_table :products do |t|
      t.change :price, :string
    end
  end
 
  def down
    change_table :products do |t|
      t.change :price, :integer
    end
  end
end
```

### Creating a Migration

"Migrations are stored as files in the db/migrate directory, one for each migration class. The name of the file is of the form YYYYMMDDHHMMSS_create_products.rb, that is to say a UTC timestamp identifying the migration followed by an underscore followed by the name of the migration. The name of the migration class (CamelCased version) should match the latter part of the file name. For example 20080906120000_create_products.rb should define class CreateProducts and 20080906120001_add_details_to_products.rb should define AddDetailsToProducts."

**Rails uses this timestamp to determine which migration should be run and in what order, so if you're copying a migration from another application or generate a file yourself, be aware of its position in the order.**

### References

http://guides.rubyonrails.org/active_record_migrations.html