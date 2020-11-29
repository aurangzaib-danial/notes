# How assets work?
Things that fall into the category of assets are

1. Stylesheets
2. Javascripts
3. Images

**Assets are for front-end only and have no effect on the backend**

Rails asset managment is intelligent. It concatenates stylesheets into one file and serves only that file. Also, signs the file with a key which is changed when a stylesheet is updated on disk. This makes our development life easy so we do not have to delete the cached styles on the browser for viewing the changes. 

**Above is all true for JavaScript as well.**

## Advent of Rails 6
Until Rails 6, all of the assets have been managed by **sprockets** gem but now sprockets have been made a part of Rails and now only manages the stylesheets management with **sass-rails** gem.

## Webpacker gem
Webpack is kind of like sprockets but more advanced. It manages concatenation and requiring of Javascript packages called **node_modules**.

### Why rails have switched to webpacker from sprockets?
We have been shipping Javascript packages as ruby gems for requiring in our application. But why make Ruby manage the JavaScript dependencies? Let webpacker take care of Javascript. Also, in the present era, all of the front-end packages are being shipped as **node_modules**. Shipping a ruby gem for a Javascript dependency is not the first priorty of a programmer.

> All of the above discussion proves that we need to delegate Javascript dependencies to a Javascript based bundler which is 'webpack' (webpacker as ruby gem)

Webpacker can also pack stylesheets and images and its a good thing because a lot of CSS frameworks are first built into node_modules so we can quickly and easily include them in our project.

> One thing is clear, webpack is for front-end only!
