
# Common options for association macros

## inverse_of (Bi-directional associations)
ActiveRecord can identify the parent from a bi-directional(two-way) association by default.

```ruby
# example
post = author.posts.first #=> also sets author of the post in memory
author.name = 'new name'
post.author.name == author.name #=> true
# does not load the post author from the database.
# this makes our program faster

# same associations but using aliasing may be foreign_key and through option
post = author.posts.first 
author.name = 'change name'
post.writer.name == author.name #=> false
# does not know in memory that the parent object was updated

## Solution
class Author
  has_many :books, inverse_of: :writer
  # inverse_of sets the writer of the book in memory whenever a book of the author is loaded
end

class Book
  belongs_to :writer, foreign_key: :author_id, class_name: 'Author'
end

post = author.posts.first
author.name = 'new name'
post.writer.name == author.name #=> true
```

Whenver foreign\_key, class\_name, scope or through options are used, inverse_of is required for auto setting parent object in memory on the children.
