# Helpers

## Controller
```ruby
policy(@post) #=> PostPolicy.new(current_user, @post)
# Above code is very useful in views
if policy(@post).destroy?
  # HTML
end

policy_scope(@posts) #=> PostPolicy::Scope.new(current_user, @posts)

authorize @post #=> for running authorization in a controller action

# Hooks
after_action :verify_authorized, except: :index
# Check if authorize was called or not in action

after_action :verify_policy_scoped, only: :index
# Check if policy_scope method is was in action or not
```

## Using Helpers in General
```ruby
Pundit.policy(user, post).update?
Pundit.policy_scope(user, posts)
```
