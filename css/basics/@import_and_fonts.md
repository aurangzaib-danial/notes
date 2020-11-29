## @import and fonts
**@import** allows us to link to another css file in a css file. It loads the content of another file.

## Fonts
We can use built-in fonts, custom fonts from disk or import fonts from the internet.

These provide the format  of how the text should look like. CSS reads this file and understands the format defined in the font file.

## Font property as a short hand
```css
body {
  font-size: 1em;
  font-weight: bold;
  line-height: 1.5em;
  font-family: Georgia, "Times new roman", serif;

  font: bold 1em/1.5em Georgia, "Times new roman", serif; /* short hand for font: weight size/line-height font_names */
}
```

> **font-family** We can provide fallback fonts if a specific font is not avaiable in the browser. If a font name has a space in it then we have to put its name inside quotes
