
# authorize

Pundit advises us to authorize each controller action manually.
## Things done by authorize method
- by default uses the controller action from which it is called (we can also override). 
- Adds a question mark at the end of the controller action name.
- automatically loads the right policy by introspecting the ActiveRecord object passed to it.
- automatically passes the current user

```ruby
class PostsController < ApplicationController
  def show
    @post = Post.find(params[:id])
    authorize @post
    # Test if current_user can access this post or not
    # Raises Pundit::NotAuthorizedError if the user does not have permission
    # override action
    authorize @post, :show?
    # we can also override and tell which Policy class to use
  end
end
```
## Whenever 'authorize' is called following happens
```ruby
post_policy = PostPolicy(current_user, @post)
post_policy.show? # Raises error if this method results in an negative
```
