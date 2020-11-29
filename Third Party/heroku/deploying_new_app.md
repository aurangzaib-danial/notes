# Deploying new app
All I have to do is push my app's local master branch to my heroku app's master branch. Then heroku will take care of everything

```shell
$ heroku create 'app_name' --region eu # default region is us
$ heroku addons:create heroku-postgresql:hobby-dev
$ heroku config:set RAILS_MASTER_KEY=123 # this is important for rails credentials
$ git push heroku master 
```
**If you have any gem which corresponds to a heroku addon then heroku will automatically add that addon in your server.**

## After app is pushed to the server
```shell
$ heroku run rails db:schema:load #=> only for first time
```

## Configuration from heroku web dashboard
1. Connect github repository with heroku server.
2. Enable automatic deploy but let travis complete first.
