
# Permitted attributes
Sometimes we want to users to able to update specific attributes of a resource. This is very difficult to achieve in controllers. Pundit gives us a very nice helper for getting the right updatable attributes of a resource for the current user.

```ruby
class PostPolicy
  def permitted_attributes
    if user.admin? || record.user == user
      [:title, :body, :tag_list]
    else
      [:tag_list]
    end
  end
end

# Not good
params.require(:post).permit(policy(@post).permitted_attributes)

# Use a helper
def update
  @post.update(permitted_attributes(@post))
  # leave post_params as it is and use permitted_attributes helper that fetches the right parameters from the params hash
  # This method also generates the right policy by introspecting on the object
end
```
