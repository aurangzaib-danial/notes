# has_many (One-to-many)
An object has many other objects from another table. Has many is always on the parent.

```ruby
class Post
  belongs_to :author
end

class Author
  has_many :posts
end

author.posts
author.posts.build(title: 'a post')
author.posts.create
author.posts << Post.new # never use it because it returns all the posts of the author as well
author.post_ids # returns all the ids of the posts
```

## Common options
```ruby
class Author
  has_many :authored_posts, class_name: 'Post', foreign_key: 'user_id'
  has_many :posts, dependent: :destroy
  # dependent accepts :destroy, :delete_all, 
  # destroy options calls the destroy method on each children object for their callbacks to run as well
  # delete_all removes all the children from the database table without running any callbacks
end
```
