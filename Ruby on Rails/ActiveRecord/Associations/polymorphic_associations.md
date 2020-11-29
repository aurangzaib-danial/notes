
# Polymorphic Associations (One - Many)
This association can be scary from its name but it's very simple.

This association allows us to associate a single model for different models. 
For example, one Comment model for saving all the comments of either a Post or a Game.

The way this works is by adding two columns on the polymorphic table. One for the foreign key and other for storing the type of model that the row belongs to.

```ruby
class Comment
  belongs_to :commentable, polymorphic: true
  # commentable must exist, validation is added
  # any commentable added will be verified if it exists in the database or not.
end

class Post
  has_many :comments, as: :commentable
  # as option tells ActiveRecord that it's an polymorphic association
end

class Game
  has_many :comments, as: :commentable
end

# get comments specific to each entity
post.comments
game.comments
```

To make this association work, we need following things on the polymorphic model

## Two columns
In above example, commentable\_id and commentable\_type are required to make this association work.

The convention for the column name is to name it after the polymorphic model and add 'able' at the end.

```ruby
# example
class Review
  belongs_to :reviewable, polymorphic: true
end
```

## Writing migration for polymorphic association
```console
$ rails g migration create_reviews body:text reviewable:references{polymorphic}
```
### Above Generates
```ruby
create_table :reviews do |t|
  t.references :reviewable, polymorphic: true
  # adds reviewable_id and reviewable_type columns and composite indices
  # composite index first field is reviewable_type
end
```

**Note: We cannot add a referential integrity on database for polymorphic associations because SQL has no concept of polymorphic associations. It can only reference a foreign key for a single table.**

[Good guide](https://semaphoreci.com/blog/2017/08/16/polymorphic-associations-in-rails.html)
[Another guide](https://launchschool.com/blog/understanding-polymorphic-associations-in-rails)
