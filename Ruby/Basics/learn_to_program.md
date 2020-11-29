# Learn to program
## Variables referencing other variables only point to values and not the variables
```ruby
var1 = 10
var2 = var1
var1 = 20
var2 #=> 10
```

## String comparison is always based on the order in which the word comes in dictionary
```ruby
'apple' < 'banana' #=> true
'orange' > 'cucumber' #=> true
```
Also, capital letters are considered to come before the lowercase letters.

```ruby
'A' < 'a' #=> true
```
