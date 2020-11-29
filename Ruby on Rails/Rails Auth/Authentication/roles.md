
# Roles
It's very common to have different types of users in a management system app. We can have an admin, a moderator or just a simple user. To solve this problem, we give an attribute of role to each user through which each user can know about its role.

```ruby
  class User < ApplicationRecord
    enum role: %i[normal moderator admin]
    # or
    enum role: { normal: 0, admin: 2, moderator: 3 }
  end
```

[Best post on roles](https://naturaily.com/blog/ruby-on-rails-enum)
