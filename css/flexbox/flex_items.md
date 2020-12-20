# Flex items
- Children of flex container are called flex items.
- To use the flex item properties, we need to place them under a flex container first.

## Auto margin for flex items
Margin property works really good on flex items.

```css
.item-1 {
  margin-right: auto;
  /* this will intelligently use up all the space, keep item-1 in the left corner and push all the items to the right. We can specify auto margin on any item */
}
```

## Ordering
- We change the order of flex items regardless of their order in HTML code. For example, item-1 can come 
- Every flex-item has a order of zero by default.

```css
.item-1 {
  order: 1; 
  /* 
  Every other item has 0 and item-1 has highest so it comes at last.
  We can even use negative values to bring items on front
  */
}
```

## flex-grow
This property allows us to change the size of flex-items. For example, by default flex-items do not take up the whole line of the container but only grow as much as the content. However, we can change that and make use the entire width of the container.

```css
.item {
  flex-grow: 1; 
  /* 
  The value '1', tells the items to take up the entire space of the container. 
  It equally divides width of the container between all of its items. 
  */
}

.item-3 {
  flex-grow: 2;
  /*
  This will make item-2 get two times the size of other items.
  This is useful when we have a two-column layout, one column for main-content and other for aside column.
  */
}
```

## flex-basis
### Problem
The value of `flex-grow: 1` sets the width of the items according to their content. If the content is more then the width of item will be more as well. It does not distribute the width of the container evenly between the items if the content size of the items is different.
### Solution
Flex basis allows us to set equal width for all items. When the space in the container runs out then the items automatically move to next line if `flex-wrap: wrap` is used.

```css
.item {
  flex-basis: 200px;
}
```

## flex-shrink
This is a less commonly used feature of flexbox. It is the opposite of flexbox-grow and allows us to shrink the size of the items.

## Shorthand for flex grow, basis and shrink
```css
.item {
  /* flex: grow, basis, shrink; basis and shrink are optional */
  
  flex: 1; 
  /* 
  this one will set basis as zero, items will have equal width and they will not wrap
  use flex-grow: 1; if you do not want to set flex-basis
  */ 
}
```







