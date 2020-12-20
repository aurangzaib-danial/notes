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
