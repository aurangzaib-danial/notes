

# Travis CI
CI stands for Continuous integration
Travis is the the company offering CI.

Continuous integration is a technique in which we depend on another company to test our project latest branch or build.
Overtime, our tests grow and it is really hard to test all of them in our own computer.

We run unit tests as we are developing but hand over full test suite for testing to a service like TravisCI.

When all tests pass in TravisCI server then we deploy our app.

## How to use?
We have to tell travis what languages to use and how to run our tests. If the last command that is evaluated  at the end of the travis flow, finishes without error then travis marks the branch passing. So it's all on us how to tell travis how to test our code.

```shell
$ gem install travis

# inside an app
travis init #=> sets up a .travis.yml file and also starts tracking our github repository for changes in the travis servers

$ gem install travis-lint 
travis lint #=> tests if our .travis.yml syntax is correct
```

```yaml
# Following configration is for a rails 6 app

language: ruby
cache:
  - bundler
  - yarn
services:
  - postgresql
before_install:
  - nvm install --lts
before_script:
  - bundle install --jobs=3 --retry=3
  - yarn
  - bundle exec rails db:create
  - bundle exec rails db:schema:load
script:
 — bundle exec rspecast

```

[medium](https://medium.com/full-taxx/how-to-setup-travis-ci-for-a-rails-application-78a453963300)
[dev.to](https://dev.to/stevepolitodesign/configure-travis-ci-for-ruby-on-rails-195l)
