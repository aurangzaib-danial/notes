
# Pundit Third Party RSpec matchers
[Repo](https://github.com/chrisalley/pundit-matchers)

- These matchers pattern is just how I like my test specs.
- Requires rspec-rails and pundit gems.

```ruby
# Add to Gemfile
group :test do
  gem 'pundit-matchers', ~> '1.6.0'
end

# rails_helper
require 'pundit/matchers'
```

## Typical Policy spec using Pundit Matchers
```ruby
describe PostPolicy do
  subject { described_class.new(user, post) }
  let(:post) { Post.create }

  context 'being a visitor' do
    let(:user) { User.new }
    
    it { is_expected.to permit_action(:show) }
    it { is_expected.to forbid_action(:destroy, :update)}
    it { is_expected.to forbid_new_and_create_actions }
  end
end
```
