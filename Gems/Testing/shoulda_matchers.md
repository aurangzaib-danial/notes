
# Shoulda Matchers
- Library of matchers for RSpec for making my life easy in common tests.
- We can easily write one liner tests.
- It allows us to quickly write test that we feel like a drag to write.

```ruby
# Gemfile
gem 'shoulda-matchers', group: :test

# spec/support/shoulda_matcher.rb
Shoulda::Matchers.configure do |config|
  config.integrate do |with|
    with.test_framework :rspec
    with.library :rails #=> adds all matchers ActiveRecord, Controller etc.
  end
end
```

## Examples
```ruby
require 'rails_helper'
RSpec.describe Post, type: :model do
  it { should validate_presence_of(:title) }
  it { should belong_to(:user) }
  it { should have_db_column(:body) }
end
```

**Note: This gem is a part of shoulda. shoulda the full gem can provide context by giving helpers like 'should' for minitest. However, RSpec already has this kind of functionality, so we just need to include the matchers.**
