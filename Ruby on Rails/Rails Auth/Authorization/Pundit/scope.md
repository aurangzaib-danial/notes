
# Scope
Pundit scope is the notion of finding all the objects/resources of a class that a user has access to.

```ruby
class ApplicationPolicy
  class Scope
    attr_reader :user, :scope
    def initialize(user, scope)
      @user = user
      @scope = scope
    end

    def resolve
      scope.all
    end
  end
end

class PostPolicy < ApplicationPolicy
  class Scope < Scope
    # Scope is for filterning objects from a collection
    # A scope object is instantiated with a user and a scope
    # A scope instance variable contains the collection of model.
    def resolve
      # This method is called to retireve the collection specific to user
      if user.admin
        scope.all
      else
        scope.where(published: true)
      end
    end
  end
end

## Controller usage

class PostsController
  def index
    @posts = policy_scope(Post.all)
  end
end

# Policy scope is short for
@posts = PostPolicy::Scope.new(user, Post.all).resolve
```
