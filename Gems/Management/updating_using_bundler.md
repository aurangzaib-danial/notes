# Updating using bundler
It's important to add version limitations to gems as we add them to our application. The reason is Gemfile.lock is only responsible for installing the current versions of gems required for our application. However, if we want to update a gem and then if we are not limiting that gem number then it will update that gem to the latest version that might break the application.

That's why it's important to add version numbers so we can update our gems with confidence.

## Updating a gem for a major version
In the **Gemfile**, change the major version of the gem to the new version. Run `bundle` and then bundler will take care of using the new major version.

## Updating a minor version
Here we need to be careful. Running `bundle update` will update all gems and this might result in unwanted updates. We should first have limitations for the gem set in the Gemfile and then run `bundle update rspec` to update it according to our requirements.
