
# Sessions and Authenticating

For authenticating a user, we have to verify their credentials and then save **user_id** in the session hash. We rely on **SessionsController** for managing the authentication aspect of our application.

## Sessions Controller

This controller is named SessionsController by convention because it is responsible for managing the sessions of our application.

Normally, use this controller for: 
- Login
- Logout

>Basically, everything related to implementing authentication.
>
> SessionsController convention is great because it also allows us to become RESTFUL, i.e. new action is for showing a form for creating a session, create action is for actually saving the **user_id** inside the session data.


## Routes for Basic Authentication

```ruby
  get 'login', to: 'sessions#new'
  post 'login', to: 'sessios#create'

  post 'logout', to: 'sessions#destroy'
```

**Note: It's best to keep _logout_ as a post request. Because according to the definition of 'GET' request, a 'GET' request does not change anything. Logging out is clearly a change, so we should use 'POST' request.**


## Implementing actions

```ruby
  class SessionsController < ApplicationController

    def new
      # render the login page
    end

    def create
      @user = User.find_by_email(params[:email])

      if @user && @user.authenticate(params[:password])
        self.current_user = @user
      else
        render :new #=> Render errors on login page
      end
    end

    def logout
      self.current_user = nil

      redirect_to login_path
    end

  end
```
