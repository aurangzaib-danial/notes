# Hooks
Hooks are very useful for setting up test data during the lifecycle of tests.

```ruby
describe User do
  before :all do
    # Code in this block runs before all groups and tests only once.
  end

  before :each do
    # Code in this block runs before each test
  end
end

RSpec.configure do |config|
  config.before :suite do
    # Code in this block runs only once before all the tests start
  end
  config.before :all do
    # Code in this block runs before all top level groups
  end
end
```

**Note: We can also use after hooks and they work just like before hooks**
