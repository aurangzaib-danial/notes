
# Introduction
ActionMailer is a framework of Rails that allows us to send email from web servers. It can send emails asynchronously using ActionJob and allows us to easily format our emails with dynamic content and HTML.

**Note: ActionMailer must be setup with a mail server for sending email to the recipient because it is not the job of ActionMailer to talk to recipients mail servers**

## Setting up Rails to send email
```ruby
  # for production.rb
  host = 'example.com'
  config.action_mailer.delivery_method = :smtp
  config.action_mailer.default_url_options = { host: host, protocol: 'https' }

  # for development.rb, does not send emails in realtime
  config.action_mailer.delivery_method = :test
  config.action_mailer.default_url_options = { :host => 'localhost:3000', protocol: 'http' }

  # SMTP settings for gmail
  config.action_mailer.smtp_settings = {
    :address              => 'smtp.gmail.com',
    :port                 => 587,
    :user_name            => 'gmail_user_name',
    :password             => 'gmail_app_password',
    :authentication       => 'plain',
    :enable_starttls_auto => true
  }

  #=> use credentials for user_name and password
  #=> create an app password for google, not regular
  #=> https://myaccount.google.com/apppasswords
```

## Using api provided gem for sending emails
When using Rails, we always want to use ActionMailer and smtp relay. API gems are useful for sending emails when we do not have something like ActionMailer at our disposal.
