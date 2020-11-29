
# Counter Cache
Counter cache is a technique that stores count of children on the parent object.
It makes our application slow to find the count of children on every request.
Many times we want to find count of children of a parent object.
This even helps us when we want to render a collection of objects and also display their children counts. This helps us avoid all the unnecessary count queries.

## Usage (Articles and Comments)
```bash
# Add column that stores the count of children
# association_count is the convention for naming the column
rails g migration add_comments_count_to_articles comments_count:integer
```
```ruby
# Tell rails to count children of an object
class Comments
  belongs_to :article, counter_cache: true
  # if the counter_cache column name on parent does not follow convention then we can do the following
  belongs_to :article, counter_cache: :the_count_of_comments
  # where the_count_of_comments is the column name of on Article
end
# Now whenever a comment is persisted or destroyed, comments_count on its article will be updated.
```
