# Faker
This gem allows us to generate fake data for our development and test environments. Having records more than one or two is better and gives us the bigger picture of our application. Also, it's a drag to write dummy data by ourselves.

## Usage
```ruby
require 'faker'

# All the entities are available as class constants inside Faker module.

Faker::Movie.title
Faker::Game.title
#Above methods do not guarantee unique data.

# Generate unique data using
Faker::Movie.unique.title
# Unique Limit Reached exception will be raised when unqiue data is not available anymore.

# Reset unique data limit
Faker::Movie.unique.clear #=> For this module
Faker::UniqueGenerator.clear #=> For all modules

```
