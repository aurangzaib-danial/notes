# Sorting
## sort_by 
```ruby
words = %w[orange grape banana]
words.sort_by { |word| word.length } #=> ["grape", "orange", "banana"]
```
Every element of the array is compared using '<' with the returned value of the block
