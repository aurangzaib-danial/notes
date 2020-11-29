# Data and Iteration
_data folder in jekyll is where we keep content separate from source code. This allow us to easily alter content in our website without have to touch source code. Jekyll supports three types of data files, YAML, JSON and CSV. I personally prefer YAML.

Create a list of navigation links

```yaml
# _data/navigation.html
- name: Home
  link: /
- name: About
  link: /about.html
- name: Team
  link: /team.html
```

This array of navigation links will be automatically made available by jekyll as `site.data.navigation`

## Iterating over the navigation links
```html
{% for item in site.data.navigation %}
  <a href="{{item.link}}">{{item.name}}</a>
{% endfor %}
```
