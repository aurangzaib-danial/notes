# Layouts
- These live in _layouts.
- Main layout is conventionally named `default.html`.
- Must define in every template which layout to use.

```html
---
layout: default
title: About
---
<!-- about.html -->
```

```html
<!-- _layouts/default.html -->
<head>
</head>
<body>
  {{ content }} <!-- content holds the processed template -->
</body>
<footer>
</footer>
```

# Includes
For reusing chunks of HTML across templates.
- Live in _includes

```html
{% include sidebar.html %}
<!-- html goes -->
```
