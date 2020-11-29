# Rails 6 Sprockets
Rails 6 implements webpacker by default for handling asset pipeline. This guides show how to remove webpacker and use good-old sprockets for managing assets. This also adds al the built-in Rails JavaScript functionality.

## Steps
### Step 1
Generate an app without JavaScript

```console
rails new my-app -J
```
### Step 2
Add following gems to Gemfile

```ruby
  gem 'sprockets', '~> 4'
  gem 'sprockets-rails', :require => 'sprockets/railtie'
  gem 'jquery-rails'
  gem 'turbolinks'
```

### Step 3
1. Create **javascripts** folder inside app/assets
2. Create javascripts/application.js.
3. Add following code to it.

```javascript
//= require jquery
//= require rails-ujs
//= require turbolinks
//= require_tree .
```

### Step 4
The file `app/assets/config/manifest.js` should like following 

```js
//= link application.js
//= link_tree ../images
//= link_directory ../stylesheets .css
//= link_directory ../javascripts .js
```

### Step 5
1. Rename `application.css` to `application.css.scss`.
2. Remove everything and import styles in scss way.

```scss
@import "bootstrap";
@import "./*";
```

### Step 6
Edit `application.html.erb` and add sprockets 'stylesheet' and 'javascript' tags.

```erb
<%= stylesheet_link_tag    'application', media: 'all' %>
<%= javascript_include_tag 'application' %>
```

All the assets will now be managed through sprockets!
