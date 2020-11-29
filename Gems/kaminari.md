# Kaminari
It is a full solution for pagination in Rails apps. It is scope based and offers easy to use helpers for views.

## Setup
Add kaminari to Gemfile

```console
$ bundle add kaminari
```
Generate a kaminari config file for editing defaults

```console
$ rails g kaminari:config
```
Config file can be used for overrwriting the defaults for kaminari like number of records on a page etc.

## Views
This is the most lovely feature of Kaminari. Views can be generated for themes that you like for example bootstrap, materialize etc.
**If views are not generated then the default Kaminari views are used**

```console
rails g kaminari:views bootstrap4
```

## API Usage
### Models
```ruby
@posts = Post.all
@posts.page(params[:page]) # That's about it
# It's just a scope, we can chain it with any scope method
# If a page number is not present then it uses the first page by default
# We can also chain some other useful kaminari scope methods
@posts.page(params[:page]).out_of_range?
```

### View helpers
```ruby
# paginate, page numbers, next, previous buttons etc.
paginate @posts

# how many enteries and total pages etc.
page_entries_info @posts
```
