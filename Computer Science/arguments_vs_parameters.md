# Arguments vs Parameters

Arguments are the data we pass to our methods whereas parameters are the variables in our methods.

```ruby
def greet(name)
  "Hello, #{name}"
end

greet("Sunny") #=> When we call a method and pass an object to it, the object we pass is called an argument.

def greet(name) #=> The variables that are set in a method based on the arguments passed to the method are called parameters.
#=> Parameters are placeholders for arguments.
```

