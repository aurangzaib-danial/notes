
# OmniAuth

This is a ruby gem that handles OAuth2 for our application.

OmniAuth as a OAuth framework is really flexible. It intelligently abstracts away the complexity of OAuth and allows us to easily implement authentication with service providers like Google, GitHub easily.

OmniAuth gem itself is the core implementation of OAuth. For every service provider, we have to get service specific OmniAuth extension gem.

### For example

- omniauth-github for GitHub
- omniauth-twitter for Twitter

Each gem extends omniauth for handling a different service provider. These gems are also called strategies.

## Steps for implementing OmniAuth

### Gems

Add OmniAuth and service specific OmniAuth extension gem to the Gemfile.

### Initializer

Make a omniauth.rb intializer inside config/initializers.

```ruby
  Rails.application.config.middleware.use OmniAuth::Builder do
    provider :developer unless Rails.env.production?
    provider :github, ENV['GITHUB_KEY'], ENV['GITHUB_SECRET'], scope: 'user'
  end
```

This code tells Rails to use OmniAuth as a middleware. This allows OmniAuth to intercept the clicks on links like 'Log in with Google' and the request that comes directly from service providers.

Also, in the block, we have to tell OmniAuth which providers we will use. We also have to provide our secrets.

**scope** option is required for some OmniAuth providers. These are for making sure that we get the data that we want.

### Routes

For linking the buttons like 'Log in with Google' etc. OmniAuth provides us some default routes e.g.

```ruby
  link_to 'Log in with Google', '/auth/google'
  link_to 'Log in with Facebook', '/auth/facebook'
```

These routes are provided by OmniAuth. When user visits these routes then they will be redirected to the service provider accordingly.


#### Redirect URL

We have to explicity define a route where the service provider will redirect users and also specify which controller action will handle it.

```ruby
  match '/auth/:provider/callback', to: 'sessions#create', via: [:get, :post]

  #=> post request is required for developer strategy
```

- This is the URL that we have to provide to a service provider as the redirect URL. Update provider accordingly when submitting the URL to the provider.
- After service provider redirects users on this route, OmniAuth intercepts and validate the redirect using the code sent by the service provider.
- Whenever verification completes, we can then access user information inside the controller action.

### OmniAuth Api

OmniAuth data can be found in the request object `request.env['omniauth.auth']

```ruby
  class SessionsController < ApplicationController
  def create
    @user = User.find_or_create_from_auth_hash(auth_hash)
    self.current_user = @user
    redirect_to root_path
  end

  protected

  def auth_hash
    request.env['omniauth.auth']
  end
end
```


## Developer strategy

This allows us to test our OmniAuth setup. When we visit a developer strategy then we will be provided with a dummy interface for logging in. It mimics service providers.

- A post request is requird for the call back URL
- We have to temporarily disable authenticity token for the request.

