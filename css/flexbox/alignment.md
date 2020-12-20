# Alignment
Flexbox was designed to provide us with perfect horizontal and vertical alignment like centering. All of the below properties work when `display: flex` is set for container.

## justify-content
This property allows us to manage the position of flex items along the main axis. 

```css
.container {
  justify-content: center;
  /* center, flex-start, flex-end, space-around, space-between */
}
```
Space-around and space-between equally distributes space between flex items without us having to calculate right margin or padding values.

## align-items
- This property allows us to align items along the cross-axis.
- By default, it has the value of stretch that means to take up all the height of the container. This is why cross-axis always maintain height of the flex-items.

```css
.container {
  align-items: center; /* aligns items vertically in the center */
}
```

## align-self
- This property is for a item to align itself.

```css
.item {
  align-self: center;
}
```

## Perfectly align an item vertically and horizontally
### First way
```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

### Second way
```css
/* flex item */
.item {
  margin: auto; /* this will set equal width from all sides of the item */
}
```





