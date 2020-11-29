# Belongs to
The class that contains the belongs_to macro has objects that belong to some other class object.

**ProTip: Class that has the belongs_to macro, its SQL table always has the foreign key column.**

```ruby
class Post
  belongs_to :user # adds user related methods
end

post.user
post.build_user
post.create_user
```

## Common options
```ruby
class Post
  belongs_to :author, class_name: 'User' # if foreign_key is author_id
  belongs_to :author, foreign_key: 'user_id', class_name: 'User' # if foreign key is user_id
end
```

**Note: belongs_to in Rails 6, adds validation for the parent to exist. However, we must add the validation on the database as well.**

## Referential Integrity
- We must always add the foreign key constraint to the table that contains a foreign key.
