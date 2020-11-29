
# Headless Policies
There will be times when we only want users to access actions that do not correspond to a object. Actions like admin dashboard, stats etc. 

Pundit gives us a way to create policy model that is not attached to a specific model. This policies are called **headless policies**.

## Model
```ruby
class AdminSitePolicy < Struct.new(:user, :admin_site)
  # admin_site argument is the record in this case
  def dashboard?
    user.admin?
  end

  def stats?
    user.moderator?
  end
end
```
## Controller
```ruby
class SiteController < ApplicationController
  def dashboard
    authorize :admin_site
    # Notice, we still have to pass the name of the policy as a symbol.
    # Symbol tells pundit that its a headless policy.
    # Otherthan this, it will call the dashboard? on the SitePolicy.
  end

  def stats
    authorize :admin_site
  end
end
```

NOTE: Notice that we are also setting up a second argument for the headless policy. The reason is that normal policies instantiate with a **user** and a **record** through the **policy(record)** method. If we do not pass a second argument then the policy method would break.
