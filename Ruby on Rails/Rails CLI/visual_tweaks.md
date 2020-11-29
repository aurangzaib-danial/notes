
# Visual Tweaks for command line

## List routes in command line in a readble manner (Rails 6)
```console
rails routes --expanded
```

## Display ActiveRecord collection of objects in a tabular form in console
In a Rails app Gemfile add

```ruby
gem 'hirb'
```
Run following code inside the rails console to enable formatting

```console
irb> Hirb.enable
```
