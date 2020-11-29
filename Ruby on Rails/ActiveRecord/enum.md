
# Enum
Enums are those values that are predefined. For example, in our database we can have specific states for different entities. Instead of using actual names for those states, we use integer values to keep our databases small and fast because numbers are light weight. However, in our application we define or give names to these numbers so that these become meaningful to use rather than using magic numbers. Also, we do not care how our data looks inside the database. We only want to be exact the at application level.

Also, one other way to understand is to think about the situation when we have an object's attribute that can be filled with one of the many available values.

#### [Awesome post on enums][post_link]

## Using enums in ActiveRecord
ActiveRecord provides us a macro for defining enums for values inside an objects' database row column.

```ruby
class Post < ApplicationRecord
  enum status: %i[not_set published unpublished]
end
```
- This enum method called takes in the name of the column on which the value is stored. 
- The order of states in the array passed for the attribute matters. As an example, in the above 'Post' case, the value for the state 'published' will be **1** in the database. We must not change the order in production because that will change the order for the data that already exists in the database.

## Methods provided by enum macro(According to above example)
For every state, 2 methods are added to the object (state\_name?, state\_name!)

```ruby
post = Post.new(status: 'published')
post.status #=> published
#=> Notice status returns the colloquial word published rather than a magic number
post.published? #=> checks if the status is published
post.not_set! #=> sets the state to 'not_set' and also fires an update statement
```
## Using a hash instead of array for enums

```ruby
enum role: [:normal, :moderator, :admin] 
# if later the requirement changes and we have to break moderator into two parts like a invigilator and semi-admin
enum role: [:normal, :invigilator, :'semi-admin', :admin] 
# We cannot do this because all the users who had 'admin' in their roles would now have semi-admin and we will have a conflict.
enum role: { normal: 0, admin: 2, invigilator: 3, 'semi-admin': 4 } 
# whereas using a hash makes our application flexible and also we do not have to worry about the order because it's a hash.
```
## Using prefix and suffix
The methods that are defined by enum for an attribute, do not seem to be attached to an attribute from their name. This can be confusing if we have lots of methods by different enums. We will ultimately get confused as to which method belongs to which enum. To solve this problem, we can prefix all the methods created by a enum with the name of the attribute.

```ruby
#=> _prefix and _suffix, we can also pass a custom name instead of true
enum role: {normal: 0, admin: 1}, _prefix: true

user.role_normal?
user.role_admin?
```
It is much more clear as to which attribute does the method belongs to.
I personally prefer this approach because this makes it much clearer for me.

## Setting default state for an enum attribute
We can set the default state for an attribute using a default value in our migration or using a ActiveRecord hook but we should do both of these.

```ruby
after_initialize :set_default_status
def set_default_status
  self.status ||= 'not_set'
end
```

## Enum best practices
- index the enum attribute if you think objects will be later found based on it.
- force POSTGRES enum constraint, if you think you really need it.

[post_link]: https://naturaily.com/blog/ruby-on-rails-enum
