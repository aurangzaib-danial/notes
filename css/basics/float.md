# Float
This property allows us to wrap elements around text by breaking the normal flow of the document.

## Problem with float
Floating an element, makes its parent forget its height. The parent can only remember its height when their is a children which is cleared past the height of the floated element. The **clear** property exists solely for this purpose. This is not a bug because this was how floats were to work.

The float property was widely used for complex layouts before the advent of flexbox and grid.

```css
.clearfix::after {
  content: "";
  display: table;
  clear: both;
}
```
