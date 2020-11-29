# Numbers
## Random numbers
We have two important methods for generating random numbers
1. rand
2. srand

### rand
- This method generates a random number between 0 - 1 if a parameter is not given.
- If a parameters is given then it generates random number less than the give parameter.
- Generated number can never be less than 0

```ruby
rand(5) # generates between 0 - 4 and never 5
rand(1) # always 0
rand(101) # between 0 - 100
```

### srand
This method allows us to generate random numbers in a deterministic squence.
