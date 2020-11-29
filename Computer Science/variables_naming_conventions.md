# Variables naming conventions
1. camelCase
2. PascalCase
3. snake_case
4. kebab-case

## camelCase
```
authorName
```

## PascalCase
```ruby
PostsController
```

## snake_case
```
author_name
```
It is also common to name file names using snake_case. For example, `posts_controller.rb`

## kebab-case
This is not an accepted variable naming technique in programming languages. However, it is really useful for repository names.
```
rails new kebab-app
```

## Conventions in Ruby
- For mere variables and method names, we use snake_case
- For data constants we keep the whole word constant

```ruby
STUDENTS = %w[Sunny Ali Junaid]
```
- For constants like classes and modules, we use PascalCase.

```ruby
module BlogApp
end
```

## Conventions in JavaScript
- For variables and function names, we use camelCase
- For filenames we use kebab-case. For example, `posts-controller.js`
- For test files, we name them as `tests/index.test.js`
