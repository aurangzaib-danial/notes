
## Links

We can link a text to a URL in two ways.
For link the text to a URL either inline-link or through references

### In-line links

Link is created between text and URL in-line.

```md
  [Search on Google](https://www.google.com)
```

- Square brackets enclose the text that needs to be linked.
- Round brackets enclose the URL

### Reference links

We can create references a link inside our markdown document.
This way we can reference the link anywhere in our document and if the link changes then we just have to update the link and do not have to change anything in the document.

 - Allow same link to be used at multiple places.
 - Later change the main link that reflects everywhere
 - We define references on the bottom of the file
 - References definition do not appear on the file

```md
  [search something on google][google is great]
  [This is also linked to google][google is great]

  [google is great]: https://www.google.com
```

**Use square brackets for writing the reference for the text instead of square brackets**

## Images

Syntax same as links but a bang on the front marks it an image

```md
  ![alternative text](image_link)
```

Also, we can use references for images link just like link references

