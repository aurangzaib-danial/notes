# friendly_id
It is the swiss army knife in Rails for creating friendly URLS.
It does everything for us for creating clean URLS.

## Features
1. easily create slugs
2. create history of slugs, so if a slug of a resource changes then the application should still be able to load the resource with the old slug.

## Usage
```bash
# add slug column to the required table
rails g migration add_slug_to_users slug:uniq

# this migration is important for keeping history of all slugs created
# can be skipped if we do not require the history feature
rails generate friendly_id

# save changes
rails db:migrate
```
```ruby
# Model
class User < ApplicationRecord
  extend FriendlyId
  friendly_id :name, use: [:slugged, :history] # add options as required
  # history feature saves the history of slugs as well

  # by default slugs are not updated after a resource is created
  # but if we still want to update them then add below method
  def should_generate_new_friendly_id?
    slug.blank? || <your_column_name_here>_changed?
  end
end

# Controller
class UsersController
  def show
    @user = User.friendly.find(params[:id])
    # where id is the user slug
  end
end
```

## Something to remember
Friendly ID monkey patches routes to use slugs instead of ID. This is only for the controller that has a corresponding model. This feature only works if the routes are defined in **RESTFUL** pattern.

```ruby
resources :users 
#=> whereas the route parameter will be :id but slug will be used instead of id

link_to user.name, user #=> /users/joe
edit_user_path(user) #=> /users/joe/edit 
```
