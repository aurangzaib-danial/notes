# Devise Mailer
Devise has its own mailer for sending email related to authentication. We can edit its mailer views to customize the display as we wish.

**It's our resposibility to setup ActionMailer for connection with a mail server**

## Following modules require ActionMailer to be setup
1. Confirmable
2. Recoverable

**We have to create relevant columns for above modules in users table if we haven't already**

### Following configuration is required in initializers/devise.rb
```ruby
  config.mailer_sender = 'email_from_which_messages_are_to_be_sent'
```

## Asking devise to use ActiveJob for emails
```ruby
  class User
    def send_devise_notification(notification, *args)
      devise_mailer.send(notification, self, *args).deliver_later
    end
  end
```

## Confirmable module
In development mode or for a user that is created using OmniAuth data, we need to disable confirmation check.

```ruby
user.skip_confirmation!
```

