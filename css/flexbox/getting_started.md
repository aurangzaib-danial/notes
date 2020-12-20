# Getting Started
The most basic thing to get started with flexbox is to set a flex container.

```css
.container {
  display: flex; 
}
```
The `.container` is now a flex container and all of its elements are now flex items.

## Direction
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

## Wrap
By default if the size of the container is less than the flex items, the flex items start to overflow the container. This is because by default the flex items are displayed on a single line. We can tell the browser to start wrapping the flex items on multi-lines when the space in the container runs out.

Also, all of the above discussion is true for column direction. When the height of the container runs out then the browser will create multiple columns but will not let flex items to break out of the height of the container.

```css
.container {
  flex-wrap: wrap;
}
```

## justify-content
This property allows us to manage the position of flex items along the main axis. 

```css
.container {
  justify-content: center;
  /* center, flex-start, flex-end, space-around, space-between */
}
```
Space-around and space-between equally distributes space between flex items without us having to calculate right margin or padding values.

## Auto margin for flex items
Margin property works really good on flex items.

```css
.item-1 {
  margin-right: auto;
  /* this will intelligently use up all the space, keep item-1 in the left corner and push all the items to the right. We can specify auto margin on any item */
}
```
