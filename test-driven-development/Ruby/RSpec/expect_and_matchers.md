# Dymystifying expect method and its arguments
```ruby
      #code to test    # Desired Result or Matchers
expect(subject.name).to eq('Sunny')
expect{subject.name}.to raise_error(NoMethodError)
```
## Code to test
- This is the place where we provide the value that we want to test.
- We can also pass blocks to the expect method. Blocks can we be useful when we want to detect if some method was run during the execution of underlying code.

## Desired Result or Matchers
Here we define the condition that we want our code to fullfil. 

## How an expectation is run?
1. We pass the value that we want as an argument to the expect method that creates an expectation object.
2. Then we call the .to method which requires a matcher.
3. The .to method passes the value that is being tested to the matcher object.
4. The matcher object compares the value against its specific matching qualities.
5. If the matcher founds the testing value to fullfil its condition then it informs the .to method that the testing value is successfully fullfilling its conditions and then the whole expectation passes.

## not_to
```ruby
expect(subject.name).not_to eq('Sunny')
#=> This negates the return value of the matcher
```
## Matchers in depth
- Matchers are logical methods, these either return true or false.
- These have the job of actually verifying if the object or code passed to them matches their conditions.

### Built-in matchers
- include (for arrays & hashes)
- start_with
- end_with
- match (for regular expression matching)
- be_between
- have_key / have_value (for hashes)
- be_instance_of
- respond_to
- have_attributes (for testing instance variables)

### Matchers based on predicates (Predicate is that part of a sentence that makes a statement about the subject)
- These matchers are not found in the rspec documentation. These are implicit matchers.
- These automatically call a predicate method that returns 'true' or 'false' on an object.

```ruby
person = Person.new(name: 'Sunny', age: 'very old')
expect(person).not_to be_valid

expect(String.new).to be_empty
# be_ is stripped of and the remaining part is called as predicate method on the object that we pass to the 'expect ' method.
# In above examples, 'valid?' will be called on 'person' object and 'empty?' will be called on the 'string' object
```
### Custom Matchers
We can define custom matchers if a built-in matcher does not suffice our needs.

### Gems for mixing additional matchers
There are lots of gems available for mixing different types of matchers. We have to plug these gems into RSpec configuration.
