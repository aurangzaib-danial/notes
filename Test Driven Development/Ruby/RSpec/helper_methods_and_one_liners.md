
# Helper Methods and One liners

## Helper Methods
RSpec provides a lot of helper methods that help us set up some predefined procedure or data that we can use across different tests.

```ruby
describe Post do
  let(:user) { User.new }
  # accepts a variable name and a block. The return of the block is set as the return of the variable.
  # The return value is memoized. Every test gets the memoized version of the variable.
  # This method is lazy i.e. the code inside the block is only run when the variable is used.

  subject { Post.new } # Implicit Implementation by RSpec
  # If we do not explicity provide a subject 
  # then we can use the implicit implementation of a 'subject' by RSpec.
  # We can set a custom subject as well for the test group.
  # Subject is also memoized.

  subject { described_class }
  # described class returns the class that is passed to the 'describe' method
end
```

## One liners
```ruby
describe Person do
  subject { described_class }

  it { is_expected.to eq(Person) }
  # instead of describing the test we can use above line to define the test
  # is_expected is always attached to the subject of the test suite.

  it { should eq(Person) }
  # should is the shorter version of is_expected.to, lesser keystrokes
end
```
