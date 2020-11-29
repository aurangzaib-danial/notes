
# alias vs alias_method

Both of these methods can create copies of methods with a new name.

## alias
This is a keyword. It is lexically scoped. alias keyword defines the copy of a method always on the object in which it's being used.

```ruby
alias print_someting puts
print_something 'Hey! There'
# Only accepts valid method names
```

We mostly avoid alias because of it's scoping nature.

## alias_method
Creates a copy of a method. This a method not a keyword and it's only available on classes and modules.
- Useful for making copies of similar methods.
- We can also make an old copy of a method that might change later etc.

```ruby
class Dog
  def bark
    puts 'wooff!!!'
  end

  alias_method :hello, :bark
  # First argument is the new method name and the second is the source method.
end
```

