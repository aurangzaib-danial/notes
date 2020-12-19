# Media queries
- A media query triggers depending on the given conditions.
- The point at where the query triggers is called a break point.
- Conditions given to media query are called media features.

## Different features for media queries
```css
@media only screen and (min-width: 400px) and (max-width: 1000px) {
}

@media only screen and (min-width: 768px),
       only screen and (min-width: 700px) and (orientation: landscape) {
  /* the comma ',' is separating two media queries and if any of them is true then the CSS code will run. The comma is like the OR of CSS.
  */
} 
```

> Orientation landscape is useful when we want to apply styles to mobiles specifically when they are in landscape mode and may be our middle device (786px) break point will not suffice for the landscape mode width.

