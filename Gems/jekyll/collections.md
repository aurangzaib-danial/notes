# Collections
## posts
The default collection in jekyll are posts. The `_posts` is automatically organized into static files and available as `site.posts` in the environment.
- all posts are saved in `_posts`.
- every post file must be named in this format `2020-11-22-post-title.md`.
- specify default layout in configuration file.
## options available on a post object
```html
for post in site.posts 
  post.title
  post.excerpt <!-- first paragraph of the post content -->
  post.url
endfor
```

## Custom Collections
We can create a custom collection like `authors`.
- Create the `_authors` folder.
- add following code in the configuration file

```yaml
collections:
  authors:
    output: true # this option will generate seperate view for each author
```

We can access authors using `site.authors`
