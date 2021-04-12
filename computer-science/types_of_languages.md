# Types of languages
There are two types of programming languages very popular.
1. Immperative programming languages
2. Declarative programming languages

## Imperative
These languages follow an order and are very strict with their execution. Examples Ruby, Python, Java etc. This is telling the computer how to do something.

## Declarative
These languages do not have a fixed order of execution. Different parts of the program can independently do things to achieve a greater task. In these languages, we are telling the computer to do something but not how to do it. These are most mostly developed on top of imperative languages for a higher level of interactivity with computers.

### Things to note about declarative programming
This type of programming shows the intent rather how it is done. The best example of declarative programming would be **rspec**.

```ruby
describe User do
  it '#initialize can take a name and an age' do
    user = User.new('Sunny', 24);
    expect(user.instance_variable_get(:name)).to eq('Sunny');
  end
end
```
As we can see that the entire functionality of as how the **describe** or the **it** statement works is totally hidden.

## Statically typed languages

## Dynamically typed languages

## Strongly typed languages

## Weakly typed languages
