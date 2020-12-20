# Getting Started
The most basic thing to get started with flexbox is to set a flex container.

```css
.container {
  display: flex; 
}
```
The `.container` is now a flex container and all of its elements are now flex items.

## Flex direction
The default direction of flex items is along the **main axis** as a row. We can easily change the direction of flex items.

```css
.container {
  flex-direction: row; /* default */
  flex-direction: column;
  /* 
  This one switches the main axis as vertical and cross axis as horizontal. 
  Now, the flex items will be wide as much as the container.
  */
}
```
