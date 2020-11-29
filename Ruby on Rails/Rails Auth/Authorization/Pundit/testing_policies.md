
# Testing Policies

Pundit policy models are very easy to test because each policy model corresponds to a data model in our domain. Instead of writing feature tests, we can easily test the policy objects.

## Example Test
```ruby
describe PostPolicy do
  it 'a normal user cannot view someone else\'s post' do
    post = User.first.posts.first
    post_policy = Pundit.policy(User.second, post)
    
    expect(post_policy.show?).to be_falsey
  end
end
```

## RSpec DSL by Pundit
Pundit provides us a DSL for RSpec. We have to require it in **rails_helper**.

```ruby
# spec/rails_helper.rb
# Add following code
require 'pundit/rspec'

# spec/policies/post_policy_spec.rb
describe PostPolicy do
  subject { described_class }

  permissions :show?, :update?, do
    it 'denies access if a normal user accesses another user\'s post' do
      post = User.first.posts.first
      expect(subject).not_to permit(User.new(role: :normal), post)
    end
  end
  # This can be difficult to understand the first time.
  # The permissions method take in all the permissions that we want to test on a policy object
  # expect will always take in the subject
  
  # permit method
  # takes in the two main arguments for instantiating a policy based on subject.
  # tests the policy against the permissions passed to the permissions method
end
```
**Above method can be somewhat magical or vague. I do not like it and prefer Pundit third party matchers**
