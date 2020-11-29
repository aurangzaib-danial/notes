
# Configuring OmniAuth

OmniAuth in devise is much more organized and modularized then in basic OmniAuth. We have to configure devise to start using OmniAuth for our models.

**NOTE: Even if we skip database authentication and use OAuth for our application, we still want to use Devise for managing OAuth because Devise adds so many awesome helpers and working with OmniAuth a breeze**

## config/devise.rb

```ruby
  # add omniauth-github gem to Gemfile

  credentials = Rails.application.credentials[Rails.env.to_sym]

  github = credentials[:github]

  config.omniauth :github, github[:app_id], github[:secret], scope: 'user'
```

## user.rb

We also have to include OmniAuth module in our 'User' model.

```ruby
  class User < ApplicationRecord
    devise :omniauthable, omniauth_providers: %i(github)

    #=> omniauth_providers is optional, if no provider is supplied than all the providers are enabled for the model.

    #=> omniauth_providers option allows us to limit the number of providers through which the model can authenticate
  end
```

## config/routes.rb

Devise does not handle user creation through OmniAuth for us. We have to handle users through our own methods.

This is the time when we extend a default devise controller.

```ruby
  devise_for :users, controllers: { omniauth_callbacks: 'users/omniauth_callbacks'}

  #=> This directs all callback routes to our custom controller

  #=> callback route example

  get 'users/auth/github/callback', to: 'users/omniauth_callbacks#github'

```

Now we have to create our own custom controller `/app/controllers/users/omniauth_callbacks.rb`

## Users::OmniauthCallbacks

```ruby
  class Users::OmniauthCallbacksController < Devise::OmniauthCallbacksController

    before_action :auth_login

    def github
    end

    def google_oauth2
    end

    protected

    def auth_hash
      request.env['omniauth.auth']
    end

    def auth_login
      @user = User.find_or_create_from_auth_info(auth_hash[:info])

      @user.identities.create(provider: auth_hash[:provider], uid: auth_hash[:uid])

      sign_in_and_redirect(@user)
    end

  end
```

In basic OmniAuth, we had one action handle all the OmniAuth callbacks but Devise allows us to modularize every provider callback. This way every callback has a specific action. We have provider specific code to each action.

## Providing OmniAuth authorize links to users

Devise names OmniAuth paths as following

```ruby
  get 'users/auth/github', to: 'users/omniauth_callbacks#passthru', as: 'user_github_omniauth_authorize' 
```

In basic OmniAuth, we would just have `/auth/github` in general but Devise shuts down these routes and scopes them under the model.

## Devise for and Devise Scope

```ruby
  devise_for :users #=> define routes for managing users
  #=> takes in a plural word

  devise_scope :user do
    delete 'users/sign_out', to: 'sessions#destroy'
  end

  #=> We have to explicitly tell devise that these routes will access devise controllers

  #=> Takes in a singular word
```



