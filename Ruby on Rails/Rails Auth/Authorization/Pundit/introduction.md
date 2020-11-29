
# Introduction

Pundit is an extremly simple authorization library but also robust at the same time. The concept introduced by Pundit is that every model that is to be authorized will have a corresponding permissions model. This way we can write permissions for each model in their own permission models. This makes our authorization code organized, modular and removes the logic of authorization from controllers and models.

Pundit can be used with other frameworks but it's mostly used with Rails.

## Setup
1. Add pundit to Gemfile
2. Run `rails g pundit:install`
3. Generate a permissions model for a specific model using `rails g pundit:policy Post`

## Files and directory
Installing pundit using the generator, creates a **policies** folder inside our app folder. Each polichy file corresponds to a model in our domain.

## Example (Post model)
```ruby
# app/policies/post_policy.rb

class PostPolicy < ApplicationPolicy
  def show?
    false
  end
end

post_policy = PostPolicy.new(user, post)
post_policy.show? #=> false
```

## Mix in Controller helpers
```ruby
class ApplicationController < ActionController::Base
  include Pundit # use pundit helpers
end
```
