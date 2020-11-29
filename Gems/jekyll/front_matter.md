# Front matter
- It is a snippet of YAML that allow us to define variables that will be used across the template. 
- It is important to add at least front matter empty tags if the file needs special processing.

## Mimimal way of defining front matter
```html
---
---
<!-- just two empty bars are enough -->
<body>
  <h1>{{ 'hello world' | downcase }}</h1>
</body>
<!-- index.html -->
```

## Accessing variables
```html
---
title: Hello World
---
<!-- access the variables using the page object -->
<head>
  <title>{{ page.title }}</title>
</head>
```

Front matter gives information to Jekyll about the document.

## Common front matter options
```yaml
permalink: /about/ # create user-friendly permalinks
```
