# Commands

```shell
$ heroku create myapp --region eu
```

We can specify a name of the app if its available.
If no app name is provided, heroku automatically generates an app name for you

If you are in a git directory then git remote of heroku is automatically set for you

**Below commands expect that you are in a git repository that has a remote of a heroku set, otherwise we have to provide a flag of `--app app_name`**

```shell
$ heroku info 
```
returns all information about the app

```shell
$ heroku run bash
$ heroku run rails console
```
Run commands on the server. If the command results in activating a prompt then heroku lets you interact with it from the shell otherwise the command executes and the result is displayed.

```shell
$ heroku config
```
Returns technical info like environment variables about the app

```shell
$ heroku config:set RAILS_MASTER_KEY=123 SECRET=123
```
Set environment variables

```shell
$ heroku 'addon_name'
```
returns info about the addon if its enabled on the app

### postgres
```shell
$ heroku pg #=> returns info about 'pg' addon
$ heroku pg:psql #=> interactive console with our database
```

```shell
$ heroku destroy
```
Delete app and all of its addons like databases, very dangerous.

```shell
$ heroku addons:create heroku-postgresql
```
Provision an addon to your app or your dyno

```shell
$ heroku releases
```
Lists all releases of the app.

