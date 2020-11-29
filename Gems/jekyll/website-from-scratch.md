# Website from Scratch
## Jekyll main features
1. Command line usage
2. Liquid for DRY templates
3. Tags for logic
4. Filters for formatting output
5. Front-matter

## Basic flow
In our project's root directory, we have to create a Gemfile and add jekyll to it. It's best to require github pages gem that will also load jekyll with it. This way we won't have any problem while hosting on Github

```ruby
# Gemfile
gem 'github-pages', '~> 207'
```

- Create any page that ends with .html or .md for serving over the server.
- Markdown is auto converted into HTML.
- All jekyll configuration folders start with underscore (_layouts) so that they are not part of the generated website.

Comman shell commands

```shell
jekyll build # generate the website and save it to _site folder in the project
jekyll serve # generates website, launches server and watches root directory for changes for regeneration
```
