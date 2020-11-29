# Configuration
This file lives in the root directory named as `_config.yml`. We can specify various application settings and defaults in this file.

## Common defaults
```yaml
collections:
  authors:
    output: true

defaults:
  - scope: # scope of collection
      path: "" # directory of collection
      type: "authors" # name of collection
    values:
      layout: "author" # layout for the collection
  - scope:
      path: ""
      type: "posts"
    values:
      layout: "post"
  - scope: # this scope is for collections that do not have a default layout specified
      path: ""
    values:
      layout: "default"
```
