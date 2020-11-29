
# Factory Bot
This gem has the purpose of setting up our test or development enironment data. It is mostly used for test environment. It is a better solution than the fixtures provided by Rails. Fixtures are written in .yaml files and quickly get complex. Also, all the data defined in a fixture is loaded even if we want a specific object from all of the data. This is where Factory Bot comes in.

## My Understanding
More often, I find myself creating multiple objects of a class. Most of the time the objects are same but sometimes I overwrite some attributes of the objects. RSpec helpers like 'let' are great but they are mostly used for specifc spec files rather than across all the test files. For solving this problem, I would want to write a method that can generate an object of the class and set some predefined data on the objects. As I create those objects, I also sometimes want to overwrite their attributes. This is exactly what Factory Bot does.

## Benefits
- Easy to setup and very concise.
- We can load specific objects instead of loading everything up.
- All interaction with FactoryBot is in Ruby. No need to worry about .yaml files.
- Separation of concerns in terms of separating test data and it is very easy to browse FactoryBot factories.
- It is extremely easy to read a factory file because all we have to do it specify requirements while FactoryBot creates the objects for us.

## How it works
1. By convention, we have a 'factories' folder inside the spec directory in which we place all of our test data. 
2. Factory file name of a class is named after the plural of the class name. For example, factory file name for a user class would `users.rb`.
3. We create a factory for the **class** whose objects we need to use in our tests.
4. By convention, we create specific file for each class but we can also define different factories inside one file.

## Typical Factory
```ruby
# spec/factories/users.rb
FactoryBot.define do
  # Here we define factories
  factory(:user) do
    # This methods requires the name of the class that is attached to this factory

    # We define default attributes values for the objects
    # These can be easily overwritten while making a object through FactoryBot
    # We specify the name of the attribute and provide a block. 
    # The return of the block will be set as the value of the attribute.
    name { 'Sunny' }
    email { 'sunny@example.com '}
    # We could have used arguments instead of blocks, for simple values it can be good.
    # But what if we want to set the attribute value dynamically instead of being static. 
    # Blocks offer lazy evaluation.
    created_at { Time.now } 
    # This will ensure that the value is different for every object
    
    created_at(Time.now) 
    # This will use a static value for all objects. Also this is not allowed in FactoryBot. 
    # We can only use blocks for setting the value of attributes.

    sequence(:email) {|n| "#{n}@example.com"}
    # This method always yeilds a unique value.
    # This allows us to keep our objects unique because of attributes like email

    trait :good_guy do
      # A trait is a special characteristic
      # Over here we can define attributes that are specific to some special users
      name: { 'Avi Flombaum'}
      email: { 'avi@fs.com'}
    end
  end
end
```

## What is a factory?
Whenever we define a factory, we are actually creating a factory object that can create objects based on the class passed to it.
What actually is great that the attributes values set by the factory for the objects can be very dynamic and customized for different situations. Also, traits allow us to alter default attributes for special objects.

## Creating objects from factories
```ruby
# for using build and create
include FactoryBot::Syntax::Methods
build(:user, :some_trait, attribute_overwrite: 'some_value')
# build instantiates
create(:user)
# create persists the object as well
```

## Integrating with Rails and RSpec
FactoryBot has a dedicated gem for Rails. It's called **factory\_bot\_rails**. We should include this gem in development and test group.

### Things factory\_bot\_rails gem does
- Ask Rails to read all the factories inside spec/factories.
- The factories are also made available for us in development environment.

## Adding RSpec configuration
1. Create a file inside spec/support called factory_bot.rb
2. Place the following code
3. Require this file in rails_helper

```ruby
# spec/support/factory_bot
RSpec.configure do |config|
  config.include FactoryBot::Syntax::Methods
end
```

