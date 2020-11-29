



# Mailer
- Mailers in Rails, are just like controllers. 
- Controllers take requests and reply with HTML to clients while Mailers send message to mail servers.
- We can create an email out of a dynamic erb view just like an ActionView.

```ruby
# Generate a mailer
rails g mailer user
#=> app/mailers/user_mailer.rb
#=> app/views/user_mailer/
```

## Typical mailer class
```ruby
class UserMailer < ApplicationMailer
  default from: 'from_email'

  def welcome(user)
    mail(to: user.email, subject: 'Thanks for signing up!')
    # mail method specifies the email settings for welcome action
  end
end

UserMailer.welcome(@user).deliver_later #=> .deliver_now

#welcome is an instance method but it is called as a class method.
#this is synatic sugar by Rails
```
