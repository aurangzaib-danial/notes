# Regex with ruby
Creating a regex object with ruby

```ruby
regex = /abc/ #=> this regex can be to match against any string
```

## Ruby methods for regex
```ruby
.scan #=> returns all the matched items in a string in the form of an array

.match #=> returns nil or matched object

.match? #=> returns a boolean

.grep #=> is an enumerator and is used for searching patterns in an array

.gsub(Regex, "replace_with" ) #=> (for replacing characters in a string)
```
