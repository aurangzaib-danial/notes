
# Struct
This a special ruby class that allows us to create temporary classes for storing data.

```ruby
Person = Struct.new(:name, :age)
sunny = Person.new('Sunny', 23)
sunny.name #=> 'Sunny'
```
- `Struct.new` returns a class which already has attribute accessors for each the symbols that we passed to it.
- The initialize method of this class can also set attributes
- Structs are really useful when we want to quickly set up a class with some attributes instead of implementing this routine by ourselves all the time.

```ruby
class Person < Struct.new(:name, :age)
  def say_hello
    puts "Hello, my name is #{self.name}"
  end
end
```

**Note: A class based on struct, its 'new' constructor does not raise an error if right number of arguments are not passed. Unpassed arguments are automatically set to nil**
