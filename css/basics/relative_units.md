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
- Percentages are always relative to the parent container.
- If it's a **block element** then its width will be relative to its parent. 
- If it's an **inline element** then we can set its font-size fluid that introspects on the font-size of the parent element.
