# Updating using bundler
It's important to add version limitations to gems as we add them to our application. The reason is Gemfile.lock is only responsible for installing the current versions of gems required for our application. However, if we want to update a gem and then if we are not limiting that gem number then it will update that gem to the latest version that might break the application.

That's why it's important to add version numbers so we can update our gems with confidence.
