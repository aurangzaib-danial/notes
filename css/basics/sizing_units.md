# Sizing units
1. pixels px
2. elastic ems
3. rem
4. fluid (%)

## Pixels
These are fixed, these stay the same always

## ems
These are relative to font-size of the parent container. By default the font-size is 16px.

1 em is equal to 16px
2 em is equal to 2 x 16 = 32px
3 em is equal to 3 x 16 = 96px

> Font-size of the container changes, then the em's also change accordingly.

## rem
These are just like ems but instead of the parent's font-size, it looks at the font-size of root element which is html element.

## fluid
- If we give a child div 50% width then its width will be 50% of the width of the parent div.
- If its a **block element** then it will look at its parent div width.
- If its a **inline element** then it will look at the font-size of the parent div.
- Always relative to the parent element.
