# Working with Sessions in Rails

In Rails, session data of a user is made available to the controllers through a **session hash**. We can access this hash by just calling **session** inside a controller action or method.

```ruby
  class PostsController < ApplicationController
    def show
      session[:posts_count] = Post.count 
    end

    def some_action
      @posts_count = session[:posts_count]
      #=> data can be accessed in any controller action
    end
  end
```

## What to store in Session hash?

- We can store basic things in Session hash easily.
- Session cookie's maximum size is 4k. We have to remember that we only get one session cookie, so we should store things that are really important.
- It's best to just store numbers, strings, hashes, and arrays. Basic things, not even ActiveRecord objects otherwise, it creates bugs.
- Whatever, we store in session hash during a request, the whole session hash is converted into a giant string and then saved as a Session cookie on the User Agent.
