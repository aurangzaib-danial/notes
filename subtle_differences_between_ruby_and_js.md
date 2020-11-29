# Subtle differences between Ruby and Javascript

## Truthy and falsey values


## String interpolation


## Functions as arguments vs passing blocks

## Return values
Methods in ruby mostly implicitly return values, that is the last line that is executed in the method's body.

However, we must always use the **return** keyword for returning data to the program in JavaScript. JS does not has the concept of implicit returns.

## Server side compiler
Ruby is compiled using 'ruby'. However, JS is compiled using node.
### Package management
In ruby, we can install system wide gems using `gem install rails`.
We use bundler for installing gems specific to projects. All installed gems are available across the system.

In node, we have npm or yarn, that can install system wide modules and also install modules specific to current project. By default, npm or yarn install node_modules inside the project itself.

Gems being available across all the projects and node_modules being available specific to each project have their pros and cons. I personally like both approaches and both approaches are appropriate for their respective environement.

## Asynchronous programming
Javascript has a very good support for doing things asynchronously while Ruby does not do well in this field. We have to implement tough workarounds for async in Ruby. Whenever, we want to do something async, we look up to JavaScript.

## require libraries
In ruby, whenever we require a gem, a constant based on that gem name is added to our environment.

```ruby
require 'pry'
Pry.start
```

However, above is not true for Javascript. Whenever we load a file inside another file in Javascript, nothing of the new file will be made available to the requiring file, this is for function override protection. The new file must explicity define what it wants to share.

The reason behind Javascript not allowing anything through is because of the nature of how JS is used by different people. JS is used in all styles i.e. procedural, functional and object oriented. Not all people are going to use class constants. 








