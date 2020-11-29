# display
- Every element is a box and it has a display property. 
- Display property by default specification is inline. 
- User agent style-sheet overwrite many elements display property.

## Common values
1. block
2. none
3. inline-block
4. inline

## Defaults for some elements
```css
div, p, h1, section, article nav {
  display: block; /* defautl */
}

a, span {
  /* text level elements */
  display: inline; /* default */
}

/* none and inline-block are not used as default on any element. */
```

## Block
A block level element takes 100% width by default and does not allow other elements side by side.

Can have
- width
- margin on all sides
- padding
- float

### Point to remember
If we have block level elements stacked on top of each other then their margins overlap. Meaning if one has margin of 10px on bottom and the other have margin of 10px on the top then only 10px is displayed by the browser. Their margins overlap and only one is used which is the largest.

## inline element
An inline element can exist with other elements side by side.
- Do not have width because they are text level elements.
- Margin is available only on sides.

## inline-block
- It is a mix of block and inline elements. 
- Can exist side by side and also have width and margin properties. 
- The problem is these blocks do not perfectly align with each other. When we add padding to elements then they do not align side by side.
- We cannot make column structure with these because the inline-block does not stack side by side or does not start as the same height of its sibling block. This is because this also has the characteristics of inline so the content stays inline instead of matching its height with its sibling. 

## Difference between `visibility: hidden;` and `display: none;`
| `visibility: hidden;` | `display: none;` |
| --- |--- |
| Does not remove the element from **DOM** | Same
| Element is not visible but it takes space in the flow of the webpage. Other elements are effected by this element. | Element is not visible and it does not take any space in the flow of webpage and other elements have no effect of this element.






