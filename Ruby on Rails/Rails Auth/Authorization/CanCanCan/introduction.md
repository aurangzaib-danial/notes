
# Introduction
CanCanCan is a simple authorization solution for Rails. It streamlines the process of authorization. It's good to use if we want to quickly implement permissions in our app.
#### [Best tutorial on CanCanCan][sitepoint]

## Things provided by CanCanCan
- Ability Class
- Controller and View helpers
- Model.accessibly_by class method for ActiveRecord models.

## Usage
After adding the gem to our Gemfile then we have to generate a CanCanCan ability class.

```console
  rails generate cancan:ability
```
This creates an ability model inside our `app/models` directory. 

## How does it work?
The pattern for handling authorization in webs app is that instead of teaching our ActiceRecord objects about permissions, we make a permission model that is only concerned with answering our questions about the permissions of a user on different resources.

### Permission Model in CanCanCan
A permission model is actually called an ability class. Every ability object is instantiated with a user and every object can tell what its attached user can do. So, I would say a single ability object is the ability of a user.

### Request Cycle of a resource(in this case a Post) that is authorized by CanCan
1. User signs in.
2. User accesses a post resource.
3. When the controller receives the request, CanCan instantiates an ability object using the current user.
4. CanCan asks the ability object if the current user can read the post.
5. If the ability class responds with negative then CanCan raises an Access::Denied exeception and stops the flow of execution.

### Ability Class

```ruby
  class Ability
    include CanCan::Ability

    def initialize(user)
      # Write permissions for the user

    end
  end
```
[sitepoint]: https://www.sitepoint.com/cancancan-rails-authorization-dance/
